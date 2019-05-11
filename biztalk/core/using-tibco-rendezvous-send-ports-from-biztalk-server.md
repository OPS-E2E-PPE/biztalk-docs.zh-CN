---
title: 使用 TIBCO Rendezvous 发送端口从 BizTalk Server |Microsoft Docs
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
ms.openlocfilehash: 9bc98cc3136483a1481590fade44de2796562b2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396768"
---
# <a name="using-tibco-rendezvous-send-ports"></a><span data-ttu-id="06bc7-102">使用 TIBCO Rendezvous 发送端口</span><span class="sxs-lookup"><span data-stu-id="06bc7-102">Using TIBCO Rendezvous Send Ports</span></span>
<span data-ttu-id="06bc7-103">传输端口可以发送任何种类的信息。</span><span class="sxs-lookup"><span data-stu-id="06bc7-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="06bc7-104">BizTalk Server 发送用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器通过一条消息，适配器生成基于消息上下文属性值，该消息或它使用默认值并将其发送到指定主题。</span><span class="sxs-lookup"><span data-stu-id="06bc7-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06bc7-105">根据 TIBCO Rendezvous 文档，通配符字符不支持在传输主题名称。</span><span class="sxs-lookup"><span data-stu-id="06bc7-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="06bc7-106">消息处理</span><span class="sxs-lookup"><span data-stu-id="06bc7-106">Message Handling</span></span>  
 <span data-ttu-id="06bc7-107">适配器会保持某种状态，并相应地处理传入的 BizTalk Server 消息。</span><span class="sxs-lookup"><span data-stu-id="06bc7-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="06bc7-108">如果因为传输失败而无法发送一条消息，则指示 BizTalk Server 稍后重新提交。</span><span class="sxs-lookup"><span data-stu-id="06bc7-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="06bc7-109">如果无法发送一条消息，因为仍在初始化适配器，BizTalk Server 消息排入队列。</span><span class="sxs-lookup"><span data-stu-id="06bc7-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="06bc7-110">如果初始化失败，则指示 BizTalk Server 稍后重新提交。</span><span class="sxs-lookup"><span data-stu-id="06bc7-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="06bc7-111">消息的生成</span><span class="sxs-lookup"><span data-stu-id="06bc7-111">Message Generation</span></span>  
 <span data-ttu-id="06bc7-112">传输适配器，用于 TIBCO Rendezvous 的 BizTalk 适配器将忽略消息目标命名空间和根元素。</span><span class="sxs-lookup"><span data-stu-id="06bc7-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="06bc7-113">如果适配器发送消息，它将发送原样的有效负载。</span><span class="sxs-lookup"><span data-stu-id="06bc7-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="06bc7-114">如果适配器生成结构化的 TIBCO Rendezvous 消息，忽略根元素的名称 （一条消息不具有一个名称）。</span><span class="sxs-lookup"><span data-stu-id="06bc7-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="06bc7-115">在所有情况下，适配器使用的上下文属性以了解使用受发布消息时。</span><span class="sxs-lookup"><span data-stu-id="06bc7-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="06bc7-116">有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)并[TIBCO Rendezvous 中的接收处理程序的数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="06bc7-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  

## <a name="using-biztalk-to-send-messages"></a><span data-ttu-id="06bc7-117">使用 BizTalk 发送消息</span><span class="sxs-lookup"><span data-stu-id="06bc7-117">Using BizTalk to Send Messages</span></span>
<span data-ttu-id="06bc7-118">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。</span><span class="sxs-lookup"><span data-stu-id="06bc7-118">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="06bc7-119">您可以指定适配器使用消息上下文属性发送的消息的类型：</span><span class="sxs-lookup"><span data-stu-id="06bc7-119">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
- <span data-ttu-id="06bc7-120">**结构化**:适配器生成 TIBRVMSG_MSG 结构化的消息，根据从 BizTalk Server 收到的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="06bc7-120">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="06bc7-121">(\*)</span><span class="sxs-lookup"><span data-stu-id="06bc7-121">(\*)</span></span>  
  
  <span data-ttu-id="06bc7-122">如果 BizTalk Server 发送字段名称长度超过 127 个字符的消息，用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到最大字段名称大小适用于 TIBCO Rendezvous 即 127。</span><span class="sxs-lookup"><span data-stu-id="06bc7-122">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
  <span data-ttu-id="06bc7-123">如果`reply subject name`提供属性，它用于 TIBCO Rendezvous 消息上设置答复主题。</span><span class="sxs-lookup"><span data-stu-id="06bc7-123">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="06bc7-124">假定的接收端口设置为侦听回复，并将其转发到 BizTalk Server 中，或某些其他 TIBCO Rendezvous 程序负责回复。</span><span class="sxs-lookup"><span data-stu-id="06bc7-124">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
  <span data-ttu-id="06bc7-125">三元数组 （服务、 守护程序、 网络） 组成传输配置。</span><span class="sxs-lookup"><span data-stu-id="06bc7-125">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="06bc7-126">一个空 （默认值） 传输配置导致通过默认传输对象发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="06bc7-126">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
  <span data-ttu-id="06bc7-127">如果代码页处于未指定，则适配器将使用 utf-8 编码 （代码页 65001）。</span><span class="sxs-lookup"><span data-stu-id="06bc7-127">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="06bc7-128">认证发送器端不支持消息。</span><span class="sxs-lookup"><span data-stu-id="06bc7-128">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06bc7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="06bc7-129">See Also</span></span>  
 <span data-ttu-id="06bc7-130">[创建发送端口](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="06bc7-130">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="06bc7-131">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="06bc7-131">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)