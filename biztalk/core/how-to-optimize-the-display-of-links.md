---
title: 如何优化链接的显示 |Microsoft Docs
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
ms.openlocfilehash: da7eec1cb22dfea1522b94d1bbb948a627ed4ffa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335828"
---
# <a name="how-to-optimize-the-display-of-links"></a>如何优化链接的显示
如果架构够大，您的映射可能包括大量的源和目标架构之间的链接。 由于映射表面的许多链接，您可能会发现难以跟踪的链接或需要处理的对象。 而且，它会非常困难，以便跟踪源架构、 链接、 functoid 和目标架构之间的端到端关系。 在 BizTalk 映射器中，可以更好地管理复杂的大型架构，并使优化显示映射中链接。 本主题提供有关如何查看链接的详细信息。  
  
 您可以分类各链接，请按如下所示：  
  
-   部分位于作用域  
  
-   完全在作用域  
  
-   完全位于作用域外  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="to-view-the-links-partially-in-scope"></a>若要查看部分位于作用域的链接  
 在网格图面上可见的至少一个最终的链接称为"部分位于作用域。  
  
 下图显示了一个链接，"部分在作用域。 下面的链接显示为虚线网格页上。  
  
 单击网格图面上, 部分可见的链接，网格页自动上移/下移以使在当前的视图的关系。  
  
 ![映射器链接部分在作用域](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")  
  
## <a name="to-view-the-links-completely-in-scope"></a>若要查看完全位于作用域的链接  
 两个末端 （节点到节点，节点到 functoid、 functoid 对 functoid 或 functoid 对节点） 显示在网格图面的链接称为"完全位于作用域。  
  
 下图显示 DataCollection1 和 ST01 之间链接的是完全在作用域中。  
  
 单击该链接，并选择从源节点到目标节点的关系。  
  
 ![映射器链接完全在作用域](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")  
  
## <a name="to-view-the-links-completely-out-of-scope"></a>若要查看链接完全超出范围  
 既没有当前映射视图中显示其终结点的链接称为"完全超出范围。"  
  
 下图显示了完全位于作用域之外的链接。  
  
 如果不想要显示这些链接在地图上图面上，这是 （因为不到任何链接是可见的），您也可通过单击关闭它们![显示所有链接](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")映射器上实用工具功能区。 这将减少在网格视图可见的链接的数量。  
  
 ![映射器链接完全超出范围](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)