---
title: "与 BizTalk Server 相关的属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], properties
- CompleteMessage property [MQSeries adapters]
- SSOAffiliateApplication property [MQSeries adapters]
- Ordered property [MQSeries adapters]
- TransactionSupported property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- SegmentationAllowed property [MQSeries adapters]
- DynamicReceive property [MQSeries adapters]
- MQSeries adapters, properties
- DataConversion property [MQSeries adapters]
ms.assetid: c27d7f9c-8198-4624-9952-054ba8ea1c7c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f729e4ab359471e002029efc04c0c8ad21e0d99b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="properties-related-to-biztalk-server"></a><span data-ttu-id="07b40-102">与 BizTalk Server 相关的属性</span><span class="sxs-lookup"><span data-stu-id="07b40-102">Properties Related to BizTalk Server</span></span>
<span data-ttu-id="07b40-103">MQSeries 适配器可以为某些不直接与 MQSeries 相关但仍在应用程序中有用的上下文属性赋值。</span><span class="sxs-lookup"><span data-stu-id="07b40-103">The MQSeries adapter assigns values to some context properties that are not directly related to MQSeries but are still useful in your applications.</span></span>  
  
 <span data-ttu-id="07b40-104">所有属性在发送和接收除期间都接收值**BizTalk_CorrelationID**。</span><span class="sxs-lookup"><span data-stu-id="07b40-104">All the properties receive values during sending and receiving except for **BizTalk_CorrelationID**.</span></span> <span data-ttu-id="07b40-105">**BizTalk_CorrelationID**属性具有仅在接收过程的值。</span><span class="sxs-lookup"><span data-stu-id="07b40-105">The **BizTalk_CorrelationID** property has a value only during receiving.</span></span>  
  
