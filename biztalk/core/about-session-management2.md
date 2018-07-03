---
title: 有关会话 Management2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ecdb4f-d384-42ac-9776-e7ad14d5f151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493df24e89a07a97dc7fd501afed53f44017781b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006006"
---
# <a name="about-session-management"></a><span data-ttu-id="b84a6-102">关于会话管理</span><span class="sxs-lookup"><span data-stu-id="b84a6-102">About Session Management</span></span>
<span data-ttu-id="b84a6-103">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器创建一个连接会话，以发送到 JD Edwards EnterpriseOne 服务器的调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-103">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne creates a connection session to send a call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="b84a6-104">调用终止时，会话会放在池中以供后续调用重用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="b84a6-105">适配器会创建多个连接会话，从而处理对 JD Edwards EnterpriseOne 服务器的并发调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="b84a6-106">池会定期进行清理，从而删除不再需要的会话。</span><span class="sxs-lookup"><span data-stu-id="b84a6-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="b84a6-107">适用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供两个消息上下文属性，以控制何时必须在同一会话中进行调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-107">The Microsoft BizTalk Adapter JD Edwards EnterpriseOne provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="b84a6-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="b84a6-108">Name</span></span>|<span data-ttu-id="b84a6-109">类型</span><span class="sxs-lookup"><span data-stu-id="b84a6-109">Type</span></span>|<span data-ttu-id="b84a6-110">，则“默认”</span><span class="sxs-lookup"><span data-stu-id="b84a6-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="b84a6-111">JDE.SessionID</span><span class="sxs-lookup"><span data-stu-id="b84a6-111">JDE.SessionID</span></span>|<span data-ttu-id="b84a6-112">smallint</span><span class="sxs-lookup"><span data-stu-id="b84a6-112">Int</span></span>|<span data-ttu-id="b84a6-113">0</span><span class="sxs-lookup"><span data-stu-id="b84a6-113">0</span></span>|  
|<span data-ttu-id="b84a6-114">JDE.ReserveSession</span><span class="sxs-lookup"><span data-stu-id="b84a6-114">JDE.ReserveSession</span></span>|<span data-ttu-id="b84a6-115">boolean</span><span class="sxs-lookup"><span data-stu-id="b84a6-115">boolean</span></span>|<span data-ttu-id="b84a6-116">false</span><span class="sxs-lookup"><span data-stu-id="b84a6-116">false</span></span>|  
  
 <span data-ttu-id="b84a6-117">如果业务功能要求对 JD Edwards EnterpriseOne 服务器进行单一调用，则不必进行会话管理。</span><span class="sxs-lookup"><span data-stu-id="b84a6-117">Session management is unnecessary if the business function requires a single call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="b84a6-118">适配器可以选择任何可用的会话，并且会话仍可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="b84a6-119">在这种情况下，由于默认值适当，因此可以忽略消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b84a6-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="b84a6-120">某些 JD Edwards EnterpriseOne 功能要求对 JD Edwards EnterpriseOne 服务器进行多次调用；例如，创建 SalesOrder 时。</span><span class="sxs-lookup"><span data-stu-id="b84a6-120">Some JD Edwards EnterpriseOne functionality requires multiple calls to the JD Edwards EnterpriseOne server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="b84a6-121">首次调用 BeginDoc 会创建一个空 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="b84a6-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="b84a6-122">随后每次调用 EditLine 会向 SalesOrder 添加一个行项目。</span><span class="sxs-lookup"><span data-stu-id="b84a6-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="b84a6-123">最后调用 EndDoc 将关闭 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="b84a6-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="b84a6-124">若要成功执行此操作，对单个 SalesOrder 的所有调用都必须在同一会话中发送。</span><span class="sxs-lookup"><span data-stu-id="b84a6-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="b84a6-125">为此，请为消息上下文属性赋值以指示适配器如何处理会话。</span><span class="sxs-lookup"><span data-stu-id="b84a6-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="b84a6-126">以 SalesOrder 为例，以下是将赋给消息上下文属性以处理 JD Edwards EnterpriseOne 会话的值：</span><span class="sxs-lookup"><span data-stu-id="b84a6-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD Edwards EnterpriseOne session:</span></span>  
  
|<span data-ttu-id="b84a6-127">函数</span><span class="sxs-lookup"><span data-stu-id="b84a6-127">Function</span></span>|<span data-ttu-id="b84a6-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="b84a6-128">SessionID</span></span>|<span data-ttu-id="b84a6-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="b84a6-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="b84a6-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="b84a6-130">BeginDoc</span></span>|<span data-ttu-id="b84a6-131">0</span><span class="sxs-lookup"><span data-stu-id="b84a6-131">0</span></span>|<span data-ttu-id="b84a6-132">true</span><span class="sxs-lookup"><span data-stu-id="b84a6-132">true</span></span>|  
|<span data-ttu-id="b84a6-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="b84a6-133">EditLine</span></span>|<span data-ttu-id="b84a6-134">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="b84a6-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="b84a6-135">true</span><span class="sxs-lookup"><span data-stu-id="b84a6-135">true</span></span>|  
|<span data-ttu-id="b84a6-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="b84a6-136">EditLine</span></span>|<span data-ttu-id="b84a6-137">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="b84a6-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="b84a6-138">true</span><span class="sxs-lookup"><span data-stu-id="b84a6-138">true</span></span>|  
|<span data-ttu-id="b84a6-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="b84a6-139">EndDoc</span></span>|<span data-ttu-id="b84a6-140">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="b84a6-140">Copied from  BeginDoc reply</span></span>|<span data-ttu-id="b84a6-141">false</span><span class="sxs-lookup"><span data-stu-id="b84a6-141">false</span></span>|  
  
- <span data-ttu-id="b84a6-142">首次调用时，适配器可以随意选择任何可用的会话（因为 SessionID 为 0）。</span><span class="sxs-lookup"><span data-stu-id="b84a6-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
- <span data-ttu-id="b84a6-143">适配器会返回已在 BeginDoc 回复中使用的 SessionID。</span><span class="sxs-lookup"><span data-stu-id="b84a6-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
- <span data-ttu-id="b84a6-144">ReserveSession 属性会指示适配器为随后显式请求此会话的调用保留此会话。</span><span class="sxs-lookup"><span data-stu-id="b84a6-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="b84a6-145">其他任何调用都不能随意重用此会话，因为此会话已保留。</span><span class="sxs-lookup"><span data-stu-id="b84a6-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
- <span data-ttu-id="b84a6-146">后续调用通过将 SessionID 设置为在 BeginDoc 中返回的值请求会话。</span><span class="sxs-lookup"><span data-stu-id="b84a6-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
- <span data-ttu-id="b84a6-147">ReserveSession 属性一直设置为 True，至少到系列中的最后一次调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
- <span data-ttu-id="b84a6-148">最后一次调用将 ReserveSession 设置为 False，从而使会话可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="b84a6-149">但是，业务流程可选择保留会话，从而用于更多次调用。</span><span class="sxs-lookup"><span data-stu-id="b84a6-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
  <span data-ttu-id="b84a6-150">如果暂时不使用会话，此会话将由池进行垃圾回收，即使仍错误地保留此会话也是如此。</span><span class="sxs-lookup"><span data-stu-id="b84a6-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
  <span data-ttu-id="b84a6-151">请参阅 BizTalk Server 文档有关消息上下文属性的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b84a6-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84a6-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="b84a6-152">See Also</span></span>  
 [<span data-ttu-id="b84a6-153">使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="b84a6-153">Using Message Context Properties</span></span>](../core/using-message-context-properties1.md)