---
title: 等效的节点和及其子节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82c58b477130431ce2b115cb141af759b6614b57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012046"
---
# <a name="equivalent-nodes-and-their-child-nodes"></a>等效的节点和及其子节点

## <a name="overview"></a>概述
**\<等效\>** 节点及其子级中使用架构树以显示出现的复杂数据类型多形性。 在从其他复杂数据类型派生一个复杂数据类型时，XSD 内的多形性允许这些数据类型之一出现在已为其指定基本复杂数据类型的位置的实例消息中。 在架构验证期间在特定位置允许多个可能的复杂数据类型之一这一事实是隐式地表示与关联的基本复杂数据类型名**基**属性**扩展**或**限制**派生的复杂数据类型的元素。 若要使此多形性在架构树中，更显而易见**\<等效\>** 显式显示节点和子节点。  

 **\<等效\>** 节点显示为子节点的基本复杂数据类型，指示有多个实例中的该位置可能会发生的复杂数据类型的出现次数消息。 子节点**\<等效\>** 节点显示的值为**名称**的相应属性**complexType**显示在尖括号内的多形性的 XSD 表示形式中的元素 (\<名称\>)。  

 **\<等效\>** 节点及其子级具有与之关联的只有两个属性：  

-   **\<等效\>** 节点：**节点名称**和**基类型**

-   子节点：**节点名称**和**派生类型**

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="xsd-representation"></a>XSD 表示形式  
 没有任何直接 XSD 表示形式**\<等效\>** 节点及其子级。 在架构树中使用此节点，可使复杂数据类型多形性表现的更为直观和明显。  

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [如何设置节点属性](../core/how-to-set-node-properties.md)