|<span data-ttu-id="07b40-106">Name</span><span class="sxs-lookup"><span data-stu-id="07b40-106">Name</span></span>|<span data-ttu-id="07b40-107">类型</span><span class="sxs-lookup"><span data-stu-id="07b40-107">Type</span></span>|<span data-ttu-id="07b40-108">Description</span><span class="sxs-lookup"><span data-stu-id="07b40-108">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="07b40-109">**BizTalk_CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="07b40-109">**BizTalk_CorrelationID**</span></span>|<span data-ttu-id="07b40-110">string</span><span class="sxs-lookup"><span data-stu-id="07b40-110">string</span></span>|<span data-ttu-id="07b40-111">使用此属性可使 MQSeries 服务器生成用于消息的相关标识符。</span><span class="sxs-lookup"><span data-stu-id="07b40-111">Use this property to have the MQSeries server generate a correlation identifier for use with the message.</span></span><br /><br /> <span data-ttu-id="07b40-112">有关详细信息，请参阅[关联消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。</span><span class="sxs-lookup"><span data-stu-id="07b40-112">For more information, see [Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md).</span></span>|  
|<span data-ttu-id="07b40-113">**数据转换**</span><span class="sxs-lookup"><span data-stu-id="07b40-113">**DataConversion**</span></span>|<span data-ttu-id="07b40-114">string</span><span class="sxs-lookup"><span data-stu-id="07b40-114">string</span></span>|<span data-ttu-id="07b40-115">将消息转换为 MQSeries Server for Windows 的 ANSI 代码页。</span><span class="sxs-lookup"><span data-stu-id="07b40-115">Converts the message to the ANSI code page of MQSeries Server for Windows.</span></span> <span data-ttu-id="07b40-116">在发送时，如果消息格式不是 MQFMT_STRING，则不会进行转换。</span><span class="sxs-lookup"><span data-stu-id="07b40-116">On Send, if the message format is not MQFMT_STRING, there is no conversion.</span></span><br /><br /> <span data-ttu-id="07b40-117">选择**是**来执行从 Unicode 此转换为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="07b40-117">Select **Yes** to perform this conversion from Unicode to ANSI.</span></span><br /><br /> <span data-ttu-id="07b40-118">**默认值：**否</span><span class="sxs-lookup"><span data-stu-id="07b40-118">**Default:** No</span></span>|  
|<span data-ttu-id="07b40-119">**排序**</span><span class="sxs-lookup"><span data-stu-id="07b40-119">**Ordered**</span></span>|<span data-ttu-id="07b40-120">string</span><span class="sxs-lookup"><span data-stu-id="07b40-120">string</span></span>|<span data-ttu-id="07b40-121">将 MQSeries 设置为从 MQSeries 队列接收消息或向其发送消息时保持消息的顺序。</span><span class="sxs-lookup"><span data-stu-id="07b40-121">Sets MQSeries to maintain the order of the messages as they are received from or sent to the MQSeries queue.</span></span><br /><br /> <span data-ttu-id="07b40-122">该属性对于接收和发送具有不同的值的集合。</span><span class="sxs-lookup"><span data-stu-id="07b40-122">The property has different sets of values for sending and receiving.</span></span> <span data-ttu-id="07b40-123">有关值的信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b40-123">For information about the values, see.</span></span> <span data-ttu-id="07b40-124">[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="07b40-124">[How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span><br /><br /> <span data-ttu-id="07b40-125">**默认值：**否</span><span class="sxs-lookup"><span data-stu-id="07b40-125">**Default:** No</span></span>|  
|<span data-ttu-id="07b40-126">**SegmentationAllowed**</span><span class="sxs-lookup"><span data-stu-id="07b40-126">**SegmentationAllowed**</span></span>|<span data-ttu-id="07b40-127">string</span><span class="sxs-lookup"><span data-stu-id="07b40-127">string</span></span>|<span data-ttu-id="07b40-128">将 MQSeries 设置为组装已分段的消息，或设置为按原样获取消息。</span><span class="sxs-lookup"><span data-stu-id="07b40-128">Sets MQSeries to assemble segmented messages or to get the message as is.</span></span> <span data-ttu-id="07b40-129">该属性对于接收和发送具有不同的值的集合。</span><span class="sxs-lookup"><span data-stu-id="07b40-129">The property has different sets of values for sending and receiving.</span></span><br /><br /> <span data-ttu-id="07b40-130">在接收时，使用**No Action**从 MQSeries 队列读取消息，而不启用分段; 使用**完整的消息**能够 MQSeries 之前将它们传递给上装配分段的消息适配器。</span><span class="sxs-lookup"><span data-stu-id="07b40-130">When receiving, use **No Action** to read messages from the MQSeries queue without enabling segmentation; use **Complete Message** to have MQSeries assemble segmented messages before passing them on to the adapter.</span></span><br /><br /> <span data-ttu-id="07b40-131">**默认值：**任何操作</span><span class="sxs-lookup"><span data-stu-id="07b40-131">**Default:** No Action</span></span><br /><br /> <span data-ttu-id="07b40-132">发送时，选择**是**来获得 MQSeries 分段的消息放入队列。</span><span class="sxs-lookup"><span data-stu-id="07b40-132">When sending, select **Yes**, to have MQSeries put segmented messages in the queue.</span></span><br /><br /> <span data-ttu-id="07b40-133">**默认值：**否</span><span class="sxs-lookup"><span data-stu-id="07b40-133">**Default:** No</span></span>|  
|<span data-ttu-id="07b40-134">**SSOAffiliateApplication**</span><span class="sxs-lookup"><span data-stu-id="07b40-134">**SSOAffiliateApplication**</span></span>|<span data-ttu-id="07b40-135">string</span><span class="sxs-lookup"><span data-stu-id="07b40-135">string</span></span>|<span data-ttu-id="07b40-136">设置单一登录 (SSO) 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="07b40-136">Sets the Single Sign-On (SSO) affiliate application.</span></span> <span data-ttu-id="07b40-137">你使用的用户 ID 和密码的 SSO **MQMD_UserIdentifier**，和**MQIIH_Authenticator** (或**MQCIH_Authenticator**) 属性分别。</span><span class="sxs-lookup"><span data-stu-id="07b40-137">You use the user ID and password from SSO for the **MQMD_UserIdentifier**, and the **MQIIH_Authenticator** (or **MQCIH_Authenticator**) property respectively.</span></span><br /><br /> <span data-ttu-id="07b40-138">仅在发送消息时使用。</span><span class="sxs-lookup"><span data-stu-id="07b40-138">Used only when sending messages.</span></span><br /><br /> <span data-ttu-id="07b40-139">**默认值：**空白</span><span class="sxs-lookup"><span data-stu-id="07b40-139">**Default:** Blank</span></span>|  
|<span data-ttu-id="07b40-140">**CompleteMessage**</span><span class="sxs-lookup"><span data-stu-id="07b40-140">**CompleteMessage**</span></span>|<span data-ttu-id="07b40-141">string</span><span class="sxs-lookup"><span data-stu-id="07b40-141">string</span></span>|<span data-ttu-id="07b40-142">指定在从队列中检索已分段的消息时是否检索“完整消息”。</span><span class="sxs-lookup"><span data-stu-id="07b40-142">Designates whether to retrieve "complete message" when retrieving segmented messages from a queue.</span></span><br /><br /> <span data-ttu-id="07b40-143">将其设置为**是**若要检索的"完成消息"的分段队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="07b40-143">Set this to **Yes** to retrieve the "complete message" for segmented messages in a queue.</span></span><br /><br /> <span data-ttu-id="07b40-144">**默认值：**否</span><span class="sxs-lookup"><span data-stu-id="07b40-144">**Default:** No</span></span>|  
|<span data-ttu-id="07b40-145">**DynamicReceive**</span><span class="sxs-lookup"><span data-stu-id="07b40-145">**DynamicReceive**</span></span>|<span data-ttu-id="07b40-146">string</span><span class="sxs-lookup"><span data-stu-id="07b40-146">string</span></span>|<span data-ttu-id="07b40-147">指定是否从队列中动态地检索消息。</span><span class="sxs-lookup"><span data-stu-id="07b40-147">Designates whether to receive messages from a queue dynamically.</span></span><br /><br /> <span data-ttu-id="07b40-148">将其设置为**是**在动态从队列接收消息时。</span><span class="sxs-lookup"><span data-stu-id="07b40-148">Set this to **Yes** when receiving messages from a queue dynamically.</span></span> <span data-ttu-id="07b40-149">此功能与要求响应发送端口结合使用。</span><span class="sxs-lookup"><span data-stu-id="07b40-149">This feature is used in conjunction with a solicit-response send port.</span></span><br /><br /> <span data-ttu-id="07b40-150">如果指定匹配选项（MessageID、CorrelationID 或 GroupID），则仅检索与匹配条件相关的消息。</span><span class="sxs-lookup"><span data-stu-id="07b40-150">If you specify match options (MessageID, CorrelationID, or GroupID), then only messages that correlate to the match criteria will be retrieved.</span></span>|  
|<span data-ttu-id="07b40-151">**TransactionSupported**</span><span class="sxs-lookup"><span data-stu-id="07b40-151">**TransactionSupported**</span></span>|<span data-ttu-id="07b40-152">string</span><span class="sxs-lookup"><span data-stu-id="07b40-152">string</span></span>|<span data-ttu-id="07b40-153">此适配器将在 BizTalk Server 和 MQSeries 服务器之间开始 Microsoft 分布式事务处理协调器 (DTC) 事务。</span><span class="sxs-lookup"><span data-stu-id="07b40-153">The adapter begins a Microsoft Distributed Transaction Coordinator (DTC) transaction between BizTalk Server and MQSeries Server.</span></span> <span data-ttu-id="07b40-154">当设置为**否**，就不能保证的消息传递。</span><span class="sxs-lookup"><span data-stu-id="07b40-154">When set to **No**, there is no guarantee of message delivery.</span></span><br /><br /> <span data-ttu-id="07b40-155">**默认值：**是</span><span class="sxs-lookup"><span data-stu-id="07b40-155">**Default:** Yes</span></span>|  
|<span data-ttu-id="07b40-156">**WaitInterval**</span><span class="sxs-lookup"><span data-stu-id="07b40-156">**WaitInterval**</span></span>|<span data-ttu-id="07b40-157">string</span><span class="sxs-lookup"><span data-stu-id="07b40-157">string</span></span>|<span data-ttu-id="07b40-158">指定 MQ 系统等待适当消息到达的大致时间（以秒表示）。</span><span class="sxs-lookup"><span data-stu-id="07b40-158">Specifies the approximate time, expressed in seconds, that the MQ system waits for a suitable message to arrive.</span></span> <span data-ttu-id="07b40-159">如果在此时间内没有适当的消息到达，则该调用失败。</span><span class="sxs-lookup"><span data-stu-id="07b40-159">If no suitable message has arrived in this time, the call fails.</span></span> <span data-ttu-id="07b40-160">**注意：**这可以在一个业务流程中设置。</span><span class="sxs-lookup"><span data-stu-id="07b40-160">**Note:**  This can be set within an orchestration only.</span></span> <br /><br /> <span data-ttu-id="07b40-161">**默认值：** 3</span><span class="sxs-lookup"><span data-stu-id="07b40-161">**Default:** 3</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07b40-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07b40-162">See Also</span></span>  
 <span data-ttu-id="07b40-163">[MQSeries 适配器属性](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="07b40-163">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="07b40-164">[数据类型转换的属性](../core/data-type-conversion-of-properties.md) </span><span class="sxs-lookup"><span data-stu-id="07b40-164">[Data Type Conversion of Properties](../core/data-type-conversion-of-properties.md) </span></span>  
 [<span data-ttu-id="07b40-165">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="07b40-165">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)