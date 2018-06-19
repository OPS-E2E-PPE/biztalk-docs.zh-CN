---
title: 如何定义度量值 |Microsoft 文档
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
ms.openlocfilehash: e56fea736baaec3f259fc8831a7256e28eaabc9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249141"
---
# <a name="how-to-define-measures"></a><span data-ttu-id="08655-102">如何定义度量值</span><span class="sxs-lookup"><span data-stu-id="08655-102">How to Define Measures</span></span>
<span data-ttu-id="08655-103">度量值定义如何计算活动。</span><span class="sxs-lookup"><span data-stu-id="08655-103">A measure defines how an activity is calculated.</span></span> <span data-ttu-id="08655-104">创建 BAM 视图时，可以为该视图中的活动定义度量值。</span><span class="sxs-lookup"><span data-stu-id="08655-104">When you create a BAM view you can define a measure for the activity in the view.</span></span> <span data-ttu-id="08655-105">例如，对于一项采购订单活动，可以计算总 PO 金额、PO 数量、平均 PO 金额等。</span><span class="sxs-lookup"><span data-stu-id="08655-105">For example, for a purchase order activity, you can calculate the total PO amount, the number of POs, the average PO amount, and so on.</span></span>  
  
 <span data-ttu-id="08655-106">BAM 支持的度量值包括：</span><span class="sxs-lookup"><span data-stu-id="08655-106">BAM supported measures include:</span></span>  
  
-   <span data-ttu-id="08655-107">Sum</span><span class="sxs-lookup"><span data-stu-id="08655-107">Sum</span></span>  
  
-   <span data-ttu-id="08655-108">Count</span><span class="sxs-lookup"><span data-stu-id="08655-108">Count</span></span>  
  
-   <span data-ttu-id="08655-109">平均值</span><span class="sxs-lookup"><span data-stu-id="08655-109">Average</span></span>  
  
-   <span data-ttu-id="08655-110">最低要求</span><span class="sxs-lookup"><span data-stu-id="08655-110">Minimum</span></span>  
  
-   <span data-ttu-id="08655-111">最大值</span><span class="sxs-lookup"><span data-stu-id="08655-111">Maximum</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08655-112">BAM 实时聚合 (RTA) 功能目前不支持“最小值”和“最大值”度量值。</span><span class="sxs-lookup"><span data-stu-id="08655-112">The BAM Real-time Aggregation (RTA) feature doesn't currently support Minimum and Maximum measures.</span></span> <span data-ttu-id="08655-113">您可以使用这些度量值，但将 Excel 透视表标记为 RTA 时，“最小值”和“最大值”将被忽略。</span><span class="sxs-lookup"><span data-stu-id="08655-113">You can use those measures, but when you mark the Excel pivot table as an RTA, Minimum and Maximum are ignored.</span></span>  
  
### <a name="to-add-new-measures"></a><span data-ttu-id="08655-114">若要添加新度量值</span><span class="sxs-lookup"><span data-stu-id="08655-114">To add new measures</span></span>  
  
1.  <span data-ttu-id="08655-115">在 BAM 视图向导中，单击**下一步**直到你看到**新 BAM 视图： 聚合维度和度量值**页。</span><span class="sxs-lookup"><span data-stu-id="08655-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="08655-116">单击**新度量值**。</span><span class="sxs-lookup"><span data-stu-id="08655-116">Click **New Measures**.</span></span>  
  
2.  <span data-ttu-id="08655-117">键入你的度量值的名称。</span><span class="sxs-lookup"><span data-stu-id="08655-117">Type a name for your measure.</span></span>  
  
3.  <span data-ttu-id="08655-118">从下拉列表中选择**基本数据项**。</span><span class="sxs-lookup"><span data-stu-id="08655-118">From the drop-down list, select the **Base data item**.</span></span>  
  
4.  <span data-ttu-id="08655-119">单击**聚合类型**你想要使用。</span><span class="sxs-lookup"><span data-stu-id="08655-119">Click the **Aggregation type** you want to use.</span></span> <span data-ttu-id="08655-120">可选类型包括：</span><span class="sxs-lookup"><span data-stu-id="08655-120">The choices include:</span></span>  
  
    -   <span data-ttu-id="08655-121">Sum</span><span class="sxs-lookup"><span data-stu-id="08655-121">Sum</span></span>  
  
    -   <span data-ttu-id="08655-122">Count</span><span class="sxs-lookup"><span data-stu-id="08655-122">Count</span></span>  
  
    -   <span data-ttu-id="08655-123">平均值</span><span class="sxs-lookup"><span data-stu-id="08655-123">Average</span></span>  
  
    -   <span data-ttu-id="08655-124">最小值 （不支持 Rta）。</span><span class="sxs-lookup"><span data-stu-id="08655-124">Minimum (not supported for RTAs).</span></span>  
  
    -   <span data-ttu-id="08655-125">最大值（RTA 不支持）</span><span class="sxs-lookup"><span data-stu-id="08655-125">Maximum (not supported for RTAs)</span></span>  
  
5.  <span data-ttu-id="08655-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="08655-126">Click **OK**.</span></span> <span data-ttu-id="08655-127">在你完成添加维度和度量值后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="08655-127">When you finish adding dimensions and measures, click **Next**.</span></span>  
  
6.  <span data-ttu-id="08655-128">上**新 BAM 视图： 摘要**页上，查看有关您的新视图的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="08655-128">On the **New BAM View: Summary** page, review the information regarding your new view, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="08655-129">单击**完成**完成**BAM 视图向导**。</span><span class="sxs-lookup"><span data-stu-id="08655-129">Click **Finish** to complete the **BAM View Wizard**.</span></span>  
  
 <span data-ttu-id="08655-130">将度量值和维度添加到 BAM 视图后，就可以将这些项添加到 Excel 工作簿的透视表中。</span><span class="sxs-lookup"><span data-stu-id="08655-130">If you added measures and dimensions to your BAM view, you can add those items to the PivotTable in the Excel workbook.</span></span> <span data-ttu-id="08655-131">有关创建数据透视表的详细信息，请参阅[如何使用数据透视表](../core/how-to-use-the-pivottable.md)。</span><span class="sxs-lookup"><span data-stu-id="08655-131">For more information about creating a PivotTable, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08655-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08655-132">See Also</span></span>  
 [<span data-ttu-id="08655-133">定义维度</span><span class="sxs-lookup"><span data-stu-id="08655-133">Defining Dimensions</span></span>](../core/defining-dimensions.md)