---
title: 发送保留的批交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9bc2207-e34d-4d06-a224-bd7f8e498c27
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 327ef8db3042199cc541d53402ea25c8d36b4a06
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399077"
---
# <a name="sending-a-preserved-batch-interchange"></a><span data-ttu-id="d178b-102">发送保留的批交换</span><span class="sxs-lookup"><span data-stu-id="d178b-102">Sending a Preserved Batch Interchange</span></span>
<span data-ttu-id="d178b-103">当 EDI 发送管道处理出站时保留的批处理交换时，它处理批的交换作为一个整体。</span><span class="sxs-lookup"><span data-stu-id="d178b-103">When the EDI send pipeline processes an outbound preserved batch interchange, it processes the batched interchange as a whole.</span></span> <span data-ttu-id="d178b-104">它通常重用现有信封 （控制） 段中创建 EDI 交换，而不应用基于协议的信封。</span><span class="sxs-lookup"><span data-stu-id="d178b-104">It normally reuses the existing envelope (control) segments in creating the EDI interchange, rather than applying an envelope based upon the agreement.</span></span> <span data-ttu-id="d178b-105">发生这种情况时**入站批处理选项**属性设置为**保留交换-出错时挂起交换**或**保留交换-挂起事务集错误**。</span><span class="sxs-lookup"><span data-stu-id="d178b-105">This occurs when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="schema-validation"></a><span data-ttu-id="d178b-106">架构验证</span><span class="sxs-lookup"><span data-stu-id="d178b-106">Schema Validation</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d178b-107">验证使用批架构和服务架构保留批的信封。</span><span class="sxs-lookup"><span data-stu-id="d178b-107">validates the envelope of a preserved batch using the batch schemas and the service schemas.</span></span> <span data-ttu-id="d178b-108">批架构用于验证保留消息; 的根节点服务架构用于验证交换、 组和事务集标头和尾部。</span><span class="sxs-lookup"><span data-stu-id="d178b-108">The batch schema is used to validate the root node of the preserved message; the service schemas are used to validate the interchange, group, and transaction set headers and trailers.</span></span> <span data-ttu-id="d178b-109">有关批架构的详细信息，请参阅[EDI 批架构](../core/edi-batch-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="d178b-109">For more information about the batch schemas, see [EDI Batch Schemas](../core/edi-batch-schemas.md).</span></span> <span data-ttu-id="d178b-110">服务架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="d178b-110">For more information on the service schemas, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d178b-111">验证在项目中使用文档架构的批处理交换中的文档。</span><span class="sxs-lookup"><span data-stu-id="d178b-111">validates the documents in a batched interchange using the document schemas in your project.</span></span>  
  
## <a name="send-side-processing"></a><span data-ttu-id="d178b-112">发送端处理</span><span class="sxs-lookup"><span data-stu-id="d178b-112">Send-Side Processing</span></span>  
 <span data-ttu-id="d178b-113">当 EDI 组装器处理保留的交换时，它通常使用相同的交换、 组和事务集标头时接收批处理交换中存在。</span><span class="sxs-lookup"><span data-stu-id="d178b-113">When the EDI Assembler processes a preserved interchange, it normally uses the same interchange, group, and transaction-set headers that existed in the batched interchange when it was received.</span></span>  
  
