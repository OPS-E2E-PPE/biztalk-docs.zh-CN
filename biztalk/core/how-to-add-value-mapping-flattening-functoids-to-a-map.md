---
title: 如何将值映射 （平展） Functoid 向映射添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b630b586e1252d0afb244deb77ab3e4c7bfaf30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343058"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a>如何添加值映射 （平展） Functoid 映射到
**值映射 （平展）** functoid，可通过将多个记录转换为单个记录平展输入的实例消息的一部分。 在转换 Microsoft Commerce Server 目录时通常执行此操作。  
  
 有关概念性信息**值映射 （平展）** functoid，请参阅[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a>向映射添加值映射 （平展） functoid 并将其配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    将显示所选类别的高级 functoid 列表。  
  
2. 拖动**值映射 （平展）** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置上显示的网格页。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
  
   > [!NOTE]
   >  如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。 从左向右执行 Functoid。 Functoid 的输出只能输入到其右侧的另一个 functoid。  
  
3. 若要建立的第一个输入的参数**值映射 （平展）** functoid 创建输入的链接： 将**值映射 （平展）** 源中的记录或字段节点到 functoid架构，或其左侧的另一个 functoid，具有布尔数据类型，并且，将生成的输入的值为"true"或"false。  
  
   > [!NOTE]
   >  也可以拖动相反方向拖动到布尔值的源**值映射 （平展）** functoid。  
  
4. 若要建立第二个输入的参数**值映射 （平展）** functoid 创建输入的链接： 将**值映射 （平展）** 源中的记录或字段节点到 functoid架构，或者将记录或字段节点拖到源架构中**值映射 （平展）** functoid，或插入一个常量。  
  
   > [!NOTE]
   >  第二个输入参数**值映射 （平展）** functoid 也可以从另一个 functoid 的输出至其左侧。 创建链接表示此类通过将一个相关 functoid 拖至其他相关 functoid 的输入源。  
  
5. 若要使用的输出参数**值映射 （平展）** functoid，创建输出链接： 将**值映射 （平展）** functoid 到的记录或字段在目标架构中，或通过拖动到目标架构中的记录字段**值映射 （平展）** functoid。  
  
   > [!NOTE]
   >  与其他 functoid 的输出一样**值映射 （平展）** functoid 可以用作另一个 functoid 的输入。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)