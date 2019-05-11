---
title: 如何使用该数据透视表 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b0400dd5cf1c21aa0c24ac54e2a72ded2e20fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333212"
---
# <a name="how-to-use-the-pivottable"></a><span data-ttu-id="04040-102">如何使用透视表</span><span class="sxs-lookup"><span data-stu-id="04040-102">How to Use the PivotTable</span></span>
<span data-ttu-id="04040-103">定义 BAM 视图，其中包括维度和度量值后，你需要更新与该视图相关联的一个或多个数据透视表。</span><span class="sxs-lookup"><span data-stu-id="04040-103">When you have defined a BAM view that includes dimensions and measures, you need to update one or more PivotTables associated with that view.</span></span>  
  
 <span data-ttu-id="04040-104">在 Excel 中的数据透视表报表是一个交互式表，使您能够轻松地合并和比较大量数据。</span><span class="sxs-lookup"><span data-stu-id="04040-104">A PivotTable report in Excel is an interactive table that enables you to easily combine and compare large amounts of data.</span></span> <span data-ttu-id="04040-105">可以旋转其行和列中的值，若要查看显示的数据的不同摘要。</span><span class="sxs-lookup"><span data-stu-id="04040-105">The values in its rows and columns can be rotated to look at different summaries of the displayed data.</span></span> <span data-ttu-id="04040-106">数据透视表，还可以执行计算的数据，例如求聚合计数或平均值。</span><span class="sxs-lookup"><span data-stu-id="04040-106">A PivotTable also enables you perform calculations on the data, such as aggregate counts or averages.</span></span>  
  
 <span data-ttu-id="04040-107">若要在创建后，请使用该数据透视表，请执行此过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="04040-107">To use the PivotTable after you have created it, follow the steps in this procedure.</span></span> <span data-ttu-id="04040-108">有关使用数据透视表的详细信息，请参阅 Microsoft Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="04040-108">For more information about using PivotTables, see the Microsoft Excel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04040-109">创建实时聚合透视表时，它可以包含最多为 14 个维度级别。</span><span class="sxs-lookup"><span data-stu-id="04040-109">When you create a real-time aggregation pivot table, it can contain a maximum of 14 dimension levels.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="04040-110">如果在 Excel 工作表上定义多个数据透视表，就可以生成的表可能增大并相互重叠，如果活动返回大型数据集。</span><span class="sxs-lookup"><span data-stu-id="04040-110">If you define multiple PivotTables on the Excel Worksheet, it is possible the resulting tables can grow and overlap each other if the Activity returns a large dataset.</span></span> <span data-ttu-id="04040-111">在此方案中，你将收到"数据透视表不能重叠另一个数据透视表报表"时刷新数据。</span><span class="sxs-lookup"><span data-stu-id="04040-111">In this scenario, you will receive "A PivotTable report cannot overlap another PivotTable report" when you refresh the data.</span></span> <span data-ttu-id="04040-112">可以通过添加列或数据透视表，以允许表增大而不重叠的之间的行来更正此错误。</span><span class="sxs-lookup"><span data-stu-id="04040-112">You can correct this error by adding addition columns or rows between the pivot tables to allow the tables to grow with out overlapping.</span></span>  
  
### <a name="to-use-the-pivottable"></a><span data-ttu-id="04040-113">若要使用该数据透视表</span><span class="sxs-lookup"><span data-stu-id="04040-113">To use the PivotTable</span></span>  
  
1.  <span data-ttu-id="04040-114">创建要与数据透视表一起使用的 BAM 视图。</span><span class="sxs-lookup"><span data-stu-id="04040-114">Create a BAM view to be used with a PivotTable.</span></span> <span data-ttu-id="04040-115">有关创建 BAM 视图的详细信息，请参阅[定义业务活动视图。](../core/defining-a-bam-view.md)</span><span class="sxs-lookup"><span data-stu-id="04040-115">For more information about creating a BAM view, see [Defining a Business Activity View](../core/defining-a-bam-view.md)</span></span>  
  
2.  <span data-ttu-id="04040-116">使用**数据透视表字段列表**，拖放一个或多个可用维度到数据透视表模板的列和行区域。</span><span class="sxs-lookup"><span data-stu-id="04040-116">Using the **PivotTable Field List**, drag-and-drop one or more available dimensions into the column and row areas of the PivotTable template.</span></span>  
  
3.  <span data-ttu-id="04040-117">使用**数据透视表字段列表**，拖放一个或多个可用度量值拖动到数据的项区域的数据透视表模板。</span><span class="sxs-lookup"><span data-stu-id="04040-117">Using the  **PivotTable Field List**, drag-and-drop one or more available measures into the data items area of the PivotTable template.</span></span>  
  
     <span data-ttu-id="04040-118">要更新该数据透视表，您会发现用示例数据填充。</span><span class="sxs-lookup"><span data-stu-id="04040-118">As you are updating the PivotTable, you will notice that it is populated with sample data.</span></span> <span data-ttu-id="04040-119">这有助于确定应如何配置该数据透视表。</span><span class="sxs-lookup"><span data-stu-id="04040-119">This helps you determine how the PivotTable should be configured.</span></span>  
  
4.  <span data-ttu-id="04040-120">使用**数据透视表**工具栏中，某个图表与该数据透视表的关联。</span><span class="sxs-lookup"><span data-stu-id="04040-120">Using the **PivotTable** toolbar, associate a chart with the PivotTable.</span></span>  
  
5.  <span data-ttu-id="04040-121">保存 Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="04040-121">Save your Excel workbook.</span></span>