---
title: 如何搜索映射项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.search
ms.assetid: 3dbb089a-6aa8-4921-a82d-81d3a193e933
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee61bccfae53a79d8fba6bd0aa5af2c537d98270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255533"
---
# <a name="how-to-search-for-map-items"></a><span data-ttu-id="3f016-102">如何搜索映射项</span><span class="sxs-lookup"><span data-stu-id="3f016-102">How to Search for Map Items</span></span>
<span data-ttu-id="3f016-103">使用 BizTalk 映射器，可以搜索源架构、目标架构和网格图面中的项目。</span><span class="sxs-lookup"><span data-stu-id="3f016-103">The BizTalk Mapper enables you to search for items in the source schema, the destination schema, and the grid surface.</span></span> <span data-ttu-id="3f016-104">本主题提供有关如何执行此操作的信息。</span><span class="sxs-lookup"><span data-stu-id="3f016-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3f016-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3f016-105">Prerequisites</span></span>  
 <span data-ttu-id="3f016-106">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="3f016-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-search-for-items"></a><span data-ttu-id="3f016-107">若要搜索的项</span><span class="sxs-lookup"><span data-stu-id="3f016-107">To search for items</span></span>  
 <span data-ttu-id="3f016-108">选择要进行搜索的架构。</span><span class="sxs-lookup"><span data-stu-id="3f016-108">Select the schema where you want to search.</span></span> <span data-ttu-id="3f016-109">如果选择源架构，则 BizTalk 映射器将只在源架构中搜索和查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="3f016-109">If you select source schema, the BizTalk Mapper searches and looks for the match only in the source schema.</span></span> <span data-ttu-id="3f016-110">但是，可以同时选择源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="3f016-110">However, you can select both source and destination schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f016-111">若要确认所选内容，请查看架构或架构项目之前的标记。</span><span class="sxs-lookup"><span data-stu-id="3f016-111">To confirm selection, look for the mark before the schema or the schema item.</span></span>  
  
 <span data-ttu-id="3f016-112">![搜索映射项](../core/media/searching-map-items.gif "Searching_map_items")</span><span class="sxs-lookup"><span data-stu-id="3f016-112">![Searching for map items](../core/media/searching-map-items.gif "Searching_map_items")</span></span>  
  
 <span data-ttu-id="3f016-113">在**搜索**映射器实用程序功能区上的框中，键入你想要搜索的项的名称。</span><span class="sxs-lookup"><span data-stu-id="3f016-113">In the **Search** box on the Mapper utility ribbon, type the name of the item you want to search.</span></span> <span data-ttu-id="3f016-114">您可以搜索源架构或目标架构中节点名称中的字符串，以及名称、标签、注释、输入或 functoid 脚本中的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f016-114">You can search for a string in the name of a node in the source or destination schema, as well as in the name, label, comment, inputs, or scripts for functoids.</span></span>  
  
 <span data-ttu-id="3f016-115">输入搜索字符串时，将突出显示符合搜索条件的对象。</span><span class="sxs-lookup"><span data-stu-id="3f016-115">As you enter the search string, the objects that meet the search criteria are highlighted.</span></span> <span data-ttu-id="3f016-116">你可以然后遍历搜索结果使用箭头键在键盘上或![在列表中向上移动](../core/media/move-up-button.gif "Move_up_button")和![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")实用程序功能区上的图标。</span><span class="sxs-lookup"><span data-stu-id="3f016-116">You can then traverse through the search results either using the arrow keys on the keyboard or the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") and ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") icons on the utility ribbon.</span></span> <span data-ttu-id="3f016-117">如果搜索结果散布在所有三个视图中，则可以按照源架构、关系视图和目标架构的顺序遍历搜索结果。</span><span class="sxs-lookup"><span data-stu-id="3f016-117">If the search results are spread across all three views, the search results are traversed in the order of the source schema, relationship view, and the destination schema.</span></span> <span data-ttu-id="3f016-118">后经过的搜索结果，你可以关闭搜索通过删除搜索字符串或通过单击 (![清除映射器搜索](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) 搜索字符串旁边的图标。</span><span class="sxs-lookup"><span data-stu-id="3f016-118">After going through the search results, you can close the search either by deleting the search string or by clicking the (![Clear Mapper search](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) icon next to the search string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f016-119">还可以按 Ctrl+M、Ctrl+J 或 Ctrl+M、Ctrl+K 分别向上或向下遍历搜索结果。</span><span class="sxs-lookup"><span data-stu-id="3f016-119">You can also press CTRL+M, CTRL+J or CTRL+M, CTRL+K to traverse through the search results upwards or downwards, respectively.</span></span> <span data-ttu-id="3f016-120">映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="3f016-120">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f016-121">如果关系视图的搜索结果未显示在单个映射视图中，则 BizTalk 映射器会在存在其他命中项的方向显示闪烁的箭头。</span><span class="sxs-lookup"><span data-stu-id="3f016-121">If the search results for the relationship view are not visible in a single map view, the BizTalk Mapper displays blinking arrows in the direction where there are additional hits.</span></span> <span data-ttu-id="3f016-122">例如，顶部的箭头图标 (![其他搜索结果的方向](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) 表示没有其他搜索结果，可通过向上滚动查看。</span><span class="sxs-lookup"><span data-stu-id="3f016-122">For example, the top arrow icon (![Direction for additional search results](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) denotes that there are additional search results that can be viewed by scrolling up.</span></span> <span data-ttu-id="3f016-123">同样，如果不同的映射页上都有搜索结果，则这些页的页选项卡将以黄色突出显示。</span><span class="sxs-lookup"><span data-stu-id="3f016-123">Similarly, if there are search results in different map pages, the page tabs for those pages are highlighted, in yellow.</span></span> <span data-ttu-id="3f016-124">当将鼠标移动到突出显示的页上时，工具提示会显示该页上的搜索匹配项数。</span><span class="sxs-lookup"><span data-stu-id="3f016-124">On moving the mouse over the highlighted page, the tooltip displays the number of search matches on that page.</span></span> <span data-ttu-id="3f016-125">状态栏会显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="3f016-125">The status bar displays the search results.</span></span>  
  
 <span data-ttu-id="3f016-126">![状态栏显示搜索结果](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")</span><span class="sxs-lookup"><span data-stu-id="3f016-126">![Status bar displaying the search results](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f016-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f016-127">See Also</span></span>  
 [<span data-ttu-id="3f016-128">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="3f016-128">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)