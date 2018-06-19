---
title: 如何优化的链接显示 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689ab4c67bfe8cabc8109c373e899d391fdd56a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254381"
---
# <a name="how-to-optimize-the-display-of-links"></a>如何优化链接的显示
如果架构够大，您的映射可能包括源和目标架构之间的大量链接。 由于映射表面有许多链接，可能很难跟踪您要处理的项目或连接。 此外，跟踪源架构、链接、functoid 和目标架构之间的端对端关系可能也很困难。 在 BizTalk 映射器中，您可以更好地管理复杂的大型架构，并可以优化显示映射中的链接。 本主题提供关于如何查看链接的详细信息。  
  
 您可以分类各链接，如下所示：  
  
-   部分位于作用域  
  
-   完全在作用域内  
  
-   完全位于作用域外  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="to-view-the-links-partially-in-scope"></a>查看部分位于作用域的链接  
 在网格图面上至少可以看见一个末端的链接称为“部分位于作用域”。  
  
 下图显示了一个“部分位作用域”的链接。 这些链接在网格图面上显示为虚线。  
  
 单击在网格图面上部分可见的链接，网格页会自动上移/下移以在当前视图中显示端对端关系。  
  
 ![作用域中的部分的映射器链接](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")  
  
## <a name="to-view-the-links-completely-in-scope"></a>查看完全位于作用域的链接  
 可以在网格图面上看到两个末端（节点对节点、节点对 functoid、functoid 对 functoid 或 functoid 对节点）的链接称为“完全位于作用域”。  
  
 下图显示 DataCollection1 和 ST01 之间完全位于作用域的链接。  
  
 单击该链接，会选中从源节点到目标节点的关系。  
  
 ![完全作用域中的映射器链接](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")  
  
## <a name="to-view-the-links-completely-out-of-scope"></a>查看完全位于作用域外的链接  
 在当前映射视图中看不到任何终结点的链接称为“完全位于作用域外”。  
  
 下图显示了完全位于作用域外的链接。  
  
 如果你不想要显示这些链接在地图上的图面 （因为所有链接都可见），你可以选择通过单击关闭它们![显示所有链接](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")上映射器实用程序功能区。 这样，就减少了网格视图上可见链接的数量。  
  
 ![完全超出范围的映射器链接](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)