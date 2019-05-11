---
title: 架构已知问题 |Microsoft Docs
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
ms.openlocfilehash: 3ba0257b3ac5898c639ef8fef1a7d93df19732e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289738"
---
# <a name="schema-known-issues"></a>架构已知问题
本部分包含可帮助你避免架构错误的有用信息。  
  
## <a name="mcf21glodefxsd-schema"></a>MCF_21_GLO_DEF.xsd 架构  
 在 templates\schemas\2.1 文件夹中，架构 MCF_21_GLO_DEF.xsd 不是 Common231 项目的一部分。  
  
## <a name="miscellaneous-errors-can-result-from-undeployed-schemas"></a>其他错误，可以得到未部署架构  
 如果你不能以标识解析或序列化中的错误，请验证已部署属性架构和常见的架构 (MSH/ACK)。 取消部署的属性架构和常见的架构可能导致其他错误。  
  
## <a name="if-the-starter-project-is-installed-but-the-hl7-2x-schemas-are-not-installed-running-the-schema-wizard-generates-an-error"></a>如果安装了初学者项目，但 HL7 2.X 架构不会安装、 运行架构向导生成一个错误  
 如果则运行的自定义安装的 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 中安装的这[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]初学者项目，但不要不安装 HL7 2.X 架构，然后尝试运行架构向导[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成出现错误。 此解决方案是重新运行自定义安装过程，对安装 HL7 2.X 架构。  
  
## <a name="msh91-enumeration-list-needs-to-be-updated"></a>需要更新 MSH9.1 枚举列表  
 MSH_25_GLO_DEF 架构由安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]时安装程序不包含完整的枚举列表 MSH9.1 (MessageType) 和 MSH9.2 (EventTrigger) HL72 中。X 标准。 下表列出了消息类型和触发事件的值，则会添加到其关联的表，如果你想要使用的消息类型包含的值的架构。 例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会处理 QBP ^ Z99 消息之前将"QBP"添加到 Table76 MSH_25_GLO_DEF 中的枚举，它将不处理 QBP ^ Z99 消息之前将"Z99"添加到 Table3 MSH_25_GLO_DEF 中的枚举。  
  
 若要添加到 MSH9.1 或 MSH9.2 枚举值，请参阅"若要将一个枚举值添加到消息标头架构"中的过程[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。  
  
|字段/表|要添加到枚举的值|  
|------------------|--------------------------------------|  
|MessageType/Table76|ARD，RDO，RRO|  
|TriggerEvent/Table3|K11、 K13、 K15、 MFA、 O22、 Q11、 Q13、 Q15、 Q26、 Q27、 Q28、 Q29、 R0R、 Z73、 Z74、 Z75、 Z76、 Z77、 Z78、 Z79、 Z80、 Z81、 Z82、 Z83、 Z84、 Z85、 Z86、 Z87、 Z88、 Z89、 Z90、 Z91、 Z92、 Z93、 Z94、 Z95、 Z96、 Z97、 Z98、 Z99|  
|MessageStructure/Table354|ARD_A19, ORL_O22|  
  
## <a name="btahl7-does-not-support-schemas-with-an-ambiguous-structure"></a>BTAHL7 不支持具有不明确的结构的架构  
 BTAHL7 引擎无法处理消息实例符合 HL7 架构具有不明确的结构。 不明确的架构结构是指由 HL7 标准未完全定义。 此类架构包括消息类型 CSU、 OMD、 ORD 和 SUR.  
  
## <a name="btahl7-will-return-a-segment-sequence-error-for-some-messages"></a>BTAHL7 将返回某些消息段序列错误  
 BTAHL7 不能处理符合下面列出的架构的消息。 这些消息的正文的分析将失败，从而导致以下错误："分段序列错误 （无效的段之后此段中找到）"。 下面列出了在消息受影响的段 Id。 对于所有这些错误的受影响的序列号为"2"。  
  
|版本|消息类型|触发器事件|段 ID|  
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
|V2.5|RDE|025|PSH_ProductSummaryHeader"|  
|V2.5|OUL|R24|PSH_ProductSummaryHeader"|  
|V2.5|OML|035|PSH_ProductSummaryHeader"|  
|V2.5|ORL|034|PSH_ProductSummaryHeader"|  
  
> [!NOTE]
>  上面的列表中的 2.5 版并不详尽，并可能包含更多的消息类型，因而"段序列错误"。  
  
## <a name="btahl7-does-not-support-some-v231-schemas"></a>BTAHL7 不支持某些适用于版本 v2.3.1 架构  
 BTAHL7 安装程序不会安装以下适用于版本 v2.3.1 架构：  
  
-   OMD_O01_231_GLO_DEF  
  
-   OMN_O01_231_GLO_DEF  
  
-   OMS_O01_231_GLO_DEF  
  
-   ORD_O02_231_GLO_DEF  
  
-   ORN_O02_231_GLO_DEF  
  
-   ORS_O02_231_GLO_DEF  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)