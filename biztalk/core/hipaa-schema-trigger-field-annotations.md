---
title: HIPAA 架构触发器字段批注 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1389284-a2ec-44e7-a2f1-8d26f83fd31d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68f8cd87ff4cb5abd58408e5736aa614d0e6d082
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387625"
---
# <a name="hipaa-schema-trigger-field-annotations"></a><span data-ttu-id="118c8-102">HIPAA 架构触发器字段批注</span><span class="sxs-lookup"><span data-stu-id="118c8-102">HIPAA Schema Trigger Field Annotations</span></span>
<span data-ttu-id="118c8-103">EDI 段通常包含修改段含义的限定符值。</span><span class="sxs-lookup"><span data-stu-id="118c8-103">EDI segments often contain qualifier values that modify the meaning of the segment.</span></span> <span data-ttu-id="118c8-104">例如，N1 段可以包含一个限定元素"BT"来表示"帐单收件人名字，"或它可能包含一个限定元素"ST"，表示"收货方名字。"</span><span class="sxs-lookup"><span data-stu-id="118c8-104">For example, an N1 segment can contain a qualifying element of “BT” to signify a “bill-to name,” or it may contain a qualifying element of “ST” to indicate a “ship-to name.”</span></span> <span data-ttu-id="118c8-105">通常情况下将由业务逻辑来确定如何解释这些字段和拆装器将 N1 段的所有实例都解析为相同的 XML 记录名称;但是，BizTalk Server 所附带的 HIPAA 架构包含批注允许 EDI 拆装器以便创建唯一 XML 记录根据限定元素存在。</span><span class="sxs-lookup"><span data-stu-id="118c8-105">Normally it is left to business logic to determine how to interpret these fields and the disassembler resolves all instances of the N1 segment to the same XML record name; however, the HIPAA schemas shipped with BizTalk Server contain annotations that allow the EDI disassembler to create unique XML records based on the presence of a qualifying element.</span></span>  
  
 <span data-ttu-id="118c8-106">**触发器字段实现**</span><span class="sxs-lookup"><span data-stu-id="118c8-106">**Trigger Field Implementation**</span></span>  
  
 <span data-ttu-id="118c8-107">触发器字段实现为一对描述段元素的 XML 属性和触发器值导致要创建此记录。</span><span class="sxs-lookup"><span data-stu-id="118c8-107">Trigger fields are implemented as a pair of XML attributes that describe the segment element and the trigger value that causes this record to be created.</span></span> <span data-ttu-id="118c8-108">下表列出了这些属性：</span><span class="sxs-lookup"><span data-stu-id="118c8-108">The following table describes these attributes:</span></span>  
  
|<span data-ttu-id="118c8-109">特性</span><span class="sxs-lookup"><span data-stu-id="118c8-109">Attribute</span></span>|<span data-ttu-id="118c8-110">用途</span><span class="sxs-lookup"><span data-stu-id="118c8-110">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="118c8-111">trigger_field</span><span class="sxs-lookup"><span data-stu-id="118c8-111">trigger_field</span></span>|<span data-ttu-id="118c8-112">段字段，它将检查其触发器值。</span><span class="sxs-lookup"><span data-stu-id="118c8-112">The segment field that will be inspected for the trigger value.</span></span>|  
|<span data-ttu-id="118c8-113">trigger_value</span><span class="sxs-lookup"><span data-stu-id="118c8-113">trigger_value</span></span>|<span data-ttu-id="118c8-114">触发器值。</span><span class="sxs-lookup"><span data-stu-id="118c8-114">The trigger value(s).</span></span><br /><br /> <span data-ttu-id="118c8-115">这可能包含单个值，或一个空格分隔的值列表。</span><span class="sxs-lookup"><span data-stu-id="118c8-115">This may contain a single value, or a space delimited list of values.</span></span>|  
  
 <span data-ttu-id="118c8-116">下表显示触发器批注，就像处理段之后显示在 HIPAA 架构，将导致触发器激活的 EDI 段和生成的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="118c8-116">The following table shows the trigger annotation as it would appear in the HIPAA schema, the EDI segment that will cause the trigger to activate, and the resulting XML data after processing the segment.</span></span>  
  
