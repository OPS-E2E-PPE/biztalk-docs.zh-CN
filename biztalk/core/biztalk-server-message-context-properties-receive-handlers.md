---
title: TIBCO Rendezvous 的接收的消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e330926c6f362ea5a84ad7b4b9291a5f2f310eee
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528328"
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a>BizTalk Server 消息上下文属性 （接收处理程序）
除了消息负载，撰写一条消息的补充信息必须可从 BizTalk Server 业务流程在运行时访问。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>TIBCO RV 消息信息升级为消息上下文属性  
 下表列出了此补充信息：  
  
|数据标识|类型|路由|接收位置|  
|-------------------------|----------|--------------|----------------------|  
|将发送主题 [空]|string|是|告诉业务流程此消息发送到哪个主题。|  
|答复主题 [空]|string|是|告诉业务流程而发件人需要答复发送，如果其中一个。|  
|字段计数 [只读]|unsigned int|否|上级消息中的字段数。 属性提供的 TIBCO rv。|  
|CM 发件人姓名 [只读]|string|是|发件人的 CM 通信名称。|  
|CM 序号 [只读]|long|否|通过发送 TIBCO 传输对象分配序列号。|  
|CM 时间限制 [只读]|double|否|时间限制，此后发送程序就不再要求其 CM 传输认证消息传递。|  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 中消息映射](../core/message-mapping-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)