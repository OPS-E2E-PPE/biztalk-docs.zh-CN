---
title: 在架构中创建自定义数据类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, creating Z data types [Z objects]
- data types, creating [Z objects]
- Z objects, creating Z data types
ms.assetid: e545c849-d414-4d5d-bb56-d3f9d5238c70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea38eb106b3554b72885355aaa9aef4928f4fda2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960675"
---
# <a name="creating-custom-data-types-in-schemas"></a>在架构中创建自定义数据类型
你可以在 datatypes_ 中创建自定义数据类型\<*版本*\>.xsd 公用架构。 你可以基于自定义数据类型，现有的数据类型，一个基本数据类型，或基于表中定义的枚举。  
  
### <a name="to-create-a-z-data-type"></a>若要创建 Z 数据类型  
  
1.  在解决方案资源管理器的 Visual Studio 中，打开通用的数据类型架构文件 (**datatypes_\<*版本*\>.xsd**)，然后单击**打开**.  
  
2.  在 BizTalk 编辑器中，右键单击**HL7DefinedDataTypes**，指向**插入架构节点**，然后单击**子记录**创建组件数据类型，或单击**子元素**创建简单的数据类型。  
  
3.  具有"Z"开头的三个字符标记名称的数据类型。  
  
4.  在属性窗格中，键入所需的值**基数据类型**，**数据类型**，和其他属性，根据需要。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)