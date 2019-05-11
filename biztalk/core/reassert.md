---
title: 重新添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23cebbb268e57d71a1702a03d2516892c1851e8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398250"
---
# <a name="reassert"></a><span data-ttu-id="d84b3-102">重新添加</span><span class="sxs-lookup"><span data-stu-id="d84b3-102">Reassert</span></span>
<span data-ttu-id="d84b3-103">向*重新添加*意味着调用**Assert**函数已在引擎中的对象上的工作内存。</span><span class="sxs-lookup"><span data-stu-id="d84b3-103">To *reassert* means to call the **Assert** function on an object that is already in the engine's working memory.</span></span> <span data-ttu-id="d84b3-104">重新添加命令相当于发出取消命令的对象，然后添加命令。</span><span class="sxs-lookup"><span data-stu-id="d84b3-104">A reassert command is equivalent to issuing a retract command for the object, followed by an assert command.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="d84b3-105">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="d84b3-105">.NET Objects</span></span>  
 <span data-ttu-id="d84b3-106">首先取消该对象，并删除上使用该对象 （在谓词或操作） 的规则议程中的任何操作。</span><span class="sxs-lookup"><span data-stu-id="d84b3-106">The object is first retracted and any actions on the agenda for rules that use the object (in a predicate or action) are removed.</span></span> <span data-ttu-id="d84b3-107">然后，该对象会添加回工作内存，并计算为新添加的任何对象。</span><span class="sxs-lookup"><span data-stu-id="d84b3-107">The object is then asserted back into working memory and evaluated as any object that is newly asserted.</span></span> <span data-ttu-id="d84b3-108">这意味着在谓词中使用的对象的任何规则将重新计算，并将其操作添加到根据议程。</span><span class="sxs-lookup"><span data-stu-id="d84b3-108">This means that any rules that use the object in a predicate are re-evaluated and their actions are added to the agenda as appropriate.</span></span> <span data-ttu-id="d84b3-109">以前计算为任何规则 **，则返回 true**和仅使用在其操作中的对象都会将其重新添加到议程的操作。</span><span class="sxs-lookup"><span data-stu-id="d84b3-109">Any rules that previously evaluated to **true** and only use the object in their actions will have their actions re-added to the agenda.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="d84b3-110">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="d84b3-110">TypedXmlDocument</span></span>  
 <span data-ttu-id="d84b3-111">在最高级别时**TypedXmlDocument** (**TXD**) 重新添加，子**TXD**s 时创建的最高级别**TXD**最初是添加具有不同的行为，具体取决于子状态**TXD**s。</span><span class="sxs-lookup"><span data-stu-id="d84b3-111">When a top level **TypedXmlDocument** (**TXD**) is reasserted, the child **TXD**s that are created when the top level **TXD** is initially asserted have different behaviors depending on the state of the child **TXD**s.</span></span> <span data-ttu-id="d84b3-112">对于新的子节点或已更新，这意味着，至少一个其字段已更改的策略中使用规则操作中，声明，或重新添加操作的子节点的子节点上执行。</span><span class="sxs-lookup"><span data-stu-id="d84b3-112">In the case of a new child node or a child node that is dirty, meaning that at least one of its fields has been changed in the policy by using a rule action, an assert, or reassert action is performed on the child node.</span></span> <span data-ttu-id="d84b3-113">未更新任何现有子节点保留在工作内存中。</span><span class="sxs-lookup"><span data-stu-id="d84b3-113">Any existing child node that is not dirty remains in the working memory.</span></span> <span data-ttu-id="d84b3-114">下面的示例是介绍时重新添加其父节点的子节点的行为的简化的方案。</span><span class="sxs-lookup"><span data-stu-id="d84b3-114">The following example is a simplified scenario that describes the behaviors of the child nodes when their parent node is reasserted.</span></span>  
  
 <span data-ttu-id="d84b3-115">假设有三个**TXD**工作内存中当前：**P**， **C**1， **C**2，和**C**3。</span><span class="sxs-lookup"><span data-stu-id="d84b3-115">Assume there are three **TXD**s currently in the working memory: **P**, **C**1, **C**2, and **C**3.</span></span> <span data-ttu-id="d84b3-116">**P**级别为顶级**TXD**，父节点; 并且每个子节点都包含字段**x**。</span><span class="sxs-lookup"><span data-stu-id="d84b3-116">**P** is the top level **TXD**, the parent node; each child node contains a field **x**.</span></span>  
  
 <span data-ttu-id="d84b3-117">**P**</span><span class="sxs-lookup"><span data-stu-id="d84b3-117">**P**</span></span>  
  
 <span data-ttu-id="d84b3-118">**C**1 (**C**1.**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="d84b3-118">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="d84b3-119">**C**2 (**C**2.**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="d84b3-119">**C**2 (**C**2.**x** = 1)</span></span>  
  
 <span data-ttu-id="d84b3-120">**C**3 (**C**3.**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="d84b3-120">**C**3 (**C**3.**x** = 1)</span></span>  
  
 <span data-ttu-id="d84b3-121">接下来，假定由于规则操作执行了以下操作：</span><span class="sxs-lookup"><span data-stu-id="d84b3-121">Next, assume the following operations have been performed as a result of rule action:</span></span>  
  
-   <span data-ttu-id="d84b3-122">字段 (**x**) 的值**C**更新 2。</span><span class="sxs-lookup"><span data-stu-id="d84b3-122">The field (**x**) value for **C**2 is updated.</span></span>  
  
-   <span data-ttu-id="d84b3-123">**C**3 删除了使用用户代码。</span><span class="sxs-lookup"><span data-stu-id="d84b3-123">**C**3 is deleted by using user code.</span></span>  
  
-   <span data-ttu-id="d84b3-124">另一个子节点**D**，添加到**P**通过用户代码。</span><span class="sxs-lookup"><span data-stu-id="d84b3-124">An additional child node, **D**, is added to **P** by using user code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d84b3-125">节点将不会标记已更新的操作，其中引擎并不知道从业务规则引擎。</span><span class="sxs-lookup"><span data-stu-id="d84b3-125">A node will not be marked dirty by the Business Rule Engine from operations, of which the engine is not aware.</span></span> <span data-ttu-id="d84b3-126">例如，添加、 删除或修改以编程方式在外部应用程序中的节点。</span><span class="sxs-lookup"><span data-stu-id="d84b3-126">For example, adding, deleting, or modifying a node programmatically in an external application.</span></span>  
  
 <span data-ttu-id="d84b3-127">在工作内存中对象的新表示形式如下所示。</span><span class="sxs-lookup"><span data-stu-id="d84b3-127">The new representation of the objects in working memory is as follows.</span></span>  
  
 <span data-ttu-id="d84b3-128">**P**</span><span class="sxs-lookup"><span data-stu-id="d84b3-128">**P**</span></span>  
  
 <span data-ttu-id="d84b3-129">**C**1 (**C**1.**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="d84b3-129">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="d84b3-130">**C**2 (**C**2.**x** = *0*)</span><span class="sxs-lookup"><span data-stu-id="d84b3-130">**C**2 (**C**2.**x** = *0*)</span></span>  
  
 <span data-ttu-id="d84b3-131">**D**</span><span class="sxs-lookup"><span data-stu-id="d84b3-131">**D**</span></span>  
  
 <span data-ttu-id="d84b3-132">现在，重新添加**P**。以下几点汇总的子节点的行为：</span><span class="sxs-lookup"><span data-stu-id="d84b3-132">Now, reassert **P**. The following points summarize the behaviors of the child nodes:</span></span>  
  
-   <span data-ttu-id="d84b3-133">节点**C**2 重新添加，因为它已变为已更新后更新其字段。</span><span class="sxs-lookup"><span data-stu-id="d84b3-133">Node **C**2 is reasserted, because it has become dirty after its field being updated.</span></span>  
  
-   <span data-ttu-id="d84b3-134">节点**C**从工作内存取消 3。</span><span class="sxs-lookup"><span data-stu-id="d84b3-134">Node **C**3 is retracted from the working memory.</span></span>  
  
-   <span data-ttu-id="d84b3-135">节点**D**添加到工作内存中。</span><span class="sxs-lookup"><span data-stu-id="d84b3-135">Node **D** is asserted into the working memory.</span></span>  
  
-   <span data-ttu-id="d84b3-136">节点**C**1 保持工作内存中保持不变，因为之前未更新该**P**重新添加。</span><span class="sxs-lookup"><span data-stu-id="d84b3-136">Node **C**1 remains unchanged in the working memory, because it was not updated before **P** was reasserted.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="d84b3-137">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="d84b3-137">TypedDataTable</span></span>  
 <span data-ttu-id="d84b3-138">如果**重新添加**会发出**TypedDataRow**，可以取消，然后将其添加到工作内存中的行。</span><span class="sxs-lookup"><span data-stu-id="d84b3-138">If **Reassert** is issued on a **TypedDataRow**, that row is retracted and then asserted into working memory.</span></span> <span data-ttu-id="d84b3-139">如果**重新添加**会发出**TypedDataTable**，则所有关联**TypedDataRow**进行取消，然后将其添加。</span><span class="sxs-lookup"><span data-stu-id="d84b3-139">If **Reassert** is issued on the **TypedDataTable**, all associated **TypedDataRow**s are retracted and then asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="d84b3-140">DataConnection</span><span class="sxs-lookup"><span data-stu-id="d84b3-140">DataConnection</span></span>  
 <span data-ttu-id="d84b3-141">所有**TypedDataRow**通过检索 s **DataConnection**中取消。</span><span class="sxs-lookup"><span data-stu-id="d84b3-141">All **TypedDataRow**s retrieved through the **DataConnection** are retracted.</span></span> <span data-ttu-id="d84b3-142">使用的所有谓词**DataConnection**然后重新评估，从而导致**DataConnection**以重新查询以创建相关**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="d84b3-142">All predicates that use the **DataConnection** are then re-evaluated, causing the **DataConnection** to be requeried to create the relevant **TypedDataRow**s.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84b3-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="d84b3-143">See Also</span></span>  
 [<span data-ttu-id="d84b3-144">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="d84b3-144">Engine Control Functions</span></span>](../core/engine-control-functions.md)