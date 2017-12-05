---
title: "等效的节点和它们的子节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05c5603cf1882aa7b262ecc5393a9d91dc93da10
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="equivalent-nodes-and-their-child-nodes"></a>等效的节点和它们的子节点

## <a name="overview"></a>概述
**\<等效\>**节点及其子级使用架构树中显示的复杂数据类型多态性匹配项。 在从其他复杂数据类型派生一个复杂数据类型时，XSD 内的多形性允许这些数据类型之一出现在已为其指定基本复杂数据类型的位置的实例消息中。 架构验证过程的多个可能的复杂数据类型之一的特定位置允许事实表示隐式的基的复杂数据类型名称与关联**基**属性**扩展**或**限制**派生的复杂数据类型的元素。 若要使此多态性更加明显架构树中，在**\<等效\>**显式显示节点和子节点。  
  
 **\<等效\>**节点显示为，该值指示是否存在可能会在实例中的此位置时发生的多个复杂数据类型的基的复杂数据类型的匹配项的子节点消息。 子节点**\<等效\>**节点显示的值为**名称**的相应属性**complexType**多态性，在尖括号中显示的 XSD 表示中的元素 (\<名称\>)。  
  
 **\<等效\>**节点及其子级每个具有与之关联的仅有两个属性：  
  
-   **\<等效\>**节点：**节点名称**和**基类型**
  
-   子节点：**节点名称**和**派生类型**

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="xsd-representation"></a>XSD 表示形式  
 没有任何直接的 XSD 表示形式**\<等效\>**节点及其子级。 在架构树中使用此节点，可使复杂数据类型多形性表现的更为直观和明显。  
  
## <a name="see-also"></a>另请参阅  
-  [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [如何设置节点属性](../core/how-to-set-node-properties.md)