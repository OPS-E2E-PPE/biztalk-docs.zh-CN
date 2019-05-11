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
# <a name="how-to-configure-the-parallel-actions-shape"></a><span data-ttu-id="50d54-102">如何配置并行操作形状</span><span class="sxs-lookup"><span data-stu-id="50d54-102">How to Configure the Parallel Actions Shape</span></span>
<span data-ttu-id="50d54-103">![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")</span><span class="sxs-lookup"><span data-stu-id="50d54-103">![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")</span></span>  
<span data-ttu-id="50d54-104">并行操作形状</span><span class="sxs-lookup"><span data-stu-id="50d54-104">Parallel Actions shape</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="50d54-105">如果将置于**Terminate**形状内**并行操作**形状，并使用分支**终止**上运行它时，该实例将立即完成，而不考虑是否其他分支完成运行。</span><span class="sxs-lookup"><span data-stu-id="50d54-105">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="50d54-106">根据你的设计，结果可能不可预测在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="50d54-106">Depending on your design, results might be unpredictable in this case.</span></span>  
  
## <a name="synchronization-of-data-access"></a><span data-ttu-id="50d54-107">同步数据访问</span><span class="sxs-lookup"><span data-stu-id="50d54-107">Synchronization of data access</span></span>  
 <span data-ttu-id="50d54-108">可能的多个分支**并行操作**形状将尝试访问相同的数据。</span><span class="sxs-lookup"><span data-stu-id="50d54-108">It is possible that more than one branch of a **Parallel Actions** shape will attempt to access the same data.</span></span> <span data-ttu-id="50d54-109">若要避免错误，将访问同步的作用域中的数据的所有形状。</span><span class="sxs-lookup"><span data-stu-id="50d54-109">To avoid errors, place any shapes that access the data inside synchronized scopes.</span></span> <span data-ttu-id="50d54-110">可以指定的属性中**作用域**形状，它是同步或不为 synchronized。</span><span class="sxs-lookup"><span data-stu-id="50d54-110">You can specify in the properties of a **Scope** shape that it is synchronized or not synchronized.</span></span> <span data-ttu-id="50d54-111">有关详细信息，请参阅[作用域](../core/scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="50d54-111">For more information, see [Scopes](../core/scopes.md).</span></span>  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a><span data-ttu-id="50d54-112">若要向并行操作形状添加分支</span><span class="sxs-lookup"><span data-stu-id="50d54-112">To add a branch to a Parallel Actions shape</span></span>  
  
1.  <span data-ttu-id="50d54-113">右键单击**并行操作**形状，然后依次**新建并行分支**。</span><span class="sxs-lookup"><span data-stu-id="50d54-113">Right-click the **Parallel Actions** shape, and then click **New Parallel Branch**.</span></span>  
  
     <span data-ttu-id="50d54-114">-或-</span><span class="sxs-lookup"><span data-stu-id="50d54-114">—Or—</span></span>  
  
2.  <span data-ttu-id="50d54-115">两个现有分支之间将新形状。</span><span class="sxs-lookup"><span data-stu-id="50d54-115">Drag a new shape between two existing branches.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50d54-116">若要删除分支起源**并行操作**形状中，右键单击你想要删除，然后单击的分支**删除**。</span><span class="sxs-lookup"><span data-stu-id="50d54-116">To remove a branch from a **Parallel Actions** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>