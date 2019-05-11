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
ms.openlocfilehash: 5f2c63d0278d4962141791a7c7a98d689e84c268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343200"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a>如何向映射添加记录计数 Functoid
**记录计数**functoid，您可以在实例消息中生成一条记录出现次数的计数。  
  
 有关概念性信息**记录计数**functoid，请参阅[记录计数 Functoid](../core/record-count-functoid.md)。  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a>向映射添加记录计数 functoid 并将其配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    将显示所选类别的高级 functoid 列表。  
  
2. 拖动**记录计数**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置上显示的网格页。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示的其他网格页。  
  
   > [!NOTE]
   >  如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。 从左向右执行 Functoid。 Functoid 的输出只能输入到其右侧的另一个 functoid。  
  
3. 若要建立输入的参数**记录计数**functoid 创建输入的链接： 将源架构中的循环记录**记录计数**functoid，或拖动**记录计数**至源架构中的循环记录。  
  
4. 若要使用的输出参数**记录计数**functoid，创建输出链接： 将**记录计数**functoid 到目标架构中或将字段拖放目标中的字段架构**记录计数**functoid。  
  
   > [!NOTE]
   >  与其他 functoid 的输出一样**记录计数**functoid 可以用作另一个 functoid 的输入。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)