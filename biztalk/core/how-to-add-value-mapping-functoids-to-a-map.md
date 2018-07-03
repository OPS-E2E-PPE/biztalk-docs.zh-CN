---
title: 如何将值映射 Functoid 向映射添加 |Microsoft Docs
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
ms.openlocfilehash: 3e4ba1b22b7db156717c2f40e91117562e879caa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996254"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a>如何向映射添加“值映射”Functoid
**值映射**functoid 在其第一个参数为 true，则返回其第二个参数的值。 该 functoid 通常用于将字段的属性更改为记录的属性。  
  
 有关概念性信息**值映射**functoid，请参阅[值映射 Functoid](../core/value-mapping-functoid.md)。  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a>向映射添加“值映射”functoid 并对其进行配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    此时，将显示所选类别的高级 functoid 列表。  
  
2. 拖动**值映射**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
  
   > [!NOTE]
   >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3. 若要建立的第一个输入的参数**值映射**functoid 创建输入的链接： 将**值映射**到源架构中的记录或字段节点或另一个 functoid 到 functoid其左侧，具有布尔数据类型，并且，将生成的输入的值为"true"或"false"。  
  
   > [!NOTE]
   >  也可以拖动相反方向拖动到布尔值的源**值映射**functoid。  
  
4. 若要建立第二个输入的参数**值映射**functoid 创建输入的链接： 将**值映射**在源架构中，或通过将一条记录的记录或字段节点到 functoid或源架构中的字段节点**值映射**functoid。  
  
   > [!NOTE]
   >  第二个输入参数**值映射**functoid 也可以从另一个 functoid 的输出至其左侧。 通过将某个相关 functoid 拖至另一个相关 functoid，可以创建表示此类输入源的链接。  
  
5. 若要使用的输出参数**值映射**functoid，创建输出链接： 将**值映射**到的记录或字段在目标架构中，或通过拖动的记录字段的 functoid目标架构**值映射**functoid。  
  
   > [!NOTE]
   >  与其他 functoid 的输出一样**值映射**functoid 可以用作另一个 functoid 的输入。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)