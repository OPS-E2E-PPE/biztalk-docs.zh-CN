---
title: "大小调整跟踪消息正文的跟踪数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
- message variables [Tracking database], MsgNum
- HAT, ports
- Tracking database, messages
- tracking, orchestrations
- tracking, messages
- HAT, orchestrations
- tracking, ports
ms.assetid: ee75e530-f15d-4ceb-ba67-0b0b24d9df6b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5abc3f2a48f2baea5d158e1a0268a7eede51c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a><span data-ttu-id="eb819-102">大小调整跟踪数据库来跟踪消息正文</span><span class="sxs-lookup"><span data-stu-id="eb819-102">Sizing the Tracking Database to Track Message Bodies</span></span>
<span data-ttu-id="eb819-103">如果计划在 BizTalk 跟踪数据库中跟踪消息正文，那么，在计算时还需考虑这些正文的大小。</span><span class="sxs-lookup"><span data-stu-id="eb819-103">If you plan to track the message bodies in the BizTalk Tracking database, then you will also need to account for the size of these bodies in your calculation.</span></span> <span data-ttu-id="eb819-104">请使用以下公式：</span><span class="sxs-lookup"><span data-stu-id="eb819-104">Use the following equation:</span></span>  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 <span data-ttu-id="eb819-105">如果与消息大小相比，消息上下文非常大，请考虑增加上面 MsgSize 中的消息上下文的平均大小。</span><span class="sxs-lookup"><span data-stu-id="eb819-105">Consider adding the average size of the message context to MsgSize above if it is significant compared to the message size.</span></span>  
  
 <span data-ttu-id="eb819-106">通过在端口级别和业务流程级别打开跟踪功能，使用“组中心”页中的消息事件和服务实例跟踪来确定 MsgNum 变量。</span><span class="sxs-lookup"><span data-stu-id="eb819-106">The MsgNum variable is determined by turning on the tracking features at the port level or at the orchestration level using the message event and service instance tracking in the Group Hub page.</span></span> <span data-ttu-id="eb819-107">您还必须将此公式应用于每个消息流程。</span><span class="sxs-lookup"><span data-stu-id="eb819-107">You must apply this formula to each message process as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb819-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb819-108">See Also</span></span>  
 <span data-ttu-id="eb819-109">[使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="eb819-109">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="eb819-110">[方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="eb819-110">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="eb819-111">[方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="eb819-111">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="eb819-112">[方案 4： 调整跟踪数据库的所有消息](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="eb819-112">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="eb819-113">方案 3： 调整跟踪数据库的消息发送到通讯组列表</span><span class="sxs-lookup"><span data-stu-id="eb819-113">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)