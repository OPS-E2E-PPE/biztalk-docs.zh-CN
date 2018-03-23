---
title: '&#39;X&#39;和&#39;Y&#39; Optionality |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, Y optionality
- segments, SegmentDataElements table
- SegmentDataElements table
- segments, X optionality
ms.assetid: 8a59b407-95a2-45ba-a8d6-db4154c91d7b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320e0188a0987601daf65c011cc24aabc49b14cb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="39x39-and-39y39-optionality"></a>&#39;X&#39;和&#39;Y&#39; Optionality
HL7 访问数据库中的 SegmentDataElements 表包含多个已设置为数据项 （字段）**请求/Opt = X**，这意味着 HL7 标准不将此字段关联与此触发器事件，如中所示下表。  
  
|段|版本|章节|数据项|所需 /<br /><br /> 選擇性|报告|Number|HTML 标准|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|OBX|2.4|7.4.2.9|00577|X|是|5|ch07.htm#Heading113|  
|OBX|2.4|7.4.2.8|00576|X||0|ch07.htm#Heading112|  
|OBX|2.4|7.4.2.6|00574|X||0|ch07.htm#Heading107|  
|OBX|2.4|7.4.2.17|00936|X|是|0|ch07.htm#Heading121|  
  
 由于[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]并不指定触发事件，你决定哪些必需/可选规则，或是否应 optionality。 根据本地站点条件，你可能决定强制实施 optionality 规则。 默认情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供列为的 23 字段为可选字段的"X"。  
  
> [!NOTE]
>  值"Y"是中的错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Access 数据库。 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] 假定所有的值**Y**和**空白**都是可选的。  
  
## <a name="see-also"></a>另请参阅  
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)