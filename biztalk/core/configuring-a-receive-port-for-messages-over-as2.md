---
title: 配置 AS2 消息接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01d4d897-d12b-4de4-a86b-e6d2718470c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e4e0989c93bb107f0530c6719484ace4ca9dad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356371"
---
# <a name="configuring-a-receive-port-for-messages-over-as2"></a>配置 AS2 消息接收端口
若要接收带有 EDI 或非 EDI 负载的 AS2 消息，创建一个 HTTP 接收端口以接收消息并返回响应返回给参与方。  

 如果将同步返回 MDN，接收端口必须是双向请求-响应接收端口。 中的接收端口的接收位置将接收 AS2 消息，而与双向接收端口相关联的发送端口会将发送同步 MDN。  

 如果将以异步方式返回 MDN，接收端口可以是单向接收端口，因为返回 MDN，必须通过单独的动态发送端口。 接收端口中，将返回 HTTP 响应是否为单向或双向端口。 如果设置了一个双向接收端口接收的 AS2 消息时返回异步 MDN，返回 HTTP 响应将通过双向发送端口接收位置。  

> [!NOTE]
>  双向接收端口用于接收的 AS2 消息不应该用于接收 MDN 消息。 应接收 MDN 消息使用静态单向接收端口。 使用请求/响应接收端口将 MDN 将阻止 200OK 消息来响应传入 MDN，从而导致不必要的 MDN 传输返回。  

 使用以下配置创建接收端口：  


|                 Location                 |                属性                |                                                                                                                                                                                                                                                                                           设置                                                                                                                                                                                                                                                                                           |
|------------------------------------------|----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   **接收端口属性：常规**   |               端口类型                |                                                                                                                                                                                                                                                                                      请求-响应                                                                                                                                                                                                                                                                                       |
| **接收位置属性：常规** |             传输类型             |                                                                                                                                                                                                          HTTP**注意：** 只有 HTTP 适配器可用于传输 EDIINT/AS2 编码的消息。 此传输不会使用非 HTTP 适配器的适配器。                                                                                                                                                                                                          |
| **接收位置属性：常规** |            接收处理程序             |                                                                                                                                                                                                                                                                                  BizTalkServerIsolatedHost                                                                                                                                                                                                                                                                                  |
| **接收位置属性：常规** |            接收管道            | -AS2EdiReceive (如果负载是 EDI 编码)<br />-AS2Receive （如果负载不是 EDI 编码的）**注意：** 使用 AS2EdiReceive 管道时，必须添加到 BizTalk Application Users 组运行 BizTalk 独立主机实例进程的用户帐户。 AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。 AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Application Users 组。 |
| **接收位置属性：常规** |             发送管道              |                                                                                                                                                                                                                                                                                           AS2Send                                                                                                                                                                                                                                                                                           |
|      **HTTP 传输属性**       | 虚拟目录和 ISAPI 扩展 |                                                                                                                                                                                                                                                                      /\<虚拟目录名称\>/BTSHTTPReceive.dll                                                                                                                                                                                                                                                                      |
|      **HTTP 传输属性**       |  请求-响应返回内容类型  |                                                                                                                                                                                                                                                                                          text/xml                                                                                                                                                                                                                                                                                           |

## <a name="functionality-of-the-receive-location-in-synchronous-and-asynchronous-modes"></a>功能的同步和异步模式在接收位置  
 双向接收端口执行以下操作来接收和处理 EDI/AS2 消息并返回响应：  

-   通过 HTTP 接收 AS2 消息。  

-   处理 AS2 消息使用 AS2EDIReceive 接收管道 （对于 EDI 编码的消息） 或 AS2Receive 接收管道 （适用于未以 EDI 编码的消息）。 此过程的详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  

-   收到的消息上设置下列上下文属性：  

    -   `IsAS2PayloadMessage == True` （因为它是负载消息）  

    -   `IsEmptyMDNResponse == False` （因为它不是空 MDN）  

-   EDI 编码消息时，拆装 EDI 文件，生成的 XML 文件，并放入 MessageBox。 设置的上下文属性`BTS.MessageType`带有命名空间的架构名称对每个 XML 文件。  

-   如果消息不是 EDI 编码，该消息放入其本机格式到 MessageBox 中。  

-   生成 MDN 文件中，如果启用，使用 AS2EdiReceive 接收管道。 此过程的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。 消息上设置下列上下文属性：  

    -   `EdiIntAS.IsAS2AsynchronousMdn == False` （如果处于同步模式）  

    -   `EdiIntAS.IsAS2AsynchronousMdn== True` （如果处于异步模式）  

-   如果在同步模式下，如果启用，使用 AS2Send 发送管道发送 MDN 文件。 此过程的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  

-   如果在异步模式下，路由该 MDN 文件，如果启用，到 MessageBox （以便选择它并将其发送一个单独的动态发送端口）。  

-   如果在异步模式下，生成它以异步方式返回在完整 MDN 之外还是空 MDN。 消息上设置下列上下文属性：  

    -   `IsAS2PayloadMessage == False`  

    -   `IsEmptyMDNResponse == True`  

-   如果在异步模式下，接收端口和发送方，这会关闭该连接返回通过 HTTP 连接对原始发件人的 HTTP 响应。 这是必需的因为完整 MDN 不会关闭同步连接。  

-   生成确认消息，如果启用，将其放入 MessageBox。 设置的上下文属性`BTS.MessageType`为确认控制架构。  

## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)   
 [处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)   
 [生成传出 MDN](../core/generating-an-outgoing-mdn.md)   
 [发送传出 MDN](../core/sending-an-outgoing-mdn.md)