---
title: 接收架构并处理事件与 TIBCO Rendezvous 适配器 |Microsoft Docs
description: 使用 TIBCO Rendezvous 架构在接收端，并使用 BizTalk Adapter for TIBCO Rendezvous BizTalk 中的事件处理
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d459ac2019ccf20edfd718815c7ee789a9089be5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302389"
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="60e3f-103">使用 TIBCO Rendezvous 从 BizTalk Server 接收端口</span><span class="sxs-lookup"><span data-stu-id="60e3f-103">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="60e3f-104">概述</span><span class="sxs-lookup"><span data-stu-id="60e3f-104">Overview</span></span>
<span data-ttu-id="60e3f-105">若要使用的接收端口，可以提供一个架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的传入消息。</span><span class="sxs-lookup"><span data-stu-id="60e3f-105">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="60e3f-106">接收端口配置为侦听一组特定的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="60e3f-106">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="60e3f-107">它使用具有可选通配符字符的使用者名称与多个使用者名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="60e3f-107">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="60e3f-108">定义不同的端口操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于每个可能的匹配给定的字符串的使用者的业务流程。</span><span class="sxs-lookup"><span data-stu-id="60e3f-108">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60e3f-109">该适配器支持业务流程和消息处理方案。</span><span class="sxs-lookup"><span data-stu-id="60e3f-109">The adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="define-schemas"></a><span data-ttu-id="60e3f-110">定义架构</span><span class="sxs-lookup"><span data-stu-id="60e3f-110">Define schemas</span></span>  
 <span data-ttu-id="60e3f-111">例如，如果该端口配置为侦听使用者名称，**股票。市场。索引。 >** ('**>** 是表示右侧任何内容的通配符字符)，它可以有效地定义使用者名称的操作如**股票。市场。索引。纽约证券交易所。与 SP500**，**股票。市场。索引。TSX.TSX60**，依次类推。</span><span class="sxs-lookup"><span data-stu-id="60e3f-111">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="60e3f-112">适配器生成消息使用的策略中所述[TIBCO Rendezvous 中的接收处理程序的数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)，并生成根元素名称和命名空间，侦听基于使用者名称和接收的消息使用者分别命名。</span><span class="sxs-lookup"><span data-stu-id="60e3f-112">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="60e3f-113">在上一示例中，适配器生成与 SP500 事件如下消息：</span><span class="sxs-lookup"><span data-stu-id="60e3f-113">In the previous example, the adapter generates a message that looks like the following for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="60e3f-114">必须定义使用相同的约定的架构。</span><span class="sxs-lookup"><span data-stu-id="60e3f-114">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="60e3f-115">例如：</span><span class="sxs-lookup"><span data-stu-id="60e3f-115">For example:</span></span>  
  
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
  
 <span data-ttu-id="60e3f-116">请注意，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**批注。</span><span class="sxs-lookup"><span data-stu-id="60e3f-116">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="60e3f-117">这是为了指示[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk 集成使用生成的.NET Framework 类型，该名称而不是包含点的名称。</span><span class="sxs-lookup"><span data-stu-id="60e3f-117">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="60e3f-118">您可以指定任何内容。</span><span class="sxs-lookup"><span data-stu-id="60e3f-118">You can specify anything.</span></span> <span data-ttu-id="60e3f-119">在示例中，点替换为下划线。</span><span class="sxs-lookup"><span data-stu-id="60e3f-119">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60e3f-120">点将导致无效的名称，若要生成的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发工具。</span><span class="sxs-lookup"><span data-stu-id="60e3f-120">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  

## <a name="event-processing"></a><span data-ttu-id="60e3f-121">事件处理</span><span class="sxs-lookup"><span data-stu-id="60e3f-121">Event processing</span></span>
<span data-ttu-id="60e3f-122">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器从队列中调度多个线程上的事件。</span><span class="sxs-lookup"><span data-stu-id="60e3f-122">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="60e3f-123">BizTalk Server 接收位置与一个 TIBCO Rendezvous 事件队列，以及自己的调度程序线程池相关联。</span><span class="sxs-lookup"><span data-stu-id="60e3f-123">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue, and its pool of dispatcher threads.</span></span>  
  
### <a name="memory-use-and-errors"></a><span data-ttu-id="60e3f-124">内存使用和错误</span><span class="sxs-lookup"><span data-stu-id="60e3f-124">Memory Use and Errors</span></span>  
 <span data-ttu-id="60e3f-125">处理事件时，适配器会监控所使用的资源情况。</span><span class="sxs-lookup"><span data-stu-id="60e3f-125">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="60e3f-126">如果内存使用量超出高水位，则适配器会停止调度事件，直至内存使用量达到低水位。</span><span class="sxs-lookup"><span data-stu-id="60e3f-126">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="60e3f-127">注意，对于未认证的消息，这会导致 TIBCO Rendezvous 消息丢失（TIBCO RV 使用者有 60 秒的时间将消息从队列中删除）。</span><span class="sxs-lookup"><span data-stu-id="60e3f-127">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="60e3f-128">此数据丢失会被报告为错误。</span><span class="sxs-lookup"><span data-stu-id="60e3f-128">This data loss is reported as an error.</span></span> <span data-ttu-id="60e3f-129">如果适配器收到 TIBCO Rendezvous 系统建议 NO_MEMORY 消息，则这些消息已经丢失。</span><span class="sxs-lookup"><span data-stu-id="60e3f-129">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="60e3f-130">用于 TIBCO Rendezvous 的 BizTalk 适配器会维持一种状态，并根据该状态的变化来执行任务。</span><span class="sxs-lookup"><span data-stu-id="60e3f-130">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="60e3f-131">如果 BizTalk 消息引擎报告错误，并且已将适配器配置为认证侦听器，则向 TIBCO Rendezvous 报告错误，以便可以重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="60e3f-131">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e3f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="60e3f-132">See Also</span></span>  
 <span data-ttu-id="60e3f-133">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="60e3f-133">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 <span data-ttu-id="60e3f-134">[数据类型映射中 TIBCO Rendezvous 接收处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="60e3f-134">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="60e3f-135">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="60e3f-135">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)