---
title: "HIPAA 架构触发器字段批注 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1389284-a2ec-44e7-a2f1-8d26f83fd31d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c50db43b14899439877fde8ce0ee476feb5095
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="hipaa-schema-trigger-field-annotations"></a><span data-ttu-id="f25a3-102">HIPAA 架构触发器字段批注</span><span class="sxs-lookup"><span data-stu-id="f25a3-102">HIPAA Schema Trigger Field Annotations</span></span>
<span data-ttu-id="f25a3-103">EDI 段通常包含修改段含义的限定符值。</span><span class="sxs-lookup"><span data-stu-id="f25a3-103">EDI segments often contain qualifier values that modify the meaning of the segment.</span></span> <span data-ttu-id="f25a3-104">例如，N1 段可包含一个限定元素“BT”，表示“帐单收件人名字”，或可能包含一个限定元素“ST”，表示“收货方名字”。</span><span class="sxs-lookup"><span data-stu-id="f25a3-104">For example, an N1 segment can contain a qualifying element of “BT” to signify a “bill-to name,” or it may contain a qualifying element of “ST” to indicate a “ship-to name.”</span></span> <span data-ttu-id="f25a3-105">通常它从左到业务逻辑来确定如何解释这些字段并拆装器将 N1 段的所有实例都解析为相同的 XML 记录名称;但是，BizTalk 服务器随附的 HIPAA 架构包含允许 EDI 反汇编程序，创建基于符合条件的元素存在的唯一 XML 记录的批注。</span><span class="sxs-lookup"><span data-stu-id="f25a3-105">Normally it is left to business logic to determine how to interpret these fields and the disassembler resolves all instances of the N1 segment to the same XML record name; however, the HIPAA schemas shipped with BizTalk Server contain annotations that allow the EDI disassembler to create unique XML records based on the presence of a qualifying element.</span></span>  
  
 <span data-ttu-id="f25a3-106">**触发器字段实现**</span><span class="sxs-lookup"><span data-stu-id="f25a3-106">**Trigger Field Implementation**</span></span>  
  
 <span data-ttu-id="f25a3-107">触发器字段实现为一对 XML 属性，这些属性描述导致创建此记录的段元素和触发器值。</span><span class="sxs-lookup"><span data-stu-id="f25a3-107">Trigger fields are implemented as a pair of XML attributes that describe the segment element and the trigger value that causes this record to be created.</span></span> <span data-ttu-id="f25a3-108">下表描述这些属性：</span><span class="sxs-lookup"><span data-stu-id="f25a3-108">The following table describes these attributes:</span></span>  
  
|<span data-ttu-id="f25a3-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f25a3-109">Attribute</span></span>|<span data-ttu-id="f25a3-110">用途</span><span class="sxs-lookup"><span data-stu-id="f25a3-110">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="f25a3-111">trigger_field</span><span class="sxs-lookup"><span data-stu-id="f25a3-111">trigger_field</span></span>|<span data-ttu-id="f25a3-112">将检查其触发器值的段字段。</span><span class="sxs-lookup"><span data-stu-id="f25a3-112">The segment field that will be inspected for the trigger value.</span></span>|  
|<span data-ttu-id="f25a3-113">trigger_value</span><span class="sxs-lookup"><span data-stu-id="f25a3-113">trigger_value</span></span>|<span data-ttu-id="f25a3-114">触发器值。</span><span class="sxs-lookup"><span data-stu-id="f25a3-114">The trigger value(s).</span></span><br /><br /> <span data-ttu-id="f25a3-115">该值可能包含单个值，或空格分隔的值列表。</span><span class="sxs-lookup"><span data-stu-id="f25a3-115">This may contain a single value, or a space delimited list of values.</span></span>|  
  
 <span data-ttu-id="f25a3-116">下表显示触发器批注，因为该批注会显示在 HIPAA 架构、将导致触发器激活的 EDI 段和处理段之后生成的 XML 数据中。</span><span class="sxs-lookup"><span data-stu-id="f25a3-116">The following table shows the trigger annotation as it would appear in the HIPAA schema, the EDI segment that will cause the trigger to activate, and the resulting XML data after processing the segment.</span></span>  
  
