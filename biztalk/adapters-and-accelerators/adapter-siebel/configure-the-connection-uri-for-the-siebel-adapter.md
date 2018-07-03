---
title: 配置 Siebel 适配器的连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying
ms.assetid: b89b60e9-0f3b-4305-865e-9d3b40d04648
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070925b09cf4e4896097be1aa88bc57fcd625626
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992390"
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a>配置 Siebel 适配器的连接 URI
一个连接 URI 是一个连接字符串以连接到 Siebel 系统。 连接 URI 包含建立与 Siebel 系统的连接所需的各种参数。 必须指定此连接在设计时和运行的时的 URI。 在设计时，必须指定要连接到 Siebel 系统生成的元数据的 URI。 在运行时，必须指定要连接到 Siebel 系统以执行操作的 URI。  

## <a name="enter-the-connection-uri-at-design-time"></a>输入连接 URI 在设计时  
 对于设计时，你必须指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a>输入连接 URI 使用使用适配器服务外接程序  

1. 右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |             执行的操作             |
   |----------------|------------------------------------|
   | **类别** | 单击**使用适配器服务**。 |
   | **模板**  | 单击**使用适配器服务**。 |


3. 若要启动**使用适配器服务**对话框中，单击**添加**。  

4. 在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.  

5. 在中**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Siebel 系统。  

6. 在中**配置适配器**对话框中，单击**URI 属性**选项卡上，并指定不同的参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  

7. 在中**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  

8. 单击“确定” 。  

#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a>输入连接 URI 使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在添加适配器向导中，选择**Wcf-siebel**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF Siebel 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**.  

7. 在中**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Siebel 系统。  

8. 在中**配置适配器**对话框中，单击**URI 属性**选项卡上，并指定不同的参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  

9. 在中**配置适配器**对话框中，单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  

    > [!NOTE]
    >  如果选择现有的 WCF Siebel 发送端口，则不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

10. 单击“确定” 。  

## <a name="enter-the-connection-uri-at-run-time"></a>输入连接 URI 在运行时  
 对于运行时中，你必须指定 URI 中的 WCF 自定义或 Wcf-siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的连接 URI  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

4. 在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。  

5. 在中**地址 (URI)** 文本框中，指定连接到 Siebel 系统连接 URI。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  

6. 在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**siebelBinding**。  

7. 若要创建的发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   1.  选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。  

   2.  选择**使用单一登录**选项，并指定关联 ESSO 应用程序。  

8. 单击“确定” 。  

#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a>输入 WCF Siebel 端口的连接 URI  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加到 WCF 的 Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 Wcf-siebel 适配器，然后单击**配置**。  

5. 在传输属性对话框中，单击**常规**选项卡。  

6. 单击**配置**按钮，并提供连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  

7. 在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  

8. 若要创建的发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   1.  选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。  

   2.  选择**使用单一登录**选项，并指定关联 ESSO 应用程序。  

9. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)