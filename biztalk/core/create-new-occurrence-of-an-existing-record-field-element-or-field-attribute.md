---
title: 如何创建现有记录、 Field 元素或字段属性节点的新实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f8974de22b7ee99a02d551553cb5e36f31a0d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238173"
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a>如何创建现有记录、 Field 元素或字段属性节点的一个新事件
你可以创建现有的新实例**记录**， **Field 元素**，或**字段特性**节点以便到任何实例的后续修改反映到所有实例。  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a>创建现有“记录”、“字段元素”或“字段属性”节点的新实例  
  
1.  选择原始**记录**， **Field 元素**，或**字段特性**节点，请确保其**基数据类型**属性设置正确，然后在其**数据结构类型**(**记录**节点) 或其**数据类型**(**Field 元素**和**字段特性**节点) 属性，键入一个自定义数据类型名称。  
  
2.  插入新**记录**， **Field 元素**，或**字段特性**节点和组的自定义数据的以下属性之一键入你在步骤 1 中键入的名称。  
  
    -   数据结构类型 (**记录**节点)  
  
    -   数据类型 (**Field 元素**和**字段特性**节点)  
  
    > [!NOTE]
    >  如果新**记录**或**Field 元素**节点是同级的原始节点，和你为新的节点作为原始节点相同的名称，您将看到一个消息框，询问有关重复相同的作用域中的节点具有相同的名称。 单击**是**执行与在步骤 2 中选择的自定义数据类型名称相同的操作。  
  
> [!NOTE]
>  创建现有的新实例**记录**， **Field 元素**，或**字段特性**节点。  
  
> [!NOTE]
>  某些属性**记录**， **Field 元素**，或**字段特性**节点实例保持相同 （一个实例的更改是对所有实例的更改），和其他属性可以单独设置每个实例。  
  
## <a name="see-also"></a>另请参阅  
 [将节点插入到架构](../core/inserting-nodes-into-a-schema.md)