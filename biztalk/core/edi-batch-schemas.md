---
title: "批处理的 EDI 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9210e8ecc251cee06dafda3aeb3111074521be1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-batch-schemas"></a><span data-ttu-id="76631-102">批处理的 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="76631-102">EDI Batch Schemas</span></span>
<span data-ttu-id="76631-103">BizTalk Server 处理保留交换时，至少使用三个架构：</span><span class="sxs-lookup"><span data-stu-id="76631-103">When BizTalk Server processes a preserved interchange, it uses at least three schemas:</span></span>  
  
-   <span data-ttu-id="76631-104">批处理架构（交换 XML 架构）：用于验证保留的批处理交换（BaseArtifacts.dll 中部署的 X12_BatchSchema 或 Edifact_BatchSchema）的根节点。</span><span class="sxs-lookup"><span data-stu-id="76631-104">The batch schemas (Interchange XML schemas) to validate the root node of the preserved batched interchange (X12_BatchSchema or Edifact_BatchSchema deployed in BaseArtifacts.dll)</span></span>  
  
-   <span data-ttu-id="76631-105">信封服务架构：用于验证交换、组、事务集标头和尾部（BaseArtifacts.dll 中部署的 X12ServiceSchema 或 EdifactServiceSchema）。</span><span class="sxs-lookup"><span data-stu-id="76631-105">The envelope service schemas to validate the interchange, gorup, and transaction set headers and trailers (X12ServiceSchema or EdifactServiceSchema deployed in BaseArtifacts.dll).</span></span> <span data-ttu-id="76631-106">有关详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="76631-106">For more information, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
-   <span data-ttu-id="76631-107">文档架构：用于批处理交换中的每个文档类型（部署在项目中）。</span><span class="sxs-lookup"><span data-stu-id="76631-107">Document schemas for each document type in the batched interchange (deployed in your project).</span></span> <span data-ttu-id="76631-108">有关详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="76631-108">For more information, see [EDI Document Schemas](../core/edi-document-schemas.md).</span></span>  
  
 <span data-ttu-id="76631-109">批处理架构在运行时用于验证保留的入站和出站批处理交换。</span><span class="sxs-lookup"><span data-stu-id="76631-109">Batch schemas are used at runtime to validate inbound and outbound batched interchanges that are being preserved.</span></span> <span data-ttu-id="76631-110">批处理架构也用于在设计时验证和生成消息实例。</span><span class="sxs-lookup"><span data-stu-id="76631-110">Batch schemas are also used at design time to validate and generate message instances.</span></span>  
  
## <a name="batch-schemas-used-at-runtime"></a><span data-ttu-id="76631-111">运行时使用的批处理架构</span><span class="sxs-lookup"><span data-stu-id="76631-111">Batch Schemas Used at Runtime</span></span>  
 <span data-ttu-id="76631-112">存在两个规范版本的批处理架构： X12_BatchSchema.xsd 的 X12 编码和 EDIFACT_BatchSchema.xsd EDIFACT 编码。</span><span class="sxs-lookup"><span data-stu-id="76631-112">Two canonical versions of the batch schemas exist: X12_BatchSchema.xsd for X12 encoding and EDIFACT_BatchSchema.xsd for EDIFACT encoding.</span></span> <span data-ttu-id="76631-113">这些架构是包括控制段的模板。</span><span class="sxs-lookup"><span data-stu-id="76631-113">These schemas are templates that include the control segment.</span></span> <span data-ttu-id="76631-114">这些架构具有以下根名称和命名空间：</span><span class="sxs-lookup"><span data-stu-id="76631-114">These schemas have the following root names and namespaces:</span></span>  
  
