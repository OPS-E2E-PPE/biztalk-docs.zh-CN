---
title: 如何添加循环 Functoid 映射到 |Microsoft Docs
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
ms.openlocfilehash: 659b9b39beea4bf5efed4c6d1553fca173191cc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988758"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a>如何向映射添加“循环”Functoid

## <a name="overview"></a>概述
**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。  

 有关概念性信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。  

 某些情况下，某些 functoid 可能不会按预期方式与在映射中使用时**循环**functoid。 如果此类某个 functoid 符合以下条件，此操作未生成预期的结果：  

-   functoid 具有多个输入链接。  

-   两个或多个 functoid 输入链接链接到输入记录的子字段**循环**functoid，这些子字段不是同级。  

-   Functoid 具有一个输出链接，链接到的输出记录的子字段链接**循环**functoid。  

## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a>向映射添加循环 functoid 并对其进行配置  

1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  

    此时，将显示所选类别的高级 functoid 列表。  

2. 拖动**循环**functoid 从工具箱拖至网格页上的适当位置。  

    ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
   循环 functoid  

   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
   > 
   >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  

3. 若要建立的输入的参数的**循环**functoid 创建输入的链接： 将一条记录或字段从源架构**循环**functoid，或拖动**循环** functoid 到记录或源架构中的字段。 根据需要包含所有相关输入的记录或字段添加到重复**循环**functoid。  

4. 若要使用的输出参数**循环**functoid，创建输出链接： 将**循环**到的记录或字段在目标架构中，或通过拖动的记录或字段中的 functoid目标架构**循环**functoid。  

   > [!NOTE]
   >  与其他许多 functoid 的输出不同**循环**functoid 只能链接到目标架构的元素。  

## <a name="see-also"></a>请参阅  
- [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)   
- **循环 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
