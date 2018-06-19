---
title: 如何使用复杂全局类型 |Microsoft 文档
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
ms.openlocfilehash: 5f84b8b872d047a62a913514a695b4bba2d482c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288653"
---
# <a name="ways-to-use-complex-global-types"></a>使用复杂全局类型的方法
将某一复杂类型转换为全局复杂类型之后，它就可以在您的架构的其他位置中重用。 有关定义复杂类型，然后将它转换为全局复杂类型的详细信息，请参阅[复杂全局类型定义和命名](../core/complex-global-type-definition-and-naming.md)。  
  
 首先，插入一个新**记录**节点。 然后，选择所插入节点并在“属性”窗口中设置以下两个节点属性之一，每个将产生不同效果：  
  
-   **数据结构类型属性**。 如果要使用复杂全局类型而不对其进行修改，则将此属性设置为您提供给复杂全局类型的类型名称，该类型名称作为下拉列表中的选项提供。 在架构树中，将在新位置中以图形方式复制所选的全局节点结构，如果对架构树中任何位置的节点结构进行后续更改，将自动对使用该复杂全局类型的所有位置进行相同更改。  
  
-   **基数据类型属性**。 如果要使用复杂全局类型的变体，以某种方式对其进行扩展或限制，则将此属性设置为您提供给复杂全局类型的类型名称，该类型名称作为下拉列表中的选项提供。 当设置此属性，**派生源**节点属性更改为**扩展**(和**内容类型**属性更改为**ComplexContent**)，指示该扩展的复杂全局类型是默认的派生类型。 你可以将其更改为**限制**如果您修改该性质的则。 对从其派生的基本复杂全局类型的更改将自动反映在派生类型中，但在派生类型中所做的更改将不会反映在基本类型中。  
  
> [!NOTE]
>  设置上述属性之一将自动导致另一个属性删除现有设置。 此外，你将注意到相关的属性，例如设置之间的其他自动交互**派生源**属性 **（默认）** 中删除任何现有设置从**基数据类型**属性。  
  
> [!NOTE]
>  您可以创建一个测试架构并为这些属性使用不同值，以观察 XSD 视图中的变化。  
  
 本部分将介绍按本主题中描述的属性设置来控制原样使用复杂全局类型，对其进行扩展和限制。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [复杂全局类型重复使用](../core/complex-global-type-re-use.md)  
  
-   [复杂全局类型派生](../core/complex-global-type-derivation.md)