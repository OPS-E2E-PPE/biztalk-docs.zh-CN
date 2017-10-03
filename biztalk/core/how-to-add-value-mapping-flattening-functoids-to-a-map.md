---
title: "如何添加值映射到图 （拼合） Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5fe3f7b55a5bd5ef532bf2727c60bad2a621c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a>如何向映射添加“值映射（平展）”Functoid
**值映射 （平展）** functoid，可通过将多个记录转换为单个记录平展输入的实例消息的一部分。 在转换 Microsoft Commerce Server 目录时通常执行此操作。  
  
 有关概念性信息**值映射 （平展）** functoid，请参阅[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a>向映射添加“值映射(平展)”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**值映射 （平展）** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。  
  
    > [!NOTE]
    >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  若要建立的第一个输入的参数**值映射 （平展）** functoid，通过拖动创建输入的链接**值映射 （平展）** functoid 到源中的记录或字段节点架构，或其左侧的另一个 functoid，具有 Boolean 数据类型和，将生成的输入的值为"true"或"false。  
  
    > [!NOTE]
    >  你也可以拖动相反的方向，拖动到的布尔值的源**值映射 （平展）** functoid。  
  
4.  若要建立的第二个输入的参数**值映射 （平展）** functoid，通过拖动创建输入的链接**值映射 （平展）** functoid 到源中的记录或字段节点架构，或通过将记录或字段的节点拖到源架构中**值映射 （平展）** functoid，或插入常量。  
  
    > [!NOTE]
    >  第二个输入参数**值映射 （平展）** functoid 也可以从另一个 functoid 输出其左侧。 创建链接表示通过将一个相关 functoid 拖到其他相关 functoid 输入此类源。  
  
5.  若要使用输出参数从**值映射 （平展）** functoid，通过拖动创建一条输出链接**值映射 （平展）**记录或字段在目标架构中，或通过 functoid拖动到目标架构中的记录字段**值映射 （平展）** functoid。  
  
    > [!NOTE]
    >  其他 functoid 的输出与**值映射 （平展）** functoid 可以用作输入另一个 functoid。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)