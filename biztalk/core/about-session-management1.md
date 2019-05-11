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
ms.openlocfilehash: 1aac0705bc4c9b90b73249a0806aa4b0a8b1aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362316"
---
# <a name="about-session-management"></a><span data-ttu-id="26d50-102">关于会话管理</span><span class="sxs-lookup"><span data-stu-id="26d50-102">About Session Management</span></span>
<span data-ttu-id="26d50-103">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器创建一个连接会话，以发送对 JD Edwards OneWorld 服务器的调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-103">The Microsoft BizTalk Adapter for JD Edwards OneWorld creates a connection session to send a call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="26d50-104">当调用终止时，会话会放在要重新使用的后续调用的池。</span><span class="sxs-lookup"><span data-stu-id="26d50-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="26d50-105">适配器会创建多个连接会话，从而处理对 JD Edwards OneWorld 服务器的并发调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="26d50-106">定期清理该池，从而删除不再需要的会话。</span><span class="sxs-lookup"><span data-stu-id="26d50-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="26d50-107">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供两个消息上下文属性，以控制何时必须在同一会话中进行调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-107">The Microsoft BizTalk Adapter for JD Edwards OneWorld provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="26d50-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="26d50-108">Name</span></span>|<span data-ttu-id="26d50-109">类型</span><span class="sxs-lookup"><span data-stu-id="26d50-109">Type</span></span>|<span data-ttu-id="26d50-110">默认</span><span class="sxs-lookup"><span data-stu-id="26d50-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="26d50-111">JDE.SessionID</span><span class="sxs-lookup"><span data-stu-id="26d50-111">JDE.SessionID</span></span>|<span data-ttu-id="26d50-112">smallint</span><span class="sxs-lookup"><span data-stu-id="26d50-112">Int</span></span>|<span data-ttu-id="26d50-113">0</span><span class="sxs-lookup"><span data-stu-id="26d50-113">0</span></span>|  
|<span data-ttu-id="26d50-114">JDE.ReserveSession</span><span class="sxs-lookup"><span data-stu-id="26d50-114">JDE.ReserveSession</span></span>|<span data-ttu-id="26d50-115">boolean</span><span class="sxs-lookup"><span data-stu-id="26d50-115">boolean</span></span>|<span data-ttu-id="26d50-116">false</span><span class="sxs-lookup"><span data-stu-id="26d50-116">false</span></span>|  
  
 <span data-ttu-id="26d50-117">如果业务功能要求对 JD Edwards OneWorld 服务器的单个调用，则会话管理。</span><span class="sxs-lookup"><span data-stu-id="26d50-117">Session management is unnecessary if the business function requires a single call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="26d50-118">适配器可以选择任何可用的会话，并且会话仍可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="26d50-119">在此方案中，你可以忽略消息上下文属性，因为默认值是适当。</span><span class="sxs-lookup"><span data-stu-id="26d50-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="26d50-120">某些 JD Edwards OneWorld 功能要求对 JD Edwards OneWorld 服务器; 的多次调用例如，创建 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="26d50-120">Some JD Edwards OneWorld functionality requires multiple calls to the JD Edwards OneWorld server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="26d50-121">首次调用 BeginDoc 会创建一个空 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="26d50-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="26d50-122">每个后续调用 editline 向 SalesOrder 添加一个行项。</span><span class="sxs-lookup"><span data-stu-id="26d50-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="26d50-123">最后调用 enddoc 将关闭 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="26d50-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="26d50-124">若要成功，必须在同一会话上发送对单个 SalesOrder 的所有调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="26d50-125">若要执行此操作，分配消息上下文属性以指示适配器如何处理会话。</span><span class="sxs-lookup"><span data-stu-id="26d50-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="26d50-126">以 SalesOrder 为例，以下是将赋给消息上下文属性以处理 JD OneWorld 会话的值：</span><span class="sxs-lookup"><span data-stu-id="26d50-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD OneWorld session:</span></span>  
  
|<span data-ttu-id="26d50-127">函数</span><span class="sxs-lookup"><span data-stu-id="26d50-127">Function</span></span>|<span data-ttu-id="26d50-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="26d50-128">SessionID</span></span>|<span data-ttu-id="26d50-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="26d50-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="26d50-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="26d50-130">BeginDoc</span></span>|<span data-ttu-id="26d50-131">0</span><span class="sxs-lookup"><span data-stu-id="26d50-131">0</span></span>|<span data-ttu-id="26d50-132">true</span><span class="sxs-lookup"><span data-stu-id="26d50-132">true</span></span>|  
|<span data-ttu-id="26d50-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="26d50-133">EditLine</span></span>|<span data-ttu-id="26d50-134">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="26d50-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="26d50-135">true</span><span class="sxs-lookup"><span data-stu-id="26d50-135">true</span></span>|  
|<span data-ttu-id="26d50-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="26d50-136">EditLine</span></span>|<span data-ttu-id="26d50-137">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="26d50-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="26d50-138">true</span><span class="sxs-lookup"><span data-stu-id="26d50-138">true</span></span>|  
|<span data-ttu-id="26d50-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="26d50-139">EndDoc</span></span>|<span data-ttu-id="26d50-140">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="26d50-140">Copied from BeginDoc reply</span></span>|<span data-ttu-id="26d50-141">false</span><span class="sxs-lookup"><span data-stu-id="26d50-141">false</span></span>|  
  
- <span data-ttu-id="26d50-142">首次调用时，适配器是随意选择任何可用的会话 （因为 SessionID 为 0）。</span><span class="sxs-lookup"><span data-stu-id="26d50-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
- <span data-ttu-id="26d50-143">适配器返回 BeginDoc 回复中使用的 SessionID。</span><span class="sxs-lookup"><span data-stu-id="26d50-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
- <span data-ttu-id="26d50-144">ReserveSession 属性会指示适配器保留显式请求此会话的以下调用此会话。</span><span class="sxs-lookup"><span data-stu-id="26d50-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="26d50-145">由于已保留，其他任何调用可以意外地重复不使用该会话。</span><span class="sxs-lookup"><span data-stu-id="26d50-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
- <span data-ttu-id="26d50-146">后续调用通过将 SessionID 设置为在 BeginDoc 中返回的值请求会话。</span><span class="sxs-lookup"><span data-stu-id="26d50-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
- <span data-ttu-id="26d50-147">ReserveSession 属性设置为 true，至少直到序列中的最后一个调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
- <span data-ttu-id="26d50-148">最后一次调用将 ReserveSession 设置为 false，以使会话可供任何调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="26d50-149">但是，业务流程可选择要保留的会话的更多调用。</span><span class="sxs-lookup"><span data-stu-id="26d50-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
  <span data-ttu-id="26d50-150">如果会话未使用一段时间，它将进行垃圾回收的池，即使错误地是仍保留在会话。</span><span class="sxs-lookup"><span data-stu-id="26d50-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
  <span data-ttu-id="26d50-151">请参阅 BizTalk Server 文档有关消息上下文属性的详细信息。</span><span class="sxs-lookup"><span data-stu-id="26d50-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d50-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="26d50-152">See Also</span></span>  
 <span data-ttu-id="26d50-153">[使用消息上下文属性](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="26d50-153">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="26d50-154">[如何分配消息上下文属性值](../core/how-to-assign-message-context-property-values2.md) </span><span class="sxs-lookup"><span data-stu-id="26d50-154">[How to Assign Message Context Property Values](../core/how-to-assign-message-context-property-values2.md) </span></span>  
 [<span data-ttu-id="26d50-155">教程：使用用于 JD Edwards OneWorld 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="26d50-155">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)