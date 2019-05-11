---
title: 如何插入序列组、 选择组或全部组节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfc4b4f244c0a265a0b65efaf2f8f7bbd25e9ebd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384955"
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a>如何插入序列组、 选择组或全部组节点
BizTalk 编辑器支持三种类型的组节点的元素：**序列组**，**选择组**，和**全部组**。 这些不同类型的组节点在相应实例消息中建立组的子节点上的各种约束。 有关这些不同类型的组的约束，您应请直接参阅 Web 上有关 XML 架构定义 (XSD) 语言的信息。 此信息的链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 BizTalk 编辑器还支持组节点对于属性，**属性组**节点。 此类节点允许一组要定义一次，并会与多个相关联的特性**记录**架构中的节点。  
  
 到您的架构中生成结构时**记录**节点假定为包含子节点的有序的序列默认情况下，并使用来表示**序列**的 XSD 表示形式中的元素架构。 可以通过更改更改组节点的类型及其**Order Type**属性。  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a>若要插入顺序组节点或选择组节点  
  
1.  在架构树视图中，选择**记录**你想要插入的节点**序列组**节点或**选择组**节点。  
  
2.  上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**序列组**或**选择组**根据。  
  
### <a name="to-insert-an-all-group-node"></a>若要插入全部组节点  
  
1.  在架构树视图中，选择新**记录**你想要插入的节点**全部组**节点。  
  
2.  上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**全部组**。  
  
> [!NOTE]
>  **全部组**选项才可用的 BizTalk （或快捷） 菜单上时相关的父**记录**节点符合 XSD 的使用施加的约束**所有**元素。  
  
> [!NOTE]
>  **全部组**选择需要**记录**节点具有基本数据类型。 为节点指定数据类型的快速方法是设置其**内容类型**到**复杂**。  
  
### <a name="to-insert-an-attribute-group-node"></a>若要插入属性组节点  
  
1.  在架构树视图中，选择**记录**你想要插入的节点**属性组**节点。  
  
2.  上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**属性组**。  
  
> [!NOTE]
>  如果你想要更改新插入的名称**属性组**节点中，键入新名称在其**组参考**属性。  
  
## <a name="see-also"></a>请参阅  
 [向架构插入节点](../core/inserting-nodes-into-a-schema.md)