|<span data-ttu-id="f25a3-117">架构触发器批注</span><span class="sxs-lookup"><span data-stu-id="f25a3-117">Schema Trigger Annotation</span></span>|<span data-ttu-id="f25a3-118">匹配的 N1 段</span><span class="sxs-lookup"><span data-stu-id="f25a3-118">Matching N1 Segment</span></span>|<span data-ttu-id="f25a3-119">生成的 XML 数据</span><span class="sxs-lookup"><span data-stu-id="f25a3-119">Resulting XML Data</span></span>|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|<span data-ttu-id="f25a3-120">N1 * PR\*Contoso\*XV\*0000000 ~</span><span class="sxs-lookup"><span data-stu-id="f25a3-120">N1*PR\*Contoso\*XV\*0000000~</span></span>|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|<span data-ttu-id="f25a3-121">N1 * PE\*Fabrikam\*FI\*9999999 ~</span><span class="sxs-lookup"><span data-stu-id="f25a3-121">N1*PE\*Fabrikam\*FI\*9999999~</span></span>|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 <span data-ttu-id="f25a3-122">**EDI 反汇编程序处理的触发器字段**</span><span class="sxs-lookup"><span data-stu-id="f25a3-122">**EDI Disassembler Processing of Trigger Fields**</span></span>  
  
 <span data-ttu-id="f25a3-123">当接收 HIPAA 事务集时，如果 EDI 拆装器遇到包含触发器字段的段时，会使用触发器信息生成特定于段和触发器组合的 XML 记录。</span><span class="sxs-lookup"><span data-stu-id="f25a3-123">When receiving a HIPAA transaction set, if the EDI disassembler encounters a segment that contains a trigger field, it uses the trigger information to generate an XML record specific to the segment and trigger combination.</span></span> <span data-ttu-id="f25a3-124">例如，在以下 EDI 数据中，存在两个 N1 段，这些段具有不同的 N101 值，PR 和 PE：</span><span class="sxs-lookup"><span data-stu-id="f25a3-124">For example, in the following EDI data, there are two N1 segments that have different values for N101, PR and PE:</span></span>  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 <span data-ttu-id="f25a3-125">架构中出现的触发器字段批注时由 EDI 反汇编程序处理，将会导致两个单独的 XML 记录 N101，< N1_PayerIdentification_TS835W1_1000A > 的值和 < N1_PayeeIdentification_TS835W1_1000B >对应于 N1 * PR 和 N1\*PE。</span><span class="sxs-lookup"><span data-stu-id="f25a3-125">When processed by the EDI disassembler, the trigger field annotations present in the schema will result in two separate XML records based on the value of N101, <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B>, corresponding to N1*PR and N1\*PE.</span></span>  
  
 <span data-ttu-id="f25a3-126">发送时，EDI 组装器将为包含触发器批注的字段丢弃“_”字符后面的后缀。</span><span class="sxs-lookup"><span data-stu-id="f25a3-126">When sending, the EDI assembler will drop the suffix following the “_” character for fields that contain a trigger annotation.</span></span> <span data-ttu-id="f25a3-127">例如，<N1_PayerIdentification_TS835W1_1000A> 和 <N1_PayeeIdentification_TS835W1_1000B> 都将变成 N1。</span><span class="sxs-lookup"><span data-stu-id="f25a3-127">For example, both <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B> will both become N1.</span></span>  
  
 <span data-ttu-id="f25a3-128">**默认的段和触发字段**</span><span class="sxs-lookup"><span data-stu-id="f25a3-128">**Default Segments and Trigger Fields**</span></span>  
  
 <span data-ttu-id="f25a3-129">下表包含有关的默认段和触发器在作为 BizTalk 服务器的一部分提供的 HIPAA 文档中使用的字段信息：</span><span class="sxs-lookup"><span data-stu-id="f25a3-129">The following table contains information on the default segments and trigger fields used in HIPAA documents supplied as part of BizTalk Server:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f25a3-130">用于触发器字段的各个触发器值在架构之间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f25a3-130">The individual trigger values used with the trigger fields may vary between schemas.</span></span>  
  
