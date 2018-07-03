---
title: EDI 批处理架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a25391fbc42b8e368a44f652ae691ff8bc2722dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999222"
---
# <a name="edi-batch-schemas"></a><span data-ttu-id="d0972-102">EDI 批处理架构</span><span class="sxs-lookup"><span data-stu-id="d0972-102">EDI Batch Schemas</span></span>
<span data-ttu-id="d0972-103">BizTalk Server 处理保留交换时，至少使用三个架构：</span><span class="sxs-lookup"><span data-stu-id="d0972-103">When BizTalk Server processes a preserved interchange, it uses at least three schemas:</span></span>  

- <span data-ttu-id="d0972-104">批处理架构（交换 XML 架构）：用于验证保留的批处理交换（BaseArtifacts.dll 中部署的 X12_BatchSchema 或 Edifact_BatchSchema）的根节点。</span><span class="sxs-lookup"><span data-stu-id="d0972-104">The batch schemas (Interchange XML schemas) to validate the root node of the preserved batched interchange (X12_BatchSchema or Edifact_BatchSchema deployed in BaseArtifacts.dll)</span></span>  

- <span data-ttu-id="d0972-105">信封服务架构：用于验证交换、组、事务集标头和尾部（BaseArtifacts.dll 中部署的 X12ServiceSchema 或 EdifactServiceSchema）。</span><span class="sxs-lookup"><span data-stu-id="d0972-105">The envelope service schemas to validate the interchange, gorup, and transaction set headers and trailers (X12ServiceSchema or EdifactServiceSchema deployed in BaseArtifacts.dll).</span></span> <span data-ttu-id="d0972-106">有关详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="d0972-106">For more information, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  

- <span data-ttu-id="d0972-107">文档架构：用于批处理交换中的每个文档类型（部署在项目中）。</span><span class="sxs-lookup"><span data-stu-id="d0972-107">Document schemas for each document type in the batched interchange (deployed in your project).</span></span> <span data-ttu-id="d0972-108">有关详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="d0972-108">For more information, see [EDI Document Schemas](../core/edi-document-schemas.md).</span></span>  

  <span data-ttu-id="d0972-109">批处理架构在运行时用于验证保留的入站和出站批处理交换。</span><span class="sxs-lookup"><span data-stu-id="d0972-109">Batch schemas are used at runtime to validate inbound and outbound batched interchanges that are being preserved.</span></span> <span data-ttu-id="d0972-110">批处理架构也用于在设计时验证和生成消息实例。</span><span class="sxs-lookup"><span data-stu-id="d0972-110">Batch schemas are also used at design time to validate and generate message instances.</span></span>  

## <a name="batch-schemas-used-at-runtime"></a><span data-ttu-id="d0972-111">运行时使用的批处理架构</span><span class="sxs-lookup"><span data-stu-id="d0972-111">Batch Schemas Used at Runtime</span></span>  
 <span data-ttu-id="d0972-112">存在两个规范版本的批处理架构： X12 的 X12_BatchSchema.xsd 编码和用于 EDIFACT 编码的 EDIFACT_BatchSchema.xsd。</span><span class="sxs-lookup"><span data-stu-id="d0972-112">Two canonical versions of the batch schemas exist: X12_BatchSchema.xsd for X12 encoding and EDIFACT_BatchSchema.xsd for EDIFACT encoding.</span></span> <span data-ttu-id="d0972-113">这些架构是包括控制段的模板。</span><span class="sxs-lookup"><span data-stu-id="d0972-113">These schemas are templates that include the control segment.</span></span> <span data-ttu-id="d0972-114">这些架构具有以下根名称和命名空间：</span><span class="sxs-lookup"><span data-stu-id="d0972-114">These schemas have the following root names and namespaces:</span></span>  


