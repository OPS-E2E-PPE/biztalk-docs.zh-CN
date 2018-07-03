---
title: 如何向映射添加迭代 Functoid |Microsoft Docs
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
ms.openlocfilehash: 8ed2dfe33feb7d5e0e6f43be61742bfbbddfc98c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997190"
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a>如何向映射添加“迭代”Functoid
**迭代**functoid 输出循环中的当前记录的索引结构，从第一条记录，2 表示第二个记录 1 开始，依次类推。  
  
 有关概念性信息**迭代**functoid，请参阅[迭代 Functoid](../core/iteration-functoid.md)。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>向映射添加“索引”functoid 并对其进行配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    此时，将显示所选类别的高级 functoid 列表。  
  
2. 拖动**索引**functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
  
   > [!NOTE]
   >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3. 若要建立循环记录输入的参数**迭代**functoid 创建输入的链接： 将源架构中的循环记录**迭代**functoid，或通过拖动**迭代**至源架构中的循环记录。  
  
4. 若要使用的输出参数**迭代**functoid，创建输出链接： 将**迭代**functoid 到目标架构中或通过拖动到目标架构中的字段的字段**迭代**functoid。  
  
   > [!NOTE]
   >  目标架构中的相关字段的数据类型必须是数值或可转换为数值，使其匹配的输出数据类型**迭代**functoid。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)