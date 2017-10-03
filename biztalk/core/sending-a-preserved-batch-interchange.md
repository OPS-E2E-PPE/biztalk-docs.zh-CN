---
title: "发送保留的批处理交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9bc2207-e34d-4d06-a224-bd7f8e498c27
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22572f01f1e76dae36cbdcb34a4321c2db1c44c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sending-a-preserved-batch-interchange"></a><span data-ttu-id="8d32f-102">发送保留的批交换</span><span class="sxs-lookup"><span data-stu-id="8d32f-102">Sending a Preserved Batch Interchange</span></span>
<span data-ttu-id="8d32f-103">当 EDI 发送管道处理保留的出站批交换时，会将批交换作为一个整体来处理。</span><span class="sxs-lookup"><span data-stu-id="8d32f-103">When the EDI send pipeline processes an outbound preserved batch interchange, it processes the batched interchange as a whole.</span></span> <span data-ttu-id="8d32f-104">在创建 EDI 交换时，它通常重用现有信封（控制）段，而不会基于协议应用信封。</span><span class="sxs-lookup"><span data-stu-id="8d32f-104">It normally reuses the existing envelope (control) segments in creating the EDI interchange, rather than applying an envelope based upon the agreement.</span></span> <span data-ttu-id="8d32f-105">发生这种情况时**入站批处理选项**属性设置为**保留交换-出错时暂停交换**或**保留交换-时暂停事务集错误**。</span><span class="sxs-lookup"><span data-stu-id="8d32f-105">This occurs when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="schema-validation"></a><span data-ttu-id="8d32f-106">架构验证</span><span class="sxs-lookup"><span data-stu-id="8d32f-106">Schema Validation</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8d32f-107">验证的信封中使用批处理架构和服务架构保留批处理。</span><span class="sxs-lookup"><span data-stu-id="8d32f-107"> validates the envelope of a preserved batch using the batch schemas and the service schemas.</span></span> <span data-ttu-id="8d32f-108">批架构用于验证保留消息的根节点；服务架构用于验证交换、组和事务集标头及尾部。</span><span class="sxs-lookup"><span data-stu-id="8d32f-108">The batch schema is used to validate the root node of the preserved message; the service schemas are used to validate the interchange, group, and transaction set headers and trailers.</span></span> <span data-ttu-id="8d32f-109">有关批处理架构的详细信息，请参阅[批处理的 EDI 架构](../core/edi-batch-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="8d32f-109">For more information about the batch schemas, see [EDI Batch Schemas](../core/edi-batch-schemas.md).</span></span> <span data-ttu-id="8d32f-110">有关服务架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="8d32f-110">For more information on the service schemas, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8d32f-111">验证批处理的交换，在你的项目中使用的文档架构中的文档。</span><span class="sxs-lookup"><span data-stu-id="8d32f-111"> validates the documents in a batched interchange using the document schemas in your project.</span></span>  
  
## <a name="send-side-processing"></a><span data-ttu-id="8d32f-112">发送端处理</span><span class="sxs-lookup"><span data-stu-id="8d32f-112">Send-Side Processing</span></span>  
 <span data-ttu-id="8d32f-113">当 EDI 组装器处理保留的交换时，使用的交换、组和事务集标头通常与收到批交换时存在于此批交换中的交换、组和事务集标头相同。</span><span class="sxs-lookup"><span data-stu-id="8d32f-113">When the EDI Assembler processes a preserved interchange, it normally uses the same interchange, group, and transaction-set headers that existed in the batched interchange when it was received.</span></span>  
  
