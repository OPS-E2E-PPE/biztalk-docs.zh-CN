---
title: 节点属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d41f0f3b0fe0b302a763629b8777669b54f6cc86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264213"
---
# <a name="node-properties"></a>节点属性

## <a name="overview"></a>概述
在 BizTalk 编辑器中，可以在“Visual Studio 属性”窗口中检查和设置节点属性。 在架构树视图中选择不同类型的节点时，“属性”窗口中将显示不同的属性集。 按原样标准中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以显示这些属性，按类别或它们的类别未指示按字母顺序。 使用靠近“属性”窗口顶部的标准按钮可以切换此设置。  
  
 节点属性（尤其是设置为默认值之外的值时）通常在 XML 架构定义 (XSD) 语言中表示为与相应元素关联的特性和特性值。 例如，在属性设置为**最小出现次数**和**Max Occurs**属性，可用于多个不同节点类型，设置的值可用作值**minOccurs**和**maxOccurs**特性，分别为其表示的节点的元素与关联**最小出现次数**和**最大值发生**正在设置属性。  

## <a name="property-types"></a>属性类型
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员参考包含组织按类别和按字母顺序的各种节点类型的属性的参考部分。 以下汇总每个节点类型与关联的属性：  
  
-   架构节点属性
  
-   记录节点属性
  
-   字段元素节点属性
  
-   字段属性节点属性
  
-   序列组节点属性
  
-   选择组节点属性 
  
-   所有组节点属性
  
-   属性组节点属性
  
-   “任何元素”节点属性
  
-   “任何属性”节点属性
  
-   等效的节点属性
  
-   等效的子节点属性

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 **节点属性-按字母顺序排列列表**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]包含的所有独立参考主题的每个节点属性，其中一些适用于各种类型的节点。 分立参考主题按照是适用于所有架构类型的基本属性还是与架构编辑器扩展（例如，平面文件扩展）关联的特殊属性进行分类。 在这些类别中，它们按字母顺序列出。  
  
 BizTalk 编辑器使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口使您能够在架构树中检查和设置节点的属性。 本部分介绍使用属性在属性窗口中，包括有关的特殊注意事项的一些特征**节点名称**属性、 属性，之间相互依赖关系的说明和属性或类型的属性，对于某些允许的最大长度有关的信息。  
  
 本部分的其余内容提供有关特定的特殊节点属性的其他信息，以及通常适用于节点属性的其他信息。  
  
## <a name="next-steps"></a>后续步骤
  
-   [节点名称属性](../core/node-name-property.md)  
  
-   [属性相互依赖关系](../core/property-interdependencies.md)  
  
-   [其他平面文件属性](../core/additional-flat-file-properties.md)