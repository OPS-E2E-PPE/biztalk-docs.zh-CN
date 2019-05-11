---
title: 生成传出 AS2 消息 |Microsoft Docs
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
ms.openlocfilehash: fd96debd3099eee795ebb661a9f5828d7de6f10f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387775"
---
# <a name="generating-an-outgoing-as2-message"></a>生成传出 AS2 消息
AS2EDISend 和 AS2Send 发送管道生成出站消息，如下所示。 每个管道的单向协议选项卡中使用的属性**协议属性**对话框来生成传出 AS2 消息。  
  
## <a name="agreement-destination-and-messageid-determination"></a>协议、 目标和 MessageID 确定  
 AS2 发送管道确定要在中，如下所示发送 AS2 消息使用的协议和目标：  
  
-   若要确定在处理传出消息要使用的协议，AS2 编码器尝试匹配 AS2-与订阅的消息的发送端口关联到的消息和 AS2Identity 进行参与方的业务配置文件或发送端口中的属性协议。 此过程的详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
-   若要确定消息的目标，在动态发送端口的发送管道使用 OutboundTransportLocation 属性，它必须写入或通过动态发送端口，若要运行的后端应用程序升级到上下文。 在静态发送管道中的发送管道将确定目标中的 AS2-From AS2 协议属性和业务配置文件属性的标识中的属性。  
  
-   AS2 编码器需要设置传出 AS2 消息的 MessageId 标头。 发送管道确定从 MessageId`EdiIntAS.MessageId`上下文属性或`HTTP.UserHttpHeaders`上下文属性。 如果设置了这两个上下文属性，编码器使用的值`HTTP.UserHttpHeaders`上下文属性。 如果它们未设置，发送管道自动生成值的消息 Id。  
  
## <a name="outgoing-message-processing"></a>传出消息处理  
 AS2 发送管道使用在处理传出的 AS2 消息的步骤如下所示：  
  
-   以本机格式创建消息的副本并将该副本存储在不可否认数据库中，如果在协议属性中启用不可否认性的 AS2 消息。  
  
-   AS2 编码器生成到的 HTTP （和 AS2） 标头`HTTP.UserHttpHeaders`上下文属性。 此过程的详细信息，请参阅[发送端处理通过 AS2 传出的 EDI 消息的](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)。  
  
-   写入`HTTP.UserHttpHeaders`到上下文。  
  
-   如果启用了，压缩的传出消息。  
  
-   执行 MIME 处理，其中包括对消息进行加密 (如果在中启用**应对消息进行加密**协议属性) 并应用数字签名 (如果在中启用**应对消息进行签名的**协议属性)。 AS2Send 管道使用 SHA1 或 MD5 应用签名，根据协议设置。  
  
-   创建的 Content-disposition MIME 标头包含指定的值，如果将文件传输协议属性中启用了名称。  
  
-   创建加密的消息的副本 （以传输格式），并将该副本存储在不可否认数据库中，如果在中启用**已为出站编码 AS2 消息启用 NRR**协议属性中。  
  
-   如果 MDN 是必需的计算的 MIC 值并将其存储在数据存储区。  
  
-   将该消息传送到 HTTP 适配器，将标头从 UserHTTPHeaders 上下文属性写入到传出的 AS2 消息。  
  
-   如果可靠消息传送是必需的重新发送该消息，直到收到 MDN。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 发送组件](../core/as2-send-components.md)