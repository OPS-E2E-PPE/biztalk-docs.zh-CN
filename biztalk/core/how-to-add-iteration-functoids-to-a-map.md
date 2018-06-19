---
title: 如何在向地图添加迭代 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2df7cda082a9a85e54e1dce427d73ea15d8f920
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247029"
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a>如何向映射添加“迭代”Functoid
**迭代**functoid 输出中循环的当前记录的索引结构，对于第一个记录，对于第二个记录，2 1 开始，依次类推。  
  
 有关概念性信息**迭代**functoid，请参阅[迭代 Functoid](../core/iteration-functoid.md)。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>向映射添加“索引”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**索引**functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。  
  
    > [!NOTE]
    >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  若要建立的循环记录输入的参数**迭代**functoid，通过将循环记录拖到源架构中创建的输入的链接**迭代**functoid，或通过拖动**迭代**functoid 到源架构中的循环记录。  
  
4.  若要使用输出参数从**迭代**functoid，通过拖动创建一条输出链接**迭代**functoid 给目标架构中或通过将拖到目标架构中的字段的字段**迭代**functoid。  
  
    > [!NOTE]
    >  目标架构中的相关字段的数据类型必须是数字或可转换为数字，使其匹配的输出数据类型**迭代**functoid。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)