---
title: "BizTalk Server 消息上下文属性 （接收处理程序） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties
- receive handlers, message context properties
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a60896a8e1cace909a160c1dc942e63e9258d85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a><span data-ttu-id="9ec17-102">BizTalk Server 消息上下文属性 （接收处理程序）</span><span class="sxs-lookup"><span data-stu-id="9ec17-102">BizTalk Server Message Context Properties (Receive Handlers)</span></span>
<span data-ttu-id="9ec17-103">除了消息负载之外，构成消息的补充信息必须可以在运行时从 BizTalk Server 业务流程访问。</span><span class="sxs-lookup"><span data-stu-id="9ec17-103">In addition to the message payload, the supplementary information that composes a message must be accessible from a BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="9ec17-104">TIBCO RV 消息信息升级为消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="9ec17-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
 <span data-ttu-id="9ec17-105">下表列出了此补充信息：</span><span class="sxs-lookup"><span data-stu-id="9ec17-105">The following table lists this supplementary information:</span></span>  
  
|<span data-ttu-id="9ec17-106">数据标识</span><span class="sxs-lookup"><span data-stu-id="9ec17-106">Data Identification</span></span>|<span data-ttu-id="9ec17-107">类型</span><span class="sxs-lookup"><span data-stu-id="9ec17-107">Type</span></span>|<span data-ttu-id="9ec17-108">可路由</span><span class="sxs-lookup"><span data-stu-id="9ec17-108">Routable</span></span>|<span data-ttu-id="9ec17-109">接收位置</span><span class="sxs-lookup"><span data-stu-id="9ec17-109">Receive Location</span></span>|  
|-------------------------|----------|--------------|----------------------|  
|<span data-ttu-id="9ec17-110">发送主题 [空]</span><span class="sxs-lookup"><span data-stu-id="9ec17-110">Send Subject [null]</span></span>|<span data-ttu-id="9ec17-111">string</span><span class="sxs-lookup"><span data-stu-id="9ec17-111">string</span></span>|<span data-ttu-id="9ec17-112">是</span><span class="sxs-lookup"><span data-stu-id="9ec17-112">Yes</span></span>|<span data-ttu-id="9ec17-113">告诉业务流程此消息发送到哪个主题。</span><span class="sxs-lookup"><span data-stu-id="9ec17-113">Tells orchestration which subject this message was sent to.</span></span>|  
|<span data-ttu-id="9ec17-114">答复主题 [空]</span><span class="sxs-lookup"><span data-stu-id="9ec17-114">Reply Subject [null]</span></span>|<span data-ttu-id="9ec17-115">string</span><span class="sxs-lookup"><span data-stu-id="9ec17-115">string</span></span>|<span data-ttu-id="9ec17-116">是</span><span class="sxs-lookup"><span data-stu-id="9ec17-116">Yes</span></span>|<span data-ttu-id="9ec17-117">告诉业务流程发件人希望将此回复发送到的位置（如果有）。</span><span class="sxs-lookup"><span data-stu-id="9ec17-117">Tells orchestration where the sender expects the reply to be sent, if one is expected.</span></span>|  
|<span data-ttu-id="9ec17-118">字段计数 [只读]</span><span class="sxs-lookup"><span data-stu-id="9ec17-118">Field Count [read only]</span></span>|<span data-ttu-id="9ec17-119">unsigned int</span><span class="sxs-lookup"><span data-stu-id="9ec17-119">unsigned int</span></span>|<span data-ttu-id="9ec17-120">是</span><span class="sxs-lookup"><span data-stu-id="9ec17-120">No</span></span>|<span data-ttu-id="9ec17-121">上级消息中的字段数。</span><span class="sxs-lookup"><span data-stu-id="9ec17-121">Number of fields in upper level message.</span></span> <span data-ttu-id="9ec17-122">一个由 TIBCO RV 提供的属性。</span><span class="sxs-lookup"><span data-stu-id="9ec17-122">A property provided by TIBCO RV.</span></span>|  
|<span data-ttu-id="9ec17-123">CM 发件人姓名 [只读]</span><span class="sxs-lookup"><span data-stu-id="9ec17-123">CM Sender Name [read-only]</span></span>|<span data-ttu-id="9ec17-124">string</span><span class="sxs-lookup"><span data-stu-id="9ec17-124">string</span></span>|<span data-ttu-id="9ec17-125">是</span><span class="sxs-lookup"><span data-stu-id="9ec17-125">Yes</span></span>|<span data-ttu-id="9ec17-126">发件人的 CM 通信名称。</span><span class="sxs-lookup"><span data-stu-id="9ec17-126">CM Correspondent name of the sender.</span></span>|  
|<span data-ttu-id="9ec17-127">CM 序号 [只读]</span><span class="sxs-lookup"><span data-stu-id="9ec17-127">CM Sequence Number [read only]</span></span>|<span data-ttu-id="9ec17-128">long</span><span class="sxs-lookup"><span data-stu-id="9ec17-128">long</span></span>|<span data-ttu-id="9ec17-129">是</span><span class="sxs-lookup"><span data-stu-id="9ec17-129">No</span></span>|<span data-ttu-id="9ec17-130">通过发送 TIBCO 传输对象分配的序列号。</span><span class="sxs-lookup"><span data-stu-id="9ec17-130">Sequence number assigned by the sending TIBCO transport object.</span></span>|  
|<span data-ttu-id="9ec17-131">CM 时间限制 [只读]</span><span class="sxs-lookup"><span data-stu-id="9ec17-131">CM Time Limit [read-only]</span></span>|<span data-ttu-id="9ec17-132">double</span><span class="sxs-lookup"><span data-stu-id="9ec17-132">double</span></span>|<span data-ttu-id="9ec17-133">是</span><span class="sxs-lookup"><span data-stu-id="9ec17-133">No</span></span>|<span data-ttu-id="9ec17-134">时间限制，在这段时间之后发送程序就不再要求其 CM 传输证实消息是否递送。</span><span class="sxs-lookup"><span data-stu-id="9ec17-134">A time limit, after which the sending program no longer expects its CM transport to certify delivery of the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ec17-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ec17-135">See Also</span></span>  
 <span data-ttu-id="9ec17-136">[TIBCO 集合中的消息映射](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="9ec17-136">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="9ec17-137">创建 TIBCO 会合接收处理程序</span><span class="sxs-lookup"><span data-stu-id="9ec17-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)