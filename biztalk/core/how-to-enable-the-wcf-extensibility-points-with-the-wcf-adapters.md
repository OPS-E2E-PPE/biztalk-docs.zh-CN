---
title: 启用使用 WCF 适配器的 WCF 扩展点 |Microsoft Docs
description: 安装程序集、 配置 machine.config，将扩展添加到 BizTalk 管理员、 创建接收位置启用 WCF 适配器在 BizTalk Server 中的 WCF 扩展点
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f7b45169a80b0acbb1a51ca410932815c1bd773
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337892"
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a>如何启用 WCF 适配器的 WCF 扩展点
启用三种 WCF 扩展点，行为扩展、 绑定元素扩展和绑定扩展 — 通过 Wcf-custom 和 Wcf-customisolated 适配器。 若要执行此操作，首先安装在全局程序集缓存 (GAC) 中实现 WCF 扩展点的程序集，然后修改你的计算机上的 machine.config 文件然后使用和配置 Wcf-custom 或 Wcf-customisolated 适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
请参阅[Extending WCF](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf)有关 WCF 扩展点的详细信息。
  
 
## <a name="prerequisites"></a>先决条件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 [用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)提供详细信息。  
  
## <a name="install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a>安装在 GAC 中实现 WCF 扩展点的程序集  
  
1. 将复制到的文件夹的 WCF 扩展点实现在本地计算机上的程序集。  
  
2. 将复制的程序集的使用 WCF 扩展点，如果有，到在本地计算机上的文件夹。  
  
3. 启动**Visual Studio 命令提示符**。  
  
4. 键入下列命令：  
  
    **gacutil.exe /if"\<**  *程序集.dll 文件路径*  **\>"**  
  
5. 这会将程序集安装到 GAC，覆盖任何现有的程序集都具有相同的程序集名称。  
  
6. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，针对你在此过程的步骤 1 和 2 中复制的所有程序集重复执行步骤 4 和 5。  
  
7. 如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 至 6 在此过程的所有计算机上。  
  
   > [!NOTE]
   >  若要启用 WCF 适配器的 WCF 扩展点，运行该适配器的 BizTalk 主机实例必须能够在运行时加载程序集实现 WCF 扩展点的位置。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-extension"></a>配置 WCF 绑定扩展在 machine.config 文件  
  
1. 在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。  
  
2. 在记事本中，如果 machine.config 文件不具有 **\<system.serverModel\>\\< 扩展\>** 元素，将这些元素添加 **\<配置\>** 元素在 machine.config 文件，并添加**\<bindingExtensions\>** 内部 WCF 绑定扩展元素 **\<system.serverModel\>\\< 扩展\>** 元素。 例如，若要启用自定义绑定扩展 netHttpBinding，添加以下代码**\<配置\>** machine.config 文件的元素：  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingExtensions>  
         <add name="netHttpBinding" type="Microsoft.Samples.Channels.NetHttpBindingCollectionElement, NetHttpBinding, Version=3.0.0.0, Culture=neutral, PublicKeyToken=5b637b51c4aaa2a8" />  
       </bindingExtensions>        
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   >  - 您可以找到要使用该命令，注册的程序集的信息**gacutil /lr** *< assembly_name >*。  
   >  - 请参阅[bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions)此元素上。
  
3. 在记事本中，保存 machine.config 文件。  
  
4. 如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 到 3 在此过程的所有计算机上。  
  
   > [!NOTE]
   >  您必须对 WCF 基础结构来处理的 BizTalk 主机实例的 WCF 扩展点的所有计算机上重复这些步骤和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台配置 WCF 绑定扩展  
  
1. 打开 **“BizTalk Server 管理”**。  
  
   > [!NOTE]
   >  如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台已经打开，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 如果使用 Wcf-custom 适配器，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开平台设置、 主机实例，，然后重新启动运行适配器的 BizTalk 主机实例。  
  
3. 如果使用 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动应用程序池关联通过 WCF 接收位置。  
  
4. 如果你想要配置接收位置以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**接收位置**，然后在右窗格中双击*\<接收位置\>*。  
  
   -   在中**接收位置属性**对话框中**类型**下拉列表中，选择**WCF 自定义**或者**Wcf-customisolated**根据你想要使用，然后单击的 WCF 适配器**配置**。  
  
5. 如果你想要配置发送端口以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**发送端口**，然后在右窗格中双击*\<发送端口\>*。  
  
   -   在中**发送端口属性**对话框中**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
6. 在传输属性对话框中，在**绑定**选项卡上，选择绑定扩展，然后配置该传输的设置的其余部分。  
  
7. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a>配置 WCF 绑定元素扩展在 machine.config 文件  
  
1. 在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。  
  
2. 在记事本中，如果 machine.config 文件不具有 **\<system.serverModel\>\\< 扩展\>** 元素，将这些元素添加 **\<配置\>** 元素在 machine.config 文件，并添加**\<bindingElementExtensions\>** WCF 绑定元素的元素扩展内部 **\<system.serverModel\>\\< 扩展\>** 元素。 例如，若要启用的自定义绑定元素扩展 Roppinginterceptor，请添加以下代码**\<配置\>** machine.config 文件的元素：  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingElementExtensions>  
         <add name="droppingInterceptor" type="Microsoft.ServiceModel.Samples.DroppingServerElement, MessageInterceptor, Version=0.0.0.0, Culture=neutral, PublicKeyToken=098514eef14aa34a"/>  
       </bindingElementExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   > - 您可以找到要使用该命令，注册的程序集的信息**gacutil /lr** *< assembly_name >*。  
   > - 请参阅[bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions)此元素上。
  
