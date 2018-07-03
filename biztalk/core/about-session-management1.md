---
title: 有关会话 Management1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1848619-d97a-4f1e-ba94-59861bd7aedf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e35feaa691833c570217ded76e95b1d79a377f4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994598"
---
# <a name="about-session-management"></a><span data-ttu-id="13ae4-102">关于会话管理</span><span class="sxs-lookup"><span data-stu-id="13ae4-102">About Session Management</span></span>
<span data-ttu-id="13ae4-103">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器创建一个连接会话，以发送对 JD Edwards OneWorld 服务器的调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-103">The Microsoft BizTalk Adapter for JD Edwards OneWorld creates a connection session to send a call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="13ae4-104">调用终止时，会话会放在池中以供后续调用重用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="13ae4-105">适配器会创建多个连接会话，从而处理对 JD Edwards OneWorld 服务器的并发调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="13ae4-106">池会定期进行清理，从而删除不再需要的会话。</span><span class="sxs-lookup"><span data-stu-id="13ae4-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="13ae4-107">适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供两个消息上下文属性，以控制何时必须在同一会话中进行调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-107">The Microsoft BizTalk Adapter for JD Edwards OneWorld provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="13ae4-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="13ae4-108">Name</span></span>|<span data-ttu-id="13ae4-109">类型</span><span class="sxs-lookup"><span data-stu-id="13ae4-109">Type</span></span>|<span data-ttu-id="13ae4-110">，则“默认”</span><span class="sxs-lookup"><span data-stu-id="13ae4-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="13ae4-111">JDE.SessionID</span><span class="sxs-lookup"><span data-stu-id="13ae4-111">JDE.SessionID</span></span>|<span data-ttu-id="13ae4-112">smallint</span><span class="sxs-lookup"><span data-stu-id="13ae4-112">Int</span></span>|<span data-ttu-id="13ae4-113">0</span><span class="sxs-lookup"><span data-stu-id="13ae4-113">0</span></span>|  
|<span data-ttu-id="13ae4-114">JDE.ReserveSession</span><span class="sxs-lookup"><span data-stu-id="13ae4-114">JDE.ReserveSession</span></span>|<span data-ttu-id="13ae4-115">boolean</span><span class="sxs-lookup"><span data-stu-id="13ae4-115">boolean</span></span>|<span data-ttu-id="13ae4-116">false</span><span class="sxs-lookup"><span data-stu-id="13ae4-116">false</span></span>|  
  
 <span data-ttu-id="13ae4-117">如果业务功能要求对 JD Edwards OneWorld 服务器进行单一调用，则不必进行会话管理。</span><span class="sxs-lookup"><span data-stu-id="13ae4-117">Session management is unnecessary if the business function requires a single call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="13ae4-118">适配器可以选择任何可用的会话，并且会话仍可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="13ae4-119">在这种情况下，由于默认值适当，因此可以忽略消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="13ae4-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="13ae4-120">某些 JD Edwards OneWorld 功能要求对 JD Edwards OneWorld 服务器进行多次调用；例如，创建 SalesOrder 时。</span><span class="sxs-lookup"><span data-stu-id="13ae4-120">Some JD Edwards OneWorld functionality requires multiple calls to the JD Edwards OneWorld server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="13ae4-121">首次调用 BeginDoc 会创建一个空 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="13ae4-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="13ae4-122">随后每次调用 EditLine 会向 SalesOrder 添加一个行项目。</span><span class="sxs-lookup"><span data-stu-id="13ae4-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="13ae4-123">最后调用 EndDoc 将关闭 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="13ae4-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="13ae4-124">若要成功执行此操作，对单个 SalesOrder 的所有调用都必须在同一会话中发送。</span><span class="sxs-lookup"><span data-stu-id="13ae4-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="13ae4-125">为此，请为消息上下文属性赋值以指示适配器如何处理会话。</span><span class="sxs-lookup"><span data-stu-id="13ae4-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="13ae4-126">以 SalesOrder 为例，以下是将赋给消息上下文属性以处理 JD OneWorld 会话的值：</span><span class="sxs-lookup"><span data-stu-id="13ae4-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD OneWorld session:</span></span>  
  
