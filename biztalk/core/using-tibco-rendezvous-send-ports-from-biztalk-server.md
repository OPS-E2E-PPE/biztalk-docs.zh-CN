---
title: 使用从 BizTalk Server TIBCO 会合发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950c4c367fe053195ba14029405f5015381fc6be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "24013732"
---
# <a name="using-tibco-rendezvous-send-ports"></a><span data-ttu-id="b07d2-102">使用 TIBCO 会合发送端口</span><span class="sxs-lookup"><span data-stu-id="b07d2-102">Using TIBCO Rendezvous Send Ports</span></span>
<span data-ttu-id="b07d2-103">传输端口可以发送任何种类的信息。</span><span class="sxs-lookup"><span data-stu-id="b07d2-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="b07d2-104">当 BizTalk Server 通过用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器发送消息时，适配器将基于消息上下文属性值生成消息，或者使用默认消息并将其发送到指定主题。</span><span class="sxs-lookup"><span data-stu-id="b07d2-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b07d2-105">根据 TIBCO Rendezvous 文档，在传输主题名称中不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="b07d2-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="b07d2-106">消息处理</span><span class="sxs-lookup"><span data-stu-id="b07d2-106">Message Handling</span></span>  
 <span data-ttu-id="b07d2-107">适配器会保持某种状态，并相应地处理传入的 BizTalk Server 消息。</span><span class="sxs-lookup"><span data-stu-id="b07d2-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="b07d2-108">如果因为传输失败而无法发送消息，则指示 BizTalk Server 稍后重新提交。</span><span class="sxs-lookup"><span data-stu-id="b07d2-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="b07d2-109">如果因为适配器正在初始化而无法发送消息，则会将 BizTalk Server 消息排入队列。</span><span class="sxs-lookup"><span data-stu-id="b07d2-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="b07d2-110">如果初始化失败，则指示 BizTalk Server 稍后重新提交。</span><span class="sxs-lookup"><span data-stu-id="b07d2-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="b07d2-111">消息生成</span><span class="sxs-lookup"><span data-stu-id="b07d2-111">Message Generation</span></span>  
 <span data-ttu-id="b07d2-112">使用传输适配器，用于 TIBCO Rendezvous 的 BizTalk 适配器会忽略消息目标命名空间和根元素。</span><span class="sxs-lookup"><span data-stu-id="b07d2-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="b07d2-113">如果适配器发送消息，则会原样发送负载。</span><span class="sxs-lookup"><span data-stu-id="b07d2-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="b07d2-114">如果适配器生成结构化 TIBCO Rendezvous 消息，则会忽略根元素的名称（消息没有名称）。</span><span class="sxs-lookup"><span data-stu-id="b07d2-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="b07d2-115">在每种情况下，适配器都将使用上下文属性来查找发布消息时使用的主题。</span><span class="sxs-lookup"><span data-stu-id="b07d2-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="b07d2-116">有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)和[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="b07d2-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  

## <a name="using-biztalk-to-send-messages"></a><span data-ttu-id="b07d2-117">使用 BizTalk 发送消息</span><span class="sxs-lookup"><span data-stu-id="b07d2-117">Using BizTalk to Send Messages</span></span>
<span data-ttu-id="b07d2-118">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。</span><span class="sxs-lookup"><span data-stu-id="b07d2-118">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="b07d2-119">您可以指定适配器使用消息上下文属性发送的消息类型：</span><span class="sxs-lookup"><span data-stu-id="b07d2-119">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
-   <span data-ttu-id="b07d2-120">**结构化**︰ 适配器生成 TIBRVMSG_MSG 结构化，根据消息从 BizTalk Server 接收的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="b07d2-120">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="b07d2-121">(\*)</span><span class="sxs-lookup"><span data-stu-id="b07d2-121">(\*)</span></span>  
  
 <span data-ttu-id="b07d2-122">如果 BizTalk Server 发送字段名称长于 127 个字符的消息，则用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到 TIBCO Rendezvous 的最大字段名称大小（即 127）。</span><span class="sxs-lookup"><span data-stu-id="b07d2-122">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
 <span data-ttu-id="b07d2-123">如果提供 `reply subject name` 属性，则该属性用于在 TIBCO Rendezvous 消息上设置答复主题。</span><span class="sxs-lookup"><span data-stu-id="b07d2-123">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="b07d2-124">假设将接收端口设置为侦听回复或将其转发到 BizTalk Server，或者一些其他的 TIBCO Rendezvous 程序负责回复。</span><span class="sxs-lookup"><span data-stu-id="b07d2-124">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
 <span data-ttu-id="b07d2-125">三联（服务、后台程序、网络）组成传输配置。</span><span class="sxs-lookup"><span data-stu-id="b07d2-125">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="b07d2-126">空（默认）传输配置导致通过默认传输对象发送消息。</span><span class="sxs-lookup"><span data-stu-id="b07d2-126">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
 <span data-ttu-id="b07d2-127">如果未指定代码页，则适配器使用 UTF-8 编码（代码页 65001）。</span><span class="sxs-lookup"><span data-stu-id="b07d2-127">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="b07d2-128">发送器端不支持经过认证的消息。</span><span class="sxs-lookup"><span data-stu-id="b07d2-128">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07d2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b07d2-129">See Also</span></span>  
 <span data-ttu-id="b07d2-130">[创建发送端口](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="b07d2-130">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="b07d2-131">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="b07d2-131">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)