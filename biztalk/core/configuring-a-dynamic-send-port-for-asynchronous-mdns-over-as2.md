---
title: 配置动态发送端口通过 AS2 发送异步 Mdn 的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6d8c962e1a417e1b97fd6fe8224718785133fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391423"
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a>配置通过 AS2 发送异步 Mdn 的动态发送端口
若要通过 HTTP/HTTPS 发送异步 EDIINT/AS2 编码的 MDN 消息，请使用以下配置创建一个动态 HTTP 发送端口：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|动态单向|  
|**发送端口属性：常规**|发送管道|AS2Send|  
|**发送端口属性：筛选器**|属性|EdiIntAS.IsAS2AsynchronousMdn|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|True|  
  
 异步 MDN 应发送到中包含的地址**回执送达选项**所接收 AS2 消息的标头。 动态发送端口将完成此操作，而静态发送端口将消息发送到**目标 URL**发送端口定义中。 此规则的例外是如果**使用的验证和 MDN 的协议设置而非消息标头**属性中设置**验证**页的单向协议选项卡的**协议属性**对话框。 在这种情况下，发送端口将发送 MDN 消息，到输入的 url**回执送达选项**协议属性。 但是，用来执行此操作的发送端口必须仍是一个动态发送端口，不是静态发送端口。  
  
 可以配置此发送端口返回 Mdn 和 EDI 确认。 在实例中，如果成功，通过 HTTP/HTTPS 传输 EDIINT/AS2 编码的消息，是但处理 EDI 编码的负载将失败，原始消息的发件人将收到同时表示成功处理了 AS2 和 EDI 的 MDN表示在 EDI 处理中的失败的确认。 EDI 编码的负载将被挂起并产生一个错误。  
  
## <a name="functionality"></a>功能  
 发送端口和管道必须执行以下操作来发送一个 MDN:  
  
-   进行筛选来获取该 MDN`EdiIntAS.IsAS2AsynchronousMdn==True`属性。  
  
-   生成 AS2 消息。 有关此过程的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
-   将 MDN 路由到中的地址**回执送达选项**消息的标头中的行。  
  
    > [!NOTE]
    >  如果**使用的验证和 MDN 的协议设置而非消息标头**属性中设置**验证**页的单向协议选项卡的**协议属性**对话框中，发送端口将 MDN 消息发送到输入的 url**回执送达选项**协议属性，而不是所述的地址**回执送达选项**接收 AS2 消息的标头。  
  
## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)