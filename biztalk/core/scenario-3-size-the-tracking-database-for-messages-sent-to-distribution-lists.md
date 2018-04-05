---
title: 方案 3： 调整跟踪数据库大小的消息发送到通讯组列表扩展 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: bc6e0da0-46d1-42d6-8ec9-29a28719fbb3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca1722e24e0c76c85699ea00fcf6ffc120b2e14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a><span data-ttu-id="a62b3-102">方案 3：对发送到分发列表的消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="a62b3-102">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>
<span data-ttu-id="a62b3-103">下图中的消息将通过业务流程、在业务流程内被更改，然后通过分发列表向外发送给多个不同的发送端口：</span><span class="sxs-lookup"><span data-stu-id="a62b3-103">In the following figure, you have a message that proceeds through an orchestration, is changed within the orchestration, and is then sent out to several different send ports through a distribution list.</span></span>  
  
 <span data-ttu-id="a62b3-104">![通过多个端口的业务流程的消息](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")</span><span class="sxs-lookup"><span data-stu-id="a62b3-104">![Message through an orchestration to multiple ports](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")</span></span>  
  
 <span data-ttu-id="a62b3-105">**通过业务流程将继续且 BizTalk Server 消息发送到多个不同的端口**</span><span class="sxs-lookup"><span data-stu-id="a62b3-105">**BizTalk Server message that proceeds through an orchestration and is sent out to several different ports**</span></span>  
  
 <span data-ttu-id="a62b3-106">以下为有关此方案的一些实际信息：</span><span class="sxs-lookup"><span data-stu-id="a62b3-106">Here are some of the facts concerning this scenario:</span></span>  
  
-   <span data-ttu-id="a62b3-107">消息大小为 10k。</span><span class="sxs-lookup"><span data-stu-id="a62b3-107">The message size is 10K.</span></span>  
  
-   <span data-ttu-id="a62b3-108">当前不升级任何属性。</span><span class="sxs-lookup"><span data-stu-id="a62b3-108">You are not promoting any properties.</span></span>  
  
-   <span data-ttu-id="a62b3-109">一年中接收的消息数是 350 万个。</span><span class="sxs-lookup"><span data-stu-id="a62b3-109">The number of messages you receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="a62b3-110">已打开对所有事件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="a62b3-110">Tracking is turned on for all events.</span></span> <span data-ttu-id="a62b3-111">此方案包含以下五个事件：</span><span class="sxs-lookup"><span data-stu-id="a62b3-111">There are five events in this scenario:</span></span>  
  
    -   <span data-ttu-id="a62b3-112">收到消息 M0</span><span class="sxs-lookup"><span data-stu-id="a62b3-112">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="a62b3-113">接收端口从消息 M1 的输出</span><span class="sxs-lookup"><span data-stu-id="a62b3-113">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="a62b3-114">通过发送端口输出消息 M3</span><span class="sxs-lookup"><span data-stu-id="a62b3-114">Output of message M3 by the send port</span></span>  
  
    -   <span data-ttu-id="a62b3-115">通过发送端口输出消息 M4</span><span class="sxs-lookup"><span data-stu-id="a62b3-115">Output of message M4 by the send port</span></span>  
  
    -   <span data-ttu-id="a62b3-116">通过发送端口输出消息 M5</span><span class="sxs-lookup"><span data-stu-id="a62b3-116">Output of message M5 by the send port</span></span>  
  
 <span data-ttu-id="a62b3-117">将这些信息应用到公式中之后结果如下：</span><span class="sxs-lookup"><span data-stu-id="a62b3-117">Applying this information to the equation gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a><span data-ttu-id="a62b3-118">业务流程中发送给分发列表并且具有单个升级属性的消息</span><span class="sxs-lookup"><span data-stu-id="a62b3-118">Messages in an orchestration that are sent out to a distribution list with a single promoted property</span></span>  
 <span data-ttu-id="a62b3-119">在此示例中，请按照之前方案中所执行的操作来升级大小约为 10 字节的单个属性。</span><span class="sxs-lookup"><span data-stu-id="a62b3-119">In this example, let's promote a single property, approximately 10 bytes in size, as we did in an earlier scenario.</span></span> <span data-ttu-id="a62b3-120">公式现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="a62b3-120">The equation now looks like this:</span></span>  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 <span data-ttu-id="a62b3-121">如果另外升级一个大小为 20 字节的属性，则公式将如下所示：</span><span class="sxs-lookup"><span data-stu-id="a62b3-121">If we promote an additional property that is 20 bytes in size the equation now looks like this:</span></span>  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a><span data-ttu-id="a62b3-122">业务流程中发送给分发列表并且已激活消息正文跟踪的消息</span><span class="sxs-lookup"><span data-stu-id="a62b3-122">Messages in an orchestration that are sent out to a distribution list with message body tracking activated</span></span>  
 <span data-ttu-id="a62b3-123">若要允许消息跟踪，则对于此示例，公式将如下所示：</span><span class="sxs-lookup"><span data-stu-id="a62b3-123">If you want to accommodate message tracking, the equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a62b3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a62b3-124">See Also</span></span>  
 <span data-ttu-id="a62b3-125">[使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="a62b3-125">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="a62b3-126">[大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="a62b3-126">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="a62b3-127">[方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a62b3-127">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="a62b3-128">[方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="a62b3-128">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="a62b3-129">方案 4： 调整跟踪数据库的所有消息</span><span class="sxs-lookup"><span data-stu-id="a62b3-129">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)