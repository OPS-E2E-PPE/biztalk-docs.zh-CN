---
title: "SB 消息适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c06c4934-45b2-4f6f-9d19-3ebd937c32ae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb2eb8f532d72708dfca199f0eef794afdf77df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sb-messaging-adapter"></a>SB 消息适配器
Service Bus (**SB 消息**) 适配器用于接收和发送从服务总线实体，如队列、 主题和中继。 你可以使用**SB 消息**来桥接之间的连接的适配器[!INCLUDE[winazure](../includes/winazure-md.md)]和本地[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，从而使用户能够创建典型混合应用程序。 此部分中的主题提供有关如何配置的说明**SB 消息**接收位置和发送端口来接收和发送消息从 Service Bus 实体。  

## <a name="before-you-get-started"></a>开始操作之前
服务总线提供了两种方法进行身份验证： 访问控制服务 (ACS) 和共享访问签名 (SAS)。 我们建议是使用服务总线进行身份验证时使用共享访问签名 (SAS)。 中列出的共享访问密钥值[Azure 门户](https://portal.azure.com)。

当你创建了服务总线命名空间时，不自动创建 Access Control (ACS) 命名空间。 若要使用访问控制，你需要此命名空间的颁发者名称和颁发者密钥值。 当你创建新的 ACS 命名空间使用 Windows PowerShell，这些值才可用。 在 Azure 门户中未列出这些值。

若要使用 ACS 进行身份验证，并获取颁发者名称和颁发者密钥值，总体步骤包括：

1. 安装[Azure Powershell cmdlet](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)。
2. 添加你的 Azure 帐户：`Add-AzureAccount`
3. 返回你的订阅名称：`get-azuresubscription`
4. 选择你的订阅：`select-azuresubscription <name of your subscription>` 
5. 创建新的命名空间：`new-azuresbnamespace <name for the service bus> "Location" -CreateACSNamespace $true -NamespaceType Messaging`

    示例：`new-azuresbnamespace biztalksbnamespace "South Central US" -CreateACSNamespace $true -NamespaceType Messaging`
      
5. 创建新的 ACS 命名空间时 （这可能会花费几分钟的时间），连接字符串中列出了 IssuerName 和 IssuerKey 值： 

    ```
    Name                  : biztalksbnamespace
    Region                : South Central US
    DefaultKey            : abcdefghijklmnopqrstuvwxyz
    Status                : Active
    CreatedAt             : 10/18/2016 9:36:30 PM
    AcsManagementEndpoint : https://biztalksbnamespace-sb.accesscontrol.windows.net/
    ServiceBusEndpoint    : https://biztalksbnamespace.servicebus.windows.net/
    ConnectionString      : Endpoint=sb://biztalksbnamespace.servicebus.windows.net/;SharedSecretIssuer=owner;SharedSecretValue=abcdefghijklmnopqrstuvwxyz
    NamespaceType         : Messaging
    ```
[新 AzureSBNamespace](https://msdn.microsoft.com/library/dn495165.aspx)

## <a name="receive-messages-from-service-bus"></a>从 Service Bus 接收消息
  
本部分提供有关如何配置信息**SB 消息**接收位置使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  之前完成以下过程，你必须已添加单向接收端口。 请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  

 
1.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，然后展开应用程序在你想要创建接收位置。  
  
2.  在左窗格中，单击“接收端口”  节点，在右窗格中，右键单击你希望将新的接收位置与其关联的接收端口，然后单击“属性” 。  
  
3.  在“接收端口属性”  对话框的左窗格中，选择“接收位置” ，然后在右窗格中单击“新建”  以创建新的接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**部分中，选择**SB 消息**从**类型**下拉列表然后单击**配置**若要配置接收位置的传输属性。  
  
5.  在**SB 消息传输属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**队列或订阅的 URL**|指定在其中部署 Service Bus 队列的 URL。 通常此 URL 的格式如下：<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**打开超时**|指定一个时间跨度值来表示完成信道打开操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**关闭超时**|指定一个时间跨度值来表示完成信道关闭操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**接收超时**|指定一个时间跨度值来表示完成接收操作的时间。<br /><br /> **默认值：** 10 分钟|  
    |**预提取计数**|指定同时从 Service Bus 队列或主题收到的消息数。 通过预获取，队列或订阅客户端可以在执行接收操作时从服务加载其他消息。 客户端将这些消息存储在本地缓存中。 缓存的大小由你在此处指定的“Prefetch 计数”属性的值决定。<br /><br /> 有关详细信息，请参阅部分"预提取"在[https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **默认值：** -1|  
    |**使用会话**|选择此复选框可使用 Service Bus 会话从队列或订阅接收消息。|  
  
6.  在**身份验证**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**访问控制服务**|选择此项可使用 ACS 进行身份验证并提供以下值：<br /><br /> -输入的服务总线访问控制服务 STS URI。 通常此 URI 的格式如下：<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -输入 Service Bus 命名空间的颁发者名称。<br /><br /> -输入 Service Bus 命名空间的颁发者密钥。|  
    |**共享访问签名**(新开头[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|选择此项可使用共享访问签名 (SAS) 进行身份验证，并提供 SAS 密钥名和密钥值。|  
  
7.  在**属性**选项卡上，在**中转消息属性的 Namespace**字段中，指定适配器使用编写中转的消息属性作为消息上下文属性上的命名空间接收的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此外，如果你想要升级的中转的消息属性，则选择**提升中转消息属性**复选框。  
  
8.  单击 **“确定”**。  
  
9. 在“接收位置属性”  对话框中输入相应的值，完成对接收位置的配置，然后单击“确定”  保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="send-messages-to-service-bus"></a>将消息发送到 Service Bus
本部分提供有关如何配置信息**SB 消息**发送端口使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击现有的发送端口来对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**SB 消息**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分中，单击**配置**按钮。  
  
3.  在**SB 消息传输属性**对话框中，在**常规**选项卡上，指定下列各项：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标 URL**|输入其中部署 Service Bus 队列的 URL。 通常此 URL 的格式如下：<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**批处理刷新间隔**|指定一个时间跨度值来表示向队列发送消息批或刷新主题的时间间隔。 默认值为 20 毫秒。<br /><br /> 有关 Service Bus 队列和主题方面对批处理的详细信息，请参阅**客户端批处理**部分[https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements)。|  
    |**打开超时**|指定一个时间跨度值来表示完成信道打开操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**发送超时时**|指定一个时间跨度值来表示完成发送操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**关闭超时**|指定一个时间跨度值来表示完成信道关闭操作的时间。<br /><br /> **默认值：** 1 分钟|  
  
4.  在**身份验证**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**访问控制服务**|选择此项可使用 ACS 进行身份验证并提供以下值：<br /><br /> -输入的服务总线访问控制服务 STS URI。 通常此 URI 的格式如下：<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -输入 Service Bus 命名空间的颁发者名称。<br /><br /> -输入 Service Bus 命名空间的颁发者密钥。|  
    |**共享访问签名**(新开头[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|选择此项可使用共享访问签名 (SAS) 进行身份验证，并提供 SAS 密钥名和密钥值。|  
  
5.  在**属性**选项卡上，在**Namespace 用户定义的中转消息属性**字段中，指定包含你想要编写作为 BizTalk 消息上下文属性的命名空间用户定义的中转消息属性的传出消息发送到 Service Bus 队列。 所有属于该命名空间的属性将作为用户定义的异步传输消息属性写入到消息中。 当写入作为异步传输消息属性的属性时，适配器将忽略该命名空间。 它仅将该命名空间用于确定要写入哪些属性。  
  
     你还可以指定 BrokeredMessage 属性的值。 有关属性的详细信息，请参阅[BrokeredMessage 属性](https://msdn.microsoft.com/library/azure/microsoft.servicebus.messaging.brokeredmessage_properties.aspx)。  
  
6.  单击**确定**和**确定**再次以保存设置。  
  
## <a name="see-also"></a>另请参阅
[使用适配器](../core/using-adapters.md)