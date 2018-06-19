---
title: 有关会话 Management2 |Microsoft 文档
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
ms.openlocfilehash: 9b9d34038acceb0bd52dc598ca48cf5e914d70d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225605"
---
# <a name="about-session-management"></a><span data-ttu-id="cb653-102">关于会话管理</span><span class="sxs-lookup"><span data-stu-id="cb653-102">About Session Management</span></span>
<span data-ttu-id="cb653-103">Microsoft BizTalk Adapter for 博士 Edwards EnterpriseOne 创建要发送到博士 Edwards EnterpriseOne 服务器调用的连接会话。</span><span class="sxs-lookup"><span data-stu-id="cb653-103">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne creates a connection session to send a call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="cb653-104">调用终止时，会话会放在池中以供后续调用重用。</span><span class="sxs-lookup"><span data-stu-id="cb653-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="cb653-105">适配器会创建多个连接会话以处理到博士 Edwards EnterpriseOne 服务器的并发调用。</span><span class="sxs-lookup"><span data-stu-id="cb653-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="cb653-106">池会定期进行清理，从而删除不再需要的会话。</span><span class="sxs-lookup"><span data-stu-id="cb653-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="cb653-107">适用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供两个消息上下文属性，以控制何时必须在同一会话中进行调用。</span><span class="sxs-lookup"><span data-stu-id="cb653-107">The Microsoft BizTalk Adapter JD Edwards EnterpriseOne provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="cb653-108">Name</span><span class="sxs-lookup"><span data-stu-id="cb653-108">Name</span></span>|<span data-ttu-id="cb653-109">类型</span><span class="sxs-lookup"><span data-stu-id="cb653-109">Type</span></span>|<span data-ttu-id="cb653-110">默认</span><span class="sxs-lookup"><span data-stu-id="cb653-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="cb653-111">JDE.SessionID</span><span class="sxs-lookup"><span data-stu-id="cb653-111">JDE.SessionID</span></span>|<span data-ttu-id="cb653-112">int</span><span class="sxs-lookup"><span data-stu-id="cb653-112">Int</span></span>|<span data-ttu-id="cb653-113">0</span><span class="sxs-lookup"><span data-stu-id="cb653-113">0</span></span>|  
|<span data-ttu-id="cb653-114">JDE.ReserveSession</span><span class="sxs-lookup"><span data-stu-id="cb653-114">JDE.ReserveSession</span></span>|<span data-ttu-id="cb653-115">boolean</span><span class="sxs-lookup"><span data-stu-id="cb653-115">boolean</span></span>|<span data-ttu-id="cb653-116">false</span><span class="sxs-lookup"><span data-stu-id="cb653-116">false</span></span>|  
  
 <span data-ttu-id="cb653-117">如果业务功能要求对 JD Edwards EnterpriseOne 服务器进行单一调用，则不必进行会话管理。</span><span class="sxs-lookup"><span data-stu-id="cb653-117">Session management is unnecessary if the business function requires a single call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="cb653-118">适配器可以选择任何可用的会话，并且会话仍可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="cb653-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="cb653-119">在这种情况下，由于默认值适当，因此可以忽略消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cb653-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="cb653-120">某些 JD Edwards EnterpriseOne 功能要求对 JD Edwards EnterpriseOne 服务器进行多次调用；例如，创建 SalesOrder 时。</span><span class="sxs-lookup"><span data-stu-id="cb653-120">Some JD Edwards EnterpriseOne functionality requires multiple calls to the JD Edwards EnterpriseOne server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="cb653-121">首次调用 BeginDoc 会创建一个空 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="cb653-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="cb653-122">随后每次调用 EditLine 会向 SalesOrder 添加一个行项目。</span><span class="sxs-lookup"><span data-stu-id="cb653-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="cb653-123">最后调用 EndDoc 将关闭 SalesOrder。</span><span class="sxs-lookup"><span data-stu-id="cb653-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="cb653-124">若要成功执行此操作，对单个 SalesOrder 的所有调用都必须在同一会话中发送。</span><span class="sxs-lookup"><span data-stu-id="cb653-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="cb653-125">为此，请为消息上下文属性赋值以指示适配器如何处理会话。</span><span class="sxs-lookup"><span data-stu-id="cb653-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="cb653-126">以 SalesOrder 为例，以下是将赋给消息上下文属性以处理 JD Edwards EnterpriseOne 会话的值：</span><span class="sxs-lookup"><span data-stu-id="cb653-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD Edwards EnterpriseOne session:</span></span>  
  
