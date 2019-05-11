---
title: V2 中的 DFT_P11。XML 2.4 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DFT_P11 schema
ms.assetid: 3887a8bb-94df-4a3b-b828-f46013d1abb8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ce08e9142a64c268390d61a36fac49dd5be9b16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255462"
---
# <a name="dftp11-in-v2xml-24"></a>V2 中的 DFT_P11。XML 2.4
您必须手动更改 V2 中的 DFT_P11 架构中的以下代码。XML 2.4，运行 Update2XMLSchema 工具后：  
  
```  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
<xsd:element ref="PV1" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="PV2" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
```  
  
 必须与以下内容，替换上面的代码中，若要解决多义性问题引起的多个实例**ROL**元素定义：  
  
```  
<xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
  <xsd:choice minOccurs="0" maxOccurs="1">  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV1" />  
      <xsd:element minOccurs="0" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
  </xsd:choice>  
```  
  
## <a name="see-also"></a>请参阅  
 [所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)   
 [实用工具](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)