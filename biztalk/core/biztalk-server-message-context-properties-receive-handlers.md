---
title: "接收消息上下文属性的 TIBCO 会合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36f4de92dbe7c4c235a1c9ebd092b28b3a198c92
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a>BizTalk Server 消息上下文属性 （接收处理程序）
除了消息负载之外，构成消息的补充信息必须可以在运行时从 BizTalk Server 业务流程访问。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>TIBCO RV 消息信息升级为消息上下文属性  
 下表列出了此补充信息：  
  
|数据标识|类型|可路由|接收位置|  
|-------------------------|----------|--------------|----------------------|  
|发送主题 [空]|string|是|告诉业务流程此消息发送到哪个主题。|  
|答复主题 [空]|string|是|告诉业务流程发件人希望将此回复发送到的位置（如果有）。|  
|字段计数 [只读]|unsigned int|是|上级消息中的字段数。 一个由 TIBCO RV 提供的属性。|  
|CM 发件人姓名 [只读]|string|是|发件人的 CM 通信名称。|  
|CM 序号 [只读]|long|是|通过发送 TIBCO 传输对象分配的序列号。|  
|CM 时间限制 [只读]|double|是|时间限制，在这段时间之后发送程序就不再要求其 CM 传输证实消息是否递送。|  
  
## <a name="see-also"></a>另请参阅  
 [TIBCO 集合中的消息映射](../core/message-mapping-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)