---
title: 词汇 |Microsoft 文档
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
ms.openlocfilehash: 5c77247054914097131103fe33d86fc78551d8cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206653"
---
# <a name="vocabulary"></a>词汇
HL7 版本 2 的词汇对于编码的元素，提供了一些支持，但大多数情况下，提供了传输绘制从本地编码系统的代码的结构。  
  
 在 HL7 版本 2 中，段表链接编码的所有字段。 段表包含的字段将使用的表的标识符。 有三种类型的表： HL7 定义，外部定义和用户定义。 在某些情况下，标准提供用户定义表的示例值。 你应方式 HL7 标准具有标记为它们来处理这些信息。  
  
 在新版本中，您不能取消代码 HL7 定义表，但你可以添加新的代码。 你可以更改将在用户定义的表。  
  
 下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   你可以使用的所有定义的 HL7 表。  
  
-   你可以导入和使用外部定义 ICD9 等 LOINC 代码集。  
  
-   你可以为用户定义的表中提供的值。  
  
-   在系统其中支持不同的代码集的情况下，你可以设置允许进行互操作的不同代码集的映射。 如有必要，你可以定义单个用户定义表转以及中间的映射的多个实例。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)