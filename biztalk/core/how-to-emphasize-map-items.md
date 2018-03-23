---
title: 如何强调映射项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6bb03969a044c6a474f5d2d1c1e5e1a5067cf81
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-emphasize-map-items"></a><span data-ttu-id="2ef3e-102">如何强调映射项</span><span class="sxs-lookup"><span data-stu-id="2ef3e-102">How to Emphasize Map Items</span></span>
<span data-ttu-id="2ef3e-103">在 BizTalk 映射器中，当您选择一个映射项目时，都会强调所有相关的链接和 functoids。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-103">In the BizTalk Mapper, when you select a map item, all the associated links and functoids are emphasized.</span></span> <span data-ttu-id="2ef3e-104">这在具有许多链接的映射中非常有用，因为识别关系和相关架构项比较困难。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-104">This is useful in maps with many links, where it is difficult to identify a relationship and the related schema items.</span></span>  
  
 <span data-ttu-id="2ef3e-105">当你选择一个链接、functoid 或一个架构元素时，BizTalk 映射器会强调相关关系和架构元素。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-105">When you select a link, a functoid, or a schema element, the BizTalk Mapper emphasizes the related relationship and schema elements.</span></span> <span data-ttu-id="2ef3e-106">对于已选择的映射项，所有的传入链接和传出链接（递归方式）将以粗体突出显示，并且所有其他映射项目将显示为灰色。以下屏幕快照将已选择的映射项用粗体和彩色显示，而其他映射项目则显示更亮些。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-106">For the selected map item, all the incoming links and the outgoing links (recursively) are highlighted in bold, and all the other map items are greyed out. The following screenshot shows the selected map item in bold and color and the other map items appear lighter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ef3e-107">在此上下文中，相关关系意思是直接或间接链接到已选择映射项目的所有链接、functoid 或结构元素。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-107">In this context, a related relationship means all the links, functoids, or schema elements directly or indirectly linked to the selected map item.</span></span>  
  
 <span data-ttu-id="2ef3e-108">![强调地图项](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span><span class="sxs-lookup"><span data-stu-id="2ef3e-108">![Emphasizing a map item](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ef3e-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="2ef3e-109">Prerequisites</span></span>  
 <span data-ttu-id="2ef3e-110">此操作要求 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-110">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-emphasize-a-map-item"></a><span data-ttu-id="2ef3e-111">若要强调地图项</span><span class="sxs-lookup"><span data-stu-id="2ef3e-111">To emphasize a map item</span></span>  
  
-   <span data-ttu-id="2ef3e-112">单击一个映射项（链接、functoid 或架构元素）。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-112">Click a map item (a link, a functoid, or a schema element).</span></span> <span data-ttu-id="2ef3e-113">您可以查看到当前网格页中与已选择映射项有关的其他链接和 functoid（包括架构节点）都是突出显示。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-113">You can see that all the other links and functoids (including the schema nodes) associated with the selected map item in the current grid page are highlighted.</span></span>  
  
     <span data-ttu-id="2ef3e-114">有时，对于已选择的节点，可能在其他网格页中存在关系。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-114">Sometimes, for the selected node, there might be relationships existing in other grid pages.</span></span> <span data-ttu-id="2ef3e-115">在此种情况下，BizTalk 映射器强调当前网格页中的实例，并且突出显示页面选项卡（存在已选择节点的其他相关关系）。</span><span class="sxs-lookup"><span data-stu-id="2ef3e-115">In such a case, the BizTalk Mapper emphasizes the instance in current grid page and also highlights the page tab where the other related relationship to the selected node exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef3e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ef3e-116">See Also</span></span>  
 [<span data-ttu-id="2ef3e-117">在 BizTalk 映射程序中使用增强的功能</span><span class="sxs-lookup"><span data-stu-id="2ef3e-117">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)