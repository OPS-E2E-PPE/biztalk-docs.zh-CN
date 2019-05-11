---
title: 配置物理端口绑定使用的端口绑定文件到 Siebel |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring by using a port binding file
ms.assetid: 1758e89c-d56c-4e67-919b-c0bbb22878bf
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10eb723c671a94fd95c7ed21a14c93fad3f907c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371947"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-siebel"></a>配置使用到 Siebel 的端口绑定文件的物理端口绑定
当你使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要为 Siebel 项目，以外的架构文件，生成元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会生成端口绑定文件。 您可以将此绑定文件导入 BizTalk 应用程序创建的物理发送端口。 请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。 如果此绑定文件导入，您无需手动创建一个物理发送端口。  
  
> [!IMPORTANT]
>  同时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不能在绑定文件中。 您必须手动添加的绑定属性和其值在绑定文件中，如果所需。  
  
 创建始终使用端口绑定文件的端口创建一个双向发送端口。 如果你想要创建单向端口，您可以创建它手动遵循的步骤[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。 或者，可以按照本主题，以修改要创建单向端口的端口绑定文件中所述的解决方法。  
  
> [!IMPORTANT]
>  使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]不会创建使用可创建 WCF Siebel 端口的端口绑定文件。 但是，无法对生成的端口绑定文件进行一些更改[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并用它来创建 WCF Siebel 端口。 有关详细信息，请参阅配置端口绑定文件生成使用使用适配器服务外接程序使用 WCF 的 Siebel 端口。  
  
 以下是一些您必须了解与生成的绑定文件相关的关键点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   创建文件时特定的命名约定。 如果生成是将消息发送到 Siebel 系统，为出站操作元数据文件的名称是 WcfSendPort_SiebelBinding_Custom.bindinginfo.xml。  
  
-   该文件包含有关绑定配置、 绑定类型、 终结点 URI，和基于为其生成元数据的操作的端口操作的信息。 导入该绑定文件来创建端口时，将自动在端口上设置配置物理端口所需的所有相关信息。  
  
    > [!IMPORTANT]
    >  默认情况下，发送端口上的操作映射到为其生成元数据的操作名称。 例如，如果您生成帐户业务组件上的插入操作的元数据，则在端口上的操作设置为`<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />`。 但是，在 BizTalk 业务流程中创建的逻辑发送端口上的操作名称可能不能相同。 您必须确保 （在 BizTalk 业务流程） 的逻辑端口 （在 BizTalk Server 管理控制台） 的物理发送端口中的操作名称都相同。 否则，会将消息发送到发送端口通过 Siebel 系统时收到错误。  
  
-   只需提供要连接到 Siebel 系统的端口的凭据。 虽然该绑定文件确实保留与要连接的用户名，出于安全原因该绑定文件不包含密码。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>使用端口绑定文件的重要注意事项  
  
-   导入绑定文件时，可能会收到通知绑定文件中的 BizTalk 应用程序名称与要向其导入绑定文件的应用程序名称不匹配对话框消息。 可以安全地忽略此消息并继续。  
  
-   绑定文件还包含端口的名称和接收位置。 如果要向其导入绑定文件的 BizTalk 应用程序创建一个端口或与同一个 BizTalk 应用程序中的现有端口具有相同名称的接收位置，将会出错。 您必须手动编辑绑定文件指定唯一名称的端口或接收位置。  
  
-   默认情况下，端口绑定文件始终包含定义为双向发送端口。 导入 BizTalk 应用程序中的此文件时，它会创建一个双向发送端口。 但是，您可能有一个单向发送端口业务流程。 因此，当您配置此类业务流程，并使用通过导入绑定文件创建的端口，端口不可用在列表中。 发生这种情况是因为业务流程的一部分创建的逻辑端口是单向端口，而在业务流程中创建的物理端口为双向端口。 在这种情况下，可以编辑绑定文件以进行以下更改：  
  
    |为此|操作|  
    |--------------|-------------|  
    |若要编辑该端口的绑定文件，以配置一个单向发送端口|-在以下摘录中，更改的值**IsTwoWay**属性设置为**false**。 最初，此值设置为 **，则返回 true**。<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -注释掉下面的摘录：<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-siebel-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>配置使用生成使用的端口绑定文件的 WCF Siebel 端口使用适配器服务外接程序  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建一个端口绑定文件，您可以在导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 可以使用相同的端口绑定文件，也创建中的 BizTalk WCF 的 Siebel 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 但是，在创建 WCF Siebel 端口之前必须执行以下任务来修改端口绑定文件。  
  
1. 在文本编辑器中打开端口绑定文件。  
  
2. 搜索和替换"WCF 自定义"中的将 Wcf-siebel 适配器添加与其同名[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 例如，如果你添加为"SiebelAdapter"Wcf-siebel 适配器，将为"Wcf-custom"与"SiebelAdapter"。  
  
3. "ConfigurationClsid"属性中，搜索并替换"7971A78D-AE8F-42B4-834D-3A957FD945E9"现有属性的值。  
  
4. 保存并关闭绑定文件。  
  
5. 导入绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。 
  
## <a name="see-also"></a>请参阅  
[生成块以创建与 Siebel 的 BizTalk 应用程序 

adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)