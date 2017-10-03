---
title: "数据类型的通用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, data types
- 2.X schemas, common schemas
- common schemas
ms.assetid: 6fd30cd3-9c4f-4391-9c79-a4dff11f2a46
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19ff35b515e70c21e2349ae54847ba312d7ce0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-types-common-schemas"></a>数据类型的通用架构
 **Datatypes_*\<版本 >*.xsd * * 架构文件 (其中*\<版本 >*是 HL7 版本号) 包含的定义所有 HL7 基本和复合数据类型的相应的 HL7 版本。 Segments_*\<版本 >*.xsd 文件使用此文件与相应的 HL7 版本匹配。 DataStructures Access 数据库表生成 DataTypes_*\<版本 >*.xsd 架构文件。 下面的示例是 HL7 基本数据类型的条目**ST**:  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 此示例定义**ST**作为**字符串**。  
  
## <a name="see-also"></a>另请参阅  
 [HL7 2.X 公共架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [段通用架构](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)   
 [表值通用架构](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)