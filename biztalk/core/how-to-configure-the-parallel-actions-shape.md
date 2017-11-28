---
title: "如何配置并行操作形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 125d479a09eefb6771a884d2cddbfa98f34aeb36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-parallel-actions-shape"></a><span data-ttu-id="bfc3c-102">如何配置并行操作形状</span><span class="sxs-lookup"><span data-stu-id="bfc3c-102">How to Configure the Parallel Actions Shape</span></span>
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
<span data-ttu-id="bfc3c-103">并行操作形状</span><span class="sxs-lookup"><span data-stu-id="bfc3c-103">Parallel Actions shape</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bfc3c-104">如果你将放置**终止**形状内**并行操作**形状和使用分支**终止**上运行，在实例完成立即，而不考虑是否其他分支已完成运行。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-104">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="bfc3c-105">根据您的设计，在此情况下结果可能不可预测。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-105">Depending on your design, results might be unpredictable in this case.</span></span>  
  
## <a name="synchronization-of-data-access"></a><span data-ttu-id="bfc3c-106">同步数据访问</span><span class="sxs-lookup"><span data-stu-id="bfc3c-106">Synchronization of data access</span></span>  
 <span data-ttu-id="bfc3c-107">很可能该多个分支的**并行操作**形状将尝试访问相同的数据。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-107">It is possible that more than one branch of a **Parallel Actions** shape will attempt to access the same data.</span></span> <span data-ttu-id="bfc3c-108">为避免出错，请将访问这些数据的所有形状都放入同步作用域。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-108">To avoid errors, place any shapes that access the data inside synchronized scopes.</span></span> <span data-ttu-id="bfc3c-109">你可以指定的属性中**作用域**形状，它是同步或不为 synchronized。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-109">You can specify in the properties of a **Scope** shape that it is synchronized or not synchronized.</span></span> <span data-ttu-id="bfc3c-110">有关详细信息，请参阅[作用域](../core/scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-110">For more information, see [Scopes](../core/scopes.md).</span></span>  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a><span data-ttu-id="bfc3c-111">向并行操作形状添加分支</span><span class="sxs-lookup"><span data-stu-id="bfc3c-111">To add a branch to a Parallel Actions shape</span></span>  
  
1.  <span data-ttu-id="bfc3c-112">右键单击**并行操作**形状，并依次**新并行分支**。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-112">Right-click the **Parallel Actions** shape, and then click **New Parallel Branch**.</span></span>  
  
     <span data-ttu-id="bfc3c-113">-或者-</span><span class="sxs-lookup"><span data-stu-id="bfc3c-113">—Or—</span></span>  
  
2.  <span data-ttu-id="bfc3c-114">将一个新形状拖到两个现有分支之间。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-114">Drag a new shape between two existing branches.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfc3c-115">若要删除分支起源**并行操作**形状，右键单击你想要删除，，然后单击的分支**删除**。</span><span class="sxs-lookup"><span data-stu-id="bfc3c-115">To remove a branch from a **Parallel Actions** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>