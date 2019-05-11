---
title: 应用场景 1：为简单 BizTalk 消息调整跟踪数据库的大小 |Microsoft Docs
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
ms.openlocfilehash: e559869bfb62439bb5f83a97b528ecf6960e123f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308615"
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a><span data-ttu-id="74ce9-102">应用场景 1：为简单 BizTalk 消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="74ce9-102">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>
<span data-ttu-id="74ce9-103">在下图中，一个简单的 BizTalk Server 消息传递而无需进行任何消息转换入和移出 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="74ce9-103">In the following figure, a simple BizTalk Server message passes in and out of BizTalk Server without undergoing any message transformation.</span></span>  
  
 <span data-ttu-id="74ce9-104">![简单的 BizTalk Server 消息&#45;无转换](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span><span class="sxs-lookup"><span data-stu-id="74ce9-104">![Simple BizTalk Server message &#45; no transformation](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span></span>  
  
 <span data-ttu-id="74ce9-105">**简单的 BizTalk Server 消息-无转换**</span><span class="sxs-lookup"><span data-stu-id="74ce9-105">**A simple BizTalk Server message - no transformation**</span></span>  
  
 <span data-ttu-id="74ce9-106">在应用上一节中的公式之前，需要收集一些有关此方案的事实。</span><span class="sxs-lookup"><span data-stu-id="74ce9-106">Before you apply the formula in the previous section, you will need to gather some facts about this scenario.</span></span> <span data-ttu-id="74ce9-107">在此示例中，我们使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="74ce9-107">In this example, we use the following:</span></span>  
  
- <span data-ttu-id="74ce9-108">消息大小为 5 个 K。</span><span class="sxs-lookup"><span data-stu-id="74ce9-108">The message size is 5K.</span></span>  
  
- <span data-ttu-id="74ce9-109">将不升级任何属性。</span><span class="sxs-lookup"><span data-stu-id="74ce9-109">No properties will be promoted.</span></span>  
  
- <span data-ttu-id="74ce9-110">一年中接收的消息数为 350 万条。</span><span class="sxs-lookup"><span data-stu-id="74ce9-110">The number of messages you receive in a year is 3.5 million.</span></span>  
  
- <span data-ttu-id="74ce9-111">跟踪被打开的所有事件。</span><span class="sxs-lookup"><span data-stu-id="74ce9-111">Tracking is turned on for all events.</span></span> <span data-ttu-id="74ce9-112">在此方案中有四个事件。</span><span class="sxs-lookup"><span data-stu-id="74ce9-112">There are four events in this scenario.</span></span> <span data-ttu-id="74ce9-113">这些事件是：</span><span class="sxs-lookup"><span data-stu-id="74ce9-113">The events are:</span></span>  
  
  -   <span data-ttu-id="74ce9-114">接收消息 M0</span><span class="sxs-lookup"><span data-stu-id="74ce9-114">Receipt of message M0</span></span>  
  
  -   <span data-ttu-id="74ce9-115">输出消息 M1 从接收端口</span><span class="sxs-lookup"><span data-stu-id="74ce9-115">Output of message M1 from the receive port</span></span>  
  
  -   <span data-ttu-id="74ce9-116">接收消息 M1 通过传输管道</span><span class="sxs-lookup"><span data-stu-id="74ce9-116">Receipt of message M1 by the transmit pipeline</span></span>  
  
  -   <span data-ttu-id="74ce9-117">通过输出消息 M2 发送管道</span><span class="sxs-lookup"><span data-stu-id="74ce9-117">Output of message M2 by the send pipeline</span></span>  
  
- <span data-ttu-id="74ce9-118">在此方案中创建两个其他消息。</span><span class="sxs-lookup"><span data-stu-id="74ce9-118">Two additional messages are created in this scenario.</span></span> <span data-ttu-id="74ce9-119">消息 M0 是传入的消息，因此不创建由 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="74ce9-119">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="74ce9-120">消息 M1 是从接收端口输出消息，M2 是从传输端口输出。</span><span class="sxs-lookup"><span data-stu-id="74ce9-120">Message M1 is the output message from the receive port and M2 is the output from the transmit port.</span></span> <span data-ttu-id="74ce9-121">由 BizTalk Server 创建 M1 和 M2。</span><span class="sxs-lookup"><span data-stu-id="74ce9-121">M1 and M2 are created by BizTalk Server.</span></span>  
  
  <span data-ttu-id="74ce9-122">将这些信息应用到公式中提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="74ce9-122">Applying this information to the formula gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a><span data-ttu-id="74ce9-123">具有单个升级属性的消息</span><span class="sxs-lookup"><span data-stu-id="74ce9-123">Messages with a single promoted property</span></span>  
 <span data-ttu-id="74ce9-124">让我们看看此示例中，并将一个事实添加到方案。</span><span class="sxs-lookup"><span data-stu-id="74ce9-124">Let's take another look at this example and add one additional fact to the scenario.</span></span> <span data-ttu-id="74ce9-125">你想要升级单个字段，约为 10 字节的大小，原始消息中。</span><span class="sxs-lookup"><span data-stu-id="74ce9-125">You want to promote a single field, approximately 10 bytes in size, from the original message.</span></span> <span data-ttu-id="74ce9-126">已升级的最大大小是字段的 256 个字符或大约 256 个字节 （512 字节 Unicode 字符是否）。</span><span class="sxs-lookup"><span data-stu-id="74ce9-126">The maximum size of a promoted field is 256 characters, or approximately 256 bytes (512 bytes if the characters are Unicode).</span></span>  
  
 <span data-ttu-id="74ce9-127">与此事实，公式将如下所示：</span><span class="sxs-lookup"><span data-stu-id="74ce9-127">With this additional fact, the equation now appears as follows:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 <span data-ttu-id="74ce9-128">如果您想要提升为大小的 10 个字节的附加字段，公式为：</span><span class="sxs-lookup"><span data-stu-id="74ce9-128">If you wanted to promote an additional field that is 10 bytes in size, the equation would be:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 <span data-ttu-id="74ce9-129">您可以看到，如果升级一个 10 字节属性在此方案中，它会将添加额外的 333.79 MB ~ 0.33 GB 每年的大小的 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="74ce9-129">As you can see, if you promote a single 10-byte property in this scenario, it will add an additional 333.79 MB ~ 0.33 GB per year to the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="74ce9-130">升级两个 10 字节属性将添加额外的 667.58 MB ~ 0.65 GB 的 BizTalk 跟踪数据库每年的大小的额外空间。</span><span class="sxs-lookup"><span data-stu-id="74ce9-130">Promoting two 10-byte properties will add an additional 667.58 MB ~ 0.65 GB of additional space per year to the size of the BizTalk Tracking database.</span></span>  
  
## <a name="messages-with-message-body-tracking-activated"></a><span data-ttu-id="74ce9-131">消息正文跟踪的消息激活</span><span class="sxs-lookup"><span data-stu-id="74ce9-131">Messages with message body tracking activated</span></span>  
 <span data-ttu-id="74ce9-132">在此示例中，我们还假设我们计划在激活消息正文跟踪。</span><span class="sxs-lookup"><span data-stu-id="74ce9-132">In this example, let us also assume that we are planning on activating message body tracking.</span></span> <span data-ttu-id="74ce9-133">我们将需要添加消息跟踪，在上一节中所示的第二个公式。</span><span class="sxs-lookup"><span data-stu-id="74ce9-133">We will need to add the second equation for message tracking, shown in the previous section.</span></span> <span data-ttu-id="74ce9-134">公式将如下所示，对于此示例：</span><span class="sxs-lookup"><span data-stu-id="74ce9-134">The equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 <span data-ttu-id="74ce9-135">通过添加两个等式的结果，我们可以估计 BizTalk 跟踪数据库的每年为 54.88 GB 增长了大约 54.48 GB。</span><span class="sxs-lookup"><span data-stu-id="74ce9-135">By adding the results of the two equations, we can estimate that the BizTalk Tracking database will grow approximately 54.48 GB to 54.88 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ce9-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="74ce9-136">See Also</span></span>  
 <span data-ttu-id="74ce9-137">[使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="74ce9-137">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="74ce9-138">[调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="74ce9-138">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="74ce9-139">[方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="74ce9-139">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="74ce9-140">[方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="74ce9-140">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="74ce9-141">方案 3:为发送到分发列表的消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="74ce9-141">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)