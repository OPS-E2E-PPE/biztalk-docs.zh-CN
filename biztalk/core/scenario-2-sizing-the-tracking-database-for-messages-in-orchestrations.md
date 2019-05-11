---
title: 应用场景 2：为业务流程中消息调整跟踪数据库的大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e3a62df0431611c294a123835d7cc2faddca474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308611"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a><span data-ttu-id="54ec4-102">应用场景 2：为业务流程中消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="54ec4-102">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>
<span data-ttu-id="54ec4-103">让我们看一下示例，其中包括业务流程。</span><span class="sxs-lookup"><span data-stu-id="54ec4-103">Let's look at an example that includes an orchestration.</span></span> <span data-ttu-id="54ec4-104">下图显示了整个业务流程。</span><span class="sxs-lookup"><span data-stu-id="54ec4-104">The following figure displays the entire business process.</span></span> <span data-ttu-id="54ec4-105">在此方案中，一条消息到 BizTalk Server，通过业务流程发送、 更改在业务流程内并且然后发出通过发送端口。</span><span class="sxs-lookup"><span data-stu-id="54ec4-105">In this scenario, a message comes into BizTalk Server, is sent through an orchestration, is changed within the orchestration, and is then sent out through a send port.</span></span>  
  
 <span data-ttu-id="54ec4-106">![BizTalk Server 消息进程](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span><span class="sxs-lookup"><span data-stu-id="54ec4-106">![BizTalk Server message process](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span></span>  
  
 <span data-ttu-id="54ec4-107">**BizTalk Server 消息处理**</span><span class="sxs-lookup"><span data-stu-id="54ec4-107">**The BizTalk Server message process**</span></span>  
  
 <span data-ttu-id="54ec4-108">下面是一些有关此方案中的事实：</span><span class="sxs-lookup"><span data-stu-id="54ec4-108">Here are some of the facts concerning this scenario:</span></span>  
  
- <span data-ttu-id="54ec4-109">消息大小为 5 个 K。</span><span class="sxs-lookup"><span data-stu-id="54ec4-109">The message size is 5K.</span></span>  
  
- <span data-ttu-id="54ec4-110">我们不会升级任何属性。</span><span class="sxs-lookup"><span data-stu-id="54ec4-110">We are not promoting any properties.</span></span>  
  
- <span data-ttu-id="54ec4-111">我们在一年中收到的消息数为 350 万条。</span><span class="sxs-lookup"><span data-stu-id="54ec4-111">The number of messages we receive in a year is 3.5 million.</span></span>  
  
- <span data-ttu-id="54ec4-112">跟踪被打开的所有事件。</span><span class="sxs-lookup"><span data-stu-id="54ec4-112">Tracking is turned on for all events.</span></span> <span data-ttu-id="54ec4-113">在此方案中有六个事件：</span><span class="sxs-lookup"><span data-stu-id="54ec4-113">There are six events in this scenario:</span></span>  
  
  -   <span data-ttu-id="54ec4-114">接收消息 M0</span><span class="sxs-lookup"><span data-stu-id="54ec4-114">Receipt of message M0</span></span>  
  
  -   <span data-ttu-id="54ec4-115">输出消息 M1 从接收端口</span><span class="sxs-lookup"><span data-stu-id="54ec4-115">Output of message M1 from the receive port</span></span>  
  
  -   <span data-ttu-id="54ec4-116">接收消息 M1 由业务流程</span><span class="sxs-lookup"><span data-stu-id="54ec4-116">Receipt of message M1 by the orchestration</span></span>  
  
  -   <span data-ttu-id="54ec4-117">输出消息 M2 从业务流程</span><span class="sxs-lookup"><span data-stu-id="54ec4-117">Output of message M2 from the orchestration</span></span>  
  
  -   <span data-ttu-id="54ec4-118">通过接收消息 M2 发送端口</span><span class="sxs-lookup"><span data-stu-id="54ec4-118">Receipt of message M2 by the send port</span></span>  
  
  -   <span data-ttu-id="54ec4-119">输出消息 M3 的发送管道</span><span class="sxs-lookup"><span data-stu-id="54ec4-119">Output of message M3 by the send pipeline</span></span>  
  
- <span data-ttu-id="54ec4-120">在此方案中创建其他三个消息。</span><span class="sxs-lookup"><span data-stu-id="54ec4-120">Three additional messages are created in this scenario.</span></span> <span data-ttu-id="54ec4-121">消息 M0 是传入的消息，因此不创建由 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="54ec4-121">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="54ec4-122">消息 M1 是输出消息从接收端口，M2 是从业务流程，输出消息，M3 是从传输端口输出消息。</span><span class="sxs-lookup"><span data-stu-id="54ec4-122">Message M1 is the output message from the receive port, M2 is the output message from the orchestration, and M3 is the output message from the transmit port.</span></span>  
  
  <span data-ttu-id="54ec4-123">将此信息应用到该公式会得到以下结果：</span><span class="sxs-lookup"><span data-stu-id="54ec4-123">Applying this information to the formula gives the following result:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a><span data-ttu-id="54ec4-124">业务流程中具有单个升级属性的消息</span><span class="sxs-lookup"><span data-stu-id="54ec4-124">Messages in orchestrations with a single promoted property</span></span>  
 <span data-ttu-id="54ec4-125">现在让我们来升级单个字段在此方案中，如前面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="54ec4-125">Now let's promote a single field in this scenario, as in the earlier example.</span></span> <span data-ttu-id="54ec4-126">升级的属性是约为 10 字节的大小。</span><span class="sxs-lookup"><span data-stu-id="54ec4-126">The promoted property is approximately 10 bytes in size.</span></span> <span data-ttu-id="54ec4-127">公式现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="54ec4-127">The equation now looks like this:</span></span>  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 <span data-ttu-id="54ec4-128">如果你需要升级的其他属性，为 20 字节的大小，该公式现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="54ec4-128">If you need to promote an additional property that is 20 bytes in size, the formula now looks like this:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a><span data-ttu-id="54ec4-129">与消息正文跟踪的业务流程中的消息激活</span><span class="sxs-lookup"><span data-stu-id="54ec4-129">Messages in orchestrations with message body tracking activated</span></span>  
 <span data-ttu-id="54ec4-130">如果你想要允许消息跟踪，所需的额外空间的计算结果等于结果中前面的方案或 50.1 GB 每年。</span><span class="sxs-lookup"><span data-stu-id="54ec4-130">If you want to accommodate message tracking, the result from calculating the additional space needed is identical to the result in the earlier scenario, or 50.1 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ec4-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="54ec4-131">See Also</span></span>  
 <span data-ttu-id="54ec4-132">[使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="54ec4-132">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="54ec4-133">[调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="54ec4-133">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="54ec4-134">[方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="54ec4-134">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="54ec4-135">[方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="54ec4-135">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="54ec4-136">方案 3:为发送到分发列表的消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="54ec4-136">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)