---
title: 创建声明的 Z 段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67b6469130173dbdc60d223f4f5c4f268699ce3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255636"
---
# <a name="creating-declared-z-segments"></a>创建声明的 Z 段
可以在任何级别 （不同于未声明的 Z 段，它必须是以下正文部分的多方消息的最后一部分） 的架构创建声明的 Z 段。  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a>若要创建在 BizTalk 编辑器中的 Z 段  
  
1.  在解决方案资源管理器的 Visual Studio 中，右键单击你想要添加的 Z 段，并单击的架构**打开**。  
  
2.  在 BizTalk 编辑器中，右键单击具有架构的名称的节点，指向**插入 Schema 节点**，然后单击**子记录**。  
  
3.  名称的名称以三个字母数字，字母都大写，与第一个数字被"Z"开头的记录。 （Z 段标记必须包含三个字符）。插入下划线 (_)，然后添加段的简短说明。 说明应为一个或一系列文字，不含空格，使用首字母大写每个单词的第一个字母。 最后一个单词应为"段"。 （例如，"ZPP_PatientPreferencesSegment。）按 **Enter**。  
  
4.  在属性窗格中，键入想要的 Z 段的属性包括**Data Structure Type** （架构名称或格式 xsd: anytype） **Max Occurs**，并**Min Occurs**。  
  
    > [!NOTE]
    >  如果输入数据结构类型的记录，你将不能添加子字段元素。  
  
5.  在 BizTalk 编辑器中，右键单击的 Z 段的名称，指向**插入 Schema 节点**，然后单击**子字段元素**。  
  
6.  键入名称开头的段名称后, 跟一个句点和跟下划线，然后在字段的简短说明的字段数的前三个数字字段的名称。 说明应为一个或一系列文字，不含空格，使用首字母大写每个单词的第一个字母。 按 **Enter**。  
  
7.  在属性窗格中，键入想要的 Z 段的属性包括**数据类型**， **Nillable**，**固定**，**最大出现次数**，并**最小出现次数**。  
  
8.  若要创建组件字段，将创建为一个记录，然后再创建该记录为每个组件的子元素。 若要使用子组件创建一个字段，创建字段和组件作为记录，并且子组件为作为子元素。 请注意，子组件不能为复合数据类型。 例如，对于名为 ZPP_PatientPreferencesSegment 的段，你可能创建 ZPP.1_Dietary 字段和 PD.1 过敏组件与 PD.1.1_FoodGroupAllergy 子组件。 PD.1.1_FoodGroupAllergy 子组件必须是简单的数据类型。  
  
## <a name="see-also"></a>请参阅  
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [在架构中创建自定义表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)