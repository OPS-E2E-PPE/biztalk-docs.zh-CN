---
title: "使用从 BizTalk Server TIBCO 会合发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, handling
- message handling
- BizTalk Server, using send ports from
- send ports, using from BizTalk Server
- messages, generating
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e11657e8e15ac0739124178e85f0c7c5c0a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-send-ports-from-biztalk-server"></a><span data-ttu-id="5856d-102">使用 TIBCO Rendezvous 从 BizTalk Server 发送端口</span><span class="sxs-lookup"><span data-stu-id="5856d-102">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>
<span data-ttu-id="5856d-103">传输端口可以发送任何种类的信息。</span><span class="sxs-lookup"><span data-stu-id="5856d-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="5856d-104">当 BizTalk Server 通过用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器发送消息时，适配器将基于消息上下文属性值生成消息，或者使用默认消息并将其发送到指定主题。</span><span class="sxs-lookup"><span data-stu-id="5856d-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5856d-105">根据 TIBCO Rendezvous 文档，在传输主题名称中不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="5856d-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="5856d-106">消息处理</span><span class="sxs-lookup"><span data-stu-id="5856d-106">Message Handling</span></span>  
 <span data-ttu-id="5856d-107">适配器会保持某种状态，并相应地处理传入的 BizTalk Server 消息。</span><span class="sxs-lookup"><span data-stu-id="5856d-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="5856d-108">如果因为传输失败而无法发送消息，则指示 BizTalk Server 稍后重新提交。</span><span class="sxs-lookup"><span data-stu-id="5856d-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="5856d-109">如果因为适配器正在初始化而无法发送消息，则会将 BizTalk Server 消息排入队列。</span><span class="sxs-lookup"><span data-stu-id="5856d-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="5856d-110">如果初始化失败，则指示 BizTalk Server 稍后重新提交。</span><span class="sxs-lookup"><span data-stu-id="5856d-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="5856d-111">消息生成</span><span class="sxs-lookup"><span data-stu-id="5856d-111">Message Generation</span></span>  
 <span data-ttu-id="5856d-112">使用传输适配器，用于 TIBCO Rendezvous 的 BizTalk 适配器会忽略消息目标命名空间和根元素。</span><span class="sxs-lookup"><span data-stu-id="5856d-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="5856d-113">如果适配器发送消息，则会原样发送负载。</span><span class="sxs-lookup"><span data-stu-id="5856d-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="5856d-114">如果适配器生成结构化 TIBCO Rendezvous 消息，则会忽略根元素的名称（消息没有名称）。</span><span class="sxs-lookup"><span data-stu-id="5856d-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="5856d-115">在每种情况下，适配器都将使用上下文属性来查找发布消息时使用的主题。</span><span class="sxs-lookup"><span data-stu-id="5856d-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="5856d-116">有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)和[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="5856d-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5856d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5856d-117">See Also</span></span>  
 <span data-ttu-id="5856d-118">[创建发送端口](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="5856d-118">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="5856d-119">创建 TIBCO 会合发送处理程序</span><span class="sxs-lookup"><span data-stu-id="5856d-119">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)