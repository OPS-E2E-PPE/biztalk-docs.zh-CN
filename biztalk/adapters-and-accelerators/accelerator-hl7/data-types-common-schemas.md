---
title: 数据类型的通用架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, data types
- 2.X schemas, common schemas
- common schemas
ms.assetid: 6fd30cd3-9c4f-4391-9c79-a4dff11f2a46
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e7d693cdf70f7d29a79aa8999dde49f408b8815
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960963"
---
# <a name="data-types-common-schemas"></a><span data-ttu-id="65160-102">数据类型的通用架构</span><span class="sxs-lookup"><span data-stu-id="65160-102">Data Types Common Schemas</span></span>
<span data-ttu-id="65160-103">**Datatypes_*\<版本\>*.xsd**架构文件 (其中*\<版本\>* 是 HL7 版本号)包含相应的 HL7 版本的所有 HL7 基本和复合数据类型的定义。</span><span class="sxs-lookup"><span data-stu-id="65160-103">The **datatypes_*\<version\>*.xsd** schema file (where *\<version\>* is the HL7 version number) contains the definition of all the HL7 elementary and composite data types for the corresponding HL7 version.</span></span> <span data-ttu-id="65160-104">Segments_*\<版本\>*.xsd 文件使用此文件与相应的 HL7 版本匹配。</span><span class="sxs-lookup"><span data-stu-id="65160-104">The segments_*\<version\>*.xsd file uses this file to match the corresponding HL7 version.</span></span> <span data-ttu-id="65160-105">DataStructures Access 数据库表生成 DataTypes_*\<版本\>*.xsd 架构文件。</span><span class="sxs-lookup"><span data-stu-id="65160-105">The DataStructures Access database table generates the DataTypes_*\<version\>*.xsd schema file.</span></span> <span data-ttu-id="65160-106">下面的示例是 HL7 基本数据类型的条目**ST**:</span><span class="sxs-lookup"><span data-stu-id="65160-106">The following example is an entry for the HL7 elementary data type **ST**:</span></span>  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 <span data-ttu-id="65160-107">此示例定义**ST**作为**字符串**。</span><span class="sxs-lookup"><span data-stu-id="65160-107">This example defines **ST** as a **string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65160-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65160-108">See Also</span></span>  
 <span data-ttu-id="65160-109">[HL7 2.X 公共架构文件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="65160-109">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="65160-110">[段通用架构](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="65160-110">[Segments Common Schemas](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span></span>  
 [<span data-ttu-id="65160-111">表值通用架构</span><span class="sxs-lookup"><span data-stu-id="65160-111">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)