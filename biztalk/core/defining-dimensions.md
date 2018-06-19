---
title: 定义维度 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916e8f29d7f1e48a7bab5f9ad78e65cb78e51802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238485"
---
# <a name="defining-dimensions"></a><span data-ttu-id="d38f3-102">定义维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-102">Defining Dimensions</span></span>
<span data-ttu-id="d38f3-103">Microsoft Excel 将维度定义为类别，这些类别用于将表中的数据组织成若干级别以供分析之用。</span><span class="sxs-lookup"><span data-stu-id="d38f3-103">Microsoft Excel defines dimensions as categories used to organize data in a table into levels that will be used for analysis.</span></span> <span data-ttu-id="d38f3-104">例如，位置数据维度可能包含下级别：县/市、省/市/自治区和国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d38f3-104">For example, a location data dimension might contain levels such as city, state/province, and country/region.</span></span> <span data-ttu-id="d38f3-105">在 BAM 视图向导中创建 BAM 视图时，您可以添加以下维度类型中的一个或多个：</span><span class="sxs-lookup"><span data-stu-id="d38f3-105">When creating BAM Views in the BAM View wizard, you can add one or more of the following dimension types:</span></span>  
  
-   [<span data-ttu-id="d38f3-106">进度维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-106">Progress Dimension</span></span>](../core/progress-dimension.md)  
  
-   [<span data-ttu-id="d38f3-107">数据维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-107">Data Dimension</span></span>](../core/data-dimension.md)  
  
-   [<span data-ttu-id="d38f3-108">时间维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-108">Time Dimension</span></span>](../core/time-dimension.md)  
  
-   [<span data-ttu-id="d38f3-109">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-109">Numeric Range Dimension</span></span>](../core/numeric-range-dimension.md)  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="d38f3-110">预先计算的聚合数据</span><span class="sxs-lookup"><span data-stu-id="d38f3-110">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="d38f3-111">您可以在“BAM 视图”向导中添加新的维度。</span><span class="sxs-lookup"><span data-stu-id="d38f3-111">You add new dimensions in the BAM View wizard.</span></span> <span data-ttu-id="d38f3-112">在添加维度之前，您需要使用该向导来创建业务活动视图。</span><span class="sxs-lookup"><span data-stu-id="d38f3-112">Before you can add dimensions, you need to use the wizard to create business activity views.</span></span> <span data-ttu-id="d38f3-113">有关使用向导的详细信息，请参阅[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="d38f3-113">For more information about using the wizard, see [Define Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
### <a name="to-add-new-dimensions"></a><span data-ttu-id="d38f3-114">添加新维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-114">To add new dimensions</span></span>  
  
1.  <span data-ttu-id="d38f3-115">在 BAM 视图向导中，单击**下一步**直到你看到**新 BAM 视图： 聚合维度和度量值**页。</span><span class="sxs-lookup"><span data-stu-id="d38f3-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="d38f3-116">单击**新维度**。</span><span class="sxs-lookup"><span data-stu-id="d38f3-116">Click **New Dimensions**.</span></span>  
  
2.  <span data-ttu-id="d38f3-117">键入该维度的名称。</span><span class="sxs-lookup"><span data-stu-id="d38f3-117">Type a name for the dimension.</span></span>  
  
3.  <span data-ttu-id="d38f3-118">从下拉列表中选择一个维度类型。</span><span class="sxs-lookup"><span data-stu-id="d38f3-118">From the drop-down list, select a dimension type.</span></span>  
  
4.  <span data-ttu-id="d38f3-119">根据你选择的维度类型，填写适当的数据，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="d38f3-119">Based on the dimension type you selected, fill in the appropriate data, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38f3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d38f3-120">See Also</span></span>  
 [<span data-ttu-id="d38f3-121">进度维度</span><span class="sxs-lookup"><span data-stu-id="d38f3-121">Progress Dimension</span></span>](../core/progress-dimension.md)