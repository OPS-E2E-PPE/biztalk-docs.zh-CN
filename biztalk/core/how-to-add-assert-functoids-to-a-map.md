---
title: 如何添加添加 Functoid 映射到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdd79a2-b70f-489b-8711-e00a50d8e2d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cfeabbbeac860e927854fb79c90d2b1608b9c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015270"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a>如何向映射中添加“添加”Functoid
**Assert** functoid，您可以在映射中测试条件的假设。 例如，如果您执行某些计算来确定产品采购额外折扣，你可能会断言额外折扣，是通过使用判断 functoid 不超过 100 美元 (**Greater Than**或**Less Than**)。  

> [!NOTE]
>  **Assert** functoid 才会触发在开发版本时，或者当**生成调试信息**中的项目生成设置的属性设置为**True**。 BizTalk 应用程序部署的编译时，**生成调试信息**属性设置为**False** （默认值），忽略断言。  

 有关概念性信息**Assert** functoid，请参阅[断言 Functoid](../core/assert-functoid.md)。  

## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a>向映射添加添加 functoid 并对其进行配置  

1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。 此时，将显示所选类别的高级 functoid 列表。  

2. 拖动**Assert** functoid (![添加 functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) 从工具箱拖到网格页上的适当位置。  

   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。 
   >    
   >  如果构造使用多个 functoid 的映射，您需要考虑其相对的从左到右位置。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  

3. 该 functoid 必须正好有三个输入参数，并且生成一个输出参数。 若要建立的第一个参数**Assert** functoid 创建输入的链接： 从某个其他拖动输出**逻辑**functoid 或从输入的实例消息中的布尔变量字段。  

4. 若要建立第二个输入的参数**Assert** functoid，由源架构中的字段节点创建输入的链接**Assert** functoid，或插入一个常量。  

5. 若要建立第三个输入的参数**Assert** functoid，由源架构中的字段节点创建输入的链接**Assert** functoid，或插入一个常量。  

6. 若要使用的输出参数**Assert** functoid，创建输出链接： 将**Assert** functoid 到目标架构中的字段。  

   > [!NOTE]
   >  与其他 functoid 的输出一样**Assert** functoid 可以用作另一个 functoid 的输入。  

## <a name="see-also"></a>请参阅  
- **声明 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)
