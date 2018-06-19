---
title: 方案 1： 调整跟踪数据库的简单 BizTalk 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: 5b8fed48-d9c9-4d1f-a320-d3e23b8b1ec9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9c99c99485e34f95c6f6a75b86170d73678518
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269717"
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a><span data-ttu-id="0f7fb-102">方案 1： 调整跟踪数据库的简单 BizTalk 消息</span><span class="sxs-lookup"><span data-stu-id="0f7fb-102">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>
<span data-ttu-id="0f7fb-103">在下图中，一个简单的 BizTalk Server 消息传递而无需进行任何消息转换入和移出 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-103">In the following figure, a simple BizTalk Server message passes in and out of BizTalk Server without undergoing any message transformation.</span></span>  
  
 <span data-ttu-id="0f7fb-104">![简单的 BizTalk Server 消息 &#45;任何转换](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span><span class="sxs-lookup"><span data-stu-id="0f7fb-104">![Simple BizTalk Server message &#45; no transformation](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span></span>  
  
 <span data-ttu-id="0f7fb-105">**简单的 BizTalk Server 消息的任何转换**</span><span class="sxs-lookup"><span data-stu-id="0f7fb-105">**A simple BizTalk Server message - no transformation**</span></span>  
  
 <span data-ttu-id="0f7fb-106">在应用上一节中的公式前，你将需要收集一些有关这种情况下事实。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-106">Before you apply the formula in the previous section, you will need to gather some facts about this scenario.</span></span> <span data-ttu-id="0f7fb-107">在此示例中，我们使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="0f7fb-107">In this example, we use the following:</span></span>  
  
-   <span data-ttu-id="0f7fb-108">消息大小为 5 的 K。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-108">The message size is 5K.</span></span>  
  
-   <span data-ttu-id="0f7fb-109">没有属性将被提升。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-109">No properties will be promoted.</span></span>  
  
-   <span data-ttu-id="0f7fb-110">一年中接收的消息数是 350 万个。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-110">The number of messages you receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="0f7fb-111">已打开对所有事件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-111">Tracking is turned on for all events.</span></span> <span data-ttu-id="0f7fb-112">在此方案中有四个事件。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-112">There are four events in this scenario.</span></span> <span data-ttu-id="0f7fb-113">这些事件是：</span><span class="sxs-lookup"><span data-stu-id="0f7fb-113">The events are:</span></span>  
  
    -   <span data-ttu-id="0f7fb-114">收到消息 M0</span><span class="sxs-lookup"><span data-stu-id="0f7fb-114">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="0f7fb-115">接收端口从消息 M1 的输出</span><span class="sxs-lookup"><span data-stu-id="0f7fb-115">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="0f7fb-116">收到消息 M1 传输管道</span><span class="sxs-lookup"><span data-stu-id="0f7fb-116">Receipt of message M1 by the transmit pipeline</span></span>  
  
    -   <span data-ttu-id="0f7fb-117">消息 M2 发送管道的输出</span><span class="sxs-lookup"><span data-stu-id="0f7fb-117">Output of message M2 by the send pipeline</span></span>  
  
-   <span data-ttu-id="0f7fb-118">在这种情况下创建两个其他消息。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-118">Two additional messages are created in this scenario.</span></span> <span data-ttu-id="0f7fb-119">消息 M0 是传入消息，并因此不由 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-119">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="0f7fb-120">消息 M1 是来自接收端口的输出消息和 M2 是传输端口的输出。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-120">Message M1 is the output message from the receive port and M2 is the output from the transmit port.</span></span> <span data-ttu-id="0f7fb-121">M1 和 M2 由 BizTalk Server 创建。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-121">M1 and M2 are created by BizTalk Server.</span></span>  
  
 <span data-ttu-id="0f7fb-122">将此信息应用于该公式中提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="0f7fb-122">Applying this information to the formula gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a><span data-ttu-id="0f7fb-123">与单个提升的属性的消息</span><span class="sxs-lookup"><span data-stu-id="0f7fb-123">Messages with a single promoted property</span></span>  
 <span data-ttu-id="0f7fb-124">让我们看一看此示例中，并添加到方案的一个附加的事实。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-124">Let's take another look at this example and add one additional fact to the scenario.</span></span> <span data-ttu-id="0f7fb-125">你想要将一个字段，大约 10 个字节的大小，提升原始消息中。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-125">You want to promote a single field, approximately 10 bytes in size, from the original message.</span></span> <span data-ttu-id="0f7fb-126">升级的最大大小是字段的 256 个字符或大约 256 个字节 （512 字节如果字符都是字段的 Unicode）。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-126">The maximum size of a promoted field is 256 characters, or approximately 256 bytes (512 bytes if the characters are Unicode).</span></span>  
  
 <span data-ttu-id="0f7fb-127">使用此附加的事实，公式现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f7fb-127">With this additional fact, the equation now appears as follows:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 <span data-ttu-id="0f7fb-128">如果你想要提升是大小为 10 个字节的其他字段，将为公式：</span><span class="sxs-lookup"><span data-stu-id="0f7fb-128">If you wanted to promote an additional field that is 10 bytes in size, the equation would be:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 <span data-ttu-id="0f7fb-129">你可以看到，如果将升级在此方案中的单个 10 字节属性，它会将添加额外的 333.79 MB ~ 0.33 GB 每年的大小的 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-129">As you can see, if you promote a single 10-byte property in this scenario, it will add an additional 333.79 MB ~ 0.33 GB per year to the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="0f7fb-130">升级两个 10 字节属性将添加额外的 667.58 MB ~ 0.65 GB 的额外的空间，每年的大小的 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-130">Promoting two 10-byte properties will add an additional 667.58 MB ~ 0.65 GB of additional space per year to the size of the BizTalk Tracking database.</span></span>  
  
## <a name="messages-with-message-body-tracking-activated"></a><span data-ttu-id="0f7fb-131">使用跟踪的消息正文的消息激活</span><span class="sxs-lookup"><span data-stu-id="0f7fb-131">Messages with message body tracking activated</span></span>  
 <span data-ttu-id="0f7fb-132">在此示例中，我们还假定我们计划在激活消息正文跟踪。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-132">In this example, let us also assume that we are planning on activating message body tracking.</span></span> <span data-ttu-id="0f7fb-133">我们将需要添加消息跟踪上, 一节中所示的第二个公式。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-133">We will need to add the second equation for message tracking, shown in the previous section.</span></span> <span data-ttu-id="0f7fb-134">公式将如下所示对于此示例：</span><span class="sxs-lookup"><span data-stu-id="0f7fb-134">The equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 <span data-ttu-id="0f7fb-135">通过添加两个公式的结果，我们可以预计 BizTalk 跟踪数据库将每年到 54.88 GB 增加了大约 54.48 GB。</span><span class="sxs-lookup"><span data-stu-id="0f7fb-135">By adding the results of the two equations, we can estimate that the BizTalk Tracking database will grow approximately 54.48 GB to 54.88 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7fb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f7fb-136">See Also</span></span>  
 <span data-ttu-id="0f7fb-137">[使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="0f7fb-137">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="0f7fb-138">[大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="0f7fb-138">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="0f7fb-139">[方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="0f7fb-139">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="0f7fb-140">[方案 4： 调整跟踪数据库的所有消息](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0f7fb-140">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="0f7fb-141">方案 3： 调整跟踪数据库的消息发送到通讯组列表</span><span class="sxs-lookup"><span data-stu-id="0f7fb-141">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)