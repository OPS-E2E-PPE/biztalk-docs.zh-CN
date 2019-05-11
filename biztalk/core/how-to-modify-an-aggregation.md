---
title: 如何修改聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], modifying
- BAM portal, aggregations
ms.assetid: dd5ce211-32d3-4e1d-8ee0-1225ec2c45fb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a073b454a270de2e7ac4f78c421513936d8f7ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336150"
---
# <a name="how-to-modify-an-aggregation"></a><span data-ttu-id="71b9d-102">如何修改聚合</span><span class="sxs-lookup"><span data-stu-id="71b9d-102">How to Modify an Aggregation</span></span>
<span data-ttu-id="71b9d-103">在使用数据透视表的相同方式报告在 Excel 中的 Office Web 组件中使用数据透视表报表。</span><span class="sxs-lookup"><span data-stu-id="71b9d-103">You use PivotTable reports in Office Web Components the same way you use PivotTable reports in Excel.</span></span> <span data-ttu-id="71b9d-104">您可以添加和删除行、 列和筛选器，以生成可以在其创建警报的聚合数据的视图。</span><span class="sxs-lookup"><span data-stu-id="71b9d-104">You can add and remove rows, columns, and filters to generate views of the aggregated data on which you can create alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71b9d-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="71b9d-105">Prerequisites</span></span>  
 <span data-ttu-id="71b9d-106">若要执行此过程，必须具有一个包含聚合的已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="71b9d-106">To perform this procedure, you must have a deployed view that contains an aggregation.</span></span>  
  
### <a name="to-modify-an-aggregation"></a><span data-ttu-id="71b9d-107">若要修改聚合</span><span class="sxs-lookup"><span data-stu-id="71b9d-107">To modify an aggregation</span></span>  
  
1.  <span data-ttu-id="71b9d-108">上**聚合**页上，从**数据透视表字段列表**窗口中，将使用你想要在行中显示它们放到左侧网格以添加行字段的列的数据字段。</span><span class="sxs-lookup"><span data-stu-id="71b9d-108">On the **Aggregations** page, from the **PivotTable Field List** window, drag the fields with data that you want to display in rows and drop them onto the left column of the grid to add row fields.</span></span> <span data-ttu-id="71b9d-109">如果看不到字段列表中，在数据透视表放置区域，边框内单击，并确保显示字段列表会显示。</span><span class="sxs-lookup"><span data-stu-id="71b9d-109">If you don't see the field list, click within the outlines of the PivotTable drop areas, and make sure Show Field List appears.</span></span> <span data-ttu-id="71b9d-110">若要查看具有级别的字段中提供了哪些级别的详细信息，请单击相应字段旁的加号 （+）。</span><span class="sxs-lookup"><span data-stu-id="71b9d-110">To see what levels of detail are available in fields that have levels, click the plus sign (+) next to the appropriate field.</span></span>  
  
2.  <span data-ttu-id="71b9d-111">将与你想要显示在标记为拖放区域的列的数据字段拖**将列字段拖至此处**。</span><span class="sxs-lookup"><span data-stu-id="71b9d-111">Drag fields with data that you want to display across columns to the drop area labeled **Drop Column Fields Here**.</span></span> <span data-ttu-id="71b9d-112">可被指定为计数或进度字段的唯一字段拖动到此区域。</span><span class="sxs-lookup"><span data-stu-id="71b9d-112">Only fields that are designated as counts or progress fields can be dragged to this area.</span></span>  
  
3.  <span data-ttu-id="71b9d-113">如果添加多个数据字段，排列这些字段中所需的顺序： 右键单击数据字段，指向**顺序**快捷菜单上，并在使用命令**顺序**菜单移动这些字段。</span><span class="sxs-lookup"><span data-stu-id="71b9d-113">If you add more than one data field, arrange these fields in the order you want: right-click a data field, point to **Order** on the shortcut menu, and use the commands on the **Order** menu to move the field.</span></span>  
  
4.  <span data-ttu-id="71b9d-114">若要重新排列字段，将它们从一个区域到另一个。</span><span class="sxs-lookup"><span data-stu-id="71b9d-114">To rearrange fields, drag them from one area to another.</span></span> <span data-ttu-id="71b9d-115">若要删除字段，将其拖出拖到导航框架数据透视表报表。</span><span class="sxs-lookup"><span data-stu-id="71b9d-115">To remove a field, drag it out of the PivotTable report onto the navigation frame.</span></span>  
  
5.  <span data-ttu-id="71b9d-116">从数据透视表报表中的总计列中，右键单击包含要设置警报的总的单元格。</span><span class="sxs-lookup"><span data-stu-id="71b9d-116">From the totals column in the PivotTable report, right-click the cell containing the total on which you are going to set an alert.</span></span> <span data-ttu-id="71b9d-117">选择**创建警报**打开警报管理页。</span><span class="sxs-lookup"><span data-stu-id="71b9d-117">Select **Create Alert** to open the Alert Management page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b9d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="71b9d-118">See Also</span></span>  
 <span data-ttu-id="71b9d-119">[BAM 门户上的聚合页](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="71b9d-119">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="71b9d-120">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="71b9d-120">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)