|<span data-ttu-id="76631-115">架构</span><span class="sxs-lookup"><span data-stu-id="76631-115">Schema</span></span>|<span data-ttu-id="76631-116">根节点</span><span class="sxs-lookup"><span data-stu-id="76631-116">Root Node</span></span>|<span data-ttu-id="76631-117">命名空间</span><span class="sxs-lookup"><span data-stu-id="76631-117">Namespace</span></span>|  
|------------|---------------|---------------|  
|<span data-ttu-id="76631-118">X12_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="76631-118">X12_BatchSchema</span></span>|<span data-ttu-id="76631-119">X12InterchangeXML</span><span class="sxs-lookup"><span data-stu-id="76631-119">X12InterchangeXML</span></span>|<span data-ttu-id="76631-120">http://schemas.microsoft.com/Edi/X12_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="76631-120">http://schemas.microsoft.com/Edi/X12_BatchSchema</span></span>|  
|<span data-ttu-id="76631-121">Edifact_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="76631-121">Edifact_BatchSchema</span></span>|<span data-ttu-id="76631-122">EdifactInterchangeXML</span><span class="sxs-lookup"><span data-stu-id="76631-122">EdifactInterchangeXML</span></span>|<span data-ttu-id="76631-123">http://schemas.microsoft.com/Edi/Edifact</span><span class="sxs-lookup"><span data-stu-id="76631-123">http://schemas.microsoft.com/Edi/Edifact</span></span>|  
  
 <span data-ttu-id="76631-124">在由接收管道生成的 XML 实例上的文档类型将是一个常量 (\<编码 > _BatchSchema.xml) 并将引用此规范的架构。</span><span class="sxs-lookup"><span data-stu-id="76631-124">The document type on the XML instance generated by the receive pipeline will be a constant (\<Encoding>_BatchSchema.xml) and will reference this canonical schema.</span></span> <span data-ttu-id="76631-125">可以在业务流程的映射中使用该实例，但是，在进行此操作前，必须更改其文档类型和命名空间以映射到所需的实际架构。</span><span class="sxs-lookup"><span data-stu-id="76631-125">You can use this instance in a map in an orchestration; however, before doing so you have to change the document type and namespace to map to the actual schema required.</span></span>  
  
 <span data-ttu-id="76631-126">在设计项目时不必指定批处理架构，因为该架构部署在 BaseArtifacts.dll 中。</span><span class="sxs-lookup"><span data-stu-id="76631-126">You do not need to specify the batch schema at design time in the project, because it is deployed in BaseArtifacts.dll.</span></span>  
  
## <a name="batch-schemas-in-the-schema-store"></a><span data-ttu-id="76631-127">架构存储中的批处理架构</span><span class="sxs-lookup"><span data-stu-id="76631-127">Batch Schemas in the Schema Store</span></span>  
 <span data-ttu-id="76631-128">BizTalk Server 在运行时用于处理保留批处理的批处理架构部署在 BaseArtifacts.dll 程序集中。</span><span class="sxs-lookup"><span data-stu-id="76631-128">The batch schemas that BizTalk Server uses at runtime to process preserved batches are deployed in the BaseArtifacts.dll assembly.</span></span> <span data-ttu-id="76631-129">这些架构可自动用于运行时处理。</span><span class="sxs-lookup"><span data-stu-id="76631-129">These are automatically available for run-time processing.</span></span> <span data-ttu-id="76631-130">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 上的 BizTalk 架构存储中也将提供 Edifact_BatchSchema 和 X12_BatchSchema。</span><span class="sxs-lookup"><span data-stu-id="76631-130">Edifact_BatchSchema and X12_BatchSchema are also available in the BizTalk schema store at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="76631-131">这些架构中的每个架构仅在设计时用于验证或生成交换。</span><span class="sxs-lookup"><span data-stu-id="76631-131">Each of these schemas is only used at design time to validate or generate the interchange.</span></span> <span data-ttu-id="76631-132">在接收管道或发动管道中，运行时进行验证不需要任何架构。</span><span class="sxs-lookup"><span data-stu-id="76631-132">Neither schema is required for validation in the receive pipeline or send pipeline at runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76631-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76631-133">See Also</span></span>  
 <span data-ttu-id="76631-134">[EDI 架构](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="76631-134">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="76631-135">处理传入的批次</span><span class="sxs-lookup"><span data-stu-id="76631-135">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)