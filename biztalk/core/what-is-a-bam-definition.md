---
title: BAM 定义概述 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], observation models
- definitions [BAM], about BAM definitions
- definitions [BAM]
ms.assetid: 1ba1f45e-85fe-492f-8a2e-98bf3570c633
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89366ff3d55edd41719fe6465be6a7d918617b2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302289"
---
# <a name="what-is-a-bam-definition"></a><span data-ttu-id="1035f-103">BAM 定义概述</span><span class="sxs-lookup"><span data-stu-id="1035f-103">What Is a BAM Definition?</span></span>
<span data-ttu-id="1035f-104">BAM 定义是 BAM 观察模型，这是你想要监视的业务流程的高级定义的 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="1035f-104">A BAM definition is an XML representation of a BAM observation model, which is a high-level definition a business process that you want to monitor.</span></span> <span data-ttu-id="1035f-105">观察模型，并因此 BAM 定义的主要组成部分是里程碑和数据要收集事件 （BAM 活动）;任何数据聚合; 的说明以及如何向用户 （BAM 视图） 显示信息。</span><span class="sxs-lookup"><span data-stu-id="1035f-105">The main parts of the observation model, and therefore the BAM definition, are the milestone and data events to collect (the BAM activity); a description of any data aggregations; and how to present the information to users (the BAM view).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1035f-106">您可以手动创建遵循 BAM 架构的 XML 文件，但这不是建议的方法是创建 BAM 定义，因为它不提供已验证的定义。</span><span class="sxs-lookup"><span data-stu-id="1035f-106">You can also manually create an XML file that follows the BAM schema, but this is not a recommended way to create the BAM definition as it does not provide a definition that has been validated.</span></span>  
  
 <span data-ttu-id="1035f-107">BAM 定义可以包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="1035f-107">BAM definitions can contain the following items:</span></span>  
  
