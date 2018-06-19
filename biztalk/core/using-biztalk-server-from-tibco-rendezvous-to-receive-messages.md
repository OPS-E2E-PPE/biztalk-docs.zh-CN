---
redirect_url: /biztalk/core/using-tibco-rendezvous-receive-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: b1738a0933b5f570edfd882778e50ebf7e2ca730
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013524"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a>使用来自 TIBCO Rendezvous 的 BizTalk Server 以接收消息
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器从队列中调度多个线程上的事件。 BizTalk Server 接收位置与一个 TIBCO Rendezvous 事件队列及其调度程序线程池关联。  
  
## <a name="memory-use-and-errors"></a>内存使用和错误  
 处理事件时，适配器会监控所使用的资源情况。 如果内存使用量超出高水位，则适配器会停止调度事件，直至内存使用量达到低水位。 注意，对于未认证的消息，这会导致 TIBCO Rendezvous 消息丢失（TIBCO RV 使用者有 60 秒的时间将消息从队列中删除）。 此数据丢失会被报告为错误。 如果适配器收到 TIBCO Rendezvous 系统建议 NO_MEMORY 消息，则这些消息已经丢失。  
  
 用于 TIBCO Rendezvous 的 BizTalk 适配器会维持一种状态，并根据该状态的变化来执行任务。 如果 BizTalk 消息引擎报告错误，并且已将适配器配置为认证侦听器，则向 TIBCO Rendezvous 报告错误，以便可以重新提交消息。  
  
## <a name="see-also"></a>另请参阅  
 [TIBCO 会合概念](../core/tibco-rendezvous-concepts.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)