3. 在记事本中，保存 machine.config 文件。  
  
4. 如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 到 3 在此过程的所有计算机上。  
  
   > [!NOTE]
   >  您必须对 WCF 基础结构来处理的 BizTalk 主机实例的 WCF 扩展点的所有计算机上重复这些步骤和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台配置 WCF 绑定元素扩展  
  
1. 打开 **“BizTalk Server 管理”**。  
  
   > [!NOTE]
   >  如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台已经打开，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 如果使用 Wcf-custom 适配器，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开平台设置、 主机实例，，然后重新启动运行适配器的 BizTalk 主机实例。  
  
3. 如果使用 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动应用程序池关联通过 WCF 接收位置。  
  
4. 如果你想要配置接收位置以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**接收位置**，然后在右窗格中双击*\<接收位置\>*。  
  
   -   在中**接收位置属性**对话框中**类型**下拉列表中，选择**WCF 自定义**或者**Wcf-customisolated**根据你想要使用，然后单击的 WCF 适配器**配置**。  
  
5. 如果你想要配置发送端口以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**发送端口**，然后在右窗格中双击*\<发送端口\>*。  
  
   -   在中**发送端口属性**对话框中**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
6. 在传输属性对话框中，在**绑定**选项卡上，在**绑定类型**下拉列表中，选择**customBinding**。  
  
7. 在传输属性对话框中，在**绑定**选项卡上，右键单击的工作区**绑定**列表，，然后单击**将扩展添加**。  
  
8. 在中**选择绑定元素扩展**对话框中，选择绑定元素扩展，然后单击**确定**。  
  
9. 在传输属性对话框中，在**绑定**选项卡上，调整中添加的绑定元素的顺序**绑定**具体取决于您在中添加的绑定元素扩展的类型的列表按如下所示的上一步：  
  
    -   在中**绑定**列表中，右键单击绑定元素扩展，然后单击**移扩展**或**下移扩展**。 在最低的绑定元素扩展**绑定**列表与通道堆栈的底部组件相对应。 中的最高的绑定元素**绑定**列表与通信堆栈的顶部组件相对应。  
  
        > [!NOTE]
        >  请参阅[自定义绑定](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings)有关自定义绑定的绑定元素的特定顺序的详细信息。
  
10. 在传输属性对话框中，将配置该传输的设置的其余部分。  
  
11. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a>配置 WCF 行为扩展在 machine.config 文件  
  
1. 在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。  
  
2. 在记事本中，如果 machine.config 文件不具有 **\<system.serverModel\>\\< 扩展\>** 元素，将这些元素添加 **\<配置\>** 元素在 machine.config 文件，并添加**\<behaviorExtensions\>** WCF 行为扩展元素内部 **\<system.serverModel\>\\< 扩展\>** 元素。 例如，若要启用自定义行为扩展 schemaValidator，添加以下代码**\<配置\>** machine.config 文件的元素：  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <behaviorExtensions>  
         <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ad307e213604f592"/>  
       </behaviorExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   >  - 您可以找到要使用该命令，注册的程序集的信息**gacutil /lr** *< assembly_name >*。  
   >  - 请参阅[behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions)此元素上。
  
3. 在记事本中，保存 machine.config 文件。  
  
4. 如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 到 3 在此过程的所有计算机上。  
  
   > [!NOTE]
   >  您必须对 WCF 基础结构来处理的 BizTalk 主机实例的 WCF 扩展点的所有计算机上重复这些步骤和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台配置 WCF 行为扩展  
  
1. 打开 **“BizTalk Server 管理”**。  
  
   > [!NOTE]
   >  如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台已经打开，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 如果使用 Wcf-custom 适配器，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开平台设置、 主机实例，，然后重新启动运行适配器的 BizTalk 主机实例。  
  
3. 如果使用 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动应用程序池关联通过 WCF 接收位置。  
  
4. 如果你想要配置接收位置以使用 WCF 扩展点，在 BizTalk 管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**接收位置**，然后在右窗格中双击*\<接收位置\>*。  
  
   -   在中**接收位置属性**对话框中**类型**下拉列表中，选择**WCF 自定义**或者**Wcf-customisolated**根据你想要使用，然后单击的 WCF 适配器**配置**。  
  
5. 如果你想要配置发送端口以使用 WCF 扩展点，在 BizTalk 管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**发送端口**，然后在右窗格中，双击*\<发送端口\>*。  
  
   -   在中**发送端口属性**对话框中**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
6. 在传输属性对话框中，在**行为**选项卡上，右键单击**ServiceBehavior**或**EndpointBehavior**根据行为扩展的类型然后，在**选择行为扩展**对话框中，选择行为扩展，然后单击**确定**。  
  
7. 在传输属性对话框中，将配置该传输的设置的其余部分。  
  
8. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。  
  
## <a name="configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a>配置 WCF 自定义接收位置使用 SSL 证书  
  
-   如果 WCF 自定义接收位置正好在使用 HTTP 内核模式驱动程序 (HTTP.sys)，如**httpsTransport**绑定元素，对于安全套接字层 (SSL) 通信，接收位置必须具有证书为每个套接字 （IP 地址/端口组合） 注册。 使用 HttpCfg.exe 工具将 SSL 证书绑定到的计算机上的端口。 有关详细信息，请参阅本主题中的[如何使用 SSL 证书配置端口](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate)。