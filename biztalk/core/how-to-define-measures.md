---
title: 如何定义度量值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68b269cd333706978bb2ef2433f0e5703e72b37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338796"
---
# <a name="how-to-define-measures"></a><span data-ttu-id="2a9ab-102">如何定义度量值</span><span class="sxs-lookup"><span data-stu-id="2a9ab-102">How to Define Measures</span></span>
<span data-ttu-id="2a9ab-103">度量值定义如何计算活动。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-103">A measure defines how an activity is calculated.</span></span> <span data-ttu-id="2a9ab-104">创建 BAM 视图时您可以在视图中定义的度量值，该活动。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-104">When you create a BAM view you can define a measure for the activity in the view.</span></span> <span data-ttu-id="2a9ab-105">例如，对于采购订单活动，可以计算总 PO 金额、 Po 数量、 平均 PO 金额等。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-105">For example, for a purchase order activity, you can calculate the total PO amount, the number of POs, the average PO amount, and so on.</span></span>  
  
 <span data-ttu-id="2a9ab-106">BAM 支持度量值包括：</span><span class="sxs-lookup"><span data-stu-id="2a9ab-106">BAM supported measures include:</span></span>  
  
-   <span data-ttu-id="2a9ab-107">Sum</span><span class="sxs-lookup"><span data-stu-id="2a9ab-107">Sum</span></span>  
  
-   <span data-ttu-id="2a9ab-108">Count</span><span class="sxs-lookup"><span data-stu-id="2a9ab-108">Count</span></span>  
  
-   <span data-ttu-id="2a9ab-109">平均值</span><span class="sxs-lookup"><span data-stu-id="2a9ab-109">Average</span></span>  
  
-   <span data-ttu-id="2a9ab-110">最低要求</span><span class="sxs-lookup"><span data-stu-id="2a9ab-110">Minimum</span></span>  
  
-   <span data-ttu-id="2a9ab-111">最大值</span><span class="sxs-lookup"><span data-stu-id="2a9ab-111">Maximum</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a9ab-112">BAM 实时聚合 (RTA) 功能目前不支持最小值和最大值的度量值。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-112">The BAM Real-time Aggregation (RTA) feature doesn't currently support Minimum and Maximum measures.</span></span> <span data-ttu-id="2a9ab-113">可以使用这些度量值，但当标记为 RTA Excel 数据透视表时，将忽略最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-113">You can use those measures, but when you mark the Excel pivot table as an RTA, Minimum and Maximum are ignored.</span></span>  
  
### <a name="to-add-new-measures"></a><span data-ttu-id="2a9ab-114">若要添加新度量值</span><span class="sxs-lookup"><span data-stu-id="2a9ab-114">To add new measures</span></span>  
  
1. <span data-ttu-id="2a9ab-115">在 BAM 视图向导中，单击**下一步**直到您看到**新建 BAM 视图：聚合维度和度量值**页。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="2a9ab-116">单击**新的度量值**。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-116">Click **New Measures**.</span></span>  
  
2. <span data-ttu-id="2a9ab-117">键入度量值的名称。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-117">Type a name for your measure.</span></span>  
  
3. <span data-ttu-id="2a9ab-118">从下拉列表中，选择**基本数据项**。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-118">From the drop-down list, select the **Base data item**.</span></span>  
  
4. <span data-ttu-id="2a9ab-119">单击**聚合类型**你想要使用。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-119">Click the **Aggregation type** you want to use.</span></span> <span data-ttu-id="2a9ab-120">选项包括：</span><span class="sxs-lookup"><span data-stu-id="2a9ab-120">The choices include:</span></span>  
  
   -   <span data-ttu-id="2a9ab-121">Sum</span><span class="sxs-lookup"><span data-stu-id="2a9ab-121">Sum</span></span>  
  
   -   <span data-ttu-id="2a9ab-122">Count</span><span class="sxs-lookup"><span data-stu-id="2a9ab-122">Count</span></span>  
  
   -   <span data-ttu-id="2a9ab-123">平均值</span><span class="sxs-lookup"><span data-stu-id="2a9ab-123">Average</span></span>  
  
   -   <span data-ttu-id="2a9ab-124">最小值 （Rta 不支持）。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-124">Minimum (not supported for RTAs).</span></span>  
  
   -   <span data-ttu-id="2a9ab-125">最大值 （Rta 不支持）</span><span class="sxs-lookup"><span data-stu-id="2a9ab-125">Maximum (not supported for RTAs)</span></span>  
  
5. <span data-ttu-id="2a9ab-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-126">Click **OK**.</span></span> <span data-ttu-id="2a9ab-127">完成添加维度和度量值后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-127">When you finish adding dimensions and measures, click **Next**.</span></span>  
  
6. <span data-ttu-id="2a9ab-128">在**新建 BAM 视图：摘要**页上，查看有关您的新视图的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-128">On the **New BAM View: Summary** page, review the information regarding your new view, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="2a9ab-129">单击**完成**若要完成**BAM 视图向导**。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-129">Click **Finish** to complete the **BAM View Wizard**.</span></span>  
  
   <span data-ttu-id="2a9ab-130">如果添加度量值和维度到 BAM 视图，您可以将这些项添加到 Excel 工作簿中数据透视表。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-130">If you added measures and dimensions to your BAM view, you can add those items to the PivotTable in the Excel workbook.</span></span> <span data-ttu-id="2a9ab-131">有关创建数据透视表的详细信息，请参阅[如何使用该数据透视表](../core/how-to-use-the-pivottable.md)。</span><span class="sxs-lookup"><span data-stu-id="2a9ab-131">For more information about creating a PivotTable, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9ab-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a9ab-132">See Also</span></span>  
 [<span data-ttu-id="2a9ab-133">定义维度</span><span class="sxs-lookup"><span data-stu-id="2a9ab-133">Defining Dimensions</span></span>](../core/defining-dimensions.md)