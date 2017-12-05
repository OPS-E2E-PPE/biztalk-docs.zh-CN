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
# <a name="hipaa-schema-trigger-field-annotations"></a>HIPAA 架构触发器字段批注
EDI 段通常包含修改段含义的限定符值。 例如，N1 段可包含一个限定元素“BT”，表示“帐单收件人名字”，或可能包含一个限定元素“ST”，表示“收货方名字”。 通常它从左到业务逻辑来确定如何解释这些字段并拆装器将 N1 段的所有实例都解析为相同的 XML 记录名称;但是，BizTalk 服务器随附的 HIPAA 架构包含允许 EDI 反汇编程序，创建基于符合条件的元素存在的唯一 XML 记录的批注。  
  
 **触发器字段实现**  
  
 触发器字段实现为一对 XML 属性，这些属性描述导致创建此记录的段元素和触发器值。 下表描述这些属性：  
  
|Attribute|用途|  
|---------------|-------------|  
|trigger_field|将检查其触发器值的段字段。|  
|trigger_value|触发器值。<br /><br /> 该值可能包含单个值，或空格分隔的值列表。|  
  
 下表显示触发器批注，因为该批注会显示在 HIPAA 架构、将导致触发器激活的 EDI 段和处理段之后生成的 XML 数据中。  
  
|架构触发器批注|匹配的 N1 段|生成的 XML 数据|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|N1 * PR\*Contoso\*XV\*0000000 ~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|N1 * PE\*Fabrikam\*FI\*9999999 ~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 **EDI 反汇编程序处理的触发器字段**  
  
 当接收 HIPAA 事务集时，如果 EDI 拆装器遇到包含触发器字段的段时，会使用触发器信息生成特定于段和触发器组合的 XML 记录。 例如，在以下 EDI 数据中，存在两个 N1 段，这些段具有不同的 N101 值，PR 和 PE：  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 架构中出现的触发器字段批注时由 EDI 反汇编程序处理，将会导致两个单独的 XML 记录 N101，< N1_PayerIdentification_TS835W1_1000A > 的值和 < N1_PayeeIdentification_TS835W1_1000B >对应于 N1 * PR 和 N1\*PE。  
  
 发送时，EDI 组装器将为包含触发器批注的字段丢弃“_”字符后面的后缀。 例如，<N1_PayerIdentification_TS835W1_1000A> 和 <N1_PayeeIdentification_TS835W1_1000B> 都将变成 N1。  
  
 **默认的段和触发字段**  
  
 下表包含有关的默认段和触发器在作为 BizTalk 服务器的一部分提供的 HIPAA 文档中使用的字段信息：  
  
> [!NOTE]
>  用于触发器字段的各个触发器值在架构之间可能会有所不同。  
  
|带有触发器的段|触发器字段|  
|--------------------------|-------------------|  
|AMT|AMT01|  
|CRC|CRC01|  
|DTM|DTM01|  
|DTP|DTP01|  
|ENT|ENT02|  
|HI|HI01:01|  
|N1|N101|  
|NM1|NM01|  
|NTE|NTE01|  
|REF|REF01|  
|RMR|RMR01|