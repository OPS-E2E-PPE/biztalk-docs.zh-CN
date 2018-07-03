---
title: 段通用架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, segments
- common schemas
ms.assetid: 6f66bce9-ead8-46c1-a66c-830750adc73b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46e961934b1595217b94aab82b2adae9fd3e456f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985478"
---
# <a name="segments-common-schemas"></a>段通用架构
**Segments_\<*版本*\>.xsd**文件包括 datatypes_\<*版本*\>.xsd 和包含HL7 版本与相关的所有段的定义。 每个消息架构使用 segments_\<*版本*\>.xsd。 HL7 消息定义下每个子文件夹，并且包括 segments_\<*版本*\>.xsd。 SegmentDataElements 和 DataElements 访问数据库表生成 segments_\<*版本*\>.xsd 文件，其中包含指向所有数据类型的 Fields.xsd 架构文件的指针。 架构文件的格式为：  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 其中*xxx*是消息类型*nnn*是触发器事件*vaa*是版本号，GLO 指示全球化，和 DEF 指示默认值。 架构文件 *\<xxx\>*<em>*\<nnn\>*  \\</em>   *\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdis从 EventMessageTypeSegments 和 SegmentDataElements 访问数据库表生成的包括指向段\_\<*版本*\>.xsd 架构文件。  
  
## <a name="see-also"></a>请参阅  
 [HL7 2.X 通用架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [数据类型通用架构](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [表值通用架构](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)