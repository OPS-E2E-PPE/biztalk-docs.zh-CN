---
title: 使用消息变量调整跟踪数据库的大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message variables [Tracking database], CMsgs
- message variables [Tracking database], Events
- message variables [Tracking database], Properties
- Tracking database, database size
- message variables [Tracking database], Nserv
- message variables [Tracking database], Msgs
- message variables [Tracking database], PropSize
- message variables [Tracking database]
- message variables [Tracking database], MsgSize
- message variables [Tracking database], MsgNum
- Tracking database, messages
ms.assetid: 2d31ae25-3d16-4002-b5a5-dca25e764ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ef731d12155ae20d7f78aaaf4a5f990b76affba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985678"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a><span data-ttu-id="08c94-102">使用消息变量调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="08c94-102">Using Message Variables to Size the Tracking Database</span></span>
<span data-ttu-id="08c94-103">在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，可以使用许多变量来确定 BizTalk 跟踪 (BizTalkDTADb) 数据库在给定时间段后的大小。</span><span class="sxs-lookup"><span data-stu-id="08c94-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use a number of variables to determine how large the BizTalk Tracking (BizTalkDTADb) database will become over a given period of time.</span></span> <span data-ttu-id="08c94-104">这些变量包括：</span><span class="sxs-lookup"><span data-stu-id="08c94-104">These variables are:</span></span>  
  
- <span data-ttu-id="08c94-105">使用的管道数</span><span class="sxs-lookup"><span data-stu-id="08c94-105">Number of pipelines used</span></span>  
  
- <span data-ttu-id="08c94-106">涉及的业务流程数</span><span class="sxs-lookup"><span data-stu-id="08c94-106">Number of orchestrations involved</span></span>  
  
- <span data-ttu-id="08c94-107">生成的事件数</span><span class="sxs-lookup"><span data-stu-id="08c94-107">Number of events generated</span></span>  
  
- <span data-ttu-id="08c94-108">跟踪的消息属性数</span><span class="sxs-lookup"><span data-stu-id="08c94-108">Number of message properties tracked</span></span>  
  
- <span data-ttu-id="08c94-109">创建的其他消息数</span><span class="sxs-lookup"><span data-stu-id="08c94-109">Number of additional messages created</span></span>  
  
- <span data-ttu-id="08c94-110">在指定时间范围内估计接收的消息数</span><span class="sxs-lookup"><span data-stu-id="08c94-110">Estimated number of messages received in the specified timeframe</span></span>  
  
  <span data-ttu-id="08c94-111">尽管用于估算 BizTalk 跟踪数据库大小的公式简单易懂，但您必须将其应用于每个使用 BizTalk Server 实现的传入和传出消息进程。</span><span class="sxs-lookup"><span data-stu-id="08c94-111">While the equation you use to estimate the size of the BizTalk Tracking database is straightforward, you must apply it to each incoming and outgoing message process that uses the BizTalk Server implementation.</span></span> <span data-ttu-id="08c94-112">换而言之，您需要将此公式应用于每个不同的消息方案，然后对其结果进行合计以获得最终估算的数据库大小。</span><span class="sxs-lookup"><span data-stu-id="08c94-112">In other words, you will need to apply this equation for every distinct message scenario and then add up the results to obtain the final estimated database size.</span></span> <span data-ttu-id="08c94-113">在本文档中我们将介绍两个方案。</span><span class="sxs-lookup"><span data-stu-id="08c94-113">In this document we will look at two scenarios.</span></span> <span data-ttu-id="08c94-114">这两个方案分别是：</span><span class="sxs-lookup"><span data-stu-id="08c94-114">The scenarios are:</span></span>  
  
1. <span data-ttu-id="08c94-115">接收消息，转换该消息，然后发送生成的消息。</span><span class="sxs-lookup"><span data-stu-id="08c94-115">Receiving a message, transforming the message, and then sending the resulting message</span></span>  
  
2. <span data-ttu-id="08c94-116">接收消息，使用该消息运行业务流程，然后发送生成的消息。</span><span class="sxs-lookup"><span data-stu-id="08c94-116">Receiving a message, running a business process using the message, and then sending the resulting message.</span></span>  
  
   <span data-ttu-id="08c94-117">这两个方案可能出现在一个 BizTalk Server 安装中，而每个方案会生成不同数量的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="08c94-117">Both of these scenarios may be present in a BizTalk Server installation, and each scenario generates a different amount of tracking data.</span></span> <span data-ttu-id="08c94-118">为该 BizTalk Server 安装生成的全部跟踪数据就是这两个方案生成的总数据量。</span><span class="sxs-lookup"><span data-stu-id="08c94-118">The total tracking data generated for the BizTalk Server installation is the sum of all the scenarios.</span></span>  
  
   <span data-ttu-id="08c94-119">公式中使用的一些变量如下所示：</span><span class="sxs-lookup"><span data-stu-id="08c94-119">The following are some variables used in the equation:</span></span>  
  
