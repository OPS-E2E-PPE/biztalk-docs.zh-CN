---
title: 架构已知问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, schemas
- schemas, known issues
ms.assetid: 17651462-baa9-448a-954c-c09e70640f17
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0568a892559ea119b9a198368b4521cbe49ddf45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207957"
---
# <a name="schema-known-issues"></a>架构已知问题
本节包含可以帮助您避免架构错误的有用信息。  
  
## <a name="mcf21glodefxsd-schema"></a>MCF_21_GLO_DEF.xsd 架构  
 在 templates\schemas\2.1 文件夹中，架构 MCF_21_GLO_DEF.xsd 不是 Common231 项目的一部分。  
  
## <a name="miscellaneous-errors-can-result-from-undeployed-schemas"></a>其他错误可能会导致取消部署架构  
 如果你不能识别中分析或序列化错误，请验证部署属性架构和常见架构 (MSH/ACK)。 未部署的属性架构和常见的架构可能导致其他错误。  
  
## <a name="if-the-starter-project-is-installed-but-the-hl7-2x-schemas-are-not-installed-running-the-schema-wizard-generates-an-error"></a>如果安装初学者项目，但 HL7 2.X 架构未安装时，运行架构向导将生成错误  
 如果运行的自定义安装[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 在其中安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]初学者项目，但不要不安装 HL7 2.X 架构，然后再尝试运行架构向导中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成错误。 到此解决方案是安装 HL7 2.X 架构再次运行自定义安装过程。  
  
## <a name="msh91-enumeration-list-needs-to-be-updated"></a>需要更新 MSH9.1 枚举列表  
 通过安装 MSH_25_GLO_DEF 架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]时安装程序不包含完整枚举列表 MSH9.1 (MessageType) 和 MSH9.2 （事件触发器），为包含 HL72 中。X 标准。 下表列出了消息类型和触发器事件的值，则会将添加到其关联的表，如果你想要使用的消息类型包含值的架构。 例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将不会处理 QBP ^ Z99 消息之前将"QBP"添加到在 MSH_25_GLO_DEF，Table76 枚举，它将不处理 QBP ^ Z99 消息将"Z99"添加到枚举为 Table3 中 MSH_25_GLO_DEF 之前。  
  
 若要添加到 MSH9.1 或 MSH9.2 枚举值，请参阅"将一个枚举值添加到消息标头架构"中的过程[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。  
  
|字段/表|要添加到枚举的值。|  
|------------------|--------------------------------------|  
|MessageType/Table76|ARD，RDO，RRO|  
|TriggerEvent/Table3|K11、 K13、 K15、 MFA、 O22、 Q11、 Q13、 Q15、 Q26、 Q27、 Q28、 Q29、 R0R、 Z73、 Z74、 Z75、 Z76、 Z77、 Z78、 Z79、 Z80、 Z81、 Z82、 Z83、 Z84、 Z85、 Z86、 Z87、 Z88、 Z89、 Z90、 Z91、 Z92、 Z93、 Z94、 Z95、 Z96、 Z97、 Z98、 Z99|  
|MessageStructure/Table354|ARD_A19 ORL_O22|  
  
## <a name="btahl7-does-not-support-schemas-with-an-ambiguous-structure"></a>BTAHL7 不支持架构具有不明确的结构  
 BTAHL7 引擎无法处理消息实例符合具有不明确的结构的 HL7 架构。 不明确的架构结构是指未完全定义的 HL7 标准。 此类架构包括与消息类型 CSU、 OMD、 ORD 和 SUR.  
  
## <a name="btahl7-will-return-a-segment-sequence-error-for-some-messages"></a>BTAHL7 将返回某些消息段序列错误  
 BTAHL7 无法处理符合下面列出的架构的消息。 这些消息的正文的分析将失败，导致以下错误:"分段序列错误 （无效段后此段找到）"。 下面列出了消息中受影响的段 Id。 对于所有这些错误的受影响的序列号为"2"。  
  
|版本|消息类型|触发器事件|分段 ID|  
|-------------|------------------|-------------------|----------------|  
|V2.3|CSU|C09|ORC_CommonOrderSegment|  
|V2.3|CSU|C10|ORC_CommonOrderSegment|  
|V2.3|CSU|C11|ORC_CommonOrderSegment|  
|V2.3|CSU|C12|ORC_CommonOrderSegment|  
|V2.3|SUR|P09|PSH_ProductSummaryHeader|  
|V2.3.1|CSU|C09|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C10|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C11|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C12|ORC_CommonOrderSegment|  
|V2.3.1|SUR|P09|PSH_ProductSummaryHeader<br />段|  
|V2.4|CSU|C09|ORC_CommonOrder|  
|V2.4|CSU|C10|ORC_CommonOrder|  
|V2.4|CSU|C11|ORC_CommonOrder|  
|V2.4|CSU|C12|ORC_CommonOrder|  
|V2.4|OMD|O03|ORC_CommonOrder|  
|V2.4|ORD|O04|ORC_CommonOrder|  
|V2.4|SUR|P09|PSH_ProductSummaryHeader|  
|V2.5|CSU|C09|ORC_CommonOrder|  
|V2.5|CSU|C10|ORC_CommonOrder|  
|V2.5|CSU|C11|ORC_CommonOrder|  
|V2.5|CSU|C12|ORC_CommonOrder|  
|V2.5|OMD|O03|ORC_CommonOrder|  
|V2.5|ORD|O04|ORC_CommonOrder|  
|V2.5|SUR|P09|PSH_ProductSummaryHeader"|  
|V2.5|累积|025|PSH_ProductSummaryHeader"|  
|V2.5|OUL|R24|PSH_ProductSummaryHeader"|  
|V2.5|OML|035|PSH_ProductSummaryHeader"|  
|V2.5|ORL|034|PSH_ProductSummaryHeader"|  
  
> [!NOTE]
>  有关版本 2.5 上面的列表并不详尽，并且可能包括其他消息类型，导致"段序列错误"。  
  
## <a name="btahl7-does-not-support-some-v231-schemas"></a>BTAHL7 不支持某些 v2.3.1 架构  
 BTAHL7 安装程序不会安装以下 v2.3.1 架构：  
  
-   OMD_O01_231_GLO_DEF  
  
-   OMN_O01_231_GLO_DEF  
  
-   OMS_O01_231_GLO_DEF  
  
-   ORD_O02_231_GLO_DEF  
  
-   ORN_O02_231_GLO_DEF  
  
-   ORS_O02_231_GLO_DEF  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)