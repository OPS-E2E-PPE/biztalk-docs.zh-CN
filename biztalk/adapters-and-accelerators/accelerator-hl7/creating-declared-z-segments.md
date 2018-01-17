---
title: "创建声明的 Z 段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae9148547f527d29238b6080cd499be8da7b7e6
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="creating-declared-z-segments"></a>创建声明的 Z 段
你可以在任何级别 （而不像未声明 Z 段，必须多方的消息，后面的正文部分的最后一部分） 架构创建声明的 Z 段。  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a>创建 BizTalk 编辑器中的 Z 段  
  
1.  在解决方案资源管理器的 Visual Studio 中，右键单击你想要添加一个 Z 段中，，然后单击的架构**打开**。  
  
2.  在 BizTalk 编辑器中，右键单击包含架构的名称的节点，指向**插入架构节点**，然后单击**子记录**。  
  
3.  名称名称开头三个字母数字数字，字母都大写，其中在"Z"的第一个数字的记录。 （Z 段标记必须包括三个字符。）插入下划线 (_)，然后再添加段的简短说明。 说明应为一个或一系列文字，不含空格，首字母大写的每个单词的首字母。 最后一个单词应为"段"。 （一个示例是"ZPP_PatientPreferencesSegment。）按 **Enter**。  
  
4.  在属性窗格中，键入的 Z 段中，所需的属性包括**数据结构类型**（架构名称或 xsd:anyType） **Max Occurs**，和**最小出现次数**。  
  
    > [!NOTE]
    >  如果为记录输入数据结构类型，你将无法将子字段元素添加。  
  
5.  在 BizTalk 编辑器中，右键单击 Z 段的名称，指向**插入架构节点**，然后单击**子字段元素**。  
  
6.  键入字段的名称，名称开头段名称后, 跟一个句点和跟下划线，然后选择字段的简短说明的字段数的前三个数字。 说明应为一个或一系列文字，不含空格，首字母大写的每个单词的首字母。 按 **Enter**。  
  
7.  在属性窗格中，键入的 Z 段中，所需的属性包括**数据类型**， **Nillable**，**固定**， **Max Occurs**，和**最小出现次数**。  
  
8.  若要创建具有组件的字段，请创建为一个记录，该字段，然后创建该记录每个组件的子元素。 若要创建子组件的字段，创建字段和组件作为记录，并且这些子组件作为子元素。 请注意，子组件不能为复合数据类型。 例如，对于名为 ZPP_PatientPreferencesSegment 段，你可能需要创建 ZPP.1_Dietary 字段和 PD.1 过敏组件与 PD.1.1_FoodGroupAllergy 子组件。 PD.1.1_FoodGroupAllergy 子组件都是一个简单的数据类型。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)