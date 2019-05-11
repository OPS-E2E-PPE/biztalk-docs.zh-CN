---
title: 如何插入记录、 字段元素或字段属性节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f63693877d9cfdc4cbb519515f64fd07a0e2510
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384940"
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a>如何插入记录、 字段元素或字段属性节点
**记录**节点 (包括**根**节点)，**字段属性**节点，和**字段元素**节点是唯一的因为它们可以被重命名，以便它们的名称表示相应的实例消息中的实际的自定义名为元素的名称。 例如，如果您命名**记录**节点 FullName，应名为 FullName 的 XML 元素的实例消息中的相应位置上。 如果该**记录**名为 FullName 的节点具有子**字段属性**名为 RequireFullMiddleName 的节点 (使用其**Min Occurs**和**Max Occurs**属性设置为**1**)，则**FullName**相应实例消息中的元素需要具有一个名为属性**RequireFullMiddleName**与之关联。  
  
 所有**记录**节点，初次插入时，表示在使用作为 XSD **complexType**元素，但不能与后续**序列**，**选择**，或**所有**元素。 出于此原因， **Group Order Type**， **Group Max Occurs**，并**Group Min Occurs**属性的**记录**节点不可用进行修改。  
  
 只要添加子**记录**或**Field 元素**节点**记录**节点，**序列**元素添加到 XSD中的表示形式**complexType**元素以包含此第一个子节点，并**Group Order Type**属性**记录**节点显示的值**序列**。 在大多数情况下，您可以更改**Group Order Type**属性从**序列**到**选**，并在更有限的情况下，从**序列**到**所有**，从而更改包含到相应的子节点的元素对**complexType/choice**或**complexType/all**分别。  
  
 **字段属性**节点不能具有相同的节点名为同一范围内。  
  
 **记录**并**Field 元素**节点可以具有相同的节点名为同一范围内，仅当满足以下条件：  
  
-   它们具有相同的数据类型。  
  
-   它们不是在**全部组**节点。  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a>插入新子记录节点、 字段元素节点或架构节点或现有的记录节点中的字段属性节点  
  
1.  选择**架构**节点或现有**记录**节点。  
  
2.  上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**子记录**，**子字段元素**，或**子字段属性**根据。  
  
    > [!NOTE]
    >  所选类型的子节点添加后的最后一个节点在架构树中 (在插入时**架构**节点) 或之后的所选现有的最后一个子节点**记录**节点 （当中的现有插入**记录**节点)。  
  
3.  键入新插入的名称**记录**， **Field 元素**，或**字段属性**节点，然后再按 ENTER。  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a>插入同级记录节点、 字段属性节点或现有记录节点中的字段元素节点  
  
1.  选择的任何子节点**记录**要在其中插入同级节点**记录**，**字段属性**，或者**字段元素**节点。  
  
2.  上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**同级记录**，**同级字段属性**，或**同级字段元素**根据。  
  
     所选类型的一个同级节点插入到所选节点的同级元素的末尾。  
  
3.  键入新插入的名称**记录**， **Field 特性**，或**字段元素**节点，然后再按 ENTER。  
  
## <a name="see-also"></a>请参阅  
 [向架构插入节点](../core/inserting-nodes-into-a-schema.md)