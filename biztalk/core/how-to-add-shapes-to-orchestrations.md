---
title: "如何将形状添加到业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fa6634adb20ffcf927da0af6f58e9daa2800ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-shapes-to-orchestrations"></a><span data-ttu-id="e57fc-102">如何将形状添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="e57fc-102">How to Add Shapes to Orchestrations</span></span>
<span data-ttu-id="e57fc-103">本部分介绍在业务流程中添加和删除形状的过程。</span><span class="sxs-lookup"><span data-stu-id="e57fc-103">This section describes the procedures for adding and removing shapes in your orchestration.</span></span> <span data-ttu-id="e57fc-104">有关可用的形状的详细信息，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="e57fc-104">For more information about the available shapes, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
### <a name="to-add-a-shape-to-an-orchestration"></a><span data-ttu-id="e57fc-105">若要将形状添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="e57fc-105">To add a shape to an orchestration</span></span>  
  
1.  <span data-ttu-id="e57fc-106">在工具箱中，在**BizTalk 业务流程**选项卡上，将形状拖条连线到业务流程设计图面上。</span><span class="sxs-lookup"><span data-stu-id="e57fc-106">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="e57fc-107">-或者-</span><span class="sxs-lookup"><span data-stu-id="e57fc-107">—Or—</span></span>  
  
2.  <span data-ttu-id="e57fc-108">右键单击连接的线条或形状占位符想要添加该形状，指向**插入形状**，然后单击你想要添加的形状名称。</span><span class="sxs-lookup"><span data-stu-id="e57fc-108">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape**, and then click the shape name you want to add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e57fc-109">此时智能标记将出现在仍未完全配置的形状上。</span><span class="sxs-lookup"><span data-stu-id="e57fc-109">A Smart Tag appears on shapes that are not yet fully configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e57fc-110">**转换**形状和**消息分配**形状可以仅存在于**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="e57fc-110">**Transform** shapes and **Message Assignment** shapes can only exist within a **Construct Message** shape.</span></span> <span data-ttu-id="e57fc-111">如果你将添加这些形状之一到外部业务流程**构造消息**形状，它被自动放置到一个新**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="e57fc-111">If you add one of these shapes to your orchestration outside of a **Construct Message** shape, it is placed automatically inside a new **Construct Message** shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e57fc-112">**捕获异常**和**补偿**块才会存在以下**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="e57fc-112">**Catch Exception** and **Compensation** blocks can only exist following a **Scope** shape.</span></span>  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a><span data-ttu-id="e57fc-113">从业务流程中删除形状</span><span class="sxs-lookup"><span data-stu-id="e57fc-113">To remove a shape from an orchestration</span></span>  
  
1.  <span data-ttu-id="e57fc-114">右击设计图面上的形状，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="e57fc-114">Right-click the shape on the design surface, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="e57fc-115">-或者-</span><span class="sxs-lookup"><span data-stu-id="e57fc-115">—Or—</span></span>  
  
2.  <span data-ttu-id="e57fc-116">选择形状，然后按**删除**密钥。</span><span class="sxs-lookup"><span data-stu-id="e57fc-116">Select the shape and press the **DELETE** key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57fc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e57fc-117">See Also</span></span>  
 [<span data-ttu-id="e57fc-118">创建业务流程</span><span class="sxs-lookup"><span data-stu-id="e57fc-118">Creating Orchestrations</span></span>](../core/creating-orchestrations.md)