---
title: 使用网格页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14a27bbf-3761-49dd-be6f-f311857e38c2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 219d763df47d606e409b241015afd76b8dd30b8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277255"
---
# <a name="working-with-grid-pages"></a><span data-ttu-id="a1c8a-102">使用网格页</span><span class="sxs-lookup"><span data-stu-id="a1c8a-102">Working with Grid Pages</span></span>
<span data-ttu-id="a1c8a-103">创建映射，对于许多业务文档可以经常涉及大量的链接和 functoid，导致网格变得复杂并且难以理解。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-103">Creating maps for many business documents can involve numerous links and functoids, often enough to make the grid complex and difficult to understand.</span></span> <span data-ttu-id="a1c8a-104">这一潜在复杂问题的解决方案是在网格页的简介。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-104">The solution to this potential complexity is the introduction of pages to the grid.</span></span> <span data-ttu-id="a1c8a-105">可以隔离在不同的页，将映射的各个方面，然后查看和单独使用这些页。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-105">You can isolate different aspects of your mapping into different pages, and then view and work with those pages separately.</span></span>  
  
 <span data-ttu-id="a1c8a-106">页表示为网格中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-106">Pages are represented as tabs in the grid.</span></span> <span data-ttu-id="a1c8a-107">可以添加新页面、 重命名页、 删除页面，其中，和之间移动和等。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-107">You can add new pages, rename pages, delete pages, move between and within them, and so on.</span></span> <span data-ttu-id="a1c8a-108">本部分提供有关上述各种页操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-108">This section provides step-by-step instructions for these various page operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1c8a-109">快捷方式来处理网格页的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-109">For a list of shortcuts to work with grid pages, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a1c8a-110">链接和 functoid 相互连接的必须是同一网格页中。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-110">Links and functoids connected to each other must all be in the same grid page.</span></span> <span data-ttu-id="a1c8a-111">可以在网格页之间移动链接和 functoid。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-111">You can move links and functoids between grid pages.</span></span>  <span data-ttu-id="a1c8a-112">我们可以执行**移至页面**通过选择任意数量的链接和/或 functoid，或选择任意数目的项并将其拖动到其他页面的操作。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-112">We can perform **Move To Page** operation either by selecting any number of link(s) and/or functoids, or  selecting any number of items and dragging them to other pages.</span></span> <span data-ttu-id="a1c8a-113">有关详细信息，请参阅[如何将移动之间和网格页内](../core/how-to-move-between-and-within-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-113">For more information, see [How to Move Between and Within Grid Pages](../core/how-to-move-between-and-within-grid-pages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1c8a-114">网格属性适用于整个网格，而不适用于单页。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-114">Grid properties apply to the entire grid and not to an individual page.</span></span> <span data-ttu-id="a1c8a-115">设置网格属性建立的所有页面和不只是显示的页面的值。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-115">Setting a Grid property establishes the value for all of the pages and not merely the page displayed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1c8a-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="a1c8a-116">In This Section</span></span>  
  
-   [<span data-ttu-id="a1c8a-117">如何移动之间和网格页内</span><span class="sxs-lookup"><span data-stu-id="a1c8a-117">How to Move Between and Within Grid Pages</span></span>](../core/how-to-move-between-and-within-grid-pages.md)  
  
-   [<span data-ttu-id="a1c8a-118">如何在网格页之间移动关系</span><span class="sxs-lookup"><span data-stu-id="a1c8a-118">How to Move a Relationship Between Grid Pages</span></span>](../core/how-to-move-a-relationship-between-grid-pages.md)  
  
-   [<span data-ttu-id="a1c8a-119">如何重排网格页顺序</span><span class="sxs-lookup"><span data-stu-id="a1c8a-119">How to Reorder Grid Pages</span></span>](../core/how-to-reorder-grid-pages.md)