---
title: 服务总线消息传送适配器 |Microsoft 文档
description: 发送和接收消息 BizTalk Server 中使用的 Azure SB 消息传送的适配器
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c06c4934-45b2-4f6f-9d19-3ebd937c32ae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1775606a911d8ce23fd2999ad367053c4f8f72de
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497870"
---
# <a name="sb-messaging-adapter"></a>SB 消息适配器
Service Bus (**SB 消息**) 适配器用于接收和发送从服务总线实体，如队列、 主题和中继。 你可以使用**SB 消息**适配器以连接本地[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Azure。

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，支持服务总线高级版。 当配置使用此适配器发送端口，可以将消息发送到分区的队列和主题。 

## <a name="authenticating-with-service-bus"></a>使用服务总线进行身份验证
服务总线提供了两种方法进行身份验证： 

- 访问控制服务 (ACS) 
- 共享访问签名 (SAS)

我们建议使用共享访问签名 (SAS) 使用 Service Bus 进行身份验证。 中列出的共享访问密钥值[Azure 门户](https://portal.azure.com)。

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

请参阅[New-azuresbnamespace](https://docs.microsoft.com/powershell/module/Azure/New-AzureSBNamespace)的指南。

## <a name="receive-messages-from-service-bus"></a>从 Service Bus 接收消息
  
1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。 

2. 右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。 

3. 为其提供一个名称，并选择**接收位置**。 

4. 选择**新建**，为其提供**名称**。 在**传输**部分中，选择**SB 消息**从**类型**下拉列表，然后选择**配置**。  
  
5. 配置**常规**属性：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**队列或订阅的 URL**|指定在其中部署 Service Bus 队列的 URL。 通常此 URL 的格式如下：<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**打开超时**|指定一个时间跨度值来表示完成信道打开操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**关闭超时**|指定一个时间跨度值来表示完成信道关闭操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**接收超时**|指定一个时间跨度值来表示完成接收操作的时间。<br /><br /> **默认值：** 10 分钟|  
    |**预提取计数**|指定同时从 Service Bus 队列或主题收到的消息数。 通过预获取，队列或订阅客户端可以在执行接收操作时从服务加载其他消息。 客户端将这些消息存储在本地缓存中。 缓存的大小由你在此处指定的“Prefetch 计数”属性的值决定。<br /><br /> 有关详细信息，请参阅部分"预提取"在[https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **默认值：** -1|  
    |**使用会话**|选择此复选框可使用 Service Bus 会话从队列或订阅接收消息。|  
  
6.  配置**身份验证**属性：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**访问控制服务**|选择此项可使用 ACS 进行身份验证并提供以下值：<br /><br /> -输入的服务总线访问控制服务 STS URI。 通常此 URI 的格式如下：<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -输入 Service Bus 命名空间的颁发者名称。<br /><br /> -输入 Service Bus 命名空间的颁发者密钥。|  
    |**共享访问签名**(新开头[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|选择此项可使用共享访问签名 (SAS) 进行身份验证，并提供 SAS 密钥名和密钥值。|  
  
7.  在**属性**选项卡上，在**中转消息属性的 Namespace**，输入适配器用于编写中转的消息属性作为消息上下文属性上的命名空间已接收消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果你想要升级的中转的消息属性，选择**提升中转消息属性**复选框。  
  
8.  选择“确定”。  
  
9. 选择你**接收处理程序**，和**接收管道**。 单击“确定”保存更改。 [创建一个接收位置](../core/how-to-create-a-receive-location.md)提供了一些指导。  
  
## <a name="send-messages-to-service-bus"></a>将消息发送到 Service Bus
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。

    [创建发送端口](../core/how-to-create-a-send-port2.md)提供了一些指导。

2. 输入**名称**。 在**传输**，将其设置**类型**到**SB 消息**，然后选择**配置**。 
  
3.  配置**常规**属性：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标 URL**|输入其中部署 Service Bus 队列的 URL。 通常此 URL 的格式如下：<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**批处理刷新间隔**|指定一个时间跨度值来表示向队列发送消息批或刷新主题的时间间隔。 默认值为 20 毫秒。<br /><br /> 有关 Service Bus 队列和主题方面对批处理的详细信息，请参阅**客户端批处理**部分[https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements)。|  
    |**打开超时**|指定一个时间跨度值来表示完成信道打开操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**发送超时时**|指定一个时间跨度值来表示完成发送操作的时间。<br /><br /> **默认值：** 1 分钟|  
    |**关闭超时**|指定一个时间跨度值来表示完成信道关闭操作的时间。<br /><br /> **默认值：** 1 分钟|  
  
4.  配置**身份验证**属性： 
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**访问控制服务**|选择此项可使用 ACS 进行身份验证并提供以下值：<br /><br /> -输入的服务总线访问控制服务 STS URI。 通常此 URI 的格式如下：<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -输入 Service Bus 命名空间的颁发者名称。<br /><br /> -输入 Service Bus 命名空间的颁发者密钥。|  
    |**共享访问签名**(新开头[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|选择此项可使用共享访问签名 (SAS) 进行身份验证，并提供 SAS 密钥名和密钥值。|  
  
5.  在**属性**选项卡上，输入**Namespace 用户定义的中转消息属性**包含你想要编写的传出消息上的 BizTalk 消息上下文属性Service Bus。 所有命名空间属性中，将写入因为用户定义的中转消息属性的消息。 当写入作为异步传输消息属性的属性时，适配器将忽略该命名空间。 它仅将该命名空间用于确定要写入哪些属性。  
  
     你还可以为 BrokeredMessage 属性输入值。 在将详细介绍这些属性[BrokeredMessage 属性](https://docs.microsoft.com/dotnet/api/microsoft.servicebus.messaging.brokeredmessage)，包括**分区键**。
  
6.  单击“确定”保存更改。  
  
## <a name="see-also"></a>另请参阅
[使用适配器](../core/using-adapters.md)