|<span data-ttu-id="f25a3-131">带有触发器的段</span><span class="sxs-lookup"><span data-stu-id="f25a3-131">Segment with Trigger</span></span>|<span data-ttu-id="f25a3-132">触发器字段</span><span class="sxs-lookup"><span data-stu-id="f25a3-132">Trigger field</span></span>|  
|--------------------------|-------------------|  
|<span data-ttu-id="f25a3-133">AMT</span><span class="sxs-lookup"><span data-stu-id="f25a3-133">AMT</span></span>|<span data-ttu-id="f25a3-134">AMT01</span><span class="sxs-lookup"><span data-stu-id="f25a3-134">AMT01</span></span>|  
|<span data-ttu-id="f25a3-135">CRC</span><span class="sxs-lookup"><span data-stu-id="f25a3-135">CRC</span></span>|<span data-ttu-id="f25a3-136">CRC01</span><span class="sxs-lookup"><span data-stu-id="f25a3-136">CRC01</span></span>|  
|<span data-ttu-id="f25a3-137">DTM</span><span class="sxs-lookup"><span data-stu-id="f25a3-137">DTM</span></span>|<span data-ttu-id="f25a3-138">DTM01</span><span class="sxs-lookup"><span data-stu-id="f25a3-138">DTM01</span></span>|  
|<span data-ttu-id="f25a3-139">DTP</span><span class="sxs-lookup"><span data-stu-id="f25a3-139">DTP</span></span>|<span data-ttu-id="f25a3-140">DTP01</span><span class="sxs-lookup"><span data-stu-id="f25a3-140">DTP01</span></span>|  
|<span data-ttu-id="f25a3-141">ENT</span><span class="sxs-lookup"><span data-stu-id="f25a3-141">ENT</span></span>|<span data-ttu-id="f25a3-142">ENT02</span><span class="sxs-lookup"><span data-stu-id="f25a3-142">ENT02</span></span>|  
|<span data-ttu-id="f25a3-143">HI</span><span class="sxs-lookup"><span data-stu-id="f25a3-143">HI</span></span>|<span data-ttu-id="f25a3-144">HI01:01</span><span class="sxs-lookup"><span data-stu-id="f25a3-144">HI01:01</span></span>|  
|<span data-ttu-id="f25a3-145">N1</span><span class="sxs-lookup"><span data-stu-id="f25a3-145">N1</span></span>|<span data-ttu-id="f25a3-146">N101</span><span class="sxs-lookup"><span data-stu-id="f25a3-146">N101</span></span>|  
|<span data-ttu-id="f25a3-147">NM1</span><span class="sxs-lookup"><span data-stu-id="f25a3-147">NM1</span></span>|<span data-ttu-id="f25a3-148">NM01</span><span class="sxs-lookup"><span data-stu-id="f25a3-148">NM01</span></span>|  
|<span data-ttu-id="f25a3-149">NTE</span><span class="sxs-lookup"><span data-stu-id="f25a3-149">NTE</span></span>|<span data-ttu-id="f25a3-150">NTE01</span><span class="sxs-lookup"><span data-stu-id="f25a3-150">NTE01</span></span>|  
|<span data-ttu-id="f25a3-151">REF</span><span class="sxs-lookup"><span data-stu-id="f25a3-151">REF</span></span>|<span data-ttu-id="f25a3-152">REF01</span><span class="sxs-lookup"><span data-stu-id="f25a3-152">REF01</span></span>|  
|<span data-ttu-id="f25a3-153">RMR</span><span class="sxs-lookup"><span data-stu-id="f25a3-153">RMR</span></span>|<span data-ttu-id="f25a3-154">RMR01</span><span class="sxs-lookup"><span data-stu-id="f25a3-154">RMR01</span></span>|