---
title: 节点属性 |Microsoft Docs
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
ms.openlocfilehash: ec003c92f374489d59986bb5324f66100adf9e63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323543"
---
# <a name="node-properties"></a>节点属性

## <a name="overview"></a>概述
在 BizTalk 编辑器中，检查并在 Visual Studio 属性窗口中设置节点属性。 在架构树视图中选择不同类型的节点，在属性窗口中显示不同的属性集。 按原样在标准[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以在类别中或未指示其类别按字母顺序显示这些属性。 使用属性窗口的顶部附近的标准按钮可以切换此设置。  
  
 节点属性，尤其是当设置为值默认设置时，通常表示 XML 架构定义 (XSD) 语言中为属性和属性值与相应元素关联。 例如，当属性设置为**最小出现次数**并**Max Occurs**属性，可用于多个不同的节点类型设置的值用作值**minOccurs**并**maxOccurs**属性，分别为其表示的节点的元素与关联**Min Occurs**和**最大值发生**设置属性。  

## <a name="property-types"></a>属性类型
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员参考包含按类别和按字母顺序组织的各种节点类型的属性的参考部分。 下面总结了与每个节点类型关联的属性：  
  
-   Schema 节点属性
  
-   记录节点属性
  
-   字段元素节点属性
  
-   字段属性节点属性
  
-   序列组节点属性
  
-   选择组节点属性 
  
-   所有组节点属性
  
-   属性组节点属性
  
-   任何元素节点属性
  
-   任何特性节点属性
  
-   等价节点属性
  
-   等价子节点属性

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 **节点属性 — 字母顺序列表**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]包含的所有分立参考主题的每个节点属性，其中一些适用于各种类型的节点。 分立参考主题进行了分类根据它们是适用于所有类型的架构的基本属性还是与架构编辑器扩展，例如平面文件扩展相关联的特殊的属性。 这些类别中它们是按字母顺序列出。  
  
 BizTalk 编辑器使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口使您可以查看和设置在架构树中节点的属性。 本部分介绍使用属性窗口，其中包括有关的特殊注意事项中的属性的某些特征**节点名称**属性、 属性之间的相互依赖项的说明和属性或类型的属性，对于某些允许的最大长度有关的信息。  
  
 本部分的其余部分提供有关特定的特殊节点属性的详细信息和其他通常适用于节点属性的信息。  
  
## <a name="next-steps"></a>后续步骤
  
-   [“节点名称”属性](../core/node-name-property.md)  
  
-   [属性依赖项](../core/property-interdependencies.md)  
  
-   [其他平面文件属性](../core/additional-flat-file-properties.md)