---
title: 分隔符已知的问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de686d136d0158315dfd00eba9690b8ffcbdccc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985646"
---
# <a name="delimiters-known-issues"></a>分隔符已知的问题
本部分包含可帮助你避免分隔符错误的有用信息。  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a>不建议用作分隔符的字符  
 建议您不要使用以下字符作为分隔符因为它们可能会导致错误：  
  
-   Null 字符  
  
-   空格  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a>标头或正文字段中的额外分隔符会导致多个错误  
 HL7 V2 中的字段中有额外分隔符时。消息，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成两条错误消息，其中一个与 XML 验证和其他与结构验证。  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a>HL7 batch 段中允许使用尾部分隔符  
 HL7 定义批处理段如 FHS、 BHS、 BTS 和 FTS 可以具有尾部分隔符和不受尾随分隔符标志，因为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证批处理段的尾部分隔符。  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)