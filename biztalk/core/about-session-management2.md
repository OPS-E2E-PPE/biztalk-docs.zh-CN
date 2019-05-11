---
title: 有关会话 Management2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ecdb4f-d384-42ac-9776-e7ad14d5f151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b316a1a145f6f5d6d839febcc02c1fe2056b9579
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362280"
---
# <a name="about-session-management"></a>关于会话管理
用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器创建一个连接会话，以发送到 JD Edwards EnterpriseOne 服务器的调用。 当调用终止时，会话会放在要重新使用的后续调用的池。 适配器会创建多个连接会话，从而处理对 JD Edwards EnterpriseOne 服务器的并发调用。 定期清理该池，从而删除不再需要的会话。  
  
 Microsoft BizTalk 适配器 JD Edwards EnterpriseOne 提供两个消息上下文属性，以控制何时必须在同一会话中进行调用。  
  
|“属性”|类型|默认|  
|----------|----------|-------------|  
|JDE.SessionID|smallint|0|  
|JDE.ReserveSession|boolean|false|  
  
 如果业务功能要求对 JD Edwards EnterpriseOne 服务器的单个调用，则会话管理。 适配器可以选择任何可用的会话，并且会话仍可用于随后的任何调用。 在此方案中，你可以忽略消息上下文属性，因为默认值是适当。  
  
 某些 JD Edwards EnterpriseOne 功能要求对 JD Edwards EnterpriseOne 服务器; 的多次调用例如，创建 SalesOrder。 首次调用 BeginDoc 会创建一个空 SalesOrder。 每个后续调用 editline 向 SalesOrder 添加一个行项。 最后调用 enddoc 将关闭 SalesOrder。  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 若要成功，必须在同一会话上发送对单个 SalesOrder 的所有调用。 若要执行此操作，分配消息上下文属性以指示适配器如何处理会话。 以 SalesOrder 为例，以下是将赋给消息上下文属性以处理 JD Edwards EnterpriseOne 会话的值：  
  
|函数|SessionID|ReserveSession|  
|--------------|---------------|--------------------|  
|BeginDoc|0|true|  
|EditLine|从 BeginDoc 回复中复制|true|  
|EditLine|从 BeginDoc 回复中复制|true|  
|EndDoc|从 BeginDoc 回复中复制|false|  
  
- 首次调用时，适配器是随意选择任何可用的会话 （因为 SessionID 为 0）。  
  
- 适配器返回 BeginDoc 回复中使用的 SessionID。  
  
- ReserveSession 属性会指示适配器保留显式请求此会话的以下调用此会话。 由于已保留，其他任何调用可以意外地重复不使用该会话。  
  
- 后续调用通过将 SessionID 设置为在 BeginDoc 中返回的值请求会话。  
  
- ReserveSession 属性设置为 true，至少直到序列中的最后一个调用。  
  
- 最后一次调用将 ReserveSession 设置为 false，以使会话可供任何调用。 但是，业务流程可选择要保留的会话的更多调用。  
  
  如果会话未使用一段时间，它将进行垃圾回收的池，即使错误地是仍保留在会话。  
  
  请参阅 BizTalk Server 文档有关消息上下文属性的详细信息。  
  
## <a name="see-also"></a>请参阅  
 [使用消息上下文属性](../core/using-message-context-properties1.md)