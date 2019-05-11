---
title: 若要使用复杂全局类型的方式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf40f80a1c1353dc56b11c8e84e8d7d395beb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393616"
---
# <a name="ways-to-use-complex-global-types"></a>使用复杂全局类型的方法
复杂类型转换为全局复杂类型后，才可以在架构中其他位置中重用它。 有关定义复杂类型并将其转换为全局复杂类型的详细信息，请参阅[复杂全局类型定义和命名](../core/complex-global-type-definition-and-naming.md)。  
  
 首先，插入一个新**记录**节点。 然后选择插入节点，并在属性窗口中，每个不同的效果设置了以下两个节点属性之一：  
  
-   **Data Structure Type 属性**。 如果你想要使用的复杂全局类型而无需以任何方式修改它，将此属性设置为您提供给复杂全局类型，可作为下拉列表中的选项的类型名称。 在架构树中，将在新位置中，以图形方式复制所选全局节点结构和任何它在架构树中位置中的节点结构的任何后续更改会自动应用到使用该复杂全局类型的所有位置.  
  
-   **Base Data Type 属性**。 如果你想要使用复杂全局类型上的一种变体，其进行扩展或限制以某种方式，此属性设置为您提供给复杂全局类型，可作为下拉列表中的选项的类型名称。 当设置此属性时**Derived By**节点属性更改为**扩展**(并**内容类型**属性更改为**ComplexContent**)，指示该扩展的复杂全局类型是默认的派生类型。 您可以将其更改为**限制**如果您的修改的任务。 对从其派生的基本复杂全局类型的更改会自动反映在派生类中，但派生类型中的更改将不会反映在基类型中。  
  
> [!NOTE]
>  自动设置这些属性之一会导致另一个具有删除现有设置。 此外，你会注意到相关属性，例如设置之间的其他自动交互**Derived By**属性设置为 **（默认）** 删除从任何现有设置**Base数据类型**属性。  
  
> [!NOTE]
>  可以创建 test 架构，并观察 XSD 视图中的更改这些属性，使用不同的值。  
  
 本部分介绍使用复杂全局类型，如，和进行扩展和限制，如由本主题中所述的属性的设置控制。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [复杂全局类型重用](../core/complex-global-type-re-use.md)  
  
-   [复杂全局类型派生](../core/complex-global-type-derivation.md)