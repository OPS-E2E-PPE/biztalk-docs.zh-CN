---
title: "BAM 定义概述 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definitions [BAM], observation models
- definitions [BAM], about BAM definitions
- definitions [BAM]
ms.assetid: 1ba1f45e-85fe-492f-8a2e-98bf3570c633
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cbc600f66be7167aabb4cf0273cb1c0bda78973
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-bam-definition"></a><span data-ttu-id="0c43e-103">BAM 定义概述</span><span class="sxs-lookup"><span data-stu-id="0c43e-103">What Is a BAM Definition?</span></span>
<span data-ttu-id="0c43e-104">BAM 定义是 BAM 观察模型的 XML 表示形式，它是要监视的业务流程的高级定义。</span><span class="sxs-lookup"><span data-stu-id="0c43e-104">A BAM definition is an XML representation of a BAM observation model, which is a high-level definition a business process that you want to monitor.</span></span> <span data-ttu-id="0c43e-105">观察模型的主要部分（即 BAM 定义）包括里程碑和要收集的数据事件（BAM 活动）、所有数据聚合的说明，以及如何向用户显示信息（BAM 视图）。</span><span class="sxs-lookup"><span data-stu-id="0c43e-105">The main parts of the observation model, and therefore the BAM definition, are the milestone and data events to collect (the BAM activity); a description of any data aggregations; and how to present the information to users (the BAM view).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c43e-106">还可以手动创建遵循 BAM 架构的 XML 文件，但不建议以这种方式创建 BAM 定义，因为此方式不能提供经过验证的定义。</span><span class="sxs-lookup"><span data-stu-id="0c43e-106">You can also manually create an XML file that follows the BAM schema, but this is not a recommended way to create the BAM definition as it does not provide a definition that has been validated.</span></span>  
  
 <span data-ttu-id="0c43e-107">BAM 定义可以包含以下项：</span><span class="sxs-lookup"><span data-stu-id="0c43e-107">BAM definitions can contain the following items:</span></span>  
  
