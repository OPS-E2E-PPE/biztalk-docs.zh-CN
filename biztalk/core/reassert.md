---
title: 重新声明 |Microsoft 文档
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
ms.openlocfilehash: 22fcc8be7760d85a12cb05c53137177703c0fa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269645"
---
# <a name="reassert"></a><span data-ttu-id="006c8-102">重新声明</span><span class="sxs-lookup"><span data-stu-id="006c8-102">Reassert</span></span>
<span data-ttu-id="006c8-103">到*重新声明*意味着调用**断言**对已在引擎中的对象的函数的工作内存。</span><span class="sxs-lookup"><span data-stu-id="006c8-103">To *reassert* means to call the **Assert** function on an object that is already in the engine's working memory.</span></span> <span data-ttu-id="006c8-104">重新添加命令相当于向该对象发出取消命令，然后执行添加命令。</span><span class="sxs-lookup"><span data-stu-id="006c8-104">A reassert command is equivalent to issuing a retract command for the object, followed by an assert command.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="006c8-105">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="006c8-105">.NET Objects</span></span>  
 <span data-ttu-id="006c8-106">首先会取消对象，并删除针使用该对象（在谓词或操作中）的规则议程中的所有操作。</span><span class="sxs-lookup"><span data-stu-id="006c8-106">The object is first retracted and any actions on the agenda for rules that use the object (in a predicate or action) are removed.</span></span> <span data-ttu-id="006c8-107">然后，将该对象添加回工作内存中，并将其作为任何新添加的对象进行计算。</span><span class="sxs-lookup"><span data-stu-id="006c8-107">The object is then asserted back into working memory and evaluated as any object that is newly asserted.</span></span> <span data-ttu-id="006c8-108">这意味着将重新计算所有在谓词中使用该对象的规则，并且根据需要将其操作添加到议程中。</span><span class="sxs-lookup"><span data-stu-id="006c8-108">This means that any rules that use the object in a predicate are re-evaluated and their actions are added to the agenda as appropriate.</span></span> <span data-ttu-id="006c8-109">以前计算结果为任何规则**true**并仅使用其操作中的对象将具有重新添加到安排其操作。</span><span class="sxs-lookup"><span data-stu-id="006c8-109">Any rules that previously evaluated to **true** and only use the object in their actions will have their actions re-added to the agenda.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="006c8-110">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="006c8-110">TypedXmlDocument</span></span>  
 <span data-ttu-id="006c8-111">在最高级别时**TypedXmlDocument** (**TXD**) reasserted 子**TXD**时，会创建的 s 顶级**TXD**最初是声明具有不同的行为，具体取决于子状态**TXD**s。</span><span class="sxs-lookup"><span data-stu-id="006c8-111">When a top level **TypedXmlDocument** (**TXD**) is reasserted, the child **TXD**s that are created when the top level **TXD** is initially asserted have different behaviors depending on the state of the child **TXD**s.</span></span> <span data-ttu-id="006c8-112">对于新的子节点或子节点已更新，这意味着到至少一个其字段已更改的策略中使用的规则操作，一个断言，或重新声明操作执行的子节点。</span><span class="sxs-lookup"><span data-stu-id="006c8-112">In the case of a new child node or a child node that is dirty, meaning that at least one of its fields has been changed in the policy by using a rule action, an assert, or reassert action is performed on the child node.</span></span> <span data-ttu-id="006c8-113">所有未更新的现有子节点都将保留在工作内存中。</span><span class="sxs-lookup"><span data-stu-id="006c8-113">Any existing child node that is not dirty remains in the working memory.</span></span> <span data-ttu-id="006c8-114">以下示例是一个简化的方案，该方案对重新添加其父节点时这些子节点的行为进行了说明。</span><span class="sxs-lookup"><span data-stu-id="006c8-114">The following example is a simplified scenario that describes the behaviors of the child nodes when their parent node is reasserted.</span></span>  
  
 <span data-ttu-id="006c8-115">假定有三个**TXD**当前在工作内存中的 s: **P**， **C**1， **C**2，和**C**3。</span><span class="sxs-lookup"><span data-stu-id="006c8-115">Assume there are three **TXD**s currently in the working memory: **P**, **C**1, **C**2, and **C**3.</span></span> <span data-ttu-id="006c8-116">**P**是最高级别**TXD**，父节点; 每个子节点包含一个字段**x**。</span><span class="sxs-lookup"><span data-stu-id="006c8-116">**P** is the top level **TXD**, the parent node; each child node contains a field **x**.</span></span>  
  
 <span data-ttu-id="006c8-117">**P**</span><span class="sxs-lookup"><span data-stu-id="006c8-117">**P**</span></span>  
  
 <span data-ttu-id="006c8-118">**C**1 (**C**1。**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="006c8-118">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="006c8-119">**C**2 (**C**2。**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="006c8-119">**C**2 (**C**2.**x** = 1)</span></span>  
  
 <span data-ttu-id="006c8-120">**C**3 (**C**3。**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="006c8-120">**C**3 (**C**3.**x** = 1)</span></span>  
  
 <span data-ttu-id="006c8-121">接下来，假定规则操作由于执行了以下操作：</span><span class="sxs-lookup"><span data-stu-id="006c8-121">Next, assume the following operations have been performed as a result of rule action:</span></span>  
  
-   <span data-ttu-id="006c8-122">字段 (**x**) 值，则为**C**更新 2。</span><span class="sxs-lookup"><span data-stu-id="006c8-122">The field (**x**) value for **C**2 is updated.</span></span>  
  
-   <span data-ttu-id="006c8-123">**C**3 删除通过用户代码。</span><span class="sxs-lookup"><span data-stu-id="006c8-123">**C**3 is deleted by using user code.</span></span>  
  
-   <span data-ttu-id="006c8-124">另外，其他子节点， **D**，添加到**P**通过用户代码。</span><span class="sxs-lookup"><span data-stu-id="006c8-124">An additional child node, **D**, is added to **P** by using user code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="006c8-125">业务规则引擎不会根据其不知道的操作来将节点标记为已更新。</span><span class="sxs-lookup"><span data-stu-id="006c8-125">A node will not be marked dirty by the Business Rule Engine from operations, of which the engine is not aware.</span></span> <span data-ttu-id="006c8-126">例如，在外部应用程序中通过编程方式添加、删除或修改节点。</span><span class="sxs-lookup"><span data-stu-id="006c8-126">For example, adding, deleting, or modifying a node programmatically in an external application.</span></span>  
  
 <span data-ttu-id="006c8-127">使用内存中对象的新表示如下所示。</span><span class="sxs-lookup"><span data-stu-id="006c8-127">The new representation of the objects in working memory is as follows.</span></span>  
  
 <span data-ttu-id="006c8-128">**P**</span><span class="sxs-lookup"><span data-stu-id="006c8-128">**P**</span></span>  
  
 <span data-ttu-id="006c8-129">**C**1 (**C**1。**x** = 1)</span><span class="sxs-lookup"><span data-stu-id="006c8-129">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="006c8-130">**C**2 (**C**2。**x** = *0*)</span><span class="sxs-lookup"><span data-stu-id="006c8-130">**C**2 (**C**2.**x** = *0*)</span></span>  
  
 <span data-ttu-id="006c8-131">**D**</span><span class="sxs-lookup"><span data-stu-id="006c8-131">**D**</span></span>  
  
 <span data-ttu-id="006c8-132">现在，重新声明**P**。以下几点汇总的子节点的行为：</span><span class="sxs-lookup"><span data-stu-id="006c8-132">Now, reassert **P**. The following points summarize the behaviors of the child nodes:</span></span>  
  
-   <span data-ttu-id="006c8-133">节点**C**reasserted 2，因为它已变得脏后其正在更新的字段。</span><span class="sxs-lookup"><span data-stu-id="006c8-133">Node **C**2 is reasserted, because it has become dirty after its field being updated.</span></span>  
  
-   <span data-ttu-id="006c8-134">节点**C**3 是否被收回从工作内存。</span><span class="sxs-lookup"><span data-stu-id="006c8-134">Node **C**3 is retracted from the working memory.</span></span>  
  
-   <span data-ttu-id="006c8-135">节点**D**到工作内存断言。</span><span class="sxs-lookup"><span data-stu-id="006c8-135">Node **D** is asserted into the working memory.</span></span>  
  
-   <span data-ttu-id="006c8-136">节点**C**1 保持在工作内存中，不变，因为它未更新之前**P**已 reasserted。</span><span class="sxs-lookup"><span data-stu-id="006c8-136">Node **C**1 remains unchanged in the working memory, because it was not updated before **P** was reasserted.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="006c8-137">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="006c8-137">TypedDataTable</span></span>  
 <span data-ttu-id="006c8-138">如果**重新声明**上发出**TypedDataRow**，收回，然后断言工作内存到该行。</span><span class="sxs-lookup"><span data-stu-id="006c8-138">If **Reassert** is issued on a **TypedDataRow**, that row is retracted and then asserted into working memory.</span></span> <span data-ttu-id="006c8-139">如果**重新声明**上发出**TypedDataTable**，所有关联**TypedDataRow**进行收回，然后断言。</span><span class="sxs-lookup"><span data-stu-id="006c8-139">If **Reassert** is issued on the **TypedDataTable**, all associated **TypedDataRow**s are retracted and then asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="006c8-140">DataConnection</span><span class="sxs-lookup"><span data-stu-id="006c8-140">DataConnection</span></span>  
 <span data-ttu-id="006c8-141">所有**TypedDataRow**通过检索 s**该组**收回。</span><span class="sxs-lookup"><span data-stu-id="006c8-141">All **TypedDataRow**s retrieved through the **DataConnection** are retracted.</span></span> <span data-ttu-id="006c8-142">使用的所有谓词**该组**然后重新评估，从而导致**该组**以重新查询以创建相关**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="006c8-142">All predicates that use the **DataConnection** are then re-evaluated, causing the **DataConnection** to be requeried to create the relevant **TypedDataRow**s.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006c8-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="006c8-143">See Also</span></span>  
 [<span data-ttu-id="006c8-144">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="006c8-144">Engine Control Functions</span></span>](../core/engine-control-functions.md)