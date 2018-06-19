---
title: 如何添加断言向地图 Functoid |Microsoft 文档
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
ms.openlocfilehash: 553daa0c6e97d09e8284d2369e801c5d2ff8beee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247757"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a>如何向映射中添加“添加”Functoid
**断言**functoid 使您能够在你的代码图中测试你的假设有关条件。 例如，如果你执行一些计算来确定在产品采购额外折扣，你可能断言额外折扣，通过使用逻辑 functoid 是不能超过 100 美元 (**大于**或**Less Than**)。  
  
> [!NOTE]
>  **断言**functoid 才会触发开发内部版本中，或者当**生成调试信息**项目生成设置的属性设置为**True**。 BizTalk 应用程序部署的编译时与**生成调试信息**属性设置为**False** （默认值）、 断言将被忽略。  
  
 有关概念性信息**断言**functoid，请参阅[断言 Functoid](../core/assert-functoid.md)。  
  
## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a>在向地图添加添加 functoid，并将其配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。 此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**断言**functoid (![断言 functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。 
    >    
    >  如果你在构造的地图，使用多个 functoid，你需要考虑它们相对的从左到右位置。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  该 functoid 必须正好有三个输入参数，并且生成一个输出参数。 若要建立的第一个参数**断言**functoid，通过将输出拖从其他创建输入的链接**逻辑**functoid 或从输入的实例消息中的变量布尔字段。  
  
4.  若要建立的第二个输入的参数**断言**functoid，源架构中的字段节点创建输入的链接**断言**functoid，或插入常量。  
  
5.  若要建立的第三个输入的参数**断言**functoid，源架构中的字段节点创建输入的链接**断言**functoid，或插入常量。  
  
6.  若要使用输出参数从**断言**functoid，通过拖动创建一条输出链接**断言**functoid 给目标架构中的字段。  
  
    > [!NOTE]
    >  其他 functoid 的输出与**断言**functoid 可以用作输入另一个 functoid。  
  
## <a name="see-also"></a>另请参阅  
-  **断言 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)