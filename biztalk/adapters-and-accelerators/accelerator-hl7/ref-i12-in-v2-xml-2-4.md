---
title: V2 中的 REF_I12。XML 2.4 |Microsoft Docs
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
ms.openlocfilehash: d2fdd92400754a22e92f5207bdfbc1c0703d3c83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289953"
---
# <a name="refi12-in-v2xml-24"></a>V2 中的 REF_I12。XML 2.4
您必须手动更改 V2 中的 REF_I12 架构中的以下代码。XML 2.4，运行 Update2XMLSchema 工具后：  
  
```  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
```  
  
 必须与以下内容，替换上面的代码中，若要解决多义性问题引起的多个实例**REF**元素定义：  
  
```  
<xsd:element minOccurs="0" maxOccurs="2" ref="REF_I12.PATIENT_VISIT" />  
```  
  
## <a name="see-also"></a>请参阅  
 [所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)   
 [实用工具](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)