|<span data-ttu-id="08c94-120">变量</span><span class="sxs-lookup"><span data-stu-id="08c94-120">Variable</span></span>|<span data-ttu-id="08c94-121">Description</span><span class="sxs-lookup"><span data-stu-id="08c94-121">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="08c94-122">**Nserv**</span><span class="sxs-lookup"><span data-stu-id="08c94-122">**Nserv**</span></span>|<span data-ttu-id="08c94-123">服务数（管道数 + 业务流程数）</span><span class="sxs-lookup"><span data-stu-id="08c94-123">Number of services (number of pipelines + number of orchestrations)</span></span>|  
|<span data-ttu-id="08c94-124">**事件**</span><span class="sxs-lookup"><span data-stu-id="08c94-124">**Events**</span></span>|<span data-ttu-id="08c94-125">生成的消息事件数</span><span class="sxs-lookup"><span data-stu-id="08c94-125">Number of generated message events</span></span>|  
|<span data-ttu-id="08c94-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="08c94-126">**Properties**</span></span>|<span data-ttu-id="08c94-127">跟踪的消息属性数</span><span class="sxs-lookup"><span data-stu-id="08c94-127">Number of message properties tracked</span></span>|  
|<span data-ttu-id="08c94-128">**PropSize**</span><span class="sxs-lookup"><span data-stu-id="08c94-128">**PropSize**</span></span>|<span data-ttu-id="08c94-129">升级属性（字段）的大小（字节）</span><span class="sxs-lookup"><span data-stu-id="08c94-129">Size (in bytes) of the promoted property (field)</span></span>|  
|<span data-ttu-id="08c94-130">**CMsgs**</span><span class="sxs-lookup"><span data-stu-id="08c94-130">**CMsgs**</span></span>|<span data-ttu-id="08c94-131">为每个传入消息创建的其他消息数</span><span class="sxs-lookup"><span data-stu-id="08c94-131">Number of additional messages created per incoming message</span></span>|  
|<span data-ttu-id="08c94-132">**消息数**</span><span class="sxs-lookup"><span data-stu-id="08c94-132">**Msgs**</span></span>|<span data-ttu-id="08c94-133">给定时间段内估计传入的消息数</span><span class="sxs-lookup"><span data-stu-id="08c94-133">Number of estimated incoming messages in a given time period</span></span>|  
|<span data-ttu-id="08c94-134">**MsgSize**</span><span class="sxs-lookup"><span data-stu-id="08c94-134">**MsgSize**</span></span>|<span data-ttu-id="08c94-135">消息大小</span><span class="sxs-lookup"><span data-stu-id="08c94-135">Message size</span></span>|  
|<span data-ttu-id="08c94-136">**消息号**</span><span class="sxs-lookup"><span data-stu-id="08c94-136">**MsgNum**</span></span>|<span data-ttu-id="08c94-137">为每个传入消息跟踪的消息数</span><span class="sxs-lookup"><span data-stu-id="08c94-137">Number of messages tracked for each incoming message</span></span>|  
  
 <span data-ttu-id="08c94-138">该公式如下所示：</span><span class="sxs-lookup"><span data-stu-id="08c94-138">The equation is as follows:</span></span>  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 <span data-ttu-id="08c94-139">此公式仅计算由消息生成的跟踪数据，不包括为业务流程调试器生成的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="08c94-139">This equation calculates only the tracking data generated by the messages and does not include the tracking data generated for the Orchestration Debugger.</span></span> <span data-ttu-id="08c94-140">必须将此公式应用于所有消息进程才能估算 BizTalk 跟踪数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="08c94-140">You must apply this formula to each message process to estimate the size of the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c94-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="08c94-141">See Also</span></span>  
 <span data-ttu-id="08c94-142">[调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="08c94-142">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="08c94-143">[方案 1： 调整简单 BizTalk 消息的大小跟踪数据库](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="08c94-143">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="08c94-144">[方案 2： 业务流程中消息调整跟踪数据库](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="08c94-144">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="08c94-145">[方案 4： 为所有消息调整跟踪数据库](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="08c94-145">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="08c94-146">方案 3：为发送到通讯组列表的消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="08c94-146">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)