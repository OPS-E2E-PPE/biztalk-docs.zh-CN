---
title: TIBCO Rendezvous 的接收的消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e330926c6f362ea5a84ad7b4b9291a5f2f310eee
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528328"
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a><span data-ttu-id="c6ac3-102">BizTalk Server 消息上下文属性 （接收处理程序）</span><span class="sxs-lookup"><span data-stu-id="c6ac3-102">BizTalk Server Message Context Properties (Receive Handlers)</span></span>
<span data-ttu-id="c6ac3-103">除了消息负载，撰写一条消息的补充信息必须可从 BizTalk Server 业务流程在运行时访问。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-103">In addition to the message payload, the supplementary information that composes a message must be accessible from a BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="c6ac3-104">TIBCO RV 消息信息升级为消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="c6ac3-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
 <span data-ttu-id="c6ac3-105">下表列出了此补充信息：</span><span class="sxs-lookup"><span data-stu-id="c6ac3-105">The following table lists this supplementary information:</span></span>  
  
|<span data-ttu-id="c6ac3-106">数据标识</span><span class="sxs-lookup"><span data-stu-id="c6ac3-106">Data Identification</span></span>|<span data-ttu-id="c6ac3-107">类型</span><span class="sxs-lookup"><span data-stu-id="c6ac3-107">Type</span></span>|<span data-ttu-id="c6ac3-108">路由</span><span class="sxs-lookup"><span data-stu-id="c6ac3-108">Routable</span></span>|<span data-ttu-id="c6ac3-109">接收位置</span><span class="sxs-lookup"><span data-stu-id="c6ac3-109">Receive Location</span></span>|  
|-------------------------|----------|--------------|----------------------|  
|<span data-ttu-id="c6ac3-110">将发送主题 [空]</span><span class="sxs-lookup"><span data-stu-id="c6ac3-110">Send Subject [null]</span></span>|<span data-ttu-id="c6ac3-111">string</span><span class="sxs-lookup"><span data-stu-id="c6ac3-111">string</span></span>|<span data-ttu-id="c6ac3-112">是</span><span class="sxs-lookup"><span data-stu-id="c6ac3-112">Yes</span></span>|<span data-ttu-id="c6ac3-113">告诉业务流程此消息发送到哪个主题。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-113">Tells orchestration which subject this message was sent to.</span></span>|  
|<span data-ttu-id="c6ac3-114">答复主题 [空]</span><span class="sxs-lookup"><span data-stu-id="c6ac3-114">Reply Subject [null]</span></span>|<span data-ttu-id="c6ac3-115">string</span><span class="sxs-lookup"><span data-stu-id="c6ac3-115">string</span></span>|<span data-ttu-id="c6ac3-116">是</span><span class="sxs-lookup"><span data-stu-id="c6ac3-116">Yes</span></span>|<span data-ttu-id="c6ac3-117">告诉业务流程而发件人需要答复发送，如果其中一个。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-117">Tells orchestration where the sender expects the reply to be sent, if one is expected.</span></span>|  
|<span data-ttu-id="c6ac3-118">字段计数 [只读]</span><span class="sxs-lookup"><span data-stu-id="c6ac3-118">Field Count [read only]</span></span>|<span data-ttu-id="c6ac3-119">unsigned int</span><span class="sxs-lookup"><span data-stu-id="c6ac3-119">unsigned int</span></span>|<span data-ttu-id="c6ac3-120">否</span><span class="sxs-lookup"><span data-stu-id="c6ac3-120">No</span></span>|<span data-ttu-id="c6ac3-121">上级消息中的字段数。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-121">Number of fields in upper level message.</span></span> <span data-ttu-id="c6ac3-122">属性提供的 TIBCO rv。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-122">A property provided by TIBCO RV.</span></span>|  
|<span data-ttu-id="c6ac3-123">CM 发件人姓名 [只读]</span><span class="sxs-lookup"><span data-stu-id="c6ac3-123">CM Sender Name [read-only]</span></span>|<span data-ttu-id="c6ac3-124">string</span><span class="sxs-lookup"><span data-stu-id="c6ac3-124">string</span></span>|<span data-ttu-id="c6ac3-125">是</span><span class="sxs-lookup"><span data-stu-id="c6ac3-125">Yes</span></span>|<span data-ttu-id="c6ac3-126">发件人的 CM 通信名称。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-126">CM Correspondent name of the sender.</span></span>|  
|<span data-ttu-id="c6ac3-127">CM 序号 [只读]</span><span class="sxs-lookup"><span data-stu-id="c6ac3-127">CM Sequence Number [read only]</span></span>|<span data-ttu-id="c6ac3-128">long</span><span class="sxs-lookup"><span data-stu-id="c6ac3-128">long</span></span>|<span data-ttu-id="c6ac3-129">否</span><span class="sxs-lookup"><span data-stu-id="c6ac3-129">No</span></span>|<span data-ttu-id="c6ac3-130">通过发送 TIBCO 传输对象分配序列号。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-130">Sequence number assigned by the sending TIBCO transport object.</span></span>|  
|<span data-ttu-id="c6ac3-131">CM 时间限制 [只读]</span><span class="sxs-lookup"><span data-stu-id="c6ac3-131">CM Time Limit [read-only]</span></span>|<span data-ttu-id="c6ac3-132">double</span><span class="sxs-lookup"><span data-stu-id="c6ac3-132">double</span></span>|<span data-ttu-id="c6ac3-133">否</span><span class="sxs-lookup"><span data-stu-id="c6ac3-133">No</span></span>|<span data-ttu-id="c6ac3-134">时间限制，此后发送程序就不再要求其 CM 传输认证消息传递。</span><span class="sxs-lookup"><span data-stu-id="c6ac3-134">A time limit, after which the sending program no longer expects its CM transport to certify delivery of the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6ac3-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6ac3-135">See Also</span></span>  
 <span data-ttu-id="c6ac3-136">[TIBCO Rendezvous 中消息映射](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="c6ac3-136">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="c6ac3-137">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="c6ac3-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)