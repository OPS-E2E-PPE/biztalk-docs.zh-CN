---
title: "控制实例的节点消息结构和变体 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af8e6ce-282d-4318-a538-046b423ef033
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa82def3f62c6a603ef67e098e53b48a49013a3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a>控制实例消息结构和变体的节点
在 BizTalk 编辑器中用于创建架构的某些节点类型控制着实例消息的结构和实例消息中的变体。 你使用**序列组**节点若要指定的元素序列必须对实例消息中的对应位置中的特定顺序发生。 你使用**选项组**节点指定的元素集合中的一个元素会在实例消息中的对应位置。 你使用**所有组**节点指定的所有指定的元素可能发生的任何顺序，但一次，在实例消息中的相应位置。 **\<等效\>**节点及其子节点显示在架构树，以指示的位置实例消息中基于派生的多态性起作用，并允许之一很多相关的复杂数据类型出现在实例消息中的对应位置。  
  
 本部分的其余部分将提供有关此类节点的其他信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [“顺序组”节点](../core/sequence-group-nodes.md)  
  
-   [“选择组”节点](../core/choice-group-nodes.md)  
  
-   [“全部组”节点](../core/all-group-nodes.md)  
  
-   [\<等效\>节点和它们的子节点](../core/equivalent-nodes-and-their-child-nodes.md)