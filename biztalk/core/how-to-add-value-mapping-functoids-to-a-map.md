---
title: 如何添加值映射到图 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e463489332c3a1d2887dab5f7bd734fdd20af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247837"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a>如何向映射添加“值映射”Functoid
**值映射**functoid 返回其第二个参数的值，如果其第一个参数为 true。 该 functoid 通常用于将字段的属性更改为记录的属性。  
  
 有关概念性信息**值映射**functoid，请参阅[值映射 Functoid](../core/value-mapping-functoid.md)。  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a>向映射添加“值映射”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**值映射**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。  
  
    > [!NOTE]
    >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  若要建立的第一个输入的参数**值映射**functoid，通过拖动创建输入的链接**值映射**functoid 到源架构中的记录或字段节点或到另一个 functoid其左侧，具有 Boolean 数据类型以及将产生的输入的值为"true"或"false"。  
  
    > [!NOTE]
    >  你也可以拖动相反的方向，拖动到的布尔值的源**值映射**functoid。  
  
4.  若要建立的第二个输入的参数**值映射**functoid，通过拖动创建输入的链接**值映射**到记录或字段节点中，在源架构中，或通过拖动记录 functoid或源架构中的字段节点**值映射**functoid。  
  
    > [!NOTE]
    >  第二个输入参数**值映射**functoid 也可以从另一个 functoid 输出其左侧。 通过将某个相关 functoid 拖至另一个相关 functoid，可以创建表示此类输入源的链接。  
  
5.  若要使用输出参数从**值映射**functoid，通过拖动创建一条输出链接**值映射**记录或字段在目标架构中，或通过将记录字段中拖动 functoid目标架构**值映射**functoid。  
  
    > [!NOTE]
    >  其他 functoid 的输出与**值映射**functoid 可用作另一个 functoid 的输入。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)