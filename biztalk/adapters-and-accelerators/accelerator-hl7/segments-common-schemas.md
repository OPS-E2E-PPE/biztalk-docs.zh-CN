---
title: "段通用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, segments
- common schemas
ms.assetid: 6f66bce9-ead8-46c1-a66c-830750adc73b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50bdcacfe1459ba4a236c3701b786d97217db8ef
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="segments-common-schemas"></a><span data-ttu-id="97669-102">段通用架构</span><span class="sxs-lookup"><span data-stu-id="97669-102">Segments Common Schemas</span></span>
<span data-ttu-id="97669-103"> **Segments_\<*版本*\>.xsd * * 文件包括 datatypes_\<*版本*\>.xsd 和包含与 HL7 版本相关的所有线段的定义。</span><span class="sxs-lookup"><span data-stu-id="97669-103">The **segments_\<*version*\>.xsd** file includes datatypes_\<*version*\>.xsd and contains the definition of all the segments related to the HL7 version.</span></span> <span data-ttu-id="97669-104">每个消息架构使用 segments_\<*版本*\>.xsd。</span><span class="sxs-lookup"><span data-stu-id="97669-104">Each message schema uses segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="97669-105">HL7 消息定义的每个子文件夹下，包括 segments_\<*版本*\>.xsd。</span><span class="sxs-lookup"><span data-stu-id="97669-105">HL7 message definitions are under each subfolder and include segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="97669-106">SegmentDataElements 和 DataElements 访问数据库表生成 segments_\<*版本*\>.xsd 文件，其中包含指向所有数据类型的 Fields.xsd 架构文件的指针。</span><span class="sxs-lookup"><span data-stu-id="97669-106">The SegmentDataElements and DataElements Access database tables generate the segments_\<*version*\>.xsd file, which includes a pointer to the Fields.xsd schema file for all data types.</span></span> <span data-ttu-id="97669-107">架构文件名称格式为：</span><span class="sxs-lookup"><span data-stu-id="97669-107">The schema file name format is:</span></span>  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 <span data-ttu-id="97669-108">其中*xxx*是消息类型，  *nnn* 是触发器事件， *vaa*是版本号，GLO 指示全球化，并 DEF 指示默认值。</span><span class="sxs-lookup"><span data-stu-id="97669-108">Where *xxx* is the message type, *nnn* is the trigger event, *vaa* is the version number, GLO indicates globalize, and DEF indicates default.</span></span> <span data-ttu-id="97669-109">架构文件 *\<xxx\>*_*\<nnn\>*\_*\<vaa\>*  \_  *\<glo\>*\_*\<def\>*.xsdis 从生成EventMessageTypeSegments 和 SegmentDataElements 访问数据库表，并包含指向段的\_\<*版本*\>.xsd 架构文件。</span><span class="sxs-lookup"><span data-stu-id="97669-109">The schema file *\<xxx\>*_*\<nnn\>*\_*\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdis generated from the EventMessageTypeSegments and SegmentDataElements Access database tables and includes a pointer to the Segments\_\<*version*\>.xsd schema file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97669-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97669-110">See Also</span></span>  
 <span data-ttu-id="97669-111">[HL7 2.X 公共架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="97669-111">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="97669-112">[数据类型的通用架构](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="97669-112">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="97669-113">表值通用架构</span><span class="sxs-lookup"><span data-stu-id="97669-113">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)