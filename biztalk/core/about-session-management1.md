---
title: 有关会话 Management1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1848619-d97a-4f1e-ba94-59861bd7aedf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 336deb34e5587e64c5177cd0a439c756cf0f2b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225645"
---
# <a name="about-session-management"></a>关于会话管理
Microsoft BizTalk Adapter for 博士 Edwards OneWorld 创建要发送到博士 Edwards OneWorld 服务器调用的连接会话。 调用终止时，会话会放在池中以供后续调用重用。 适配器会创建多个连接会话，从而处理对 JD Edwards OneWorld 服务器的并发调用。 池会定期进行清理，从而删除不再需要的会话。  
  
 适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供两个消息上下文属性，以控制何时必须在同一会话中进行调用。  
  
|Name|类型|默认|  
|----------|----------|-------------|  
|JDE.SessionID|int|0|  
|JDE.ReserveSession|boolean|false|  
  
 如果业务功能要求对 JD Edwards OneWorld 服务器进行单一调用，则不必进行会话管理。 适配器可以选择任何可用的会话，并且会话仍可用于随后的任何调用。 在这种情况下，由于默认值适当，因此可以忽略消息上下文属性。  
  
 某些 JD Edwards OneWorld 功能要求对 JD Edwards OneWorld 服务器进行多次调用；例如，创建 SalesOrder 时。 首次调用 BeginDoc 会创建一个空 SalesOrder。 随后每次调用 EditLine 会向 SalesOrder 添加一个行项目。 最后调用 EndDoc 将关闭 SalesOrder。  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 若要成功执行此操作，对单个 SalesOrder 的所有调用都必须在同一会话中发送。 为此，请为消息上下文属性赋值以指示适配器如何处理会话。 以 SalesOrder 为例，以下是将赋给消息上下文属性以处理 JD OneWorld 会话的值：  
  
|函数|SessionID|ReserveSession|  
|--------------|---------------|--------------------|  
|BeginDoc|0|true|  
|EditLine|从 BeginDoc 回复中复制|true|  
|EditLine|从 BeginDoc 回复中复制|true|  
|EndDoc|从 BeginDoc 回复中复制|false|  
  
-   首次调用时，适配器可以随意选择任何可用的会话（因为 SessionID 为 0）。  
  
-   适配器会返回已在 BeginDoc 回复中使用的 SessionID。  
  
-   ReserveSession 属性会指示适配器为随后显式请求此会话的调用保留此会话。 其他任何调用都不能随意重用此会话，因为此会话已保留。  
  
-   后续调用通过将 SessionID 设置为在 BeginDoc 中返回的值请求会话。  
  
-   ReserveSession 属性一直设置为 True，至少到系列中的最后一次调用。  
  
-   最后一次调用将 ReserveSession 设置为 False，从而使会话可用于随后的任何调用。 但是，业务流程可选择保留会话，从而用于更多次调用。  
  
 如果暂时不使用会话，此会话将由池进行垃圾回收，即使仍错误地保留此会话也是如此。  
  
 请参阅有关消息上下文属性的详细信息的 BizTalk Server 文档。  
  
## <a name="see-also"></a>另请参阅  
 [使用消息上下文属性](../core/using-message-context-properties2.md)   
 [如何将消息上下文属性值分配](../core/how-to-assign-message-context-property-values2.md)   
 [教程： 使用适用于博士 Edwards OneWorld BizTalk 适配器](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)