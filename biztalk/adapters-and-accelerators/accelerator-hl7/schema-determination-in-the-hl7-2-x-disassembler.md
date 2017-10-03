---
title: "HL7 2.X 反汇编程序中的架构确定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6314f9651d09dbb041d2e8851565e904366c9efe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a>HL7 2.X 反汇编程序中的架构确定
HL7 2.X 消息包含跟正文段的编号和可选的 Z 段的标头段 (MSH)。 MSH 包含 21 字段。  
  
 当消息到达时，2.X 引擎读取标头以确定要用于分析消息正文的架构。 事件按下列顺序发生：  
  
1.  反汇编程序读取 MSH3 值 （源方） 以确定以下的验证选项：  
  
    1.  是否正文执行 XML 验证  
  
    2.  是否要验证自定义数据类型字段中的正文数据  
  
    3.  是否允许尾随分隔符在正文中  
  
    4.  什么是正文架构的目标命名空间 (**TargetNS**)  
  
2.  然后，拆装器读取 MSH9 并 MSH12 确定正文的根节点名称。 算法是，如下所示：  
  
    ```  
    Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
    ```  
  
     [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 始终允许尾随分隔符消息标头中的。 引擎将检查每个行的前三个字符的段标识符。 它保留对于正文架构定义的所有部门生成 XML。 当它遇到一个未定义的段时，它将该段视为 Z 段。 从那一刻开始，所有未定义的段构成消息的 Z 部分。 下一步 MSH 将标记此消息的末尾。 对于批处理消息下, 一步 MSH 或 BTS （批处理预告片段标记） 将标记消息的末尾。 Z 段只能包含在架构中未声明的段。 它是错误遇到声明的段。  
  
## <a name="see-also"></a>另请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)