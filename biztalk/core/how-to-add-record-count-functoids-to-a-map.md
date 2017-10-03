---
title: "如何在向地图添加记录计数 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd315a637b3efd069361dfa2d780cff179559da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a>如何在向地图添加记录计数 Functoid
**记录计数**functoid，可以对实例消息中生成的记录出现的次数计数。  
  
 有关概念性信息**记录计数**functoid，请参阅[记录计数 Functoid](../core/record-count-functoid.md)。  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a>向映射添加“记录计数”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**记录计数**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。  
  
    > [!NOTE]
    >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  若要建立的输入的参数**记录计数**functoid，通过将循环记录拖到源架构中创建的输入的链接**记录计数**functoid，或拖动**记录计数**functoid 到源架构中的循环记录。  
  
4.  若要使用输出参数从**记录计数**functoid，通过拖动创建一条输出链接**记录计数**functoid 给目标架构中或通过将字段拖到目标中的字段将架构与**记录计数**functoid。  
  
    > [!NOTE]
    >  其他 functoid 的输出与**记录计数**functoid 可以用作输入另一个 functoid。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)