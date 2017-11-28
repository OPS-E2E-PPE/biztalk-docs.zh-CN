---
title: "如何使用数据透视表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed416f7a04392804c4c031a69940c4229eabe99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-pivottable"></a><span data-ttu-id="6c74f-102">如何使用透视表</span><span class="sxs-lookup"><span data-stu-id="6c74f-102">How to Use the PivotTable</span></span>
<span data-ttu-id="6c74f-103">当您定义了包含维度和度量的 BAM 视图后，您需要更新与该视图相关联的一个或多个透视表。</span><span class="sxs-lookup"><span data-stu-id="6c74f-103">When you have defined a BAM view that includes dimensions and measures, you need to update one or more PivotTables associated with that view.</span></span>  
  
 <span data-ttu-id="6c74f-104">Excel 中的透视表报告是一个交互式表，使用它可以轻松地合并和比较大量的数据。</span><span class="sxs-lookup"><span data-stu-id="6c74f-104">A PivotTable report in Excel is an interactive table that enables you to easily combine and compare large amounts of data.</span></span> <span data-ttu-id="6c74f-105">表中的行值和列值可以循环滚动，以查看所显示数据的不同摘要。</span><span class="sxs-lookup"><span data-stu-id="6c74f-105">The values in its rows and columns can be rotated to look at different summaries of the displayed data.</span></span> <span data-ttu-id="6c74f-106">您还可以使用透视表对数据执行计算，例如求聚合计数或平均数。</span><span class="sxs-lookup"><span data-stu-id="6c74f-106">A PivotTable also enables you perform calculations on the data, such as aggregate counts or averages.</span></span>  
  
 <span data-ttu-id="6c74f-107">创建透视表后，要使用透视表，请执行以下过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="6c74f-107">To use the PivotTable after you have created it, follow the steps in this procedure.</span></span> <span data-ttu-id="6c74f-108">有关使用透视表的详细信息，请参阅 Microsoft Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="6c74f-108">For more information about using PivotTables, see the Microsoft Excel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c74f-109">创建实时聚合透视表时，它最多可以包含 14 个维度级别。</span><span class="sxs-lookup"><span data-stu-id="6c74f-109">When you create a real-time aggregation pivot table, it can contain a maximum of 14 dimension levels.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c74f-110">如果在 Excel 工作表上定义多个透视表，且活动返回大的数据集，则最终的表可能增大并相互重叠。</span><span class="sxs-lookup"><span data-stu-id="6c74f-110">If you define multiple PivotTables on the Excel Worksheet, it is possible the resulting tables can grow and overlap each other if the Activity returns a large dataset.</span></span> <span data-ttu-id="6c74f-111">在这种情况下，在刷新数据时将收到“数据透视表不能覆盖另一个数据透视表”错误消息。</span><span class="sxs-lookup"><span data-stu-id="6c74f-111">In this scenario, you will receive "A PivotTable report cannot overlap another PivotTable report" when you refresh the data.</span></span> <span data-ttu-id="6c74f-112">通过在透视表间添加列或行以允许表增大而不发生重叠，可以更正此错误。</span><span class="sxs-lookup"><span data-stu-id="6c74f-112">You can correct this error by adding addition columns or rows between the pivot tables to allow the tables to grow with out overlapping.</span></span>  
  
### <a name="to-use-the-pivottable"></a><span data-ttu-id="6c74f-113">使用透视表</span><span class="sxs-lookup"><span data-stu-id="6c74f-113">To use the PivotTable</span></span>  
  
1.  <span data-ttu-id="6c74f-114">创建一个要与透视表一起使用的 BAM 视图。</span><span class="sxs-lookup"><span data-stu-id="6c74f-114">Create a BAM view to be used with a PivotTable.</span></span> <span data-ttu-id="6c74f-115">有关创建 BAM 视图的详细信息，请参阅[定义业务活动视图](../core/defining-a-bam-view.md)</span><span class="sxs-lookup"><span data-stu-id="6c74f-115">For more information about creating a BAM view, see [Defining a Business Activity View](../core/defining-a-bam-view.md)</span></span>  
  
2.  <span data-ttu-id="6c74f-116">使用**数据透视表字段列表**，拖放一个或多个可用维度到的列和行区域的数据透视表模板。</span><span class="sxs-lookup"><span data-stu-id="6c74f-116">Using the **PivotTable Field List**, drag-and-drop one or more available dimensions into the column and row areas of the PivotTable template.</span></span>  
  
3.  <span data-ttu-id="6c74f-117">使用**数据透视表字段列表**，拖放一个或多个可用度量值数据项区域的数据透视表模板。</span><span class="sxs-lookup"><span data-stu-id="6c74f-117">Using the  **PivotTable Field List**, drag-and-drop one or more available measures into the data items area of the PivotTable template.</span></span>  
  
     <span data-ttu-id="6c74f-118">更新透视表时，您将看到该表中填充了示例数据。</span><span class="sxs-lookup"><span data-stu-id="6c74f-118">As you are updating the PivotTable, you will notice that it is populated with sample data.</span></span> <span data-ttu-id="6c74f-119">这可帮助您确定如何配置透视表。</span><span class="sxs-lookup"><span data-stu-id="6c74f-119">This helps you determine how the PivotTable should be configured.</span></span>  
  
4.  <span data-ttu-id="6c74f-120">使用**数据透视表**工具栏上，一个数据透视表与图表相关联。</span><span class="sxs-lookup"><span data-stu-id="6c74f-120">Using the **PivotTable** toolbar, associate a chart with the PivotTable.</span></span>  
  
5.  <span data-ttu-id="6c74f-121">保存您的 Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="6c74f-121">Save your Excel workbook.</span></span>