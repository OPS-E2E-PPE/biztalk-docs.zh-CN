---
title: 服务总线消息传送适配器 |Microsoft Docs
description: 发送和接收消息在 BizTalk Server 中使用 Azure SB 消息适配器
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
ms.openlocfilehash: d050a2f2b4435daa0ea2bff8b7f2a2f19456d624
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309399"
---
# <a name="sb-messaging-adapter"></a>SB 消息适配器
服务总线 (**SB 消息**) 适配器用于接收和发送从服务总线实体，例如队列、 主题和中继。 可以使用**Sb-messaging**适配器来连接本地[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Azure。

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，支持服务总线高级版。 在配置使用此适配器的发送端口，可以将消息发送到分区的队列和主题。 

## <a name="authenticating-with-service-bus"></a>使用服务总线进行身份验证
服务总线提供两种方法进行身份验证： 

- 访问控制服务 (ACS) 
- 共享访问签名 (SAS)

我们建议使用共享访问签名 (SAS) 来使用服务总线进行身份验证。 中列出的共享访问密钥值[Azure 门户](https://portal.azure.com)。

在创建服务总线命名空间时，不自动创建 Access Control (ACS) 命名空间。 若要使用访问控制，需要此命名空间的颁发者名称和颁发者密钥值。 创建新的 ACS 命名空间使用 Windows PowerShell 时，这些值都可用。 在 Azure 门户中未列出这些值。

若要使用 ACS 进行身份验证，并获取颁发者名称和颁发者密钥值，总体步骤包括：

1. 安装[Azure Powershell cmdlet](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)。
2. 添加 Azure 帐户： `Add-AzureAccount`
3. 返回你的订阅名称： `get-azuresubscription`
4. 选择你的订阅： `select-azuresubscription <name of your subscription>` 
5. 创建新的命名空间： `new-azuresbnamespace <name for the service bus> "Location" -CreateACSNamespace $true -NamespaceType Messaging`

    示例：    `new-azuresbnamespace biztalksbnamespace "South Central US" -CreateACSNamespace $true -NamespaceType Messaging`

5. 创建新的 ACS 命名空间时 （这可能需要几分钟时间），在连接字符串中列出了 IssuerName 和 IssuerKey 值： 

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

请参阅[New-azuresbnamespace](https://docs.microsoft.com/powershell/module/Azure/New-AzureSBNamespace)有关的指南。

## <a name="receive-messages-from-service-bus"></a>从服务总线接收消息

1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。 

2. 右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。 

3. 为其提供一个名称，然后选择**接收位置**。 

4. 选择**新建**，为其提供**名称**。 在中**传输**部分中，选择**SB 消息**从**类型**下拉列表，然后选择**配置**。  

5. 配置**常规**属性：  


   |           使用此选项            |                                                                                                                                                                                                                                                                                                                                              执行的操作                                                                                                                                                                                                                                                                                                                                               |
   |-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **队列或订阅 URL** |                                                                                                                                                                                                                                                               指定部署的服务总线队列的 URL。 通常此 URL 的格式如下：<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`                                                                                                                                                                                                                                                               |
   |       **打开超时**        |                                                                                                                                                                                                                                                                                 指定一个时间跨度值，该值指示信道打开操作完成的时间。<br /><br /> **默认值：** 1 分钟                                                                                                                                                                                                                                                                                 |
   |       **关闭超时**       |                                                                                                                                                                                                                                                                                指定一个时间跨度值，该值指示信道关闭操作完成的时间。<br /><br /> **默认值：** 1 分钟                                                                                                                                                                                                                                                                                 |
   |      **接收超时**      |                                                                                                                                                                                                                                                                                  指定一个时间跨度值，该值指示为完成接收操作的时间。<br /><br /> **默认值：** 10 分钟。                                                                                                                                                                                                                                                                                   |
   |      **预提取计数**       | 指定同时接收来自服务总线队列或主题的消息数。 预提取使队列或订阅客户端执行接收操作时从服务加载其他消息。 客户端将这些消息存储在本地缓存中。 缓存的大小由你在此处指定的预提取计数属性值确定。<br /><br /> 有关详细信息，请参阅部分"预提取"时 [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **默认值：** -1 |
   |        **使用会话**        |                                                                                                                                                                                                                                                                                                选中此复选框以使用 Service Bus 会话从队列或订阅接收消息。                                                                                                                                                                                                                                                                                                 |


6. 配置**身份验证**属性：  


   |                                               使用此选项                                                |                                                                                                                                                                                             执行的操作                                                                                                                                                                                             |
   |-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                      **访问控制服务**                                       | 选择此选项可使用 ACS 进行身份验证并提供以下值：<br /><br /> -输入服务总线访问控制服务 STS URI。 通常此 URI 的格式如下：<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -输入服务总线命名空间的颁发者名称。<br /><br /> -输入服务总线命名空间的颁发者密钥。 |
   | **共享访问签名**(新开头[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]) |                                                                                                                                          选择此选项可使用共享访问签名 (SAS) 进行身份验证，并提供 SAS 密钥名称和密钥值。                                                                                                                                          |


7. 在中**属性**选项卡上，在**异步传输消息属性的 Namespace**，输入适配器使用将中转的消息属性为消息上下文属性上的命名空间收到的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果你想要升级的中转的消息属性，请选择**推广异步传输消息属性**复选框。  

8. 选择 **确定**。  

9. 选择你**接收处理程序**，并**接收管道**。 选择**确定**以保存所做的更改。 [创建接收位置](../core/how-to-create-a-receive-location.md)提供一些指导。  

## <a name="send-messages-to-service-bus"></a>将消息发送到服务总线

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。

   [创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。

2. 输入**名称**。 在**传输**，请设置**类型**到**SB 消息**，然后选择**配置**。 

3. 配置**常规**属性：  


   |         使用此选项         |                                                                                                                                                                                                                                             执行的操作                                                                                                                                                                                                                                              |
   |--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **目标 URL**    |                                                                                                                                                               输入部署的服务总线队列的位置的 URL。 通常此 URL 的格式如下：<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`                                                                                                                                                               |
   | **批刷新时间间隔** | 指定一个时间跨度值，该值指示间隔时向队列发送消息批或刷新主题。 默认值为 20 毫秒。<br /><br /> 批处理服务总线队列和主题的详细信息，请参阅**客户端批处理**在部分[ https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements ](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements)。 |
   |     **打开超时**     |                                                                                                                                                                                指定一个时间跨度值，该值指示信道打开操作完成的时间。<br /><br /> **默认值：** 1 分钟                                                                                                                                                                                |
   |     **发送超时**     |                                                                                                                                                                                    指定一个时间跨度值，该值指示为完成发送操作的时间。<br /><br /> **默认值：** 1 分钟                                                                                                                                                                                    |
   |    **关闭超时**     |                                                                                                                                                                               指定一个时间跨度值，该值指示信道关闭操作完成的时间。<br /><br /> **默认值：** 1 分钟                                                                                                                                                                                |


4. 配置**身份验证**属性： 


   |                                               使用此选项                                                |                                                                                                                                                                                             执行的操作                                                                                                                                                                                             |
   |-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                      **访问控制服务**                                       | 选择此选项可使用 ACS 进行身份验证并提供以下值：<br /><br /> -输入服务总线访问控制服务 STS URI。 通常此 URI 的格式如下：<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -输入服务总线命名空间的颁发者名称。<br /><br /> -输入服务总线命名空间的颁发者密钥。 |
   | **共享访问签名**(新开头[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]) |                                                                                                                                          选择此选项可使用共享访问签名 (SAS) 进行身份验证，并提供 SAS 密钥名称和密钥值。                                                                                                                                          |


5. 在中**属性**选项卡上，输入**Namespace 为用户定义的中转消息属性**包含你想要编写的传出消息上的 BizTalk 消息上下文属性服务总线。 所有命名空间属性作为用户定义的中转消息属性写入消息。 在编写为异步传输消息属性的属性时，则适配器将忽略该命名空间。 它使用命名空间只是为了确定要写入哪些属性。  

    此外可以输入 BrokeredMessage 属性的值。 这些属性，请参阅[BrokeredMessage 属性](https://docs.microsoft.com/dotnet/api/microsoft.servicebus.messaging.brokeredmessage)，其中包括**分区键**。

6. 选择**确定**以保存所做的更改。  

## <a name="see-also"></a>另请参阅
[使用适配器](../core/using-adapters.md)