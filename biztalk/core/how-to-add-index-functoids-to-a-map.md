---
title: 如何向映射添加索引 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b560b1565638c7d82d6f497319387fc5f58755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976182"
---
# <a name="how-to-add-index-functoids-to-a-map"></a>如何向映射添加“索引”Functoid
**索引**functoid，您可以选择从一系列循环记录中的特定记录的信息。 每个**索引**functoid 从单个字段中选择信息。  
  
 有关概念性信息**索引**functoid，请参阅[索引 Functoid](../core/index-functoid.md)。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>向映射添加“索引”functoid 并对其进行配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    此时，将显示所选类别的高级 functoid 列表。  
  
2. 拖动**索引**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。  
  
   > [!NOTE]
   >  如果构造一起使用多个 functoid 的映射，您需要考虑其相对的从左到右位置。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3. 若要建立字段输入的参数**索引**functoid，通过将循环记录中的字段拖到源架构中创建输入的链接**索引**functoid，或拖动**索引**至源架构中的循环记录中的字段。  
  
4. 若要建立至少一个索引输入的参数**索引**functoid，请执行以下步骤：  
  
   1.  与**索引**functoid 选择，单击省略号 (**...**) 按钮与相关联**输入参数**中的属性**属性**窗口。  
  
   2.  在中**配置索引 Functoid**对话框中，单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。  
  
   3.  在编辑框中，键入数值形式的索引输入参数。 如果其他索引值是必需的然后单击根据需要重复**确定**。  
  
5. 若要使用的输出参数**索引**functoid，创建输出链接： 将**索引**functoid 到目标架构中或通过将目标架构中的字段拖至的字段**索引**functoid。  
  
   > [!NOTE]
   >  与其他 functoid 的输出一样**索引**functoid 可以用作另一个 functoid 的输入。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)