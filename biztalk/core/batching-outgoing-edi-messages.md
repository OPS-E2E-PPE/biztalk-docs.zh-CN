---
title: "对传出的 EDI 消息进行批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f95ed755dcc709084d52c6fb8b207e9bbd9e866d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batching-outgoing-edi-messages"></a><span data-ttu-id="74412-102">对传出 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="74412-102">Batching Outgoing EDI Messages</span></span>
<span data-ttu-id="74412-103">如果已为协议（与将接收它的业务合作伙伴相关联）启用了批处理，则 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将对 EDI 事务集进行批处理。</span><span class="sxs-lookup"><span data-stu-id="74412-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will batch EDI transaction sets if batching has been enabled for the agreement associated with the business partner that will be receiving it.</span></span> <span data-ttu-id="74412-104">使用协议的 EDI 属性可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74412-104">The EDI properties for an agreement enable you to do the following:</span></span>  
  
-   <span data-ttu-id="74412-105">定义多个传出批处理</span><span class="sxs-lookup"><span data-stu-id="74412-105">Define multiple outgoing batches</span></span>  
  
-   <span data-ttu-id="74412-106">定义交换</span><span class="sxs-lookup"><span data-stu-id="74412-106">Define the interchange</span></span>  
  
-   <span data-ttu-id="74412-107">定义交换中的组</span><span class="sxs-lookup"><span data-stu-id="74412-107">Define the groups in the interchange</span></span>  
  
-   <span data-ttu-id="74412-108">设置批处理发布条件</span><span class="sxs-lookup"><span data-stu-id="74412-108">Set the batch release criteria</span></span>  
  
-   <span data-ttu-id="74412-109">设置批处理激活条件。</span><span class="sxs-lookup"><span data-stu-id="74412-109">Set the batch activation criteria.</span></span>  
  
 <span data-ttu-id="74412-110">Microsoft [!INCLUDE[prague](../includes/prague-md.md)] EDI 和 AS2 启用 EDI 交换以下处理：</span><span class="sxs-lookup"><span data-stu-id="74412-110">Microsoft [!INCLUDE[prague](../includes/prague-md.md)] EDI and AS2 enables the following processing of EDI interchanges:</span></span>  
  
-   <span data-ttu-id="74412-111">EDI 交换可以包含事务集和/或确认。</span><span class="sxs-lookup"><span data-stu-id="74412-111">EDI interchanges can include transaction sets and/or acknowledgments.</span></span>  
  
-   <span data-ttu-id="74412-112">EDI 接收管道可以拆分到 XML 事务集，以做进一步的处理的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，或者它可以保留交换，将通过其传递[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在其收到的窗体中。</span><span class="sxs-lookup"><span data-stu-id="74412-112">The EDI receive pipeline can split an interchange into XML transaction sets for further processing by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], or it can preserve the interchange, passing it through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in its received form.</span></span>  
  
-   <span data-ttu-id="74412-113">EDI 路由业务流程使[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行批处理设置多个传出交换到单个事务。</span><span class="sxs-lookup"><span data-stu-id="74412-113">The EDI routing orchestration enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to batch a single transaction set into more than one outgoing interchange.</span></span>  
  
-   <span data-ttu-id="74412-114">批处理业务流程的 EDI 组合 XML 事务集成的 EDI 交换中，并验证和提供根据协议的 EDI 属性交换。</span><span class="sxs-lookup"><span data-stu-id="74412-114">The EDI batching orchestration assembles XML transaction sets into an EDI interchange, and validates and delivers the interchange according to an agreement's EDI properties.</span></span>  
  
 <span data-ttu-id="74412-115">EDI 批处理（又称为交换）包含消息组，而消息组包含各个消息。</span><span class="sxs-lookup"><span data-stu-id="74412-115">EDI batches, called interchanges, contain message groups, and message groups contain individual messages.</span></span> <span data-ttu-id="74412-116">传出批处理可包含多个组，不过每一种文档类型只允许有一个组。</span><span class="sxs-lookup"><span data-stu-id="74412-116">Outgoing batches can include multiple groups, but only one group per document type.</span></span> <span data-ttu-id="74412-117">组中可以包含多个事务集，但每个事务集必须属于相同的文档类型。</span><span class="sxs-lookup"><span data-stu-id="74412-117">A group can contain multiple transaction sets, but each must have the same document type.</span></span> <span data-ttu-id="74412-118">消息信封用于包装各个事务集、各个组和整个交换。</span><span class="sxs-lookup"><span data-stu-id="74412-118">Message envelopes are used to wrap individual transaction sets, individual groups, and the entire interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74412-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="74412-119">In This Section</span></span>  
  
-   [<span data-ttu-id="74412-120">配置传出批处理</span><span class="sxs-lookup"><span data-stu-id="74412-120">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
  
-   [<span data-ttu-id="74412-121">组合批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="74412-121">Assembling a Batched EDI Interchange</span></span>](../core/assembling-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="74412-122">发送保留的批处理交换</span><span class="sxs-lookup"><span data-stu-id="74412-122">Sending a Preserved Batch Interchange</span></span>](../core/sending-a-preserved-batch-interchange.md)