|       <span data-ttu-id="d0972-115">架构</span><span class="sxs-lookup"><span data-stu-id="d0972-115">Schema</span></span>        |       <span data-ttu-id="d0972-116">根节点</span><span class="sxs-lookup"><span data-stu-id="d0972-116">Root Node</span></span>       |                    <span data-ttu-id="d0972-117">命名空间</span><span class="sxs-lookup"><span data-stu-id="d0972-117">Namespace</span></span>                     |
|---------------------|-----------------------|--------------------------------------------------|
|   <span data-ttu-id="d0972-118">X12_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="d0972-118">X12_BatchSchema</span></span>   |   <span data-ttu-id="d0972-119">X12InterchangeXML</span><span class="sxs-lookup"><span data-stu-id="d0972-119">X12InterchangeXML</span></span>   | http://schemas.microsoft.com/Edi/X12_BatchSchema |
| <span data-ttu-id="d0972-120">Edifact_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="d0972-120">Edifact_BatchSchema</span></span> | <span data-ttu-id="d0972-121">EdifactInterchangeXML</span><span class="sxs-lookup"><span data-stu-id="d0972-121">EdifactInterchangeXML</span></span> |     http://schemas.microsoft.com/Edi/Edifact     |

 <span data-ttu-id="d0972-122">由接收管道生成的 XML 实例上的文档类型将是一个常量 (\<编码\>_BatchSchema.xml) 并将引用此规范架构。</span><span class="sxs-lookup"><span data-stu-id="d0972-122">The document type on the XML instance generated by the receive pipeline will be a constant (\<Encoding\>_BatchSchema.xml) and will reference this canonical schema.</span></span> <span data-ttu-id="d0972-123">可以在业务流程的映射中使用该实例，但是，在进行此操作前，必须更改其文档类型和命名空间以映射到所需的实际架构。</span><span class="sxs-lookup"><span data-stu-id="d0972-123">You can use this instance in a map in an orchestration; however, before doing so you have to change the document type and namespace to map to the actual schema required.</span></span>  

 <span data-ttu-id="d0972-124">在设计项目时不必指定批处理架构，因为该架构部署在 BaseArtifacts.dll 中。</span><span class="sxs-lookup"><span data-stu-id="d0972-124">You do not need to specify the batch schema at design time in the project, because it is deployed in BaseArtifacts.dll.</span></span>  

## <a name="batch-schemas-in-the-schema-store"></a><span data-ttu-id="d0972-125">架构存储中的批处理架构</span><span class="sxs-lookup"><span data-stu-id="d0972-125">Batch Schemas in the Schema Store</span></span>  
 <span data-ttu-id="d0972-126">BizTalk Server 在运行时用于处理保留批处理的批处理架构部署在 BaseArtifacts.dll 程序集中。</span><span class="sxs-lookup"><span data-stu-id="d0972-126">The batch schemas that BizTalk Server uses at runtime to process preserved batches are deployed in the BaseArtifacts.dll assembly.</span></span> <span data-ttu-id="d0972-127">这些架构可自动用于运行时处理。</span><span class="sxs-lookup"><span data-stu-id="d0972-127">These are automatically available for run-time processing.</span></span> <span data-ttu-id="d0972-128">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 上的 BizTalk 架构存储中也将提供 Edifact_BatchSchema 和 X12_BatchSchema。</span><span class="sxs-lookup"><span data-stu-id="d0972-128">Edifact_BatchSchema and X12_BatchSchema are also available in the BizTalk schema store at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="d0972-129">这些架构中的每个架构仅在设计时用于验证或生成交换。</span><span class="sxs-lookup"><span data-stu-id="d0972-129">Each of these schemas is only used at design time to validate or generate the interchange.</span></span> <span data-ttu-id="d0972-130">在接收管道或发动管道中，运行时进行验证不需要任何架构。</span><span class="sxs-lookup"><span data-stu-id="d0972-130">Neither schema is required for validation in the receive pipeline or send pipeline at runtime.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d0972-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0972-131">See Also</span></span>  
 <span data-ttu-id="d0972-132">[EDI 架构](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="d0972-132">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="d0972-133">处理传入批</span><span class="sxs-lookup"><span data-stu-id="d0972-133">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)