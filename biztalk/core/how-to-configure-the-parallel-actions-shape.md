---
title: 如何配置并行操作形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Actions shape [Orchestration Designer], Terminate shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], synchronizing data access
- Parallel Actions shape [Orchestration Designer]
- configuring [Orchestration Designer], Parallel Actions shapes
- Parallel Actions shape [Orchestration Designer], branching
- Parallel Actions shape [Orchestration Designer], about Parallel Actions shape
- Terminate shape [Orchestration Designer], Parallel Actions shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], configuring
ms.assetid: 396d6182-f5dd-4aab-9edc-92efe236fd3e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 125d479a09eefb6771a884d2cddbfa98f34aeb36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247797"
---
# <a name="how-to-configure-the-parallel-actions-shape"></a>如何配置并行操作形状
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
并行操作形状  
  
> [!CAUTION]
>  如果你将放置**终止**形状内**并行操作**形状和使用分支**终止**上运行，在实例完成立即，而不考虑是否其他分支已完成运行。 根据您的设计，在此情况下结果可能不可预测。  
  
## <a name="synchronization-of-data-access"></a>同步数据访问  
 很可能该多个分支的**并行操作**形状将尝试访问相同的数据。 为避免出错，请将访问这些数据的所有形状都放入同步作用域。 你可以指定的属性中**作用域**形状，它是同步或不为 synchronized。 有关详细信息，请参阅[作用域](../core/scopes.md)。  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a>向并行操作形状添加分支  
  
1.  右键单击**并行操作**形状，并依次**新并行分支**。  
  
     -或者-  
  
2.  将一个新形状拖到两个现有分支之间。  
  
> [!NOTE]
>  若要删除分支起源**并行操作**形状，右键单击你想要删除，，然后单击的分支**删除**。