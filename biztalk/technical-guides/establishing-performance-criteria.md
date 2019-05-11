---
title: 建立性能标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 181011d1-aa74-43fe-b05a-30b043956d70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6cd5c7b733ec85eb08acdc506d816d1a3fb1ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305656"
---
# <a name="establishing-performance-criteria"></a><span data-ttu-id="514e5-102">建立性能标准</span><span class="sxs-lookup"><span data-stu-id="514e5-102">Establishing Performance Criteria</span></span>
<span data-ttu-id="514e5-103">BizTalk Server 解决方案的性能目标通常划分为两个类别、 吞吐量或延迟之一。</span><span class="sxs-lookup"><span data-stu-id="514e5-103">The performance goals of a BizTalk Server solution typically fall into one of two categories, throughput or latency.</span></span> <span data-ttu-id="514e5-104">本主题介绍评估吞吐量或延迟的 BizTalk Server 解决方案时应考虑的因素。</span><span class="sxs-lookup"><span data-stu-id="514e5-104">This topic describes the factors that should be considered when evaluating the throughput or latency of a BizTalk Server solution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="514e5-105">优化吞吐量或延迟的 BizTalk Server 解决方案通常表示冲突的目标。</span><span class="sxs-lookup"><span data-stu-id="514e5-105">Optimizing throughput or latency of a BizTalk Server solution often represents conflicting goals.</span></span> <span data-ttu-id="514e5-106">例如，可能会提高吞吐量的文件接收适配器的增加批大小，但这样做会减少延迟。</span><span class="sxs-lookup"><span data-stu-id="514e5-106">For example, you might improve the throughput of the file receive adapter by increasing the batch size, but doing so would reduce latency.</span></span> <span data-ttu-id="514e5-107">在此方案中，适配器长积累更大的批大小，这反过来将减少在某个给定消息的端到端延迟的消息。</span><span class="sxs-lookup"><span data-stu-id="514e5-107">In this scenario the adapter takes longer to accumulate messages for a larger batch size, which in turn will reduce end-to-end latency for a given message.</span></span>  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a><span data-ttu-id="514e5-108">因素会影响 BizTalk Server 解决方案的吞吐量</span><span class="sxs-lookup"><span data-stu-id="514e5-108">Factors affecting throughput of a BizTalk Server solution</span></span>  
 <span data-ttu-id="514e5-109">**吞吐量**-广泛测量作为 BizTalk Server 解决方案可以处理某个给定的时间间隔内的文档数。</span><span class="sxs-lookup"><span data-stu-id="514e5-109">**Throughput**- Broadly measured as the number of documents that a BizTalk Server solution can process within a given time interval.</span></span>  
  
 <span data-ttu-id="514e5-110">会影响吞吐量的因素包括：</span><span class="sxs-lookup"><span data-stu-id="514e5-110">Factors that affect throughput include:</span></span>  
  
