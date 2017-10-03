---
title: "如何在向地图添加 Nil 值 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc7d8b0035161b4a2126ace021072ffcd1d17e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a>如何向映射中添加“Nil 值”Functoid
**Nil 值**functoid 设置到的目标节点的值**Nil**。  
  
 有关概念性信息**Nil 值**functoid，请参阅[Nil 值 Functoid](../core/nil-value-functoid.md)。  
  
## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a>在向地图添加 Nil 值 functoid，并将其配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。 此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**Nil 值**functoid (![Nil 值 functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。  
    >
    >  如果你在构造的地图，使用多个 functoid，你需要考虑它们相对的从左到右位置。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  **Nil 值**functoid 可以具有零到一个输入参数。 如果没有此 functoid 没有输入的参数，将目标节点设置为**Nil**。 若要建立的输入的参数**Nil 值**functoid，通过将输出拖从其他创建输入的链接**逻辑**functoid 或从输入的实例消息中的变量布尔字段。  
  
4.  若要使用输出参数从**Nil 值**functoid，通过拖动创建一条输出链接**Nil 值**functoid 记录或目标架构中的字段。  
  
    > [!NOTE]
    >  其他 functoid 的输出与**Nil 值**functoid 可以用作输入另一个 functoid。  
  
## <a name="see-also"></a>另请参阅  
-  **Nil 值 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)