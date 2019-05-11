---
title: 如何向业务流程添加形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba5e1f6484b1e7e3c268b1461aed1ea6534152b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343211"
---
# <a name="how-to-add-shapes-to-orchestrations"></a><span data-ttu-id="f8b50-102">如何向业务流程添加形状</span><span class="sxs-lookup"><span data-stu-id="f8b50-102">How to Add Shapes to Orchestrations</span></span>
<span data-ttu-id="f8b50-103">本部分介绍用于添加和删除形状在业务流程中的过程。</span><span class="sxs-lookup"><span data-stu-id="f8b50-103">This section describes the procedures for adding and removing shapes in your orchestration.</span></span> <span data-ttu-id="f8b50-104">有关可用形状的详细信息，请参阅[业务流程形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="f8b50-104">For more information about the available shapes, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
### <a name="to-add-a-shape-to-an-orchestration"></a><span data-ttu-id="f8b50-105">若要向业务流程添加形状</span><span class="sxs-lookup"><span data-stu-id="f8b50-105">To add a shape to an orchestration</span></span>  
  
1.  <span data-ttu-id="f8b50-106">在工具箱中，在**BizTalk 业务流程**选项卡上，在业务流程设计图面上形状拖动到连接的线条。</span><span class="sxs-lookup"><span data-stu-id="f8b50-106">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="f8b50-107">-或-</span><span class="sxs-lookup"><span data-stu-id="f8b50-107">—Or—</span></span>  
  
2.  <span data-ttu-id="f8b50-108">右键单击连接的线条或形状占位符，你想要添加形状，指向**插入形状**，然后单击你想要添加的形状名称。</span><span class="sxs-lookup"><span data-stu-id="f8b50-108">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape**, and then click the shape name you want to add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8b50-109">尚未完全配置的形状中显示智能标记。</span><span class="sxs-lookup"><span data-stu-id="f8b50-109">A Smart Tag appears on shapes that are not yet fully configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8b50-110">**转换**形状和**消息赋值**形状只能存在于**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="f8b50-110">**Transform** shapes and **Message Assignment** shapes can only exist within a **Construct Message** shape.</span></span> <span data-ttu-id="f8b50-111">如果您添加一个这些形状向业务流程之外**构造消息**形状，它被自动放置到一个新**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="f8b50-111">If you add one of these shapes to your orchestration outside of a **Construct Message** shape, it is placed automatically inside a new **Construct Message** shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8b50-112">**捕获异常**并**补偿**块只能存在以下**范围**形状。</span><span class="sxs-lookup"><span data-stu-id="f8b50-112">**Catch Exception** and **Compensation** blocks can only exist following a **Scope** shape.</span></span>  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a><span data-ttu-id="f8b50-113">若要从业务流程中删除形状</span><span class="sxs-lookup"><span data-stu-id="f8b50-113">To remove a shape from an orchestration</span></span>  
  
1.  <span data-ttu-id="f8b50-114">右键单击设计图面上的形状，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="f8b50-114">Right-click the shape on the design surface, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="f8b50-115">-或-</span><span class="sxs-lookup"><span data-stu-id="f8b50-115">—Or—</span></span>  
  
2.  <span data-ttu-id="f8b50-116">选择形状，然后按**删除**密钥。</span><span class="sxs-lookup"><span data-stu-id="f8b50-116">Select the shape and press the **DELETE** key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b50-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8b50-117">See Also</span></span>  
 [<span data-ttu-id="f8b50-118">创建业务流程</span><span class="sxs-lookup"><span data-stu-id="f8b50-118">Creating Orchestrations</span></span>](../core/creating-orchestrations.md)