|<span data-ttu-id="118c8-117">架构触发器批注</span><span class="sxs-lookup"><span data-stu-id="118c8-117">Schema Trigger Annotation</span></span>|<span data-ttu-id="118c8-118">匹配的 N1 段</span><span class="sxs-lookup"><span data-stu-id="118c8-118">Matching N1 Segment</span></span>|<span data-ttu-id="118c8-119">生成的 XML 数据</span><span class="sxs-lookup"><span data-stu-id="118c8-119">Resulting XML Data</span></span>|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|<span data-ttu-id="118c8-120">N1\*PR\*Contoso\*XV\*0000000~</span><span class="sxs-lookup"><span data-stu-id="118c8-120">N1\*PR\*Contoso\*XV\*0000000~</span></span>|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|<span data-ttu-id="118c8-121">N1\*PE\*Fabrikam\*FI\*9999999~</span><span class="sxs-lookup"><span data-stu-id="118c8-121">N1\*PE\*Fabrikam\*FI\*9999999~</span></span>|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 <span data-ttu-id="118c8-122">**触发器字段的 EDI 拆装器处理**</span><span class="sxs-lookup"><span data-stu-id="118c8-122">**EDI Disassembler Processing of Trigger Fields**</span></span>  
  
 <span data-ttu-id="118c8-123">当接收 HIPAA 事务集，如果 EDI 拆装器遇到包含触发器字段的段时，它使用触发器信息生成特定于该段和触发器组合的 XML 记录。</span><span class="sxs-lookup"><span data-stu-id="118c8-123">When receiving a HIPAA transaction set, if the EDI disassembler encounters a segment that contains a trigger field, it uses the trigger information to generate an XML record specific to the segment and trigger combination.</span></span> <span data-ttu-id="118c8-124">例如，在以下 EDI 数据中，有的 N101，PR 和 PE 具有不同的值的两个 N1 段：</span><span class="sxs-lookup"><span data-stu-id="118c8-124">For example, in the following EDI data, there are two N1 segments that have different values for N101, PR and PE:</span></span>  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 <span data-ttu-id="118c8-125">触发器字段批注在架构中存在时由 EDI 拆装器处理，将会导致两个单独的 XML 记录基于 N101，< N1_PayerIdentification_TS835W1_1000A > 的值和 < N1_PayeeIdentification_TS835W1_1000B >对应于 N1 \* PR 和 N1\*PE。</span><span class="sxs-lookup"><span data-stu-id="118c8-125">When processed by the EDI disassembler, the trigger field annotations present in the schema will result in two separate XML records based on the value of N101, <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B>, corresponding to N1\*PR and N1\*PE.</span></span>  
  
 <span data-ttu-id="118c8-126">在发送时，EDI 组装器将删除包含触发器批注的字段"_"字符后面的后缀。</span><span class="sxs-lookup"><span data-stu-id="118c8-126">When sending, the EDI assembler will drop the suffix following the “_” character for fields that contain a trigger annotation.</span></span> <span data-ttu-id="118c8-127">例如，这两个 < N1_PayerIdentification_TS835W1_1000A > 和 < N1_PayeeIdentification_TS835W1_1000B > 都将变成 N1。</span><span class="sxs-lookup"><span data-stu-id="118c8-127">For example, both <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B> will both become N1.</span></span>  
  
 <span data-ttu-id="118c8-128">**默认段和触发器字段**</span><span class="sxs-lookup"><span data-stu-id="118c8-128">**Default Segments and Trigger Fields**</span></span>  
  
 <span data-ttu-id="118c8-129">下表包含的默认段和触发器字段作为 BizTalk Server 的一部分提供的 HIPAA 文档中使用的信息：</span><span class="sxs-lookup"><span data-stu-id="118c8-129">The following table contains information on the default segments and trigger fields used in HIPAA documents supplied as part of BizTalk Server:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="118c8-130">与触发器字段一起使用的各个触发器值在架构之间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="118c8-130">The individual trigger values used with the trigger fields may vary between schemas.</span></span>  
  
