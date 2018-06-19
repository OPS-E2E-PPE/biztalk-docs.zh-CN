---
title: 配置动态发送端口异步 Mdn 的通过 AS2 |Microsoft 文档
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
ms.openlocfilehash: 754917ed1a089e3182c8543e8a132a9eff73615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233445"
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a>配置用于 AS2 上的异步 MDN 的动态发送端口
要通过 HTTP/HTTPS 发送异步的 EDIINT/AS2 编码消息，请使用以下配置创建一个动态 HTTP 发送端口：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|动态单向|  
|**发送端口属性： 常规**|发送管道|AS2Send|  
|**发送端口属性： 筛选器**|属性|EdiIntAS.IsAS2AsynchronousMdn|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|True|  
  
 应将异步 MDN 发送到中包含的地址**回执送达选项**已接收的 AS2 消息的标头。 动态发送端口将执行此操作，而静态发送端口将消息发送到**目标 URL**发送端口定义中。 此规则的例外是如果**使用验证和 MDN 的协议设置，而不是消息标头**属性在中设置**验证**的单向协议选项卡页**协议属性**对话框。 在这种情况下，发送端口将将 MDN 消息发送到的 URL 输入到**回执送达选项**协议属性。 但是，用于执行此操作的发送端口仍然必须是一个动态发送端口，而不是静态发送端口。  
  
 可以将此发送端口配置为既返回 MDN 确认也返回 EDI 确认。 在此情况下，如果成功地通过 HTTP/HTTPS 传输了 EDIINT/AS2 编码的消息，但是在处理 EDI 编码的负载时失败，原始消息的发送方既会收到表示成功处理了 AS2 的 MDN 确认，也会收到表示 EDI 处理失败的 EDI 确认。 EDI 编码的负载将被挂起并产生一个错误。  
  
## <a name="functionality"></a>功能  
 若要发送一个 MDN，发送端口和管道必须执行以下操作：  
  
-   通过对 `EdiIntAS.IsAS2AsynchronousMdn==True` 属性进行筛选，获取该 MDN。  
  
-   生成一条 AS2 消息。 有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
-   将 MDN 路由到中的地址**回执送达选项**消息的标头中的行。  
  
    > [!NOTE]
    >  如果**使用验证和 MDN 的协议设置，而不是消息标头**属性在中设置**验证**的单向协议选项卡页**协议属性**对话框中，发送端口将 MDN 消息发送到的 URL 输入到**回执送达选项**协议属性，而不是中所述的地址**回执送达选项**已接收的 AS2 消息的标头。  
  
## <a name="see-also"></a>另请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)