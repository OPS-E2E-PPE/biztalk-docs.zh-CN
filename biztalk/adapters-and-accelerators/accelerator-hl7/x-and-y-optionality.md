---
title: '&#39;X&#39;和&#39;Y&#39;可选性 |Microsoft Docs'
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82507c8c6d6f57c4fa85c4e20599b4fc79802e76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285292"
---
# <a name="39x39-and-39y39-optionality"></a>&#39;X&#39;和&#39;Y&#39;可选性
HL7 访问数据库中的 SegmentDataElements 表包含多个已设置为数据项 （字段）**请求/Opt = X**，这意味着 HL7 标准不会将此字段关联与此触发器事件，如中所示下表。  
  
|段|版本|一章|数据项|所需 /<br /><br /> 可选|报告|Number|HTML 标准|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|OBX|2.4|7.4.2.9|00577|X|Y|5|ch07.htm#Heading113|  
|OBX|2.4|7.4.2.8|00576|X||0|ch07.htm#Heading112|  
|OBX|2.4|7.4.2.6|00574|X||0|ch07.htm#Heading107|  
|OBX|2.4|7.4.2.17|00936|X|Y|0|ch07.htm#Heading121|  
  
 由于 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]不指定触发事件，决定哪些必需/可选规则，或应为可选。 根据本地站点的条件，您可以决定以强制实施此规则。 默认情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供 23 字段列出为"X"为可选字段。  
  
> [!NOTE]
>  值"Y"是中的错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Access 数据库。 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] 假定所有的值**Y**并**空白**都是可选的。  
  
## <a name="see-also"></a>请参阅  
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)