|<span data-ttu-id="118c8-131">带有触发器的段</span><span class="sxs-lookup"><span data-stu-id="118c8-131">Segment with Trigger</span></span>|<span data-ttu-id="118c8-132">触发器字段</span><span class="sxs-lookup"><span data-stu-id="118c8-132">Trigger field</span></span>|  
|--------------------------|-------------------|  
|<span data-ttu-id="118c8-133">AMT</span><span class="sxs-lookup"><span data-stu-id="118c8-133">AMT</span></span>|<span data-ttu-id="118c8-134">AMT01</span><span class="sxs-lookup"><span data-stu-id="118c8-134">AMT01</span></span>|  
|<span data-ttu-id="118c8-135">CRC</span><span class="sxs-lookup"><span data-stu-id="118c8-135">CRC</span></span>|<span data-ttu-id="118c8-136">CRC01</span><span class="sxs-lookup"><span data-stu-id="118c8-136">CRC01</span></span>|  
|<span data-ttu-id="118c8-137">DTM</span><span class="sxs-lookup"><span data-stu-id="118c8-137">DTM</span></span>|<span data-ttu-id="118c8-138">DTM01</span><span class="sxs-lookup"><span data-stu-id="118c8-138">DTM01</span></span>|  
|<span data-ttu-id="118c8-139">DTP</span><span class="sxs-lookup"><span data-stu-id="118c8-139">DTP</span></span>|<span data-ttu-id="118c8-140">DTP01</span><span class="sxs-lookup"><span data-stu-id="118c8-140">DTP01</span></span>|  
|<span data-ttu-id="118c8-141">ENT</span><span class="sxs-lookup"><span data-stu-id="118c8-141">ENT</span></span>|<span data-ttu-id="118c8-142">ENT02</span><span class="sxs-lookup"><span data-stu-id="118c8-142">ENT02</span></span>|  
|<span data-ttu-id="118c8-143">HI</span><span class="sxs-lookup"><span data-stu-id="118c8-143">HI</span></span>|<span data-ttu-id="118c8-144">HI01:01</span><span class="sxs-lookup"><span data-stu-id="118c8-144">HI01:01</span></span>|  
|<span data-ttu-id="118c8-145">N1</span><span class="sxs-lookup"><span data-stu-id="118c8-145">N1</span></span>|<span data-ttu-id="118c8-146">N101</span><span class="sxs-lookup"><span data-stu-id="118c8-146">N101</span></span>|  
|<span data-ttu-id="118c8-147">NM1</span><span class="sxs-lookup"><span data-stu-id="118c8-147">NM1</span></span>|<span data-ttu-id="118c8-148">NM01</span><span class="sxs-lookup"><span data-stu-id="118c8-148">NM01</span></span>|  
|<span data-ttu-id="118c8-149">不超过</span><span class="sxs-lookup"><span data-stu-id="118c8-149">NTE</span></span>|<span data-ttu-id="118c8-150">NTE01</span><span class="sxs-lookup"><span data-stu-id="118c8-150">NTE01</span></span>|  
|<span data-ttu-id="118c8-151">REF</span><span class="sxs-lookup"><span data-stu-id="118c8-151">REF</span></span>|<span data-ttu-id="118c8-152">REF01</span><span class="sxs-lookup"><span data-stu-id="118c8-152">REF01</span></span>|  
|<span data-ttu-id="118c8-153">RMR</span><span class="sxs-lookup"><span data-stu-id="118c8-153">RMR</span></span>|<span data-ttu-id="118c8-154">RMR01</span><span class="sxs-lookup"><span data-stu-id="118c8-154">RMR01</span></span>|