---
title: "如何在向地图添加索引 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6695f7830dcc35fbb0100c012cff10fa207f1ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-index-functoids-to-a-map"></a>如何向映射添加“索引”Functoid
**索引**functoid 使您能够选择从特定的循环记录序列中记录的信息。 每个**索引**functoid 从单个字段中选择信息。  
  
 有关概念性信息**索引**functoid，请参阅[索引 Functoid](../core/index-functoid.md)。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>向映射添加“索引”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**索引**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。  
  
    > [!NOTE]
    >  如果你在构造结合使用多个 functoid 的映射，你需要考虑它们相对的从左到右位置。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  若要建立的字段输入的参数**索引**functoid，通过将循环记录中的字段拖到源架构中创建的输入的链接**索引**functoid，或拖动**索引**functoid 到源架构中的循环记录中的字段。  
  
4.  若要建立在至少一个索引中的输入的参数**索引**functoid，执行以下步骤：  
  
    1.  与**索引**functoid 选择，单击省略号 (**...**) 与关联的按钮**输入参数**中的属性**属性**窗口。  
  
    2.  在**配置索引 Functoid**对话框中，单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。  
  
    3.  在编辑框中，键入数值形式的索引输入参数。 根据需要重复操作，如果其他索引值是必需的然后单击**确定**。  
  
5.  若要使用输出参数从**索引**functoid，通过拖动创建一条输出链接**索引**向字段在目标架构中，或通过将目标架构中的字段拖到functoid**索引**functoid。  
  
    > [!NOTE]
    >  其他 functoid 的输出与**索引**functoid 可以用作输入另一个 functoid。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)