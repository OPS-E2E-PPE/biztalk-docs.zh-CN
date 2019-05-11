---
title: 如何在多个链接和 Functoid 上设置标签和注释 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b554a19-2bd4-4dbc-b5cb-567b98c07024
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9353a8d612d5aac43f380e1410809f61fa19f708
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334388"
---
# <a name="how-to-set-label-and-comment-on-multiple-links-and-functoids"></a><span data-ttu-id="9c34d-102">如何在多个链接和 Functoid 上设置标签和注释</span><span class="sxs-lookup"><span data-stu-id="9c34d-102">How to Set Label and Comment on Multiple Links and Functoids</span></span>
<span data-ttu-id="9c34d-103">您可以设置通用标签和/或多个 functoid 和/或链接的注释。</span><span class="sxs-lookup"><span data-stu-id="9c34d-103">You can set a common label and/or a comment for multiple functoids and/or links.</span></span> <span data-ttu-id="9c34d-104">本主题提供有关如何执行此操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c34d-104">This topic provides details about how to perform this operation.</span></span>  
  
 <span data-ttu-id="9c34d-105">有关如何选择多个 functoid 和/或链接的信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="9c34d-105">For information about how to select multiple functoid(s) and/or link(s), see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
 <span data-ttu-id="9c34d-106">选择多个 functoid 和/或链接之后, 可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="9c34d-106">After selecting multiple functoid(s) and/or link(s), you can do any of the following:</span></span>  
  
-   <span data-ttu-id="9c34d-107">设置通用标签为所选链接。</span><span class="sxs-lookup"><span data-stu-id="9c34d-107">Set a common label for selected links.</span></span>  
  
-   <span data-ttu-id="9c34d-108">一个常见的标签和/或注释为所选 functoid 设置。</span><span class="sxs-lookup"><span data-stu-id="9c34d-108">Set a common label and/or comment for the selected functoids.</span></span>  
  
-   <span data-ttu-id="9c34d-109">设置通用标签为所选的 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="9c34d-109">Set a common label for the selected functoids and links.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c34d-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="9c34d-110">Prerequisites</span></span>  
 <span data-ttu-id="9c34d-111">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="9c34d-111">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-links"></a><span data-ttu-id="9c34d-112">若要设置通用标签为所选链接</span><span class="sxs-lookup"><span data-stu-id="9c34d-112">To set a common label for selected links</span></span>  
 <span data-ttu-id="9c34d-113">在多个链接设置通用标签是一个原子操作。</span><span class="sxs-lookup"><span data-stu-id="9c34d-113">Setting a common label on multiple links is one atomic operation.</span></span> <span data-ttu-id="9c34d-114">您可以撤消或重做此操作。</span><span class="sxs-lookup"><span data-stu-id="9c34d-114">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="9c34d-115">若要设置通用标签为所选链接：</span><span class="sxs-lookup"><span data-stu-id="9c34d-115">To set a common label for the selected links:</span></span>  
  
1.  <span data-ttu-id="9c34d-116">在映射器网格页上，选择所需的链接。</span><span class="sxs-lookup"><span data-stu-id="9c34d-116">On the Mapper grid page, select the desired links.</span></span>  
  
2.  <span data-ttu-id="9c34d-117">在中**属性**窗口中，输入在合适的标签**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="9c34d-117">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="to-set-a-common-label-andor-comment-for-selected-functoids"></a><span data-ttu-id="9c34d-118">若要设置通用标签和/或所选 functoid 的注释</span><span class="sxs-lookup"><span data-stu-id="9c34d-118">To set a common label and/or comment for selected functoids</span></span>  
 <span data-ttu-id="9c34d-119">设置通用标签和设置为所选 functoid 通用注释是两个不同的原子操作。</span><span class="sxs-lookup"><span data-stu-id="9c34d-119">Setting a common label and setting a common comment for the selected functoids are two different atomic operations.</span></span> <span data-ttu-id="9c34d-120">您可以撤消或重做这些操作。</span><span class="sxs-lookup"><span data-stu-id="9c34d-120">You can undo or redo these operations.</span></span>  
  
 <span data-ttu-id="9c34d-121">若要设置通用标签/注释为所选 functoid:</span><span class="sxs-lookup"><span data-stu-id="9c34d-121">To set a common label/comment for the selected functoids:</span></span>  
  
1.  <span data-ttu-id="9c34d-122">在映射器网格页上，选择所需的 functoid。</span><span class="sxs-lookup"><span data-stu-id="9c34d-122">On the Mapper grid page, select the desired functoids.</span></span>  
  
2.  <span data-ttu-id="9c34d-123">在中**属性**窗口中，输入合适的标签和/或注释**标签**并**注释**属性。</span><span class="sxs-lookup"><span data-stu-id="9c34d-123">In the **Properties** window, enter a suitable label and/or comment in the **Label** and **Comments** properties.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-functoids-and-links"></a><span data-ttu-id="9c34d-124">若要设置通用标签为所选的 functoid 和链接</span><span class="sxs-lookup"><span data-stu-id="9c34d-124">To set a common label for selected functoids and links</span></span>  
 <span data-ttu-id="9c34d-125">可以设置通用标签为所选的 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="9c34d-125">You can set a common label for the selected functoids and links.</span></span> <span data-ttu-id="9c34d-126">**标签**是普遍适用于 functoid 和链接的唯一属性。</span><span class="sxs-lookup"><span data-stu-id="9c34d-126">**Label** is the only property which is common to both functoids and links.</span></span> <span data-ttu-id="9c34d-127">您可以撤消或重做此操作。</span><span class="sxs-lookup"><span data-stu-id="9c34d-127">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="9c34d-128">若要设置通用标签为所选的 functoid 和链接：</span><span class="sxs-lookup"><span data-stu-id="9c34d-128">To set a common label for the selected functoids and links:</span></span>  
  
1.  <span data-ttu-id="9c34d-129">在映射器网格页上，选择所需的 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="9c34d-129">On the Mapper grid page, select the desired functoids and links.</span></span>  
  
2.  <span data-ttu-id="9c34d-130">在中**属性**窗口中，输入在合适的标签**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="9c34d-130">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c34d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c34d-131">See Also</span></span>  
 [<span data-ttu-id="9c34d-132">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="9c34d-132">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)