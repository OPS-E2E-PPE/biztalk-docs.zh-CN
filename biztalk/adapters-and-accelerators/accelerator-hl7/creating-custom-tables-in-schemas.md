---
title: "在架构中创建自定义表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c3ce69e60517f90af4031bf76691a551afcbe2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-tables-in-schemas"></a>在架构中创建自定义的表
你可以在 tablevalues_ 中创建自定义表格\<*版本*>.xsd 公用架构。 你可以基于自定义的表，现有的数据类型，一个基本数据类型，或基于表中定义的枚举。  
  
### <a name="to-create-a-z-table"></a>若要创建 Z 表  
  
1.  在解决方案资源管理器，打开通用的数据类型架构文件 **tablevalues_\<*版本*>.xsd * *，，然后单击**打开**。  
  
2.  在 BizTalk 编辑器中，右键单击**HL7DefinedTables**，指向**插入架构节点**，然后单击**子字段元素**。  
  
3.  命名此表与字母"Z"开头的标记。  
  
4.  根据需要请在属性窗格中，键入所需的特定属性的值。  
  
5.  若要将枚举与表中，在属性窗格中，关联设置**派生源**到**限制**，单击**枚举**，单击的省略号（…）按钮**枚举**，然后键入想要包含在枚举编辑器中的枚举的值。 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)