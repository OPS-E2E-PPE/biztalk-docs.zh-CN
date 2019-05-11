---
title: 词汇 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b031e30bf1206b80d292458700b45470cb6cc7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285326"
---
# <a name="vocabulary"></a>词汇
HL7 版本 2 提供一些支持的编码元素的词汇，但大多数情况下，提供传输来自本地编码系统的代码的结构。  
  
 HL7 版本 2 中的段表链接所有编码的字段。 段表包含的字段将使用的表的标识符。 有三种类型的表：HL7 定义的外部定义和用户定义。 在某些情况下，标准提供用户定义表的示例值。 如 HL7 标准具有标记它们所示，应将它们。  
  
 在新版本中，不能从 HL7 定义的表，删除代码，但您可以添加新的代码。 你可以在将用户定义表。  
  
 Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   您可以使用所有 HL7 定义表。  
  
-   可以导入和使用外部定义如 ICD9 和 LOINC 代码集。  
  
-   对于用户定义表，可以提供的值。  
  
-   在系统的支持不同的代码的情况下，您可以设置允许不同的代码集以进行互操作的映射。 如有必要，可以定义单个用户定义表的中间映射随附的多个实例。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)