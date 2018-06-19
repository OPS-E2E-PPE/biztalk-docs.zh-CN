---
title: 如何添加循环到图 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa380b4a92de685ad8dc19c27a98f6578d12dc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248725"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a>如何向映射添加“循环”Functoid

## <a name="overview"></a>概述
**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。  
  
 有关概念性信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。  
  
 某些情况下，某些 functoid 可能不会按预期在映射中使用时**循环**functoid。 如果此类 functoid 满足以下条件，它不会不会产生预期的结果：  
  
-   functoid 具有多个输入链接。  
  
-   两个或多个 functoid 输入链接链接到的输入记录的子字段**循环**functoid，子字段不是同级。  
  
-   Functoid 具有一条输出链接链接到的输出记录的子字段**循环**functoid。  
  
## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a>在向地图添加循环 functoid，并将其配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**循环**functoid 从工具箱拖到网格页上的适当位置。  
  
     ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
循环 functoid  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。  
    > 
    >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  若要建立的输入的参数**循环**functoid，通过拖动记录创建输入的链接，或从源架构字段**循环**functoid，或拖动**循环** functoid 记录或源架构中的字段。 根据需要包含的所有相关的输入的记录或字段以重复**循环**functoid。  
  
4.  若要使用输出参数从**循环**functoid，通过拖动创建一条输出链接**循环**functoid 记录或字段在目标架构中，或通过拖动的记录或中的字段目标架构**循环**functoid。  
  
    > [!NOTE]
    >  与许多其他 functoid 的输出不同**循环**functoid 只能链接目标架构中的元素。  
  
## <a name="see-also"></a>另请参阅  
-  [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)   
-  **循环 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]