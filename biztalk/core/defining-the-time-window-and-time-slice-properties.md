---
title: 定义时间窗口中，然后时间切片属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- managing [BAM], real-time data
- Primary Import database [BAM], time properties
- aggregations [BAM], managing
- Primary Import database [BAM], real-time data
- BAMConfiguration.xml file
- aggregations [BAM], real-time data
ms.assetid: 7f07b179-da10-4702-baf7-69516c8f16a6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d846b03866196e0a31facbbff68db50ec6a00a5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239053"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a><span data-ttu-id="13c28-102">定义时间窗口中，然后时间切片属性</span><span class="sxs-lookup"><span data-stu-id="13c28-102">Defining the Time Window and Time Slice Properties</span></span>
<span data-ttu-id="13c28-103">管理员可以使用 BAMConfiguration.xml 文件的 TimeWindow 属性和 TimeSlice 属性定义 BAM 主导入数据库的实时聚合表中数据的寿命。</span><span class="sxs-lookup"><span data-stu-id="13c28-103">Administrators use the TimeWindow and the TimeSlice properties in the BAMConfiguration.xml file to define the life of the data in the real-time aggregation tables in the BAM primary import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c28-104">若要使自己在 BAM 配置文件中所做的更改生效，管理员必须先取消部署当前 BAM 配置，然后部署已更新的 BAMConfiguration.xml。</span><span class="sxs-lookup"><span data-stu-id="13c28-104">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="13c28-105">有关取消部署的 BAM 定义的信息，请参阅[如何删除 BAM 定义](../core/how-to-remove-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="13c28-105">For information about undeploying a BAM definition, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="13c28-106">有关部署的 BAM 定义的信息，请参阅[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="13c28-106">For information about deploying a BAM definition, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="13c28-107">如果要更改 TimeWindow 和 TimeSlice 值，而不取消部署 BAM 基础结构，则需要修改 BAM 主导入数据库的 BAM_Metadata_Activities 表中的列。</span><span class="sxs-lookup"><span data-stu-id="13c28-107">If you want to change the TimeWindow and TimeSlice values without undeploying the BAM infrastructure, you can modifying the columns in the BAM_Metadata_Activities table in the BAM primary import database.</span></span>  
  
## <a name="timeslice"></a><span data-ttu-id="13c28-108">TimeSlice</span><span class="sxs-lookup"><span data-stu-id="13c28-108">TimeSlice</span></span>  
 <span data-ttu-id="13c28-109">可以使用 TimeSlice 属性对已完成的 BAM 实例数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="13c28-109">You use the TimeSlice property to group completed BAM instance data.</span></span> <span data-ttu-id="13c28-110">TimeSlice 属性按照数据写入 BAM 主导入数据库的时间对 BAM 实例数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="13c28-110">The TimeSlice property uses time that the data is written to the BAM primary import database to group BAM instance data.</span></span>  
  
 <span data-ttu-id="13c28-111">例如，完成并在 1/1/2000 BAM 主导入数据库中持久保存实例 A 凌晨 1:02</span><span class="sxs-lookup"><span data-stu-id="13c28-111">For example, instance A is completed and persisted in the BAM primary import database at 1/1/2000 1:02 a.m.</span></span> <span data-ttu-id="13c28-112">实例 B 处于已完成并在 1/1/2000 BAM 主导入数据库中保留凌晨 1:04</span><span class="sxs-lookup"><span data-stu-id="13c28-112">Instance B is completed and persisted in the BAM primary import database at 1/1/2000 1:04 a.m.</span></span> <span data-ttu-id="13c28-113">如果你将设置五分钟时间间隔属性的值，实例 A 和实例 B 被组合在一起。</span><span class="sxs-lookup"><span data-stu-id="13c28-113">If you set the value of the TimeSlice property to five minutes, instance A and instance B are grouped together.</span></span>  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a><span data-ttu-id="13c28-114">更改 BAM 配置文件中的 TimeSlice 值</span><span class="sxs-lookup"><span data-stu-id="13c28-114">To change the TimeSlice value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="13c28-115">更改 BAM 配置文件的下列一行中的值：</span><span class="sxs-lookup"><span data-stu-id="13c28-115">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="13c28-116">更改 BAM_Metadata_Activities 表中的 TimeSlice 值</span><span class="sxs-lookup"><span data-stu-id="13c28-116">To change the TimeSlice value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="13c28-117">修改 RTATimeSlice 值，该值位于 BAM 主导入数据库的 bam_Metadata_Activities 表中。</span><span class="sxs-lookup"><span data-stu-id="13c28-117">Modify the RTATimeSlice values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="13c28-118">如果为一个或多个活动部署多个实时聚合 (RTA)，则可以选择为每个 RTA 指定不同的时段。</span><span class="sxs-lookup"><span data-stu-id="13c28-118">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13c28-119">RTAWindow 的值必须为整数，且时间单位始终为分钟。</span><span class="sxs-lookup"><span data-stu-id="13c28-119">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="timewindow"></a><span data-ttu-id="13c28-120">TimeWindow</span><span class="sxs-lookup"><span data-stu-id="13c28-120">TimeWindow</span></span>  
 <span data-ttu-id="13c28-121">运行 CubeUpdate DTS 包时，该程序包将数据从 BAM 主导入数据库移至 BAM 多维数据集中。</span><span class="sxs-lookup"><span data-stu-id="13c28-121">When you run the CubeUpdate DTS package, the package moves data from the BAM primary import database into the BAM cubes.</span></span> <span data-ttu-id="13c28-122">在 BAM 数据实例组中所有实时聚合数据都超过 RTA 时段属性中指定的期限后，该程序包就会以组的形式移动这些数据。</span><span class="sxs-lookup"><span data-stu-id="13c28-122">The package moves real-time aggregation data as grouped BAM data instances after all of the data in the group is older than the age specified in the RTA window property.</span></span>  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a><span data-ttu-id="13c28-123">更改 BAM 配置文件中的 TimeWindow 值</span><span class="sxs-lookup"><span data-stu-id="13c28-123">To change the TimeWindow value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="13c28-124">更改 BAM 配置文件的下列一行中的值：</span><span class="sxs-lookup"><span data-stu-id="13c28-124">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="13c28-125">更改 BAM_Metadata_Activities 表中的 TimeWindow 值</span><span class="sxs-lookup"><span data-stu-id="13c28-125">To change the TimeWindow value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="13c28-126">修改 RTAWindow 值，该值位于 BAM 主导入数据库的 bam_Metadata_Activities 表中。</span><span class="sxs-lookup"><span data-stu-id="13c28-126">Modify the RTAWindow values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="13c28-127">如果为一个或多个活动部署多个实时聚合 (RTA)，则可以选择为每个 RTA 指定不同的时段。</span><span class="sxs-lookup"><span data-stu-id="13c28-127">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13c28-128">RTAWindow 的值必须为整数，且时间单位始终为分钟。</span><span class="sxs-lookup"><span data-stu-id="13c28-128">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c28-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13c28-129">See Also</span></span>  
 <span data-ttu-id="13c28-130">[BAM 配置架构](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="13c28-130">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 [<span data-ttu-id="13c28-131">BAM 安全建议</span><span class="sxs-lookup"><span data-stu-id="13c28-131">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)