|<span data-ttu-id="13ae4-127">函数</span><span class="sxs-lookup"><span data-stu-id="13ae4-127">Function</span></span>|<span data-ttu-id="13ae4-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="13ae4-128">SessionID</span></span>|<span data-ttu-id="13ae4-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="13ae4-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="13ae4-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="13ae4-130">BeginDoc</span></span>|<span data-ttu-id="13ae4-131">0</span><span class="sxs-lookup"><span data-stu-id="13ae4-131">0</span></span>|<span data-ttu-id="13ae4-132">true</span><span class="sxs-lookup"><span data-stu-id="13ae4-132">true</span></span>|  
|<span data-ttu-id="13ae4-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="13ae4-133">EditLine</span></span>|<span data-ttu-id="13ae4-134">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="13ae4-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="13ae4-135">true</span><span class="sxs-lookup"><span data-stu-id="13ae4-135">true</span></span>|  
|<span data-ttu-id="13ae4-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="13ae4-136">EditLine</span></span>|<span data-ttu-id="13ae4-137">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="13ae4-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="13ae4-138">true</span><span class="sxs-lookup"><span data-stu-id="13ae4-138">true</span></span>|  
|<span data-ttu-id="13ae4-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="13ae4-139">EndDoc</span></span>|<span data-ttu-id="13ae4-140">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="13ae4-140">Copied from BeginDoc reply</span></span>|<span data-ttu-id="13ae4-141">false</span><span class="sxs-lookup"><span data-stu-id="13ae4-141">false</span></span>|  
  
- <span data-ttu-id="13ae4-142">首次调用时，适配器可以随意选择任何可用的会话（因为 SessionID 为 0）。</span><span class="sxs-lookup"><span data-stu-id="13ae4-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
- <span data-ttu-id="13ae4-143">适配器会返回已在 BeginDoc 回复中使用的 SessionID。</span><span class="sxs-lookup"><span data-stu-id="13ae4-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
- <span data-ttu-id="13ae4-144">ReserveSession 属性会指示适配器为随后显式请求此会话的调用保留此会话。</span><span class="sxs-lookup"><span data-stu-id="13ae4-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="13ae4-145">其他任何调用都不能随意重用此会话，因为此会话已保留。</span><span class="sxs-lookup"><span data-stu-id="13ae4-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
- <span data-ttu-id="13ae4-146">后续调用通过将 SessionID 设置为在 BeginDoc 中返回的值请求会话。</span><span class="sxs-lookup"><span data-stu-id="13ae4-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
- <span data-ttu-id="13ae4-147">ReserveSession 属性一直设置为 True，至少到系列中的最后一次调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
- <span data-ttu-id="13ae4-148">最后一次调用将 ReserveSession 设置为 False，从而使会话可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="13ae4-149">但是，业务流程可选择保留会话，从而用于更多次调用。</span><span class="sxs-lookup"><span data-stu-id="13ae4-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
  <span data-ttu-id="13ae4-150">如果暂时不使用会话，此会话将由池进行垃圾回收，即使仍错误地保留此会话也是如此。</span><span class="sxs-lookup"><span data-stu-id="13ae4-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
  <span data-ttu-id="13ae4-151">请参阅 BizTalk Server 文档有关消息上下文属性的详细信息。</span><span class="sxs-lookup"><span data-stu-id="13ae4-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ae4-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="13ae4-152">See Also</span></span>  
 <span data-ttu-id="13ae4-153">[使用消息上下文属性](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="13ae4-153">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="13ae4-154">[如何分配消息上下文属性值](../core/how-to-assign-message-context-property-values2.md) </span><span class="sxs-lookup"><span data-stu-id="13ae4-154">[How to Assign Message Context Property Values](../core/how-to-assign-message-context-property-values2.md) </span></span>  
 [<span data-ttu-id="13ae4-155">教程：使用适用于 JD Edwards OneWorld 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="13ae4-155">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)