---
title: EDI 类型 （数据元素） 验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd53685f-a49c-41c8-813e-29700fc0b62b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22dd511711a8ec2245c1196e5865f574cf47fc08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389145"
---
# <a name="edi-type-data-element-validation"></a><span data-ttu-id="5e057-102">EDI 类型 （数据元素） 验证</span><span class="sxs-lookup"><span data-stu-id="5e057-102">EDI Type (Data Element) Validation</span></span>
<span data-ttu-id="5e057-103">EDI 接收管道和 EDI 发送管道对事务集数据元素执行 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="5e057-103">The EDI receive pipeline and EDI send pipeline perform EDI validation on transaction-set data elements.</span></span> <span data-ttu-id="5e057-104">对于所有消息都进出特定参与方，通过该参与方的协议属性上配置此验证**验证**页 (下**事务集设置**X12 的部分或 EDIFACT 协议）。</span><span class="sxs-lookup"><span data-stu-id="5e057-104">This validation is configured for all messages from or to a specific party, through that party's agreement properties on the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT agreements).</span></span> <span data-ttu-id="5e057-105">如果**EDI 类型验证**属性中未选定**验证**页上，将不会执行本主题中所述的验证的数据。</span><span class="sxs-lookup"><span data-stu-id="5e057-105">If the **EDI Type Validation** property is not selected in the **Validation** page, the data validations described in this topic will not be performed.</span></span>  
  
 <span data-ttu-id="5e057-106">选择针对传入消息和传出消息启用 EDI 类型验证**EDI 类型验证**属性中的**验证**中的双向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="5e057-106">EDI type validation is enabled for incoming as well as outgoing messages by selecting the **EDI type Validation** property in the **Validation** page of the bi-directional agreement tabs in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="5e057-107">对于传入和传出消息，此属性会选择默认情况下，以便默认启用 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="5e057-107">For both incoming and outgoing messages, this property is selected by default so that EDI validation is enabled by default.</span></span>  
  
## <a name="validation-checks"></a><span data-ttu-id="5e057-108">验证检查</span><span class="sxs-lookup"><span data-stu-id="5e057-108">Validation Checks</span></span>  
 <span data-ttu-id="5e057-109">当 EDI 接收管道或 EDI 发送管道执行 EDI 验证时，它验证下列各项：</span><span class="sxs-lookup"><span data-stu-id="5e057-109">When the EDI receive pipeline or EDI send pipeline performs EDI validation, it validates the following:</span></span>  
  
- <span data-ttu-id="5e057-110">架构的 EDI 属性定义数据类型</span><span class="sxs-lookup"><span data-stu-id="5e057-110">Data types as defined by the EDI properties of the schema</span></span>  
  
- <span data-ttu-id="5e057-111">长度限制</span><span class="sxs-lookup"><span data-stu-id="5e057-111">Length restrictions</span></span>  
  
- <span data-ttu-id="5e057-112">空数据元素和尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="5e057-112">Empty data elements and trailing separators</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5e057-113">此验证不会检查代码集 （枚举） 或发生最小值或最大值。</span><span class="sxs-lookup"><span data-stu-id="5e057-113">This validation does not check code sets (enumerations) or min or max occurs.</span></span>  
  
  <span data-ttu-id="5e057-114">**字符集**</span><span class="sxs-lookup"><span data-stu-id="5e057-114">**Character Sets**</span></span>  
  
  <span data-ttu-id="5e057-115">若要执行 EDI 数据元素验证，EDI 接收和发送管道要求按如下方式建立字符集：</span><span class="sxs-lookup"><span data-stu-id="5e057-115">To perform EDI data element validations, the EDI receive and send pipelines require the character set to be established as follows:</span></span>  
  
- <span data-ttu-id="5e057-116">对于 EDIFACT，数据元素中建立字符集**UNB1**的**字符集和分隔符**的单向协议选项卡的页面**协议属性**对话框中或**EDIFACT 后备设置**对话框 （如果尚未建立任何协议）。</span><span class="sxs-lookup"><span data-stu-id="5e057-116">For EDIFACT, the character set is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box or the **EDIFACT Fallback Settings** dialog box (if no agreement has been established).</span></span>  
  
- <span data-ttu-id="5e057-117">对于 KEDIFACT，数据元素中建立字符**UNB1**的**字符集和分隔符**的单向协议选项卡的页面**协议属性**对话框框中，与 EDIFACT 一样。</span><span class="sxs-lookup"><span data-stu-id="5e057-117">For KEDIFACT, the character is established in data element **UNB1** of the **Charset and Separators** page of the one-way agreement tab of the **Agreement Properties** dialog box, as for EDIFACT.</span></span> <span data-ttu-id="5e057-118">值**UNB1.1**元素必须设置为`KECA`。</span><span class="sxs-lookup"><span data-stu-id="5e057-118">The value for the **UNB1.1** element must be set to `KECA`.</span></span>  
  
- <span data-ttu-id="5e057-119">对于 X12，消息在管道属性中建立字符集。</span><span class="sxs-lookup"><span data-stu-id="5e057-119">For X12, the character set is established for the message in the pipeline properties.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5e057-120">当 BizTalk 运行时执行的一条消息的 EDI 验证时，它将使用 X12 字符集在管道属性中选择的设置。</span><span class="sxs-lookup"><span data-stu-id="5e057-120">When the BizTalk runtime performs EDI validation of a message, it will use the X12 character set selected in the pipeline properties.</span></span> <span data-ttu-id="5e057-121">但是的页中输入的属性的验证**协议属性**使用在所选的字符集执行对话框**字符集和分隔符**该对话框的页。</span><span class="sxs-lookup"><span data-stu-id="5e057-121">However, validation of the properties entered in the pages of the **Agreement Properties** dialog box is performed using the character set selected in the **Charset and Separators** page of that dialog box.</span></span> <span data-ttu-id="5e057-122">在运行时，管道将忽略此值的 x12 字符集属性**字符集和分隔符**页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="5e057-122">During runtime, the pipeline ignores the value of the X12 character set property **Charset and Separators** page of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="5e057-123">如果这两个设置不相同 (即，X12 字符集属性中**协议属性**对话框的设置为**扩展**，而管道属性中的字符属性设置为 X12**基本**)，则可能发生验证错误消息。</span><span class="sxs-lookup"><span data-stu-id="5e057-123">If these two settings are not the same (i.e., the X12 character set property in the **Agreement Properties** dialog box is set to **Extended** while the X12 character property in the pipeline properties is set to **Basic**), message validation errors could result.</span></span>  
  
  <span data-ttu-id="5e057-124">**数据类型验证**</span><span class="sxs-lookup"><span data-stu-id="5e057-124">**Data Type Validation**</span></span>  
  
  <span data-ttu-id="5e057-125">对于 X12，以下 EDI 数据类型在验证的架构中批注中接收或发送管道的拆装器/组装器组件：数字、 十进制、 标识符、 字符串、 日期、 时间、 二进制和复合。</span><span class="sxs-lookup"><span data-stu-id="5e057-125">For X12, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Numeric, Decimal, Identifier, String, Date, Time, Binary, and Composite.</span></span>  
  
  <span data-ttu-id="5e057-126">对于 EDIFACT，在验证的架构中接收或发送管道中的拆装器/组装器组件批注以下 EDI 数据类型：字母、 数字、 标识符、 字符串和复合。</span><span class="sxs-lookup"><span data-stu-id="5e057-126">For EDIFACT, the following EDI data types are annotated in schema for validation by the Disassembler/Assembler components in the Receive or Send Pipelines: Alphabetic, Numeric, Identifier, String, and Composite.</span></span>  
  
  <span data-ttu-id="5e057-127">**长度限制**</span><span class="sxs-lookup"><span data-stu-id="5e057-127">**Length Restrictions**</span></span>  
  
  <span data-ttu-id="5e057-128">对于 X12 和 EDIFACT，元素或子元素必须验证的长度 （最小和最大） 要求。</span><span class="sxs-lookup"><span data-stu-id="5e057-128">For both X12 and EDIFACT, elements or sub-elements must be validated for length (minimum and maximum) requirement.</span></span> <span data-ttu-id="5e057-129">长度定义为使用的字符位置数。</span><span class="sxs-lookup"><span data-stu-id="5e057-129">Length is defined as the number of character positions used.</span></span> <span data-ttu-id="5e057-130">长度不包括符号和十进制符号。</span><span class="sxs-lookup"><span data-stu-id="5e057-130">Length does not include signs and decimal notations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e057-131">对于 X12_AN 字符串数据类型，保留前导空格和尾随空格允许在任何段中以满足最小长度要求。</span><span class="sxs-lookup"><span data-stu-id="5e057-131">For the X12_AN string data type, leading spaces are preserved and trailing spaces are allowed in any segment to satisfy the minimum length requirement.</span></span>  
  
 <span data-ttu-id="5e057-132">对于 KECA，长度解释为字节数。</span><span class="sxs-lookup"><span data-stu-id="5e057-132">For KECA, length is interpreted as the number of bytes.</span></span> <span data-ttu-id="5e057-133">例如，如果长度定义为三个，该元素或子元素可以包括三个单字节字符或一个双字节字符和一个单字节字符的组合。</span><span class="sxs-lookup"><span data-stu-id="5e057-133">For example, if the length is defined as three, the element or sub-element can include either three one-byte characters or the combination of one two-byte character and one one-byte character.</span></span>  
  
 <span data-ttu-id="5e057-134">**空数据元素和尾部分隔符验证**</span><span class="sxs-lookup"><span data-stu-id="5e057-134">**Empty Data Elements and Trailing Separator Validation**</span></span>  
  
 <span data-ttu-id="5e057-135">对于 X12，如果段存在不能为空实例中标记为必需数据元素。</span><span class="sxs-lookup"><span data-stu-id="5e057-135">For X12, data elements marked as mandatory cannot be empty in an instance if the segment is present.</span></span> <span data-ttu-id="5e057-136">复合数据元素是否至少一个组件数据元素必须是值。</span><span class="sxs-lookup"><span data-stu-id="5e057-136">If the data element is composite at least one component data element must be valued.</span></span>  
  
 <span data-ttu-id="5e057-137">对于 EDIFACT，非值和条件的数据元素 （和子组件） 可以不包括;但是，保留分隔符。</span><span class="sxs-lookup"><span data-stu-id="5e057-137">For EDIFACT, non-valued and conditional data elements (and sub-components) may be excluded; however, the separator is retained.</span></span>  
  
 <span data-ttu-id="5e057-138">尾部分隔符对于 X12 或 EDIFACT，不是必需，但建议。</span><span class="sxs-lookup"><span data-stu-id="5e057-138">Trailing separators are not required for either X12 or EDIFACT, but are recommended.</span></span>  
  
## <a name="when-edi-type-validation-is-disabled"></a><span data-ttu-id="5e057-139">当禁用 EDI 类型验证时</span><span class="sxs-lookup"><span data-stu-id="5e057-139">When EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="5e057-140">如果停用 EDI 类型验证，EDI 接收管道或 EDI 发送管道将处理而不会挂起正在处理的消息由 EDI 类型验证查出有错的数据元素。</span><span class="sxs-lookup"><span data-stu-id="5e057-140">If you deactivate the EDI type validation, the EDI receive pipeline or EDI send pipeline will process data elements that have errors checked by the EDI type validation without suspending the message being processed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e057-141">即使禁用 EDI 类型验证，则会执行 EDI 结构验证。</span><span class="sxs-lookup"><span data-stu-id="5e057-141">EDI structural validation is performed even if the EDI type validation is disabled.</span></span> <span data-ttu-id="5e057-142">未通过基本结构验证的交换将挂起，即使禁用 EDI 类型验证。</span><span class="sxs-lookup"><span data-stu-id="5e057-142">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
 <span data-ttu-id="5e057-143">下面是一些将处理而不会导致消息挂起的错误：</span><span class="sxs-lookup"><span data-stu-id="5e057-143">Some of the errors that will be processed without causing the message to be suspended are:</span></span>  
  
- <span data-ttu-id="5e057-144">意外/未定义事务集</span><span class="sxs-lookup"><span data-stu-id="5e057-144">An unexpected/undefined transaction set</span></span>  
  
- <span data-ttu-id="5e057-145">段/循环和数据元素级别上意外/未定义的数据</span><span class="sxs-lookup"><span data-stu-id="5e057-145">Unexpected/undefined data at the segment/loop and data element level</span></span>  
  
- <span data-ttu-id="5e057-146">可选性 （最小值和最大发生） 段/循环和数据元素级别</span><span class="sxs-lookup"><span data-stu-id="5e057-146">Optionality (min and max occurs) at the segment/loop and data element level</span></span>  
  
- <span data-ttu-id="5e057-147">在数据元素级别 （数据长度超出最大级别或低于最小级别） 的长度 （最小/最大） 违规</span><span class="sxs-lookup"><span data-stu-id="5e057-147">Length (min/max) violation at the data element level (data with length exceeding the maximum level or below the minimum level)</span></span>  
  
- <span data-ttu-id="5e057-148">（ID 数据类型除外，它具有其自己的控件） 的数据元素级别的数据类型不匹配</span><span class="sxs-lookup"><span data-stu-id="5e057-148">Data type mismatch at the data element level (except for the ID data type, which has its own control)</span></span>  
  
- <span data-ttu-id="5e057-149">数据元素级别的无效枚举列表。</span><span class="sxs-lookup"><span data-stu-id="5e057-149">Invalid enumeration list at the data element level.</span></span>  
  
  <span data-ttu-id="5e057-150">如果禁用在接收端，但在发送端启用 EDI 类型验证，EDI 发送管道不能将重新处理成有效的 EDI 文件生成由接收管道，如果 XML 文件包含错误的 XML。</span><span class="sxs-lookup"><span data-stu-id="5e057-150">If EDI type validation is disabled on the receive side, but enabled on the send side, the EDI send pipeline will not be able to reprocess the XML produced by the receive pipeline into a valid EDI file if the XML file contains errors.</span></span> <span data-ttu-id="5e057-151">因此，发送管道将生成错误。</span><span class="sxs-lookup"><span data-stu-id="5e057-151">As a result, the send pipeline will generate an error.</span></span>  
  
  <span data-ttu-id="5e057-152">如果禁用 EDI 类型验证，EDI 接收管道或发送管道将处理错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5e057-152">If EDI Type validation is disabled, the EDI receive pipeline or send pipeline will handle errors as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e057-153">意外的数据</span><span class="sxs-lookup"><span data-stu-id="5e057-153">Unexpected Data</span></span>|<span data-ttu-id="5e057-154">操作</span><span class="sxs-lookup"><span data-stu-id="5e057-154">Action</span></span>|  
|<span data-ttu-id="5e057-155">意外/未定义事务集</span><span class="sxs-lookup"><span data-stu-id="5e057-155">Unexpected/undefined transaction set</span></span>|<span data-ttu-id="5e057-156">EDI 接收或发送管道将接受事务集。 即使尚未部署的架构，该</span><span class="sxs-lookup"><span data-stu-id="5e057-156">The EDI receive or send pipeline will accept a transaction set even if a schema for it has not been deployed</span></span>|  
|<span data-ttu-id="5e057-157">意外的段/记录</span><span class="sxs-lookup"><span data-stu-id="5e057-157">Unexpected segment/record</span></span>|<span data-ttu-id="5e057-158">接收管道将生成具有相应的前缀的标记：\<UnexpectedSegment_ _ %segmentid%\>。</span><span class="sxs-lookup"><span data-stu-id="5e057-158">The receive pipeline will generate a tag with the appropriate prefix: \<UnexpectedSegment_%SegmentID%\>.</span></span><br /><br /> <span data-ttu-id="5e057-159">发送管道将使用第一个 XML 标记名称的一到三个字符作为段名称。</span><span class="sxs-lookup"><span data-stu-id="5e057-159">The send pipeline will use the first one to three characters of the XML Tag name as the segment name.</span></span>|  
|<span data-ttu-id="5e057-160">意外简单数据元素</span><span class="sxs-lookup"><span data-stu-id="5e057-160">Unexpected simple data element</span></span>|<span data-ttu-id="5e057-161">接收管道将生成具有前缀、 段标识符和表示数据元素的位置的段中索引的 XML 标记： < UnexpectedDataElement_ _ %fieldname%。</span><span class="sxs-lookup"><span data-stu-id="5e057-161">The receive pipeline will generate an XML tag with a prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="5e057-162">意外复合数据元素</span><span class="sxs-lookup"><span data-stu-id="5e057-162">Unexpected composite data element</span></span>|<span data-ttu-id="5e057-163">接收管道将生成一个 XML 前缀、 段标识符和表示数据元素在段中的所处位置的索引的标记： < UnexpectedCompositeDataElement_ _ %fieldname%。</span><span class="sxs-lookup"><span data-stu-id="5e057-163">The receive pipeline will generate an XML tags with prefix, segment identifier, and index representing the position of the data element in the segment: <UnexpectedCompositeDataElement_%FieldName%.</span></span>|  
|<span data-ttu-id="5e057-164">缺少所需的数据</span><span class="sxs-lookup"><span data-stu-id="5e057-164">Missing required data</span></span>|<span data-ttu-id="5e057-165">管道会将数据视为可选。</span><span class="sxs-lookup"><span data-stu-id="5e057-165">The pipeline will treat the data as optional.</span></span>|  
|<span data-ttu-id="5e057-166">数据元素长度违规</span><span class="sxs-lookup"><span data-stu-id="5e057-166">Data element length violation</span></span>|<span data-ttu-id="5e057-167">管道会将无效的数据元素长度视为有效 (最小值 = 0，最大 = 不受限制)。</span><span class="sxs-lookup"><span data-stu-id="5e057-167">The pipeline will treat the invalid data element length as valid (min = 0 and max = unbounded).</span></span>|  
|<span data-ttu-id="5e057-168">（适用于 ID 数据类型） 的实例中的无效枚举值</span><span class="sxs-lookup"><span data-stu-id="5e057-168">Invalid enumeration value in the instance (applicable to the ID data type)</span></span>|<span data-ttu-id="5e057-169">管道将忽略错误并继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="5e057-169">The pipeline will ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="5e057-170">实例中的 Max 违规</span><span class="sxs-lookup"><span data-stu-id="5e057-170">‘Max’ repletion violation in the instance</span></span>|<span data-ttu-id="5e057-171">管道会将此类重复数据视为有效 (最小出现次数 = 0，最大出现次数 = 不受限制)。</span><span class="sxs-lookup"><span data-stu-id="5e057-171">The pipeline will treat such repetitive data as valid (min occurs = 0 and max occurs = unbounded).</span></span>|  
  
 <span data-ttu-id="5e057-172">**错误报告**</span><span class="sxs-lookup"><span data-stu-id="5e057-172">**Error Reporting**</span></span>  
  
 <span data-ttu-id="5e057-173">当关闭 EDI 类型验证时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会报告错误在事件查看器中，但会报告警告。</span><span class="sxs-lookup"><span data-stu-id="5e057-173">When EDI type validation is turned off, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not report errors in the Event Viewer, but reports a warning.</span></span> <span data-ttu-id="5e057-174">此外，确认报告将接受回源参与方，AK501 和 AK901 设置为"E"在 X12 997 或 UCI.4、 UCM.3 和 ucf.4 设置为"7"EDIFACT CONTRL 中。</span><span class="sxs-lookup"><span data-stu-id="5e057-174">In addition, the acknowledgment reports an ‘Accept’ back to the source party, setting AK501 and AK901 as “E” in an X12 997 or UCI.4, UCM.3, and UCF.4 as “7” in an EDIFACT CONTRL.</span></span> <span data-ttu-id="5e057-175">因此，将消除在将来传输中进行纠正的任何机会。</span><span class="sxs-lookup"><span data-stu-id="5e057-175">As a result, any chance of rectification in future transmissions will be eliminated.</span></span> <span data-ttu-id="5e057-176">但是，消息接收方必须更正通过手动干预文档而不是拒绝或挂起消息。</span><span class="sxs-lookup"><span data-stu-id="5e057-176">However, receivers of the message will have an opportunity to salvage the document via manual intervention rather than the message being rejected or suspended.</span></span> <span data-ttu-id="5e057-177">此外，`Edi.ErrorsInTransactionSet`会升级上下文属性，如果以上任一错误遇到的 EDI 接收管道。</span><span class="sxs-lookup"><span data-stu-id="5e057-177">Also, the `Edi.ErrorsInTransactionSet` context property will be promoted if any of these errors are encountered by the EDI receive pipeline.</span></span> <span data-ttu-id="5e057-178">如果遇到 EDI 或扩展验证错误，此属性将升级为"True"。</span><span class="sxs-lookup"><span data-stu-id="5e057-178">This property will be promoted as "True" if EDI or Extended validation errors are encountered.</span></span> <span data-ttu-id="5e057-179">如果没有遇到错误时，该属性将升级为"False"。</span><span class="sxs-lookup"><span data-stu-id="5e057-179">If not errors are encountered, the property will be promoted as "False".</span></span>  
  
 <span data-ttu-id="5e057-180">如果接收或发送管道遇到意外的数据，它将报告父级别错误，并忽略子级别错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5e057-180">If the receive or send pipeline encounters unexpected data, it will report the error at the parent level and ignore child level errors, as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e057-181">意外的数据</span><span class="sxs-lookup"><span data-stu-id="5e057-181">Unexpected Data</span></span>|<span data-ttu-id="5e057-182">操作</span><span class="sxs-lookup"><span data-stu-id="5e057-182">Action</span></span>|  
|<span data-ttu-id="5e057-183">意外的事务集</span><span class="sxs-lookup"><span data-stu-id="5e057-183">Unexpected transaction set</span></span>|<span data-ttu-id="5e057-184">确认报告此错误，并忽略段/循环和数据元素级别的后续错误</span><span class="sxs-lookup"><span data-stu-id="5e057-184">The acknowledgment reports this error and ignores subsequent errors at the segment/loop and data element level</span></span>|  
|<span data-ttu-id="5e057-185">意外的段/循环</span><span class="sxs-lookup"><span data-stu-id="5e057-185">Unexpected segment/loop</span></span>|<span data-ttu-id="5e057-186">确认报告此错误，并忽略数据元素级别的错误。</span><span class="sxs-lookup"><span data-stu-id="5e057-186">The acknowledgment reports this error and ignores errors at the data element level.</span></span>|  
|<span data-ttu-id="5e057-187">意外的数据元素</span><span class="sxs-lookup"><span data-stu-id="5e057-187">Unexpected data element</span></span>|<span data-ttu-id="5e057-188">确认报告此错误，并忽略与属性，如 ID、 长度、 出现次数等相关的复合错误） 和 （如果适用） 到复合数据元素字段相关的错误。</span><span class="sxs-lookup"><span data-stu-id="5e057-188">The acknowledgment reports this error and ignores compound errors relating to properties like ID, length, occours, etc) and errors relating to composite data element fields (if applicable).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e057-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e057-189">See Also</span></span>  
 <span data-ttu-id="5e057-190">[EDI 消息验证](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="5e057-190">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 [<span data-ttu-id="5e057-191">扩展 (BTS-XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="5e057-191">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)