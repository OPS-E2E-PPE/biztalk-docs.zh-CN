---
title: 定义维度 |Microsoft Docs
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
ms.openlocfilehash: be3c55298b58d2d5ca51652ed9911c901235863e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013654"
---
# <a name="defining-dimensions"></a><span data-ttu-id="4365b-102">定义维度</span><span class="sxs-lookup"><span data-stu-id="4365b-102">Defining Dimensions</span></span>
<span data-ttu-id="4365b-103">Microsoft Excel 将维度定义为类别，这些类别用于将表中的数据组织成若干级别以供分析之用。</span><span class="sxs-lookup"><span data-stu-id="4365b-103">Microsoft Excel defines dimensions as categories used to organize data in a table into levels that will be used for analysis.</span></span> <span data-ttu-id="4365b-104">例如，位置数据维度可能包含下级别：县/市、省/市/自治区和国家/地区。</span><span class="sxs-lookup"><span data-stu-id="4365b-104">For example, a location data dimension might contain levels such as city, state/province, and country/region.</span></span> <span data-ttu-id="4365b-105">在 BAM 视图向导中创建 BAM 视图时，您可以添加以下维度类型中的一个或多个：</span><span class="sxs-lookup"><span data-stu-id="4365b-105">When creating BAM Views in the BAM View wizard, you can add one or more of the following dimension types:</span></span>  
  
- [<span data-ttu-id="4365b-106">进度维度</span><span class="sxs-lookup"><span data-stu-id="4365b-106">Progress Dimension</span></span>](../core/progress-dimension.md)  
  
- [<span data-ttu-id="4365b-107">数据维度</span><span class="sxs-lookup"><span data-stu-id="4365b-107">Data Dimension</span></span>](../core/data-dimension.md)  
  
- [<span data-ttu-id="4365b-108">时间维度</span><span class="sxs-lookup"><span data-stu-id="4365b-108">Time Dimension</span></span>](../core/time-dimension.md)  
  
- [<span data-ttu-id="4365b-109">数值范围维度</span><span class="sxs-lookup"><span data-stu-id="4365b-109">Numeric Range Dimension</span></span>](../core/numeric-range-dimension.md)  
  
  <span data-ttu-id="4365b-110">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="4365b-110">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
  <span data-ttu-id="4365b-111">预先计算的聚合数据</span><span class="sxs-lookup"><span data-stu-id="4365b-111">Pre-calculated Aggregation Data</span></span>  
  
  <span data-ttu-id="4365b-112">您可以在“BAM 视图”向导中添加新的维度。</span><span class="sxs-lookup"><span data-stu-id="4365b-112">You add new dimensions in the BAM View wizard.</span></span> <span data-ttu-id="4365b-113">在添加维度之前，您需要使用该向导来创建业务活动视图。</span><span class="sxs-lookup"><span data-stu-id="4365b-113">Before you can add dimensions, you need to use the wizard to create business activity views.</span></span> <span data-ttu-id="4365b-114">有关使用向导的详细信息，请参阅[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="4365b-114">For more information about using the wizard, see [Define Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
### <a name="to-add-new-dimensions"></a><span data-ttu-id="4365b-115">添加新维度</span><span class="sxs-lookup"><span data-stu-id="4365b-115">To add new dimensions</span></span>  
  
1.  <span data-ttu-id="4365b-116">在 BAM 视图向导中，单击**下一步**直到您看到**新建 BAM 视图： 聚合维度和度量值**页。</span><span class="sxs-lookup"><span data-stu-id="4365b-116">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="4365b-117">单击**新维度**。</span><span class="sxs-lookup"><span data-stu-id="4365b-117">Click **New Dimensions**.</span></span>  
  
2.  <span data-ttu-id="4365b-118">键入该维度的名称。</span><span class="sxs-lookup"><span data-stu-id="4365b-118">Type a name for the dimension.</span></span>  
  
3.  <span data-ttu-id="4365b-119">从下拉列表中选择一个维度类型。</span><span class="sxs-lookup"><span data-stu-id="4365b-119">From the drop-down list, select a dimension type.</span></span>  
  
4.  <span data-ttu-id="4365b-120">根据所选的维度类型，填写适当的数据，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="4365b-120">Based on the dimension type you selected, fill in the appropriate data, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4365b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4365b-121">See Also</span></span>  
 [<span data-ttu-id="4365b-122">进度维度</span><span class="sxs-lookup"><span data-stu-id="4365b-122">Progress Dimension</span></span>](../core/progress-dimension.md)