-   <span data-ttu-id="8d32f-114">为交换的 X12 的单向协议选项卡中的不同页上的属性设置**协议属性**对话框 (这将决定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将创建的传出的 ISA，GS 和 ST 标头交换） 通常不适用于。</span><span class="sxs-lookup"><span data-stu-id="8d32f-114">For X12 interchanges, the property settings on different pages in the one-way agreement tab in the **Agreement Properties** dialog box (which determine how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will create the ISA, GS, and ST headers of an outgoing interchange) do not normally apply.</span></span>  
  
-   <span data-ttu-id="8d32f-115">对于 EDIFACT 交换，通常使用协议属性中的 UNA 设置。</span><span class="sxs-lookup"><span data-stu-id="8d32f-115">For EDIFACT interchanges, the UNA settings in the agreement properties are normally used.</span></span> <span data-ttu-id="8d32f-116">UNA 段在 EDIFACT 编码消息中是可选的，但对于序列化保留的批交换，该段则是必需的。</span><span class="sxs-lookup"><span data-stu-id="8d32f-116">The UNA segment is optional in an EDIFACT-encoded message, but it is required for serializing a preserved batch interchange.</span></span> <span data-ttu-id="8d32f-117">如果 XML 实例中的 UNA 段未设置值，将使用发送管道组件的默认属性值。</span><span class="sxs-lookup"><span data-stu-id="8d32f-117">If there is no value for the UNA segment in the XML instance, the default property values for the send pipeline component will be used.</span></span> <span data-ttu-id="8d32f-118">如果未对发送管道组件的属性赋值，那么将挂起保留批的中间 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="8d32f-118">If the send pipeline component properties are not valued, then the preserved batch intermediate XML message will be suspended.</span></span>  
  
-   <span data-ttu-id="8d32f-119">如果针对保留的交换（在自定义组件中）将 `EDI.PopulateInterchangeValues` 上下文属性升级为“True”，则发送端口中的 EdiAssembler 会将所有交换、组和事务集标头填充为在协议属性中设置的值。</span><span class="sxs-lookup"><span data-stu-id="8d32f-119">If you promote the `EDI.PopulateInterchangeValues` context property to "True" on the interchange being preserved (in a custom component), the EdiAssembler in the send port will populate all of the interchange, group, and transaction-set headers to the values set in the agreement properties.</span></span>  
  
-   <span data-ttu-id="8d32f-120">如果在发送管道处理此交换前将此交换的 `EDIOverride.OverrideEdiHeader` 上下文属性升级为“True”，则可以通过设置适当的 `EDIOverride` 上下文属性值来覆盖出站文档的信封值。</span><span class="sxs-lookup"><span data-stu-id="8d32f-120">If you promote the `EDIOverride.OverrideEdiHeader` context property to “True” on the interchange before it is processed by the send pipeline, you can override the envelope values for the outbound document by setting the appropriate `EDIOverride` context property values.</span></span> <span data-ttu-id="8d32f-121">有关详细信息，请参阅[重写 EDI 标头](../core/overriding-edi-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="8d32f-121">For more information, see [Overriding EDI Headers](../core/overriding-edi-headers.md).</span></span>  
  
 <span data-ttu-id="8d32f-122">对于保留的没有任何错误的交换，组装器将保留各个事务集在该交换的组中的序列以及各个组在该交换中的序列。</span><span class="sxs-lookup"><span data-stu-id="8d32f-122">For a preserved interchange that has no errors, the Assembler will preserve the sequence of transaction sets in a group of the interchange and the sequence of groups in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d32f-123">使用 XML 发送管道可以发送保留批。</span><span class="sxs-lookup"><span data-stu-id="8d32f-123">You can send a preserved batch with an XML send pipeline.</span></span> <span data-ttu-id="8d32f-124">但是，若要执行此操作，您需要更改批架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8d32f-124">However, to do so requires that you change the namespace for the batch schema.</span></span> <span data-ttu-id="8d32f-125">有关详细信息，请参阅[与 XML 发送管道发送保留批处理](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="8d32f-125">For more information, see [Sending a Preserved Batch with an XML Send Pipeline](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md).</span></span>  
  
## <a name="error-processing"></a><span data-ttu-id="8d32f-126">错误处理</span><span class="sxs-lookup"><span data-stu-id="8d32f-126">Error Processing</span></span>  
 <span data-ttu-id="8d32f-127">由于 XML 中存在保留标记，EDI 发送管道将批处理 EDI 交换识别为保留批。</span><span class="sxs-lookup"><span data-stu-id="8d32f-127">The EDI send pipeline recognizes a batched EDI interchange as a preserved batch because of a reserved tag in the XML.</span></span> <span data-ttu-id="8d32f-128">此标记，或者\<X12InterchangeXml > 或\<EdifactInterchangeXml >，按以下方式应用于 XML EDI 接收管道。</span><span class="sxs-lookup"><span data-stu-id="8d32f-128">This tag, either \<X12InterchangeXml> or \<EdifactInterchangeXml>, is applied to the XML by the EDI receive pipeline.</span></span>  
  
 <span data-ttu-id="8d32f-129">挂起的出错事务集具有以下特殊情况：</span><span class="sxs-lookup"><span data-stu-id="8d32f-129">The following special cases apply to suspending transaction sets on error:</span></span>  
  
-   <span data-ttu-id="8d32f-130">如果组中的所有事务集无效，那么 EDI 发送管道将在生成的 EDI 中包含组控制段，但该组不包含任何事务集（因为将被删除）。</span><span class="sxs-lookup"><span data-stu-id="8d32f-130">If all transaction sets in a group are invalid, then the EDI send pipeline will include group control segments in the generated EDI, but the group will not contain any transaction sets (because they will have been dropped).</span></span> <span data-ttu-id="8d32f-131">组页脚总数更新为零。</span><span class="sxs-lookup"><span data-stu-id="8d32f-131">The group footer totals are updated to zero.</span></span> <span data-ttu-id="8d32f-132">交换控制段保留不变。</span><span class="sxs-lookup"><span data-stu-id="8d32f-132">The interchange control segments remain unchanged.</span></span>  
  
-   <span data-ttu-id="8d32f-133">如果交换中的所有事务集无效，那么生成的 EDI 交换仍将包含交换控制段，但该交换将不包含任何事务集（因为将被删除）。</span><span class="sxs-lookup"><span data-stu-id="8d32f-133">If all transaction sets in an interchange are invalid, then the interchange control segments will still be included in the generated EDI interchange, but the interchange will not contain any transaction sets (because they will have been dropped).</span></span> <span data-ttu-id="8d32f-134">这会构成一个空交换。</span><span class="sxs-lookup"><span data-stu-id="8d32f-134">This would constitute an empty interchange.</span></span>  
  
-   <span data-ttu-id="8d32f-135">如果组控制段或交换控制段无效，则不会生成 EDI 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="8d32f-135">If the group control segments or the interchange control segments are invalid, an EDI-encoded interchange will not be generated.</span></span> <span data-ttu-id="8d32f-136">将在事件查看器中创建一个日志，指示已拒绝交换。</span><span class="sxs-lookup"><span data-stu-id="8d32f-136">A log will be created in the event viewer indicating that the interchange was rejected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d32f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d32f-137">See Also</span></span>  
 [<span data-ttu-id="8d32f-138">对传出的 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="8d32f-138">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)