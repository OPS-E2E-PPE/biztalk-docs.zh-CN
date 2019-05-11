---
title: 如何配置并行操作形状 |Microsoft Docs
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
ms.openlocfilehash: f3179995031ea91243f602d554808c198863f2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386021"
---
# <a name="how-to-configure-the-parallel-actions-shape"></a>如何配置并行操作形状
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
并行操作形状  
  
> [!CAUTION]
>  如果将置于**Terminate**形状内**并行操作**形状，并使用分支**终止**上运行它时，该实例将立即完成，而不考虑是否其他分支完成运行。 根据你的设计，结果可能不可预测在这种情况下。  
  
## <a name="synchronization-of-data-access"></a>同步数据访问  
 可能的多个分支**并行操作**形状将尝试访问相同的数据。 若要避免错误，将访问同步的作用域中的数据的所有形状。 可以指定的属性中**作用域**形状，它是同步或不为 synchronized。 有关详细信息，请参阅[作用域](../core/scopes.md)。  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a>若要向并行操作形状添加分支  
  
1.  右键单击**并行操作**形状，然后依次**新建并行分支**。  
  
     -或-  
  
2.  两个现有分支之间将新形状。  
  
> [!NOTE]
>  若要删除分支起源**并行操作**形状中，右键单击你想要删除，然后单击的分支**删除**。