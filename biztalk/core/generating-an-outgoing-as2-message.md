---
title: 生成传出的 AS2 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a0b1e37e96086de7d8901b61afa8dea859a388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246541"
---
# <a name="generating-an-outgoing-as2-message"></a>生成传出的 AS2 消息
AS2EDISend 和 AS2Send 发送管道生成出站消息，如下所示。 每个管道的单向协议选项卡中使用的属性**协议属性**对话框生成传出的 AS2 消息。  
  
## <a name="agreement-destination-and-messageid-determination"></a>确定协议、目标和 MessageID  
 AS2 发送管道确定用于发送 AS2 消息，如下所示的协议和目标：  
  
-   为了确定处理传出消息时使用的协议，AS2 编码器尝试将消息中的 AS2-To 属性和参与方业务配置文件的 AS2Identity 进行匹配，或者将订阅消息的发送端口和与协议关联的发送端口进行匹配。 此过程的详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
-   若要确定消息的目标，在动态发送端口发送管道，请使用 OutboundTransportLocation 属性，必须编写或通过动态发送端口工作的后端应用程序提升到上下文。 静态发送管道中的发送管道将通过 AS2 协议属性中的 AS2-From 属性和业务配置文件属性的标识来确定目标。  
  
-   AS2 编码器需要设置传出的 AS2 消息的 MessageId 标头。 发送管道将从 `EdiIntAS.MessageId` 上下文属性或 `HTTP.UserHttpHeaders` 上下文属性来确定 MessageId。 如果上述两个上下文属性均已设置，则编码器将使用 `HTTP.UserHttpHeaders` 上下文属性中的值。 如果这些都不设置，发送管道自动生成一个值的 MessageID。  
  
## <a name="outgoing-message-processing"></a>传出消息处理  
 AS2 发送管道处理传出 AS2 消息中使用的步骤如下所示：  
  
-   以本机格式创建消息的副本，并将该副本存储在不可否认数据库中（如果在协议属性中启用 AS2 消息的不可否认）。  
  
-   AS2 编码器将 HTTP（和 AS2）标头生成到 `HTTP.UserHttpHeaders` 上下文属性中。 此过程的详细信息，请参阅[发送方的传出通过 AS2 EDI 消息处理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)。  
  
-   将 `HTTP.UserHttpHeaders` 写入到上下文。  
  
-   如果启用，将压缩的传出消息。  
  
-   执行 MIME 处理，包括加密消息 (如果在中启用**应对消息进行加密**协议属性) 并将其应用数字签名 (如果在中启用**消息应为签名的**协议属性)。 AS2Send 管道使用 SHA1 或 MD5 应用签名，基于协议设置。  
  
-   如果已在协议属性中启用传输文件名，则创建一个包含指定值的 Content-Disposition MIME 标头。  
  
-   （在连网格式），将加密的消息的副本，并将副本存储在不可否认性数据库中，如果在中启用**为出站的已编码 AS2 消息启用 NRR**协议属性中。  
  
-   如果需要 MDN，计算 MIC 值并将其存储在数据存储。  
  
-   消息传送至 HTTP 适配器，这将从 UserHTTPHeaders 上下文属性的标头写入到传出的 AS2 消息。  
  
-   如果可靠消息传递是必需的重新发送消息，直到收到 MDN。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 发送组件](../core/as2-send-components.md)