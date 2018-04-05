---
title: V2 中的 REF_I12。XML 2.4 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF_I12 schema
ms.assetid: 95f40b75-a176-4fc6-b9ad-65721d456ea4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a230611424efb527eec6f75f6fb7623561760e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="refi12-in-v2xml-24"></a>V2 中的 REF_I12。XML 2.4
你必须手动更改 V2 中的 REF_I12 架构中的以下代码。XML 2.4 后运行 Update2XMLSchema 工具：  
  
```  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
```  
  
 你必须将上面的代码替换为以下，以便修复导致多个匹配项的多义性**REF**元素定义：  
  
```  
<xsd:element minOccurs="0" maxOccurs="2" ref="REF_I12.PATIENT_VISIT" />  
```  
  
## <a name="see-also"></a>另请参阅  
 [所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)   
 [实用程序](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)