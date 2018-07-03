---
title: 如何向映射添加记录计数 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5fda3565d2b7c3302b5ae3cb596bfed6781609
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980326"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a>如何向映射添加记录计数 Functoid
**记录计数**functoid，您可以在实例消息中生成一条记录出现次数的计数。  
  
 有关概念性信息**记录计数**functoid，请参阅[记录计数 Functoid](../core/record-count-functoid.md)。  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a>向映射添加“记录计数”functoid 并对其进行配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    此时，将显示所选类别的高级 functoid 列表。  
  
2. 拖动**记录计数**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。  
  
   > [!NOTE]
   >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3. 若要建立输入的参数**记录计数**functoid 创建输入的链接： 将源架构中的循环记录**记录计数**functoid，或拖动**记录计数**至源架构中的循环记录。  
  
4. 若要使用的输出参数**记录计数**functoid，创建输出链接： 将**记录计数**functoid 到目标架构中或将字段拖放目标中的字段架构**记录计数**functoid。  
  
   > [!NOTE]
   >  与其他 functoid 的输出一样**记录计数**functoid 可以用作另一个 functoid 的输入。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)