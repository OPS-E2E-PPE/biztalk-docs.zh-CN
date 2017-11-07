---
title: "接收架构和处理事件的 TIBCO 会合适配器 |Microsoft 文档"
description: "适用于 TIBCO 会合架构上接收端，并使用适用于在 BizTalk TIBCO 会合 BizTalk 适配器的事件处理"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbbae69dc1b7df1f5675442dde544a444cec02fb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="e1d7a-103">使用 TIBCO Rendezvous 从 BizTalk Server 接收端口</span><span class="sxs-lookup"><span data-stu-id="e1d7a-103">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="e1d7a-104">概述</span><span class="sxs-lookup"><span data-stu-id="e1d7a-104">Overview</span></span>
<span data-ttu-id="e1d7a-105">若要使用接收端口，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中为传入消息提供一个架构。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-105">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="e1d7a-106">随后，将接收端口配置为侦听一组特定的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-106">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="e1d7a-107">它使用具有可选通配符字符的使用者名称与多个使用者名称匹配。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-107">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="e1d7a-108">您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程中为匹配给定字符串的每个可能使用者配置不同的端口操作。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-108">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1d7a-109">适配器支持业务流程和消息传送方案。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-109">The adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="define-schemas"></a><span data-ttu-id="e1d7a-110">定义的架构</span><span class="sxs-lookup"><span data-stu-id="e1d7a-110">Define schemas</span></span>  
 <span data-ttu-id="e1d7a-111">例如，如果端口被配置为侦听为使用者名称中，**库存。市场。索引。 >** (**>**意味着其他右侧的通配符)，它将有效地定义使用者名称的操作，如**库存。市场。索引。纽约证券交易所。SP500**，**库存。市场。索引。TSX.TSX60**，依次类推。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-111">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="e1d7a-112">适配器生成使用的策略中所述的消息[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)，并生成的根元素名称和命名空间上侦听基于使用者名称和收到的消息使用者名称分别。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-112">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="e1d7a-113">在前面的示例中，适配器生成一条消息，如下所示为 SP500 事件：</span><span class="sxs-lookup"><span data-stu-id="e1d7a-113">In the previous example, the adapter generates a message that looks like the following for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="e1d7a-114">你必须定义使用相同的约定的架构。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-114">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="e1d7a-115">例如：</span><span class="sxs-lookup"><span data-stu-id="e1d7a-115">For example:</span></span>  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="e1d7a-116">请注意，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**批注。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-116">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="e1d7a-117">这指示 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk 集成使用生成 .NET Framework 类型的名称，而非包含点的名称。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-117">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="e1d7a-118">您可以指定任何内容：</span><span class="sxs-lookup"><span data-stu-id="e1d7a-118">You can specify anything.</span></span> <span data-ttu-id="e1d7a-119">在示例中，点替换为下划线。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-119">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1d7a-120">因为，点将导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发工具生成无效的名称。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-120">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  

## <a name="event-processing"></a><span data-ttu-id="e1d7a-121">事件处理</span><span class="sxs-lookup"><span data-stu-id="e1d7a-121">Event processing</span></span>
<span data-ttu-id="e1d7a-122">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器从队列中调度多个线程上的事件。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-122">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="e1d7a-123">BizTalk Server 接收位置与一个 TIBCO 会合事件队列和自己的调度程序线程池相关联。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-123">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue, and its pool of dispatcher threads.</span></span>  
  
### <a name="memory-use-and-errors"></a><span data-ttu-id="e1d7a-124">内存使用和错误</span><span class="sxs-lookup"><span data-stu-id="e1d7a-124">Memory Use and Errors</span></span>  
 <span data-ttu-id="e1d7a-125">处理事件时，适配器会监控所使用的资源情况。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-125">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="e1d7a-126">如果内存使用量超出高水位，则适配器会停止调度事件，直至内存使用量达到低水位。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-126">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="e1d7a-127">注意，对于未认证的消息，这会导致 TIBCO Rendezvous 消息丢失（TIBCO RV 使用者有 60 秒的时间将消息从队列中删除）。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-127">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="e1d7a-128">此数据丢失会被报告为错误。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-128">This data loss is reported as an error.</span></span> <span data-ttu-id="e1d7a-129">如果适配器收到 TIBCO Rendezvous 系统建议 NO_MEMORY 消息，则这些消息已经丢失。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-129">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="e1d7a-130">用于 TIBCO Rendezvous 的 BizTalk 适配器会维持一种状态，并根据该状态的变化来执行任务。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-130">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="e1d7a-131">如果 BizTalk 消息引擎报告错误，并且已将适配器配置为认证侦听器，则向 TIBCO Rendezvous 报告错误，以便可以重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="e1d7a-131">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d7a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1d7a-132">See Also</span></span>  
 <span data-ttu-id="e1d7a-133">[TIBCO 会合概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="e1d7a-133">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 <span data-ttu-id="e1d7a-134">[数据类型映射中 TIBCO 会合接收处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="e1d7a-134">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="e1d7a-135">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="e1d7a-135">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)