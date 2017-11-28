---
title: "方案 2： 调整跟踪数据库的业务流程中的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62ea6e463dfb3a44e2628f57b632634d7a9bd212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a><span data-ttu-id="51c17-102">方案 2：调整业务流程中消息的跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="51c17-102">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>
<span data-ttu-id="51c17-103">我们将介绍一个包含业务流程的示例。</span><span class="sxs-lookup"><span data-stu-id="51c17-103">Let's look at an example that includes an orchestration.</span></span> <span data-ttu-id="51c17-104">下图显示了整个业务流程。</span><span class="sxs-lookup"><span data-stu-id="51c17-104">The following figure displays the entire business process.</span></span> <span data-ttu-id="51c17-105">在此方案中，通过业务流程发送传递到 BizTalk Server 中的消息并在该业务流程内对其进行更改，然后通过发送端口发送出该消息。</span><span class="sxs-lookup"><span data-stu-id="51c17-105">In this scenario, a message comes into BizTalk Server, is sent through an orchestration, is changed within the orchestration, and is then sent out through a send port.</span></span>  
  
 <span data-ttu-id="51c17-106">![BizTalk Server 消息进程](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span><span class="sxs-lookup"><span data-stu-id="51c17-106">![BizTalk Server message process](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span></span>  
  
 <span data-ttu-id="51c17-107">**BizTalk Server 消息进程**</span><span class="sxs-lookup"><span data-stu-id="51c17-107">**The BizTalk Server message process**</span></span>  
  
 <span data-ttu-id="51c17-108">以下为有关此方案的一些实际信息：</span><span class="sxs-lookup"><span data-stu-id="51c17-108">Here are some of the facts concerning this scenario:</span></span>  
  
-   <span data-ttu-id="51c17-109">消息大小为 5 的 K。</span><span class="sxs-lookup"><span data-stu-id="51c17-109">The message size is 5K.</span></span>  
  
-   <span data-ttu-id="51c17-110">我们不提升任何属性。</span><span class="sxs-lookup"><span data-stu-id="51c17-110">We are not promoting any properties.</span></span>  
  
-   <span data-ttu-id="51c17-111">一年内接收的消息数为 350 万条。</span><span class="sxs-lookup"><span data-stu-id="51c17-111">The number of messages we receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="51c17-112">已打开对所有事件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="51c17-112">Tracking is turned on for all events.</span></span> <span data-ttu-id="51c17-113">此方案包含以下六个事件：</span><span class="sxs-lookup"><span data-stu-id="51c17-113">There are six events in this scenario:</span></span>  
  
    -   <span data-ttu-id="51c17-114">收到消息 M0</span><span class="sxs-lookup"><span data-stu-id="51c17-114">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="51c17-115">接收端口从消息 M1 的输出</span><span class="sxs-lookup"><span data-stu-id="51c17-115">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="51c17-116">通过业务流程接收消息 M1</span><span class="sxs-lookup"><span data-stu-id="51c17-116">Receipt of message M1 by the orchestration</span></span>  
  
    -   <span data-ttu-id="51c17-117">从业务流程输出消息 M2</span><span class="sxs-lookup"><span data-stu-id="51c17-117">Output of message M2 from the orchestration</span></span>  
  
    -   <span data-ttu-id="51c17-118">通过发送端口接收消息 M2</span><span class="sxs-lookup"><span data-stu-id="51c17-118">Receipt of message M2 by the send port</span></span>  
  
    -   <span data-ttu-id="51c17-119">通过发送管道输出消息 M3</span><span class="sxs-lookup"><span data-stu-id="51c17-119">Output of message M3 by the send pipeline</span></span>  
  
-   <span data-ttu-id="51c17-120">此方案中创建了其他三个消息。</span><span class="sxs-lookup"><span data-stu-id="51c17-120">Three additional messages are created in this scenario.</span></span> <span data-ttu-id="51c17-121">消息 M0 是传入消息，并因此不由 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="51c17-121">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="51c17-122">消息 M1 是从接收端口输出的消息，M2 是从业务流程输出的消息，M3 是从传输端口输出的消息。</span><span class="sxs-lookup"><span data-stu-id="51c17-122">Message M1 is the output message from the receive port, M2 is the output message from the orchestration, and M3 is the output message from the transmit port.</span></span>  
  
 <span data-ttu-id="51c17-123">将此信息应用于该公式会得到以下结果：</span><span class="sxs-lookup"><span data-stu-id="51c17-123">Applying this information to the formula gives the following result:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a><span data-ttu-id="51c17-124">业务流程中具有单个升级属性的消息</span><span class="sxs-lookup"><span data-stu-id="51c17-124">Messages in orchestrations with a single promoted property</span></span>  
 <span data-ttu-id="51c17-125">在此方案中，请按照之前示例中所执行的操作来升级单个字段。</span><span class="sxs-lookup"><span data-stu-id="51c17-125">Now let's promote a single field in this scenario, as in the earlier example.</span></span> <span data-ttu-id="51c17-126">升级的属性大小约为 10 字节。</span><span class="sxs-lookup"><span data-stu-id="51c17-126">The promoted property is approximately 10 bytes in size.</span></span> <span data-ttu-id="51c17-127">公式现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="51c17-127">The equation now looks like this:</span></span>  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 <span data-ttu-id="51c17-128">如果需要另外升级一个大小为 20 字节的属性，则公式将如下所示：</span><span class="sxs-lookup"><span data-stu-id="51c17-128">If you need to promote an additional property that is 20 bytes in size, the formula now looks like this:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a><span data-ttu-id="51c17-129">业务流程中已激活消息正文跟踪的消息</span><span class="sxs-lookup"><span data-stu-id="51c17-129">Messages in orchestrations with message body tracking activated</span></span>  
 <span data-ttu-id="51c17-130">若要允许消息跟踪，则所需额外空间的计算结果应与之前方案中的结果相同，或为每年 50.1 GB。</span><span class="sxs-lookup"><span data-stu-id="51c17-130">If you want to accommodate message tracking, the result from calculating the additional space needed is identical to the result in the earlier scenario, or 50.1 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c17-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51c17-131">See Also</span></span>  
 <span data-ttu-id="51c17-132">[使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="51c17-132">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="51c17-133">[大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="51c17-133">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="51c17-134">[方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="51c17-134">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="51c17-135">[方案 4： 调整跟踪数据库的所有消息](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="51c17-135">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="51c17-136">方案 3： 调整跟踪数据库的消息发送到通讯组列表</span><span class="sxs-lookup"><span data-stu-id="51c17-136">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)