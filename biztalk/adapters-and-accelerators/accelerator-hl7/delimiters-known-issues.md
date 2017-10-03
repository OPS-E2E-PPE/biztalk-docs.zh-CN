---
title: "分隔符已知的问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18168ade94eed99efff0a062904c14b387de6bcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="delimiters-known-issues"></a>分隔符已知的问题
本节包含可以帮助您避免分隔符错误的有用信息。  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a>不建议用作分隔符的字符  
 建议，你并不使用以下字符作为分隔符因为它们可能导致错误：  
  
-   Null 字符  
  
-   空格  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a>标头或正文字段中的额外分隔符导致多个错误  
 HL7 V2 中的字段中有额外的分隔符时。X 消息， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成两条错误消息，其中一个与 XML 验证和其他与结构化的验证。  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a>HL7 批处理段中允许存在尾随分隔符  
 HL7 定义批处理段 FHS、 BHS、 BTS 和 FT 可以包含尾随分隔符，以及不受尾随分隔符标志，因为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证批处理段的尾随分隔符。  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)