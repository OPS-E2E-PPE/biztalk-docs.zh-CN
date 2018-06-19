---
title: 可重复字段段 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a801e39fac0e0bdf0cfb9ee88811703fd1c4373d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206325"
---
# <a name="repeatable-field-segments"></a>可重复字段段
段表 HL7 访问数据库中的包含的列段 （ADD、 RDT 和 QPD） 的最后一个字段， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 定义为可重复 (**Last_field_repeatable**  = **True**)。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不支持添加。 但是，RDT 和 QPD 查询的表存在，并且使用表值进行响应。 下面的示例演示如何[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]处理这些列。  
  
 客户端提交以下查询，并指示客户端通过设置想即时响应**RCP 1 响应优先级**到"**我**":  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 服务器的响应更高版本并显示以下消息的一分钟：  
  
```  
MSH|^&~\|PIMS|Gen Hosp|PCR||199811201401-0800||RTB^K42^RTB_K13|8858|P|2.3||||||||  
MSA|AA|8699|  
QAK|Q010|OK|Q42^Tabular Dispense History^HL7nnn|4  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR||19980531|19990531|  
RDF|7|PatientId^CX^20~PatientName^XPN^48~OrderControlCode^ID^2~ MedicationDispensed^CE^100~DispenseDate^TS^26~QuantityDispensed^NM^20~ OrderingProvider^XCN^120  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|525440345^Verapamil Hydrochloride 120 mg TAB^NDC |199805291115-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00182196901^VERAPAMIL HCL ER TAB 180MG ER^NDC |19980821-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00172409660^BACLOFEN 10MG TABS^NDC |199809221415-0700|10|88^Semmelweis^Samuel^^^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00054384163^THEOPHYLLINE 80MG/15ML SOLN^NDC|199810121145-0700|10|99^Lister^Lenora^^^DR^MD  
```  
  
 在示例中，你看到 QPD 和 RDT 是定义的自定义/站点。 HL7 规范，如下所示定义 QPD 和 RDT 段。  
  
## <a name="qpd---query-parameter-definition"></a>QPD-查询参数定义  
 下表显示 HL7 规范定义 QPD 的方式。  
  
|SEQ|LEN|DT|选择|RP / #|TBL #|项 #|元素名称|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|250|CE|R||0471|01375|消息查询名称|  
|2|32|ST|C|||00696|查询标记|  
|3-n|256|不定||||01435|连续字段中的用户参数|  
  
## <a name="rdt---table-row-data"></a>RDT-表行数据  
 下表显示 HL7 规范定义 RDT 的方式。  
  
|SEQ|LEN|DT|选择|RP / #|TBL #|项 #|元素名称|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1-n|变量|变量|R|||00703|列的值|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将 QPD 和 RDT 解释为可以重复的站点定义的值。 由于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]仍然无法解决的数据类型和其他详细信息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将 QPD.3 和 RDT.1 视为架构中的字符串数据类型。 你可能需要修改这些架构，具体取决于你自己站点的条件。  
  
## <a name="see-also"></a>另请参阅  
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)