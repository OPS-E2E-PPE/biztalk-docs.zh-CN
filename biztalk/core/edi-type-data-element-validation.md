---
title: "EDI 类型 （数据元素） 验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd53685f-a49c-41c8-813e-29700fc0b62b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a989c58f59581795f641601938fe76bb7b1671f6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="edi-type-data-element-validation"></a><span data-ttu-id="44bb0-102">EDI 类型（数据元素）验证</span><span class="sxs-lookup"><span data-stu-id="44bb0-102">EDI Type (Data Element) Validation</span></span>
<span data-ttu-id="44bb0-103">EDI 接收管道和 EDI 发送管道对事务集数据元素执行 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="44bb0-103">The EDI receive pipeline and EDI send pipeline perform EDI validation on transaction-set data elements.</span></span> <span data-ttu-id="44bb0-104">在上将此验证配置的所有消息从或对特定方，通过该参与方的协议属性**验证**页 (下**事务设置设置**任一 X12 的部分或 EDIFACT 协议）。</span><span class="sxs-lookup"><span data-stu-id="44bb0-104">This validation is configured for all messages from or to a specific party, through that party's agreement properties on the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT agreements).</span></span> <span data-ttu-id="44bb0-105">如果**EDI 类型验证**中未选定属性**验证**页上，将不会执行本主题中所述的验证的数据。</span><span class="sxs-lookup"><span data-stu-id="44bb0-105">If the **EDI Type Validation** property is not selected in the **Validation** page, the data validations described in this topic will not be performed.</span></span>  
  
 <span data-ttu-id="44bb0-106">通过选择情况下，启用传入以及传出消息的 EDI 类型验证**EDI 类型验证**中的属性**验证**中双向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="44bb0-106">EDI type validation is enabled for incoming as well as outgoing messages by selecting the **EDI type Validation** property in the **Validation** page of the bi-directional agreement tabs in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="44bb0-107">默认情况下，为传入消息和传出消息选择此属性，以便默认启用 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="44bb0-107">For both incoming and outgoing messages, this property is selected by default so that EDI validation is enabled by default.</span></span>  
  
## <a name="validation-checks"></a><span data-ttu-id="44bb0-108">验证检查内容</span><span class="sxs-lookup"><span data-stu-id="44bb0-108">Validation Checks</span></span>  
 <span data-ttu-id="44bb0-109">当 EDI 接收管道或 EDI 发送管道执行 EDI 验证时，将验证下列各项：</span><span class="sxs-lookup"><span data-stu-id="44bb0-109">When the EDI receive pipeline or EDI send pipeline performs EDI validation, it validates the following:</span></span>  
  
-   <span data-ttu-id="44bb0-110">由架构的 EDI 属性定义的数据类型</span><span class="sxs-lookup"><span data-stu-id="44bb0-110">Data types as defined by the EDI properties of the schema</span></span>  
  
-   <span data-ttu-id="44bb0-111">长度限制</span><span class="sxs-lookup"><span data-stu-id="44bb0-111">Length restrictions</span></span>  
  
-   <span data-ttu-id="44bb0-112">空数据元素和尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="44bb0-112">Empty data elements and trailing separators</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44bb0-113">该验证不会检查代码集（枚举）或最小/最大出现次数。</span><span class="sxs-lookup"><span data-stu-id="44bb0-113">This validation does not check code sets (enumerations) or min or max occurs.</span></span>  
  
 <span data-ttu-id="44bb0-114">**字符集**</span><span class="sxs-lookup"><span data-stu-id="44bb0-114">**Character Sets**</span></span>  
  
 <span data-ttu-id="44bb0-115">为执行 EDI 数据元素验证，EDI 接收和发送管道要求按如下方式建立字符集：</span><span class="sxs-lookup"><span data-stu-id="44bb0-115">To perform EDI data element validations, the EDI receive and send pipelines require the character set to be established as follows:</span></span>  
  
-   <span data-ttu-id="44bb0-116">对于 edifact 而言的字符集会在数据元素中建立**UNB1**的**字符集和分隔符**的单向协议选项卡页**协议属性**对话框中或**EDIFACT 回退设置**对话框中 （如果已建立没有协议）。</span><span class="sxs-lookup"><span data-stu-id="44bb0-116">For EDIFACT, the character set is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box or the **EDIFACT Fallback Settings** dialog box (if no agreement has been established).</span></span>  
  
-   <span data-ttu-id="44bb0-117">对于 KEDIFACT，字符才会建立数据元素中**UNB1**的**字符集和分隔符**的单向协议选项卡页**协议属性**对话框框中，对于 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="44bb0-117">For KEDIFACT, the character is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box, as for EDIFACT.</span></span> <span data-ttu-id="44bb0-118">值**UNB1.1**元素必须设置为`KECA`。</span><span class="sxs-lookup"><span data-stu-id="44bb0-118">The value for the **UNB1.1** element must be set to `KECA`.</span></span>  
  
-   <span data-ttu-id="44bb0-119">对于 X12，字符集是针对管道属性中的消息建立的。</span><span class="sxs-lookup"><span data-stu-id="44bb0-119">For X12, the character set is established for the message in the pipeline properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44bb0-120">BizTalk 运行时对消息执行 EDI 验证时，将使用在管道属性中选择的 X12 字符集。</span><span class="sxs-lookup"><span data-stu-id="44bb0-120">When the BizTalk runtime performs EDI validation of a message, it will use the X12 character set selected in the pipeline properties.</span></span> <span data-ttu-id="44bb0-121">但是，页中输入的属性的验证**协议属性**对话框中执行使用中选定的字符集**字符集和分隔符**该对话框中的页。</span><span class="sxs-lookup"><span data-stu-id="44bb0-121">However, validation of the properties entered in the pages of the **Agreement Properties** dialog box is performed using the character set selected in the **Charset and Separators** page of that dialog box.</span></span> <span data-ttu-id="44bb0-122">在运行时，管道将忽略此值的 X12 字符集属性**字符集和分隔符**页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="44bb0-122">During runtime, the pipeline ignores the value of the X12 character set property **Charset and Separators** page of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="44bb0-123">如果这两个设置不相同 (即，字符集属性中的 X12**协议属性**对话框中设置为**扩展**而的 X12 管道属性中的字符属性设置为**基本**)，可能会导致验证错误的消息。</span><span class="sxs-lookup"><span data-stu-id="44bb0-123">If these two settings are not the same (i.e., the X12 character set property in the **Agreement Properties** dialog box is set to **Extended** while the X12 character property in the pipeline properties is set to **Basic**), message validation errors could result.</span></span>  
  
 <span data-ttu-id="44bb0-124">**数据类型验证**</span><span class="sxs-lookup"><span data-stu-id="44bb0-124">**Data Type Validation**</span></span>  
  
 <span data-ttu-id="44bb0-125">对于 X12，将在架构中批注以下 EDI 数据类型，以供接收或发送管道中的拆装器/组装器组件验证：数字、十进制、标识符、字符串、日期、时间、二进制和复合数据。</span><span class="sxs-lookup"><span data-stu-id="44bb0-125">For X12, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Numeric, Decimal, Identifier, String, Date, Time, Binary, and Composite.</span></span>  
  
 <span data-ttu-id="44bb0-126">对于 EDIFACT，将在架构中批注以下 EDI 数据类型，以供接收或发送管道中的拆装器/组装器组件验证：字母、数字、标识符、字符串和复合数据。</span><span class="sxs-lookup"><span data-stu-id="44bb0-126">For EDIFACT, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Alphabetic, Numeric, Identifier, String, and Composite.</span></span>  
  
 <span data-ttu-id="44bb0-127">**长度限制**</span><span class="sxs-lookup"><span data-stu-id="44bb0-127">**Length Restrictions**</span></span>  
  
 <span data-ttu-id="44bb0-128">对于 X12 和 EDIFACT，必须验证元素或子元素，以确定其是否符合长度（最小和最大）要求。</span><span class="sxs-lookup"><span data-stu-id="44bb0-128">For both X12 and EDIFACT, elements or sub-elements must be validated for length (minimum and maximum) requirement.</span></span> <span data-ttu-id="44bb0-129">长度定义为占用的字符位置数。</span><span class="sxs-lookup"><span data-stu-id="44bb0-129">Length is defined as the number of character positions used.</span></span> <span data-ttu-id="44bb0-130">长度不包括符号和十进制符号。</span><span class="sxs-lookup"><span data-stu-id="44bb0-130">Length does not include signs and decimal notations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44bb0-131">对于 X12_AN 字符串数据类型，可以在任何段中保留前导空格并允许使用尾部空格，以满足最小长度要求。</span><span class="sxs-lookup"><span data-stu-id="44bb0-131">For the X12_AN string data type, leading spaces are preserved and trailing spaces are allowed in any segment to satisfy the minimum length requirement.</span></span>  
  
 <span data-ttu-id="44bb0-132">对于 KECA，长度解释为字节数。</span><span class="sxs-lookup"><span data-stu-id="44bb0-132">For KECA, length is interpreted as the number of bytes.</span></span> <span data-ttu-id="44bb0-133">例如，如果长度定义为三个，该元素或子元素可以包含三个单字节字符或一个双字节字符和一个单字节字符的组合。</span><span class="sxs-lookup"><span data-stu-id="44bb0-133">For example, if the length is defined as three, the element or sub-element can include either three one-byte characters or the combination of one two-byte character and one one-byte character.</span></span>  
  
 <span data-ttu-id="44bb0-134">**空数据元素和尾随分隔符验证**</span><span class="sxs-lookup"><span data-stu-id="44bb0-134">**Empty Data Elements and Trailing Separator Validation**</span></span>  
  
 <span data-ttu-id="44bb0-135">对于 X12，实例中标记为必需的数据元素不能为空（如果段存在）。</span><span class="sxs-lookup"><span data-stu-id="44bb0-135">For X12, data elements marked as mandatory cannot be empty in an instance if the segment is present.</span></span> <span data-ttu-id="44bb0-136">如果数据元素为复合数据，则必须至少有一个组件数据元素为值。</span><span class="sxs-lookup"><span data-stu-id="44bb0-136">If the data element is composite at least one component data element must be valued.</span></span>  
  
 <span data-ttu-id="44bb0-137">对于 EDIFACT，将排除非值和条件可选的数据元素（和子组件），但保留分隔符。</span><span class="sxs-lookup"><span data-stu-id="44bb0-137">For EDIFACT, non-valued and conditional data elements (and sub-components) may be excluded; however, the separator is retained.</span></span>  
  
 <span data-ttu-id="44bb0-138">对于 X12 或 EDIFACT，推荐使用尾部分隔符，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="44bb0-138">Trailing separators are not required for either X12 or EDIFACT, but are recommended.</span></span>  
  
## <a name="when-edi-type-validation-is-disabled"></a><span data-ttu-id="44bb0-139">禁用 EDI 类型验证时</span><span class="sxs-lookup"><span data-stu-id="44bb0-139">When EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="44bb0-140">如果停用 EDI 类型验证，EDI 接收管道或 EDI 发送管道将处理 EDI 类型验证查出有错的数据元素，而不会挂起正在处理的消息。</span><span class="sxs-lookup"><span data-stu-id="44bb0-140">If you deactivate the EDI type validation, the EDI receive pipeline or EDI send pipeline will process data elements that have errors checked by the EDI type validation without suspending the message being processed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44bb0-141">即使 EDI 类型验证已禁用，仍会执行 EDI 结构验证。</span><span class="sxs-lookup"><span data-stu-id="44bb0-141">EDI structural validation is performed even if the EDI type validation is disabled.</span></span> <span data-ttu-id="44bb0-142">即使 EDI 类型验证已禁用，未通过基本结构验证的交换也会被挂起。</span><span class="sxs-lookup"><span data-stu-id="44bb0-142">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
 <span data-ttu-id="44bb0-143">将在不挂起消息的情况下处理的一些错误包括：</span><span class="sxs-lookup"><span data-stu-id="44bb0-143">Some of the errors that will be processed without causing the message to be suspended are:</span></span>  
  
-   <span data-ttu-id="44bb0-144">意外/未定义的事务集</span><span class="sxs-lookup"><span data-stu-id="44bb0-144">An unexpected/undefined transaction set</span></span>  
  
-   <span data-ttu-id="44bb0-145">段/循环和数据元素级别的意外/未定义数据</span><span class="sxs-lookup"><span data-stu-id="44bb0-145">Unexpected/undefined data at the segment/loop and data element level</span></span>  
  
-   <span data-ttu-id="44bb0-146">段/循环和数据元素级别的可选性（最小和最大出现次数）</span><span class="sxs-lookup"><span data-stu-id="44bb0-146">Optionality (min and max occurs) at the segment/loop and data element level</span></span>  
  
-   <span data-ttu-id="44bb0-147">数据元素级别的长度（最小/最大）违规（数据长度超出最大级别或低于最小级别）</span><span class="sxs-lookup"><span data-stu-id="44bb0-147">Length (min/max) violation at the data element level (data with length exceeding the maximum level or below the minimum level)</span></span>  
  
-   <span data-ttu-id="44bb0-148">数据元素级别的数据类型不匹配（ID 数据类型除外，该类型具有其自己的控件）</span><span class="sxs-lookup"><span data-stu-id="44bb0-148">Data type mismatch at the data element level (except for the ID data type, which has its own control)</span></span>  
  
-   <span data-ttu-id="44bb0-149">数据元素级别的无效枚举列表。</span><span class="sxs-lookup"><span data-stu-id="44bb0-149">Invalid enumeration list at the data element level.</span></span>  
  
 <span data-ttu-id="44bb0-150">如果在接收端禁用 EDI 类型验证，但在发送端启用该验证，当 XML 文件包含错误时，EDI 发送管道无法将接收管道生成的 XML 重新处理成有效的 EDI 文件，</span><span class="sxs-lookup"><span data-stu-id="44bb0-150">If EDI type validation is disabled on the receive side, but enabled on the send side, the EDI send pipeline will not be able to reprocess the XML produced by the receive pipeline into a valid EDI file if the XML file contains errors.</span></span> <span data-ttu-id="44bb0-151">进而导致发送管道生成错误。</span><span class="sxs-lookup"><span data-stu-id="44bb0-151">As a result, the send pipeline will generate an error.</span></span>  
  
 <span data-ttu-id="44bb0-152">如果禁用 EDI 类型验证，EDI 接收管道或发送管道将按如下方式处理错误：</span><span class="sxs-lookup"><span data-stu-id="44bb0-152">If EDI Type validation is disabled, the EDI receive pipeline or send pipeline will handle errors as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44bb0-153">意外数据</span><span class="sxs-lookup"><span data-stu-id="44bb0-153">Unexpected Data</span></span>|<span data-ttu-id="44bb0-154">操作</span><span class="sxs-lookup"><span data-stu-id="44bb0-154">Action</span></span>|  
|<span data-ttu-id="44bb0-155">意外/未定义事务集</span><span class="sxs-lookup"><span data-stu-id="44bb0-155">Unexpected/undefined transaction set</span></span>|<span data-ttu-id="44bb0-156">即使尚未部署 EDI 接收或发送管道的架构，该管道仍将接受事务集。</span><span class="sxs-lookup"><span data-stu-id="44bb0-156">The EDI receive or send pipeline will accept a transaction set even if a schema for it has not been deployed</span></span>|  
|<span data-ttu-id="44bb0-157">意外段/记录</span><span class="sxs-lookup"><span data-stu-id="44bb0-157">Unexpected segment/record</span></span>|<span data-ttu-id="44bb0-158">接收管道将生成一个标记具有相应的前缀： \<UnexpectedSegment_ %segmentid%\>。</span><span class="sxs-lookup"><span data-stu-id="44bb0-158">The receive pipeline will generate a tag with the appropriate prefix: \<UnexpectedSegment_%SegmentID%\>.</span></span><br /><br /> <span data-ttu-id="44bb0-159">发送管道将使用 XML 标记名称的前一至三个字符作为段名称。</span><span class="sxs-lookup"><span data-stu-id="44bb0-159">The send pipeline will use the first one to three characters of the XML Tag name as the segment name.</span></span>|  
|<span data-ttu-id="44bb0-160">意外简单数据元素</span><span class="sxs-lookup"><span data-stu-id="44bb0-160">Unexpected simple data element</span></span>|<span data-ttu-id="44bb0-161">接收管道将生成带有前缀、段标识符和表示数据元素在段中的位置的索引的 XML 标记：<UnexpectedDataElement_%FieldName%。</span><span class="sxs-lookup"><span data-stu-id="44bb0-161">The receive pipeline will generate an XML tag with a prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="44bb0-162">意外复合数据元素</span><span class="sxs-lookup"><span data-stu-id="44bb0-162">Unexpected composite data element</span></span>|<span data-ttu-id="44bb0-163">接收管道将生成带有前缀、段标识符和表示数据元素在段中的位置的索引的 XML 标记：<UnexpectedCompositeDataElement_%FieldName%。</span><span class="sxs-lookup"><span data-stu-id="44bb0-163">The receive pipeline will generate an XML tags with prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedCompositeDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="44bb0-164">缺少必需数据</span><span class="sxs-lookup"><span data-stu-id="44bb0-164">Missing required data</span></span>|<span data-ttu-id="44bb0-165">管道将此数据视为可选数据。</span><span class="sxs-lookup"><span data-stu-id="44bb0-165">The pipeline will treat the data as optional.</span></span>|  
|<span data-ttu-id="44bb0-166">数据元素长度违规</span><span class="sxs-lookup"><span data-stu-id="44bb0-166">Data element length violation</span></span>|<span data-ttu-id="44bb0-167">管道将无效数据元素长度视为有效（最小 = 0，最大 = 不受限制）。</span><span class="sxs-lookup"><span data-stu-id="44bb0-167">The pipeline will treat the invalid data element length as valid (min = 0 and max = unbounded).</span></span>|  
|<span data-ttu-id="44bb0-168">实例中的无效枚举值（适用于 ID 数据类型）</span><span class="sxs-lookup"><span data-stu-id="44bb0-168">Invalid enumeration value in the instance (applicable to the ID data type)</span></span>|<span data-ttu-id="44bb0-169">管道将忽略错误，并继续处理。</span><span class="sxs-lookup"><span data-stu-id="44bb0-169">The pipeline will ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="44bb0-170">实例中的“最大”重复违规</span><span class="sxs-lookup"><span data-stu-id="44bb0-170">‘Max’ repletion violation in the instance</span></span>|<span data-ttu-id="44bb0-171">管道将此类重复数据视为有效（最小出现次数 = 0，最大出现次数 = 不受限制）。</span><span class="sxs-lookup"><span data-stu-id="44bb0-171">The pipeline will treat such repetitive data as valid (min occurs = 0 and max occurs = unbounded).</span></span>|  
  
 <span data-ttu-id="44bb0-172">**错误报告**</span><span class="sxs-lookup"><span data-stu-id="44bb0-172">**Error Reporting**</span></span>  
  
 <span data-ttu-id="44bb0-173">当关闭 EDI 类型验证时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不会在事件查看器中报告错误，但会报告警告。</span><span class="sxs-lookup"><span data-stu-id="44bb0-173">When EDI type validation is turned off, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not report errors in the Event Viewer, but reports a warning.</span></span> <span data-ttu-id="44bb0-174">此外，确认将“接受”报告回源参与方，并在 X12 997 或 UCI.4、UCM.3 中将 AK501 和 AK901 设置为“E”，在 EDIFACT CONTRL 中将 UCF.4 设置为“7”。</span><span class="sxs-lookup"><span data-stu-id="44bb0-174">In addition, the acknowledgment reports an ‘Accept’ back to the source party, setting AK501 and AK901 as “E” in an X12 997 or UCI.4, UCM.3, and UCF.4 as “7” in an EDIFACT CONTRL.</span></span> <span data-ttu-id="44bb0-175">因此，将消除在将来传输中进行纠正的任何可能。</span><span class="sxs-lookup"><span data-stu-id="44bb0-175">As a result, any chance of rectification in future transmissions will be eliminated.</span></span> <span data-ttu-id="44bb0-176">但是，消息接收方可以通过手动干预更正文档，而不是拒绝或挂起消息。</span><span class="sxs-lookup"><span data-stu-id="44bb0-176">However, receivers of the message will have an opportunity to salvage the document via manual intervention rather than the message being rejected or suspended.</span></span> <span data-ttu-id="44bb0-177">此外，如果 EDI 接收管道遇到以上任一错误，将升级 `Edi.ErrorsInTransactionSet` 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="44bb0-177">Also, the `Edi.ErrorsInTransactionSet` context property will be promoted if any of these errors are encountered by the EDI receive pipeline.</span></span> <span data-ttu-id="44bb0-178">如果遇到 EDI 或扩展验证错误，该属性将升级为“True”。</span><span class="sxs-lookup"><span data-stu-id="44bb0-178">This property will be promoted as "True" if EDI or Extended validation errors are encountered.</span></span> <span data-ttu-id="44bb0-179">如果未遇到任何错误，该属性将升级为“False”。</span><span class="sxs-lookup"><span data-stu-id="44bb0-179">If not errors are encountered, the property will be promoted as "False".</span></span>  
  
 <span data-ttu-id="44bb0-180">如果接收或发送管道遇到意外数据，将报告父级别错误，并忽略子级别错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="44bb0-180">If the receive or send pipeline encounters unexpected data, it will report the error at the parent level and ignore child level errors, as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44bb0-181">意外数据</span><span class="sxs-lookup"><span data-stu-id="44bb0-181">Unexpected Data</span></span>|<span data-ttu-id="44bb0-182">操作</span><span class="sxs-lookup"><span data-stu-id="44bb0-182">Action</span></span>|  
|<span data-ttu-id="44bb0-183">意外事务集</span><span class="sxs-lookup"><span data-stu-id="44bb0-183">Unexpected transaction set</span></span>|<span data-ttu-id="44bb0-184">确认报告此错误，并忽略段/循环和数据元素级别的后续错误。</span><span class="sxs-lookup"><span data-stu-id="44bb0-184">The acknowledgment reports this error and ignores subsequent errors at the segment/loop and data element level</span></span>|  
|<span data-ttu-id="44bb0-185">意外段/循环</span><span class="sxs-lookup"><span data-stu-id="44bb0-185">Unexpected segment/loop</span></span>|<span data-ttu-id="44bb0-186">确认报告此错误，并忽略数据元素级别的错误。</span><span class="sxs-lookup"><span data-stu-id="44bb0-186">The acknowledgment reports this error and ignores errors at the data element level.</span></span>|  
|<span data-ttu-id="44bb0-187">意外数据元素</span><span class="sxs-lookup"><span data-stu-id="44bb0-187">Unexpected data element</span></span>|<span data-ttu-id="44bb0-188">确认报告此错误，并忽略与属性相关的复合错误（如 ID、长度和出现次数等）以及与复合数据元素字段（如果适用）相关的错误。</span><span class="sxs-lookup"><span data-stu-id="44bb0-188">The acknowledgment reports this error and ignores compound errors relating to properties like ID, length, occours, etc) and errors relating to composite data element fields (if applicable).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44bb0-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44bb0-189">See Also</span></span>  
 <span data-ttu-id="44bb0-190">[EDI 消息验证](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="44bb0-190">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 [<span data-ttu-id="44bb0-191">扩展 (BTS-XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="44bb0-191">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)