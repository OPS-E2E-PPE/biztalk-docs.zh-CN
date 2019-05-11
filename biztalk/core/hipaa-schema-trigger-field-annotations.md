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
# <a name="hipaa-schema-trigger-field-annotations"></a>HIPAA 架构触发器字段批注
EDI 段通常包含修改段含义的限定符值。 例如，N1 段可以包含一个限定元素"BT"来表示"帐单收件人名字，"或它可能包含一个限定元素"ST"，表示"收货方名字。" 通常情况下将由业务逻辑来确定如何解释这些字段和拆装器将 N1 段的所有实例都解析为相同的 XML 记录名称;但是，BizTalk Server 所附带的 HIPAA 架构包含批注允许 EDI 拆装器以便创建唯一 XML 记录根据限定元素存在。  
  
 **触发器字段实现**  
  
 触发器字段实现为一对描述段元素的 XML 属性和触发器值导致要创建此记录。 下表列出了这些属性：  
  
|特性|用途|  
|---------------|-------------|  
|trigger_field|段字段，它将检查其触发器值。|  
|trigger_value|触发器值。<br /><br /> 这可能包含单个值，或一个空格分隔的值列表。|  
  
 下表显示触发器批注，就像处理段之后显示在 HIPAA 架构，将导致触发器激活的 EDI 段和生成的 XML 数据。  
  
|架构触发器批注|匹配的 N1 段|生成的 XML 数据|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|N1*PR\*Contoso\*XV\*0000000~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|N1*PE\*Fabrikam\*FI\*9999999~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 **触发器字段的 EDI 拆装器处理**  
  
 当接收 HIPAA 事务集，如果 EDI 拆装器遇到包含触发器字段的段时，它使用触发器信息生成特定于该段和触发器组合的 XML 记录。 例如，在以下 EDI 数据中，有的 N101，PR 和 PE 具有不同的值的两个 N1 段：  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 触发器字段批注在架构中存在时由 EDI 拆装器处理，将会导致两个单独的 XML 记录基于 N101，< N1_PayerIdentification_TS835W1_1000A > 的值和 < N1_PayeeIdentification_TS835W1_1000B >对应于 N1 * PR 和 N1\*PE。  
  
 在发送时，EDI 组装器将删除包含触发器批注的字段"_"字符后面的后缀。 例如，这两个 < N1_PayerIdentification_TS835W1_1000A > 和 < N1_PayeeIdentification_TS835W1_1000B > 都将变成 N1。  
  
 **默认段和触发器字段**  
  
 下表包含的默认段和触发器字段作为 BizTalk Server 的一部分提供的 HIPAA 文档中使用的信息：  
  
> [!NOTE]
>  与触发器字段一起使用的各个触发器值在架构之间可能会有所不同。  
  
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
|不超过|NTE01|  
|REF|REF01|  
|RMR|RMR01|