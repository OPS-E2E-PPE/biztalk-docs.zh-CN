---
title: "如何插入序列组、 选择组或所有组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e498eb5ec8e7aa1398cfb58732f978faa9d0b415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a>如何插入序列组、 选择组或所有组节点
BizTalk 编辑器支持三种类型的组节点的元素：**序列组**，**选项组**，和**所有组**。 这些不同类型的组节点可以在相应的实例消息中建立对组的子节点的不同约束。 有关这些不同类型的组所受约束的信息，请直接参阅 Web 上有关 XML 架构定义 (XSD) 语言的信息。 此信息的链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 BizTalk 编辑器还支持组节点的属性，**属性组**节点。 此类节点允许一组要定义一次，，然后与多个关联的特性**记录**架构中的节点。  
  
 到您的架构生成结构时**记录**节点被假定为包含的子节点的有序的序列默认情况下，而通过使用表示**序列**的 XSD 表示形式中的元素架构。 您可以通过更改更改组节点的类型及其**顺序类型**属性。  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a>插入“顺序组”节点或“选择组”节点  
  
1.  在架构树视图中，选择**记录**你想要插入的节点**序列组**节点或**选项组**节点。  
  
2.  上**BizTalk**菜单上，指向**插入架构节点**，然后单击**序列组**或**选项组**适当。  
  
### <a name="to-insert-an-all-group-node"></a>插入“全部组”节点  
  
1.  在架构树视图中，选择新**记录**你想要插入的节点**所有组**节点。  
  
2.  上**BizTalk**菜单上，指向**插入架构节点**，然后单击**所有组**。  
  
> [!NOTE]
>  **所有组**选择是仅在 BizTalk （或快捷方式） 菜单上可用时相关的父**记录**节点满足 XSD 有一定的使用约束**所有**元素。  
  
> [!NOTE]
>  **所有组**选择需要**记录**节点具有一个基本数据类型。 快速的方法来为数据类型的节点是若要设置其**内容类型**到**复杂**。  
  
### <a name="to-insert-an-attribute-group-node"></a>插入“属性组”节点  
  
1.  在架构树视图中，选择**记录**你想要插入的节点**属性组**节点。  
  
2.  上**BizTalk**菜单上，指向**插入架构节点**，然后单击**属性组**。  
  
> [!NOTE]
>  如果你想要更改新插入的名称**属性组**节点，键入新名称出现在其**组引用**属性。  
  
## <a name="see-also"></a>另请参阅  
 [将节点插入到架构](../core/inserting-nodes-into-a-schema.md)