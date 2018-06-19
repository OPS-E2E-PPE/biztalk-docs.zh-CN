---
title: 如何在多个链接和 Functoid 上设置标签和注释 |Microsoft 文档
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
ms.openlocfilehash: 65bcb25fae52da46bbea1679e3b4e215720782d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255621"
---
# <a name="how-to-set-label-and-comment-on-multiple-links-and-functoids"></a><span data-ttu-id="30101-102">如何在多个链接和 Functoid 上设置标签和注释</span><span class="sxs-lookup"><span data-stu-id="30101-102">How to Set Label and Comment on Multiple Links and Functoids</span></span>
<span data-ttu-id="30101-103">您可以为多个 functoid 和/或链接设置通用标签和/或注释。</span><span class="sxs-lookup"><span data-stu-id="30101-103">You can set a common label and/or a comment for multiple functoids and/or links.</span></span> <span data-ttu-id="30101-104">本主题提供有关如何执行此操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="30101-104">This topic provides details about how to perform this operation.</span></span>  
  
 <span data-ttu-id="30101-105">有关如何选择多个 functoid(s) 和/或链接的信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="30101-105">For information about how to select multiple functoid(s) and/or link(s), see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
 <span data-ttu-id="30101-106">选择多个 functoid 和/或链接后，可以执行以下任何操作：</span><span class="sxs-lookup"><span data-stu-id="30101-106">After selecting multiple functoid(s) and/or link(s), you can do any of the following:</span></span>  
  
-   <span data-ttu-id="30101-107">为所选链接设置通用标签。</span><span class="sxs-lookup"><span data-stu-id="30101-107">Set a common label for selected links.</span></span>  
  
-   <span data-ttu-id="30101-108">设置一个常见的标签和/或所选 functoid 的注释。</span><span class="sxs-lookup"><span data-stu-id="30101-108">Set a common label and/or comment for the selected functoids.</span></span>  
  
-   <span data-ttu-id="30101-109">设置的所选的 functoid 和链接的常见标签。</span><span class="sxs-lookup"><span data-stu-id="30101-109">Set a common label for the selected functoids and links.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="30101-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="30101-110">Prerequisites</span></span>  
 <span data-ttu-id="30101-111">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="30101-111">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-links"></a><span data-ttu-id="30101-112">为所选链接设置通用标签</span><span class="sxs-lookup"><span data-stu-id="30101-112">To set a common label for selected links</span></span>  
 <span data-ttu-id="30101-113">为多个链接设置通用标签是一个原子操作。</span><span class="sxs-lookup"><span data-stu-id="30101-113">Setting a common label on multiple links is one atomic operation.</span></span> <span data-ttu-id="30101-114">可以撤销或重做此操作。</span><span class="sxs-lookup"><span data-stu-id="30101-114">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="30101-115">为所选链接设置通用标签：</span><span class="sxs-lookup"><span data-stu-id="30101-115">To set a common label for the selected links:</span></span>  
  
1.  <span data-ttu-id="30101-116">在映射器网格页上，选择所需的链接。</span><span class="sxs-lookup"><span data-stu-id="30101-116">On the Mapper grid page, select the desired links.</span></span>  
  
2.  <span data-ttu-id="30101-117">在**属性**窗口中，输入中的合适标签**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="30101-117">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="to-set-a-common-label-andor-comment-for-selected-functoids"></a><span data-ttu-id="30101-118">为所选 functoid 设置通用标签和/或注释</span><span class="sxs-lookup"><span data-stu-id="30101-118">To set a common label and/or comment for selected functoids</span></span>  
 <span data-ttu-id="30101-119">为所选 functoid 设置通用标签和设置通用注释是两个不同的原子操作。</span><span class="sxs-lookup"><span data-stu-id="30101-119">Setting a common label and setting a common comment for the selected functoids are two different atomic operations.</span></span> <span data-ttu-id="30101-120">可以撤销或重做这些操作。</span><span class="sxs-lookup"><span data-stu-id="30101-120">You can undo or redo these operations.</span></span>  
  
 <span data-ttu-id="30101-121">为所选 functoid 设置通用标签/注释：</span><span class="sxs-lookup"><span data-stu-id="30101-121">To set a common label/comment for the selected functoids:</span></span>  
  
1.  <span data-ttu-id="30101-122">在映射器网格页上，选择所需的 functoid。</span><span class="sxs-lookup"><span data-stu-id="30101-122">On the Mapper grid page, select the desired functoids.</span></span>  
  
2.  <span data-ttu-id="30101-123">在**属性**窗口中，输入合适的标签和/或注释中**标签**和**注释**属性。</span><span class="sxs-lookup"><span data-stu-id="30101-123">In the **Properties** window, enter a suitable label and/or comment in the **Label** and **Comments** properties.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-functoids-and-links"></a><span data-ttu-id="30101-124">为所选 functoid 和链接设置通用标签</span><span class="sxs-lookup"><span data-stu-id="30101-124">To set a common label for selected functoids and links</span></span>  
 <span data-ttu-id="30101-125">可以为所选 functoid 和链接设置通用标签。</span><span class="sxs-lookup"><span data-stu-id="30101-125">You can set a common label for the selected functoids and links.</span></span> <span data-ttu-id="30101-126">**标签**是唯一的属性，这是通用的 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="30101-126">**Label** is the only property which is common to both functoids and links.</span></span> <span data-ttu-id="30101-127">可以撤销或重做此操作。</span><span class="sxs-lookup"><span data-stu-id="30101-127">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="30101-128">为所选 functoid 和链接设置通用标签：</span><span class="sxs-lookup"><span data-stu-id="30101-128">To set a common label for the selected functoids and links:</span></span>  
  
1.  <span data-ttu-id="30101-129">在映射器网格页上，选择所需的 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="30101-129">On the Mapper grid page, select the desired functoids and links.</span></span>  
  
2.  <span data-ttu-id="30101-130">在**属性**窗口中，输入中的合适标签**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="30101-130">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30101-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30101-131">See Also</span></span>  
 [<span data-ttu-id="30101-132">使用链接以指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="30101-132">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)