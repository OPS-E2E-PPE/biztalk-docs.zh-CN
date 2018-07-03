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
ms.openlocfilehash: 85499228eb7bb9622f07be353d8bc0705d25adc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983942"
---
# <a name="configuring-a-receive-port-for-messages-over-as2"></a>配置 AS2 消息的接收端口
若要接收带有 EDI 或非 EDI 负载的 AS2 消息，请创建一个 HTTP 接收端口以接收消息并向参与方返回响应。  

 如果将同步返回 MDN，接收端口必须是双向请求-响应接收端口。 接收端口中的接收位置将接收该 AS2 消息，而与双向接收端口相关联的发送端口将发送同步 MDN。  

 如果将异步返回 MDN，接收端口可以是单向的，因为 MDN 必须通过单独的动态发送端口返回。 无论接收端口是单向还是双向端口，都将返回一个 HTTP 响应。 如果设置一个双向接收端口来接收 AS2 消息，则在返回异步 MDN 时，将通过双向接收位置的发送端口返回 HTTP 响应。  

> [!NOTE]
>  用于接收 AS2 消息的双向接收端口不得用于接收 MDN 消息， 而应使用静态单向接收端口来接收 MDN 消息。 对 MDN 使用请求/响应接收端口将会阻止返回 200OK 消息来响应传入 MDN，从而导致不必要地重试 MDN 传输。  

 使用下列配置创建接收端口：  


|                 位置                 |                “属性”                |                                                                                                                                                                                                                                                                                           设置                                                                                                                                                                                                                                                                                           |
|------------------------------------------|----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   **接收端口属性： 常规**   |               端口类型                |                                                                                                                                                                                                                                                                                      请求-响应                                                                                                                                                                                                                                                                                       |
| **接收位置属性： 常规** |             传输类型             |                                                                                                                                                                                                          HTTP**注意：** 只有 HTTP 适配器可用于传输 EDIINT/AS2 编码的消息。 此传输不能用于除 HTTP 适配器之外的其他适配器。                                                                                                                                                                                                          |
| **接收位置属性： 常规** |            接收处理程序             |                                                                                                                                                                                                                                                                                  BizTalkServerIsolatedHost                                                                                                                                                                                                                                                                                  |
| **接收位置属性： 常规** |            接收管道            | -AS2EdiReceive (如果负载是 EDI 编码)<br />-AS2Receive （如果负载不是 EDI 编码的）**注意：** 使用 AS2EdiReceive 管道时，必须添加到 BizTalk Application Users 组运行 BizTalk 独立主机实例进程的用户帐户。 AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。 AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Users 组。 |
| **接收位置属性： 常规** |             发送管道              |                                                                                                                                                                                                                                                                                           AS2Send                                                                                                                                                                                                                                                                                           |
|      **HTTP 传输属性**       | 虚拟目录和 ISAPI 扩展 |                                                                                                                                                                                                                                                                      /\<虚拟目录名称\>/BTSHTTPReceive.dll                                                                                                                                                                                                                                                                      |
|      **HTTP 传输属性**       |  请求-响应返回内容类型  |                                                                                                                                                                                                                                                                                          text/xml                                                                                                                                                                                                                                                                                           |

## <a name="functionality-of-the-receive-location-in-synchronous-and-asynchronous-modes"></a>同步和异步模式中的接收位置的功能  
 双向接收端口执行以下操作来接收和处理 EDI/AS2 消息并返回一个响应：  

-   通过 HTTP 接收 AS2 消息。  

-   使用 AS2EDIReceive 接收管道（对于 EDI 编码的消息）或 AS2Receive 接收管道（对于非 EDI 编码的消息）处理 AS2 消息。 此过程的详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。  

-   在接收的消息上设置下列上下文属性：  

    -   `IsAS2PayloadMessage == True`（因为它是负载消息）  

    -   `IsEmptyMDNResponse == False`（因为它不是空 MDN）  

-   如果是 EDI 编码的消息，则拆装 EDI 文件、生成 XML 文件并将它们放入 MessageBox。 为每个 XML 文件将 `BTS.MessageType` 的上下文属性设置为带有命名空间的架构名称。  

-   如果不是 EDI 编码的消息，则将消息以其本机格式放入 MessageBox。  

-   使用 AS2EdiReceive 接收管道生成 MDN 文件（如果启用）。 此过程的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。 在消息上设置下列上下文属性：  

    -   `EdiIntAS.IsAS2AsynchronousMdn == False`（如果处于同步模式）  

    -   `EdiIntAS.IsAS2AsynchronousMdn== True`（如果处于异步模式）  

-   如果在同步模式下，则使用 AS2Send 发送管道发送 MDN 文件（如果启用）。 此过程的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。  

-   如果在异步模式下，则将 MDN 文件（如果启用）路由到 MessageBox（以便独立的动态发送端口提取并发送它）。  

-   如果在异步模式下，则除生成异步返回的完整 MDN 之外还生成空的 MDN。 在消息上设置下列上下文属性：  

    -   `IsAS2PayloadMessage == False`  

    -   `IsEmptyMDNResponse == True`  

-   如果在异步模式下，则通过接收端口和发送方之间的 HTTP 连接对原始发送方返回 HTTP 响应，此响应将关闭该连接。 这是必要的，因为完整 MDN 不会关闭同步连接。  

-   生成确认消息（如果启用）并将其放入 MessageBox 中。 将 `BTS.MessageType` 的上下文属性设置为确认控制架构。  

## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)   
 [处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)   
 [生成传出 MDN](../core/generating-an-outgoing-mdn.md)   
 [发送传出 MDN](../core/sending-an-outgoing-mdn.md)