- <span data-ttu-id="1035f-108">业务活动-有效的 BAM 定义必须包含业务活动 （也称为 BAM 活动）。</span><span class="sxs-lookup"><span data-stu-id="1035f-108">Business activities - A valid BAM definition must contain a business activity (also referred to as a BAM activity).</span></span> <span data-ttu-id="1035f-109">在定义中的所有其他项是可选的。</span><span class="sxs-lookup"><span data-stu-id="1035f-109">All other items in the definition are optional.</span></span> <span data-ttu-id="1035f-110">有关向定义中添加业务活动的信息，请参阅[如何定义业务活动](../core/how-to-define-a-business-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="1035f-110">For information about adding a business activity to a definition, see [How to Define a Business Activity](../core/how-to-define-a-business-activity.md).</span></span>  
  
- <span data-ttu-id="1035f-111">视图 – 视图定义的用户可以访问业务活动定义的数据集。</span><span class="sxs-lookup"><span data-stu-id="1035f-111">Views – Views define the set of users that can access the data defined by the business activity.</span></span> <span data-ttu-id="1035f-112">视图包含已筛选数据，聚合的已筛选的数据，并显示所筛选的数据，如数据透视图报表的方式。</span><span class="sxs-lookup"><span data-stu-id="1035f-112">Views consist of filtered data, aggregations of the filtered data, and ways of presenting the filtered data, such as a PivotChart report.</span></span> <span data-ttu-id="1035f-113">BAM 支持每个活动的一个或多个视图的定义。</span><span class="sxs-lookup"><span data-stu-id="1035f-113">BAM supports the definition of one or more views per activity.</span></span>  
  
   <span data-ttu-id="1035f-114">在视图中可以定义以下业务流程：</span><span class="sxs-lookup"><span data-stu-id="1035f-114">In a view you can define the following business processes:</span></span>  
  
  -   <span data-ttu-id="1035f-115">使用别名的业务数据的别名，可将友好名称应用于数据项。</span><span class="sxs-lookup"><span data-stu-id="1035f-115">Aliased business data - Aliasing allows you to apply friendly names to data items.</span></span> <span data-ttu-id="1035f-116">例如，开发人员可能定义数据项名为"LName"。</span><span class="sxs-lookup"><span data-stu-id="1035f-116">For example, a developer may define a data item called “LName.”</span></span> <span data-ttu-id="1035f-117">您可以创建一个别名，以便"LName"显示为"Last Name"时查看 BAM 实时数据。</span><span class="sxs-lookup"><span data-stu-id="1035f-117">You can create an alias so that the “LName” is displayed as “Last Name” when viewing the BAM live data.</span></span>  <span data-ttu-id="1035f-118">有关使用别名的详细信息，请参阅[如何重命名视图项](../core/how-to-rename-view-items.md)。</span><span class="sxs-lookup"><span data-stu-id="1035f-118">For more information about aliasing, see [How to Rename View Items](../core/how-to-rename-view-items.md).</span></span>  
  
  -   <span data-ttu-id="1035f-119">持续时间-对其监视活动的时间段。</span><span class="sxs-lookup"><span data-stu-id="1035f-119">Duration - The time period over which the activity is monitored.</span></span>  
  
  -   <span data-ttu-id="1035f-120">里程碑组-业务里程碑的。</span><span class="sxs-lookup"><span data-stu-id="1035f-120">Milestone groups - Sets of business milestones.</span></span> <span data-ttu-id="1035f-121">可以使用组作为开始业务里程碑或结束业务里程碑的持续时间。</span><span class="sxs-lookup"><span data-stu-id="1035f-121">You can use a group as either the starting or ending business milestone of a duration.</span></span>  
  
  -   <span data-ttu-id="1035f-122">聚合-这些可以是实时聚合 (Rta) 或计划的聚合 （也称为联机分析处理 (OLAP)），并包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="1035f-122">Aggregations -  These can be either real-time aggregations (RTAs) or scheduled aggregations (also referred to as online analytical processing (OLAP)), and consist of the following items:</span></span>  
  
- <span data-ttu-id="1035f-123">度量值的一系列数值中基于多维数据集的事实数据表中的列的 Analysis Services (OLAP) 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="1035f-123">Measures - A set of numeric values in an Analysis Services (OLAP) cube based on a column in the fact table of the cube.</span></span>  
  
- <span data-ttu-id="1035f-124">进度维度-表示创建的活动的过程中仍在聚合的进度。</span><span class="sxs-lookup"><span data-stu-id="1035f-124">Progress dimension - Represents the creation of aggregations with respect to the progress of activities that are still in process.</span></span>  
  
- <span data-ttu-id="1035f-125">数据维度-用于对聚合进行分类。</span><span class="sxs-lookup"><span data-stu-id="1035f-125">Data dimension - Used to categorize an aggregation.</span></span> <span data-ttu-id="1035f-126">数据维度基于 BAM 活动中的字符串的格式化数据项目的值。</span><span class="sxs-lookup"><span data-stu-id="1035f-126">Data dimensions are based on the value of string formatted data items in the BAM activity.</span></span>  
  
- <span data-ttu-id="1035f-127">时间维度-用于在定义的时间段创建聚合。</span><span class="sxs-lookup"><span data-stu-id="1035f-127">Time dimension - Used to create aggregations across defined time segments.</span></span>  
  
- <span data-ttu-id="1035f-128">数值范围维度-用于对基于的友好名称的聚合进行分类给定数值范围。</span><span class="sxs-lookup"><span data-stu-id="1035f-128">Numeric range dimension - Used to categorize aggregations based on friendly names of given numeric ranges.</span></span>  
  
  <span data-ttu-id="1035f-129">BAM 定义可以包含在视图中定义的警报定义。</span><span class="sxs-lookup"><span data-stu-id="1035f-129">BAM definitions can contain alert definitions that are defined in the views.</span></span> <span data-ttu-id="1035f-130">BAM 定义还可以包含数据透视表布局。</span><span class="sxs-lookup"><span data-stu-id="1035f-130">BAM definitions can also contain PivotTable layouts.</span></span> <span data-ttu-id="1035f-131">部署 BAM 定义，其中包含可以使用 Excel 实时数据工作簿查看实时业务数据的数据透视表报表后或通过 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="1035f-131">Once the BAM definition is deployed, the PivotTable reports containing the live business data that can be viewed using the Excel livedata workbook or through the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1035f-132">创建使用 Excel BAM 外接程序的 BAM 定义不能包含警报。</span><span class="sxs-lookup"><span data-stu-id="1035f-132">BAM definitions created using the BAM Add-in for Excel cannot contain alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1035f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="1035f-133">See Also</span></span>  
 <span data-ttu-id="1035f-134">[在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="1035f-134">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 <span data-ttu-id="1035f-135">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="1035f-135">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="1035f-136">BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="1035f-136">BAM Dynamic Infrastructure</span></span>](../core/bam-dynamic-infrastructure.md)