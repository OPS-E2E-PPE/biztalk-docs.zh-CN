---
title: HL7 2.X 反汇编程序的架构确定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e415e08882a0f1b690802af0ef165041b93eeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289749"
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a>HL7 2.X 反汇编程序的架构确定
HL7 2.X 消息包含标头段 (MSH) 后, 跟正文段数和可选的 Z 段的数目。 MSH 包含 21 字段。  
  
 当消息到达时，2.X 引擎读取的标头来确定要用于分析消息正文的架构。 发生以下事件序列：  
  
1. 拆装器读取的 MSH3 值 （源参与方） 以确定以下验证选项：  
  
   1.  是否为正文执行 XML 验证  
  
   2.  是否要验证自定义数据类型字段中的正文数据  
  
   3.  是否允许尾部分隔符在正文中  
  
   4.  什么是正文架构的目标命名空间 (**TargetNS**)  
  
2. 拆装器然后读取 MSH9 并 MSH12 确定主体的根节点名称。 该算法如下所示：  
  
   ```  
   Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
   ```  
  
    Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 始终将允许尾随分隔符消息标头中的。 引擎将检查每个行的前三个字符的段标识符。 它将保留为正文架构定义的所有段生成 XML。 当它遇到一条未定义的线段时，它视为该时间段的 Z 段。 此后，未定义的所有段都构成消息的 Z 部分。 下一步 MSH 标记此消息的末尾。 对于批处理的消息下, 一步 MSH 或 BTS （批处理尾部段标记） 标记末尾的一条消息。 Z 段只能包含在架构中未声明的段。 它是错误遇到声明的段。  
  
## <a name="see-also"></a>请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)