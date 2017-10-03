---
title: "如何匹配映射中的架构节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e2ce880489ca49b0b55d2e6f45b9e887d719a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-match-schema-nodes-in-a-map"></a>如何在映射中匹配架构节点
如果源或目标架构很复杂，映射元素将非常困难。 BizTalk 映射程序引入了**指示匹配**功能，使得您可以将复杂架构元素映射的建议最可能的匹配。 本主题提供有关如何执行此操作的信息。  
  
> [!NOTE]
>  BizTalk 映射器为架构节点建议可能的匹配。 当前仅为英语名称支持此功能。  
  
## <a name="prerequisites"></a>先决条件  
 这些操作需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-match-relevant-schema-nodes"></a>匹配相关架构节点  
  
1.  选择并右键单击你需要知道最佳匹配项，并依次的架构元素**指示匹配**。 BizTalk 映射器突出显示最佳匹配（仅限于 7 个），且最优化匹配处于选中状态。  
  
     或者，你可以选择**指示匹配**BizTalk 菜单上，或者按 SHIFT + 空间键。  
  
     下图显示了目标架构中所选节点的建议匹配。  
  
     ![暗示映射](../core/media/suggestive-mapping.gif "Suggestive_Mapping")  
  
    > [!NOTE]
    >  按住 SHIFT 键以遍历建议匹配。  
  
2.  现在您可以执行以下操作：  
  
    -   按 Enter 确认突出显示（最佳）的匹配。  
  
    -   使用向上/向下键按优先顺序在突出显示的匹配中循环选择。  
  
        > [!NOTE]
        >  按向下键可遍历到下一个最佳匹配，按向上键可突出显示上一个最佳匹配。  
  
    -   按主页键返回到顶部的匹配项。  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)