---
title: 在架构中创建自定义表 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41efa501b1b937bcb179c61d6d21f1dd12deac88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255721"
---
# <a name="creating-custom-tables-in-schemas"></a>在架构中创建自定义表
可以创建自定义表中 tablevalues_\<*版本*\>.xsd 公用架构。 可以基于自定义的表，对现有数据类型的基本数据类型，或基于的表中定义的枚举。  
  
### <a name="to-create-a-z-table"></a>若要创建 Z 表  
  
1.  在解决方案资源管理器中打开的常见数据类型的架构文件**tablevalues_\<*版本*\>.xsd**，然后单击**打开**。  
  
2.  在 BizTalk 编辑器中，右键单击**HL7DefinedTables**，依次指向**插入 Schema 节点**，然后单击**子字段元素**。  
  
3.  命名此表与字母"Z"开头的标记。  
  
4.  在属性窗格中，根据需要键入所需的特定属性的值。  
  
5.  若要枚举相关联的表，在属性窗格中设置**Derived By**到**限制**，单击**枚举**，单击的省略号（...）按钮**枚举**，然后键入你想要包含在枚举编辑器中的枚举的值。 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)