- <span data-ttu-id="d178b-114">对于 X12 交换，在单向协议选项卡中的不同页上的属性设置**协议属性**对话框中 (这将决定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将创建的传出的 ISA、 GS 和 ST 标头交换） 通常不适用。</span><span class="sxs-lookup"><span data-stu-id="d178b-114">For X12 interchanges, the property settings on different pages in the one-way agreement tab in the **Agreement Properties** dialog box (which determine how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will create the ISA, GS, and ST headers of an outgoing interchange) do not normally apply.</span></span>  
  
- <span data-ttu-id="d178b-115">对于 EDIFACT 交换，通常使用协议属性中的 UNA 设置。</span><span class="sxs-lookup"><span data-stu-id="d178b-115">For EDIFACT interchanges, the UNA settings in the agreement properties are normally used.</span></span> <span data-ttu-id="d178b-116">UNA 段中是可选的 EDIFACT 编码的消息，但它是必需的序列化保留的批交换。</span><span class="sxs-lookup"><span data-stu-id="d178b-116">The UNA segment is optional in an EDIFACT-encoded message, but it is required for serializing a preserved batch interchange.</span></span> <span data-ttu-id="d178b-117">如果没有 UNA 段中的 XML 实例的值，将使用发送管道组件的默认属性值。</span><span class="sxs-lookup"><span data-stu-id="d178b-117">If there is no value for the UNA segment in the XML instance, the default property values for the send pipeline component will be used.</span></span> <span data-ttu-id="d178b-118">如果发送管道组件属性值，则将挂起保留的批的中间 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d178b-118">If the send pipeline component properties are not valued, then the preserved batch intermediate XML message will be suspended.</span></span>  
  
- <span data-ttu-id="d178b-119">如果您将升级`EDI.PopulateInterchangeValues`上下文属性设置为"True"（在自定义组件中） 保留交换，发送端口中的 EdiAssembler 会将所有填充的交换、 组和事务集标头为协议中设置的值属性。</span><span class="sxs-lookup"><span data-stu-id="d178b-119">If you promote the `EDI.PopulateInterchangeValues` context property to "True" on the interchange being preserved (in a custom component), the EdiAssembler in the send port will populate all of the interchange, group, and transaction-set headers to the values set in the agreement properties.</span></span>  
  
- <span data-ttu-id="d178b-120">如果您将升级`EDIOverride.OverrideEdiHeader`上下文属性设置为"True"的交换的发送管道处理之前，您可以重写出站文档的信封值通过设置适当`EDIOverride`上下文属性值。</span><span class="sxs-lookup"><span data-stu-id="d178b-120">If you promote the `EDIOverride.OverrideEdiHeader` context property to “True” on the interchange before it is processed by the send pipeline, you can override the envelope values for the outbound document by setting the appropriate `EDIOverride` context property values.</span></span> <span data-ttu-id="d178b-121">有关详细信息，请参阅[替代 EDI 标头](../core/overriding-edi-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="d178b-121">For more information, see [Overriding EDI Headers](../core/overriding-edi-headers.md).</span></span>  
  
  <span data-ttu-id="d178b-122">对于保留的交换的没有任何错误，则组装器将会保留与交换的组和交换中的组的序列中的事务集的序列。</span><span class="sxs-lookup"><span data-stu-id="d178b-122">For a preserved interchange that has no errors, the Assembler will preserve the sequence of transaction sets in a group of the interchange and the sequence of groups in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d178b-123">您可以发送保留的批使用 XML 发送管道。</span><span class="sxs-lookup"><span data-stu-id="d178b-123">You can send a preserved batch with an XML send pipeline.</span></span> <span data-ttu-id="d178b-124">但是，若要执行此操作需要更改批架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d178b-124">However, to do so requires that you change the namespace for the batch schema.</span></span> <span data-ttu-id="d178b-125">有关详细信息，请参阅[使用 XML 发送管道发送保留批](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="d178b-125">For more information, see [Sending a Preserved Batch with an XML Send Pipeline](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md).</span></span>  
  
## <a name="error-processing"></a><span data-ttu-id="d178b-126">错误处理</span><span class="sxs-lookup"><span data-stu-id="d178b-126">Error Processing</span></span>  
 <span data-ttu-id="d178b-127">EDI 发送管道将批处理的 EDI 交换为保留批识别由于 XML 中的保留标记。</span><span class="sxs-lookup"><span data-stu-id="d178b-127">The EDI send pipeline recognizes a batched EDI interchange as a preserved batch because of a reserved tag in the XML.</span></span> <span data-ttu-id="d178b-128">此标记，或者\<X12InterchangeXml\>或\<EdifactInterchangeXml\>，应用于 XML 由 EDI 接收管道。</span><span class="sxs-lookup"><span data-stu-id="d178b-128">This tag, either \<X12InterchangeXml\> or \<EdifactInterchangeXml\>, is applied to the XML by the EDI receive pipeline.</span></span>  
  
 <span data-ttu-id="d178b-129">具有以下特殊情况适用于错误时挂起事务集：</span><span class="sxs-lookup"><span data-stu-id="d178b-129">The following special cases apply to suspending transaction sets on error:</span></span>  
  
-   <span data-ttu-id="d178b-130">如果在组中的所有事务都集将无效，则 EDI 发送管道将包含组控制段中生成的 EDI 中，但组将不包含任何事务都集 （因为它们将被删除）。</span><span class="sxs-lookup"><span data-stu-id="d178b-130">If all transaction sets in a group are invalid, then the EDI send pipeline will include group control segments in the generated EDI, but the group will not contain any transaction sets (because they will have been dropped).</span></span> <span data-ttu-id="d178b-131">组页脚总数更新为零。</span><span class="sxs-lookup"><span data-stu-id="d178b-131">The group footer totals are updated to zero.</span></span> <span data-ttu-id="d178b-132">交换控制段保持不变。</span><span class="sxs-lookup"><span data-stu-id="d178b-132">The interchange control segments remain unchanged.</span></span>  
  
-   <span data-ttu-id="d178b-133">如果交换中的所有事务集无效，然后交换控制段将仍包含在生成的 EDI 交换，但该交换将不包含任何事务集 （因为它们将被删除）。</span><span class="sxs-lookup"><span data-stu-id="d178b-133">If all transaction sets in an interchange are invalid, then the interchange control segments will still be included in the generated EDI interchange, but the interchange will not contain any transaction sets (because they will have been dropped).</span></span> <span data-ttu-id="d178b-134">这会构成一个空交换。</span><span class="sxs-lookup"><span data-stu-id="d178b-134">This would constitute an empty interchange.</span></span>  
  
-   <span data-ttu-id="d178b-135">如果组控制段或交换控制段无效，将生成的 EDI 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="d178b-135">If the group control segments or the interchange control segments are invalid, an EDI-encoded interchange will not be generated.</span></span> <span data-ttu-id="d178b-136">日志将创建在事件查看器，指示已拒绝交换。</span><span class="sxs-lookup"><span data-stu-id="d178b-136">A log will be created in the event viewer indicating that the interchange was rejected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d178b-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d178b-137">See Also</span></span>  
 [<span data-ttu-id="d178b-138">对传出 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="d178b-138">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)