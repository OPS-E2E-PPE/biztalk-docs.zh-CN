---
title: 如何向映射中添加 Nil 值 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90d5fa95bb7f7889eeca7a7a047019a67d672acd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343245"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a>如何向映射中添加 Nil 值 Functoid
**Nil 值**functoid 设置到目标节点的值**Nil**。  

 有关概念性信息**Nil 值**functoid，请参阅[零值 Functoid](../core/nil-value-functoid.md)。  

## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a>向映射添加 Nil 值 functoid 并对其进行配置  

1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。 将显示所选类别的高级 functoid 列表。  

2. 拖动**Nil 值**functoid (![Nil 值 functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) 从工具箱拖到网格页上的适当位置。  

   > [!NOTE]
   >  该 functoid 将放置上显示的网格页。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
   >
   >  如果构造使用多个 functoid 的映射，您需要考虑其相对的从左到右位置。 从左向右执行 Functoid。 Functoid 的输出只能输入到其右侧的另一个 functoid。  

3. **Nil 值**functoid 可以具有零到一个输入参数。 如果没有使此 functoid 输入的参数，将目标节点设置为**Nil**。 若要建立输入的参数**Nil 值**functoid 创建输入的链接： 从某个其他拖动输出**逻辑**functoid 或从输入的实例消息中的布尔变量字段。  

4. 若要使用的输出参数**Nil 值**functoid，创建输出链接： 将**Nil 值**functoid 到记录或目标架构中的字段。  

   > [!NOTE]
   >  与其他 functoid 的输出一样**Nil 值**functoid 可以用作另一个 functoid 的输入。  

## <a name="see-also"></a>请参阅  
- **Nil 值 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)
