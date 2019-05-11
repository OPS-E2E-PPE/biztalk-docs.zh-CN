---
title: 如何向映射添加批量复制 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cff63fc-8f34-4bd0-8501-a8401bde6349
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9949e849dae69873ff3f71ad2813b7d26058e124
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343264"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a>如何向映射添加批量复制 Functoid
**批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。 从本质上讲，这些元素是 XML 架构定义语言为匹配未知的结构或集的属性中提供的通配符。  
  
 有关概念性信息**批量复制**functoid，请参阅[批量复制 Functoid](../core/mass-copy-functoid.md)。  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a>向映射添加批量复制 functoid 并将其配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    将显示所选类别的高级 functoid 列表。  
  
2. 拖动**批量复制**functoid (![](../core/media/advmasscopy.gif "advmasscopy")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置上显示的网格页。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
  
   > [!NOTE]
   >  如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。 从左向右执行 Functoid。 Functoid 的输出只能输入到其右侧的另一个 functoid。  
  
3. 若要建立输入的参数**批量复制**functoid，通过拖动源架构中的一条记录创建输入的链接**批量复制**functoid，或拖动**批量复制**至源架构中的记录。  
  
4. 若要使用的输出参数**批量复制**functoid，创建输出链接： 将**批量复制**至目标架构中或通过将一条记录拖到目标架构中的记录**批量复制**functoid。  
  
   > [!NOTE]
   >  与其他 functoid 不同，您不能使用的输出**批量复制**作为另一个 functoid 的输入的 functoid。  
  
> [!NOTE]
>  可以插入和配置**批量复制**直接记录通过将两个链接的 functoid。 详细信息，请参阅"使用一个批量复制 functoid 链接"部分中[如何自动链接记录](../core/how-to-link-records-automatically.md)。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)