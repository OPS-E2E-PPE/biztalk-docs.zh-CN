---
title: "如何修改聚合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], modifying
- BAM portal, aggregations
ms.assetid: dd5ce211-32d3-4e1d-8ee0-1225ec2c45fb
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f5f157da15cb53da41d6735524ed502cd35156
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-an-aggregation"></a><span data-ttu-id="28a42-102">如何修改聚合</span><span class="sxs-lookup"><span data-stu-id="28a42-102">How to Modify an Aggregation</span></span>
<span data-ttu-id="28a42-103">在 Office Web 组件中使用数据透视表的方法与在 Excel 中使用数据透视表的方法相同。</span><span class="sxs-lookup"><span data-stu-id="28a42-103">You use PivotTable reports in Office Web Components the same way you use PivotTable reports in Excel.</span></span> <span data-ttu-id="28a42-104">可以添加和移除行、列及筛选器，以便生成可在聚合数据上创建警报的视图。</span><span class="sxs-lookup"><span data-stu-id="28a42-104">You can add and remove rows, columns, and filters to generate views of the aggregated data on which you can create alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28a42-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="28a42-105">Prerequisites</span></span>  
 <span data-ttu-id="28a42-106">若要执行此过程，必须拥有包含聚合的已部署视图。</span><span class="sxs-lookup"><span data-stu-id="28a42-106">To perform this procedure, you must have a deployed view that contains an aggregation.</span></span>  
  
### <a name="to-modify-an-aggregation"></a><span data-ttu-id="28a42-107">修改聚合</span><span class="sxs-lookup"><span data-stu-id="28a42-107">To modify an aggregation</span></span>  
  
1.  <span data-ttu-id="28a42-108">上**聚合**页上，从**数据透视表字段列表**窗口中，将与你想要在行中显示并将它们放要将行字段添加的网格左侧列的数据字段。</span><span class="sxs-lookup"><span data-stu-id="28a42-108">On the **Aggregations** page, from the **PivotTable Field List** window, drag the fields with data that you want to display in rows and drop them onto the left column of the grid to add row fields.</span></span> <span data-ttu-id="28a42-109">如果没有看到该字段列表，请在数据透视表放置区域的边框内单击，确保出现“显示字段列表”。</span><span class="sxs-lookup"><span data-stu-id="28a42-109">If you don't see the field list, click within the outlines of the PivotTable drop areas, and make sure Show Field List appears.</span></span> <span data-ttu-id="28a42-110">若要查看具有级别的字段的详细的可用级别，请单击相应字段旁的加号 (+)。</span><span class="sxs-lookup"><span data-stu-id="28a42-110">To see what levels of detail are available in fields that have levels, click the plus sign (+) next to the appropriate field.</span></span>  
  
2.  <span data-ttu-id="28a42-111">将与你想要在列标记为拖放区域上显示的数据的字段拖**将列字段拖至此处**。</span><span class="sxs-lookup"><span data-stu-id="28a42-111">Drag fields with data that you want to display across columns to the drop area labeled **Drop Column Fields Here**.</span></span> <span data-ttu-id="28a42-112">只有指定为计数字段或进度字段的字段才能拖到此区域中。</span><span class="sxs-lookup"><span data-stu-id="28a42-112">Only fields that are designated as counts or progress fields can be dragged to this area.</span></span>  
  
3.  <span data-ttu-id="28a42-113">如果添加多个数据字段，排列所需的顺序中的这些字段： 右键单击数据字段，指向**顺序**的快捷菜单上，并在使用命令**顺序**菜单可将字段。</span><span class="sxs-lookup"><span data-stu-id="28a42-113">If you add more than one data field, arrange these fields in the order you want: right-click a data field, point to **Order** on the shortcut menu, and use the commands on the **Order** menu to move the field.</span></span>  
  
4.  <span data-ttu-id="28a42-114">若要重新排列字段，请将它们从一个区域拖放到另一个区域中。</span><span class="sxs-lookup"><span data-stu-id="28a42-114">To rearrange fields, drag them from one area to another.</span></span> <span data-ttu-id="28a42-115">若要删除字段，请将该字段拖出数据透视表，放到导航框架上。</span><span class="sxs-lookup"><span data-stu-id="28a42-115">To remove a field, drag it out of the PivotTable report onto the navigation frame.</span></span>  
  
5.  <span data-ttu-id="28a42-116">从数据透视表的“汇总”列中，用鼠标右键单击要基于其汇总值设置警报的单元格。</span><span class="sxs-lookup"><span data-stu-id="28a42-116">From the totals column in the PivotTable report, right-click the cell containing the total on which you are going to set an alert.</span></span> <span data-ttu-id="28a42-117">选择**创建警报**以打开警报管理页。</span><span class="sxs-lookup"><span data-stu-id="28a42-117">Select **Create Alert** to open the Alert Management page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a42-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28a42-118">See Also</span></span>  
 <span data-ttu-id="28a42-119">[BAM 门户上的聚合页](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="28a42-119">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="28a42-120">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="28a42-120">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)