|<span data-ttu-id="cb653-127">函数</span><span class="sxs-lookup"><span data-stu-id="cb653-127">Function</span></span>|<span data-ttu-id="cb653-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="cb653-128">SessionID</span></span>|<span data-ttu-id="cb653-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="cb653-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="cb653-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="cb653-130">BeginDoc</span></span>|<span data-ttu-id="cb653-131">0</span><span class="sxs-lookup"><span data-stu-id="cb653-131">0</span></span>|<span data-ttu-id="cb653-132">true</span><span class="sxs-lookup"><span data-stu-id="cb653-132">true</span></span>|  
|<span data-ttu-id="cb653-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="cb653-133">EditLine</span></span>|<span data-ttu-id="cb653-134">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="cb653-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="cb653-135">true</span><span class="sxs-lookup"><span data-stu-id="cb653-135">true</span></span>|  
|<span data-ttu-id="cb653-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="cb653-136">EditLine</span></span>|<span data-ttu-id="cb653-137">从 BeginDoc 回复中复制</span><span class="sxs-lookup"><span data-stu-id="cb653-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="cb653-138">true</span><span class="sxs-lookup"><span data-stu-id="cb653-138">true</span></span>|  
|<span data-ttu-id="cb653-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="cb653-139">EndDoc</span></span>|<span data-ttu-id="cb653-140">从 BeginDoc 答复复制</span><span class="sxs-lookup"><span data-stu-id="cb653-140">Copied from  BeginDoc reply</span></span>|<span data-ttu-id="cb653-141">false</span><span class="sxs-lookup"><span data-stu-id="cb653-141">false</span></span>|  
  
-   <span data-ttu-id="cb653-142">首次调用时，适配器可以随意选择任何可用的会话（因为 SessionID 为 0）。</span><span class="sxs-lookup"><span data-stu-id="cb653-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
-   <span data-ttu-id="cb653-143">适配器会返回已在 BeginDoc 回复中使用的 SessionID。</span><span class="sxs-lookup"><span data-stu-id="cb653-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
-   <span data-ttu-id="cb653-144">ReserveSession 属性会指示适配器为随后显式请求此会话的调用保留此会话。</span><span class="sxs-lookup"><span data-stu-id="cb653-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="cb653-145">其他任何调用都不能随意重用此会话，因为此会话已保留。</span><span class="sxs-lookup"><span data-stu-id="cb653-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
-   <span data-ttu-id="cb653-146">后续调用通过将 SessionID 设置为在 BeginDoc 中返回的值请求会话。</span><span class="sxs-lookup"><span data-stu-id="cb653-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
-   <span data-ttu-id="cb653-147">ReserveSession 属性一直设置为 True，至少到系列中的最后一次调用。</span><span class="sxs-lookup"><span data-stu-id="cb653-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
-   <span data-ttu-id="cb653-148">最后一次调用将 ReserveSession 设置为 False，从而使会话可用于随后的任何调用。</span><span class="sxs-lookup"><span data-stu-id="cb653-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="cb653-149">但是，业务流程可选择保留会话，从而用于更多次调用。</span><span class="sxs-lookup"><span data-stu-id="cb653-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
 <span data-ttu-id="cb653-150">如果暂时不使用会话，此会话将由池进行垃圾回收，即使仍错误地保留此会话也是如此。</span><span class="sxs-lookup"><span data-stu-id="cb653-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
 <span data-ttu-id="cb653-151">请参阅有关消息上下文属性的详细信息的 BizTalk Server 文档。</span><span class="sxs-lookup"><span data-stu-id="cb653-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb653-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb653-152">See Also</span></span>  
 [<span data-ttu-id="cb653-153">使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="cb653-153">Using Message Context Properties</span></span>](../core/using-message-context-properties1.md)