-   <span data-ttu-id="0c43e-108">业务活动 - 有效的 BAM 定义必须包含业务活动（也称为 BAM 活动）。</span><span class="sxs-lookup"><span data-stu-id="0c43e-108">Business activities - A valid BAM definition must contain a business activity (also referred to as a BAM activity).</span></span> <span data-ttu-id="0c43e-109">定义中的所有其他项都是可选的。</span><span class="sxs-lookup"><span data-stu-id="0c43e-109">All other items in the definition are optional.</span></span> <span data-ttu-id="0c43e-110">有关将业务活动添加到定义的信息，请参阅[如何定义业务活动](../core/how-to-define-a-business-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="0c43e-110">For information about adding a business activity to a definition, see [How to Define a Business Activity](../core/how-to-define-a-business-activity.md).</span></span>  
  
-   <span data-ttu-id="0c43e-111">视图 – 视图定义了可访问业务活动所定义数据的一组用户 。</span><span class="sxs-lookup"><span data-stu-id="0c43e-111">Views – Views define the set of users that can access the data defined by the business activity.</span></span> <span data-ttu-id="0c43e-112">视图包括筛选出的数据、所筛选数据的聚合，以及显示所筛选数据的方式（如数据透视图）。</span><span class="sxs-lookup"><span data-stu-id="0c43e-112">Views consist of filtered data, aggregations of the filtered data, and ways of presenting the filtered data, such as a PivotChart report.</span></span> <span data-ttu-id="0c43e-113">BAM 支持为每个活动定义一个或多个视图。</span><span class="sxs-lookup"><span data-stu-id="0c43e-113">BAM supports the definition of one or more views per activity.</span></span>  
  
     <span data-ttu-id="0c43e-114">可以在视图中定义以下业务流程：</span><span class="sxs-lookup"><span data-stu-id="0c43e-114">In a view you can define the following business processes:</span></span>  
  
    -   <span data-ttu-id="0c43e-115">具有别名的业务数据 - 使用别名能够将友好名称应用于数据项。</span><span class="sxs-lookup"><span data-stu-id="0c43e-115">Aliased business data - Aliasing allows you to apply friendly names to data items.</span></span> <span data-ttu-id="0c43e-116">例如，开发人员可能定义了一个名为“LName”的数据项。</span><span class="sxs-lookup"><span data-stu-id="0c43e-116">For example, a developer may define a data item called “LName.”</span></span> <span data-ttu-id="0c43e-117">您可以创建一个别名，以便在查看 BAM 实时数据时“LName”显示为“Last Name”。</span><span class="sxs-lookup"><span data-stu-id="0c43e-117">You can create an alias so that the “LName” is displayed as “Last Name” when viewing the BAM live data.</span></span>  <span data-ttu-id="0c43e-118">有关别名的详细信息，请参阅[如何重命名视图项](../core/how-to-rename-view-items.md)。</span><span class="sxs-lookup"><span data-stu-id="0c43e-118">For more information about aliasing, see [How to Rename View Items](../core/how-to-rename-view-items.md).</span></span>  
  
    -   <span data-ttu-id="0c43e-119">持续时间 - 监视活动的时间段。</span><span class="sxs-lookup"><span data-stu-id="0c43e-119">Duration - The time period over which the activity is monitored.</span></span>  
  
    -   <span data-ttu-id="0c43e-120">里程碑组 - 业务里程碑的集合。</span><span class="sxs-lookup"><span data-stu-id="0c43e-120">Milestone groups - Sets of business milestones.</span></span> <span data-ttu-id="0c43e-121">可以将组用作一段持续时间中的开始业务里程碑或结束业务里程碑。</span><span class="sxs-lookup"><span data-stu-id="0c43e-121">You can use a group as either the starting or ending business milestone of a duration.</span></span>  
  
    -   <span data-ttu-id="0c43e-122">聚合 - 可以是实时聚合 (RTA)，也可以是计划聚合（也称为联机分析处理 (OLAP)）。它包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="0c43e-122">Aggregations -  These can be either real-time aggregations (RTAs) or scheduled aggregations (also referred to as online analytical processing (OLAP)), and consist of the following items:</span></span>  
  
-   <span data-ttu-id="0c43e-123">度量值 - Analysis Services (OLAP) 多维数据集中的一组数值，这些数值基于此多维数据集的事实表中的一列。</span><span class="sxs-lookup"><span data-stu-id="0c43e-123">Measures - A set of numeric values in an Analysis Services (OLAP) cube based on a column in the fact table of the cube.</span></span>  
  
-   <span data-ttu-id="0c43e-124">进度维度 - 表示对仍在进行的活动的进度创建聚合的过程。</span><span class="sxs-lookup"><span data-stu-id="0c43e-124">Progress dimension - Represents the creation of aggregations with respect to the progress of activities that are still in process.</span></span>  
  
-   <span data-ttu-id="0c43e-125">数据维度 - 用于对聚合进行分类。</span><span class="sxs-lookup"><span data-stu-id="0c43e-125">Data dimension - Used to categorize an aggregation.</span></span> <span data-ttu-id="0c43e-126">数据维度基于 BAM 活动中格式化的字符串数据项的值。</span><span class="sxs-lookup"><span data-stu-id="0c43e-126">Data dimensions are based on the value of string formatted data items in the BAM activity.</span></span>  
  
-   <span data-ttu-id="0c43e-127">时间维度 - 用于为已定义的时间段创建聚合。</span><span class="sxs-lookup"><span data-stu-id="0c43e-127">Time dimension - Used to create aggregations across defined time segments.</span></span>  
  
-   <span data-ttu-id="0c43e-128">数值范围维度 - 用于根据给定数值范围的友好名称对聚合进行分类。</span><span class="sxs-lookup"><span data-stu-id="0c43e-128">Numeric range dimension - Used to categorize aggregations based on friendly names of given numeric ranges.</span></span>  
  
 <span data-ttu-id="0c43e-129">BAM 定义可以包含在视图中定义的警报定义。</span><span class="sxs-lookup"><span data-stu-id="0c43e-129">BAM definitions can contain alert definitions that are defined in the views.</span></span> <span data-ttu-id="0c43e-130">BAM 定义还可以包含数据透视表布局。</span><span class="sxs-lookup"><span data-stu-id="0c43e-130">BAM definitions can also contain PivotTable layouts.</span></span> <span data-ttu-id="0c43e-131">部署了 BAM 定义后，数据透视表将包含可使用 Excel 实时数据工作簿或通过 BAM 门户查看的实时业务数据。</span><span class="sxs-lookup"><span data-stu-id="0c43e-131">Once the BAM definition is deployed, the PivotTable reports containing the live business data that can be viewed using the Excel livedata workbook or through the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c43e-132">创建使用用于 Excel BAM 外接 BAM 定义不能包含警报。</span><span class="sxs-lookup"><span data-stu-id="0c43e-132">BAM definitions created using the BAM Add-in for Excel cannot contain alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c43e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c43e-133">See Also</span></span>  
 <span data-ttu-id="0c43e-134">[在 Excel 中定义的业务活动和视图](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0c43e-134">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 <span data-ttu-id="0c43e-135">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="0c43e-135">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="0c43e-136">BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="0c43e-136">BAM Dynamic Infrastructure</span></span>](../core/bam-dynamic-infrastructure.md)