-   <span data-ttu-id="514e5-111">**消息大小**– 更大的消息使用更多开销较小的消息，高于，尤其是使用映射转换和非常大，以便向文件系统映射操作期间缓冲消息。</span><span class="sxs-lookup"><span data-stu-id="514e5-111">**Message size** – Larger messages consume more overhead than smaller messages, especially if the messages are transformed with a map and are large enough so that they are buffered to the file system during the mapping operation.</span></span> <span data-ttu-id="514e5-112">消息大小如何影响 BizTalk Server 性能的详细信息，请参阅[如何 BizTalk Server 处理大消息](http://go.microsoft.com/fwlink/?LinkId=139293)(http://go.microsoft.com/fwlink/?LinkId=139293)。</span><span class="sxs-lookup"><span data-stu-id="514e5-112">For more information about how message size affects BizTalk Server performance, see [How BizTalk Server Processes Large Messages](http://go.microsoft.com/fwlink/?LinkId=139293) (http://go.microsoft.com/fwlink/?LinkId=139293).</span></span>  
  
-   <span data-ttu-id="514e5-113">**消息格式**-消息接收到 BizTalk Server 在两种主要格式、 XML 文件或平面文件之一。</span><span class="sxs-lookup"><span data-stu-id="514e5-113">**Message format** - Messages are received into BizTalk Server in one of two primary formats, XML files or flat files.</span></span> <span data-ttu-id="514e5-114">因为平面文件必须转换为要由 BizTalk 消息引擎处理的 XML 格式，额外的开销不会引起的平面文件处理。</span><span class="sxs-lookup"><span data-stu-id="514e5-114">Because flat files must be translated into the XML format to be processed by the BizTalk Messaging engine, additional overhead is incurred by the processing of flat files.</span></span>  
  
-   <span data-ttu-id="514e5-115">**适配器要求**– 不同适配器经常包含不同的性能功能。</span><span class="sxs-lookup"><span data-stu-id="514e5-115">**Adapter requirements** – Different adapters frequently have varying performance capabilities.</span></span> <span data-ttu-id="514e5-116">例如，要求 MSDTC 事务支持的适配器将产生与不使用 MSDTC 事务的适配器相比其他开销/降低性能。</span><span class="sxs-lookup"><span data-stu-id="514e5-116">For example, adapters that require MSDTC transaction support will incur additional overhead/reduced performance as compared to an adapter that does not use MSDTC transactions.</span></span> <span data-ttu-id="514e5-117">根据您的贸易合作伙伴的要求和/或内部的业务需求而异 BizTalk 解决方案所使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="514e5-117">Adapters used by the BizTalk solution will vary depending on your trading partner’s requirements and/or internal business needs.</span></span>  
  
-   <span data-ttu-id="514e5-118">**业务流程处理要求**– 业务流程提供用于封装极大的灵活性，并将业务流程应用于消息接收到 biztalk。</span><span class="sxs-lookup"><span data-stu-id="514e5-118">**Orchestration processing requirements** – Orchestrations provide great flexibility for encapsulating and applying business processes to messages received by BizTalk.</span></span> <span data-ttu-id="514e5-119">同时，业务流程使用估计的 BizTalk Server 解决方案的吞吐量时，必须考虑的开销。</span><span class="sxs-lookup"><span data-stu-id="514e5-119">At the same time, orchestrations consume overhead, which must be considered when estimating the throughput of a BizTalk Server solution.</span></span>  
  
-   <span data-ttu-id="514e5-120">**峰值负载要求**– 大多数文档处理不一定会发生以测量的有序方式。</span><span class="sxs-lookup"><span data-stu-id="514e5-120">**Peak load requirements** – Most document processing does not necessarily occur in a measured orderly fashion.</span></span> <span data-ttu-id="514e5-121">例如，BizTalk Server 解决方案而可能承受其在营业日结束位置的处理负荷很大百分比。</span><span class="sxs-lookup"><span data-stu-id="514e5-121">For example, a BizTalk Server solution may sustain a large percentage of its processing load at the close of a business day.</span></span> <span data-ttu-id="514e5-122">因此峰值负载要求和 BizTalk Server 解决方案的最大可承受吞吐量 (MST) 应考虑建立吞吐量条件时。</span><span class="sxs-lookup"><span data-stu-id="514e5-122">Therefore peak load requirements and the Maximum Sustainable Throughput (MST) of a BizTalk Server solution should be taken into account when establishing throughput criteria.</span></span> <span data-ttu-id="514e5-123">有关度量 MST 的 BizTalk Server 解决方案的详细信息，请参阅[测量最大可承受引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)和[测量最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).</span><span class="sxs-lookup"><span data-stu-id="514e5-123">For more information about measuring the MST of a BizTalk Server solution, see [Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388) and [Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).</span></span>  
  
-   <span data-ttu-id="514e5-124">**文档跟踪要求**– 文档跟踪会产生在系统上的其他开销。</span><span class="sxs-lookup"><span data-stu-id="514e5-124">**Document tracking requirements** – Document tracking imposes additional overhead on the system.</span></span> <span data-ttu-id="514e5-125">估计的 BizTalk 解决方案的吞吐量目标时，文档跟踪要求应为一个主要考虑因素。</span><span class="sxs-lookup"><span data-stu-id="514e5-125">Document tracking requirements should be a primary consideration when estimating the throughput goals of a BizTalk solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514e5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="514e5-126">See Also</span></span>  
 [<span data-ttu-id="514e5-127">BizTalk Server 性能测试方法</span><span class="sxs-lookup"><span data-stu-id="514e5-127">BizTalk Server Performance Testing Methodology</span></span>](../technical-guides/biztalk-server-performance-testing-methodology.md)