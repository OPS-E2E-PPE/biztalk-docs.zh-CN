---
title: 定义时间范围和时间切片属性 |Microsoft Docs
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
ms.openlocfilehash: 902d50596185de13792e5d03b0d7e0dbd4238f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352352"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a><span data-ttu-id="f246c-102">定义时间范围和时间切片属性</span><span class="sxs-lookup"><span data-stu-id="f246c-102">Defining the Time Window and Time Slice Properties</span></span>
<span data-ttu-id="f246c-103">管理员用于 TimeWindow 和 TimeSlice 属性 BAMConfiguration.xml 文件中定义数据的生存期在 BAM 主导入数据库中的实时聚合表中。</span><span class="sxs-lookup"><span data-stu-id="f246c-103">Administrators use the TimeWindow and the TimeSlice properties in the BAMConfiguration.xml file to define the life of the data in the real-time aggregation tables in the BAM primary import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f246c-104">若要执行他们所做的更改 BAM 配置文件中，管理员必须取消部署当前 BAM 配置，然后部署已更新的 BAMConfiguration.xml。</span><span class="sxs-lookup"><span data-stu-id="f246c-104">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="f246c-105">有关取消部署 BAM 定义的信息，请参阅[如何删除 BAM 定义](../core/how-to-remove-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="f246c-105">For information about undeploying a BAM definition, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="f246c-106">有关部署 BAM 定义的信息，请参阅[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="f246c-106">For information about deploying a BAM definition, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="f246c-107">如果你想要更改 TimeWindow 和 TimeSlice 值，而取消部署 BAM 基础结构，则可以修改 BAM 主导入数据库中 BAM_Metadata_Activities 表中的列。</span><span class="sxs-lookup"><span data-stu-id="f246c-107">If you want to change the TimeWindow and TimeSlice values without undeploying the BAM infrastructure, you can modifying the columns in the BAM_Metadata_Activities table in the BAM primary import database.</span></span>  
  
## <a name="timeslice"></a><span data-ttu-id="f246c-108">TimeSlice</span><span class="sxs-lookup"><span data-stu-id="f246c-108">TimeSlice</span></span>  
 <span data-ttu-id="f246c-109">使用 TimeSlice 属性对 BAM 实例数据进行分组已完成。</span><span class="sxs-lookup"><span data-stu-id="f246c-109">You use the TimeSlice property to group completed BAM instance data.</span></span> <span data-ttu-id="f246c-110">TimeSlice 属性使用的数据写入 BAM 主导入数据库对 BAM 实例数据进行分组的时间。</span><span class="sxs-lookup"><span data-stu-id="f246c-110">The TimeSlice property uses time that the data is written to the BAM primary import database to group BAM instance data.</span></span>  
  
 <span data-ttu-id="f246c-111">例如，完成并在 1/1/2000 BAM 主导入数据库中保存实例 A 凌晨 1:02</span><span class="sxs-lookup"><span data-stu-id="f246c-111">For example, instance A is completed and persisted in the BAM primary import database at 1/1/2000 1:02 a.m.</span></span> <span data-ttu-id="f246c-112">完成并在 1/1/2000 BAM 主导入数据库中保存的实例 B 凌晨 1:04</span><span class="sxs-lookup"><span data-stu-id="f246c-112">Instance B is completed and persisted in the BAM primary import database at 1/1/2000 1:04 a.m.</span></span> <span data-ttu-id="f246c-113">如果将 TimeSlice 属性的值设置为五分钟，实例 A 和实例 B 组合在一起。</span><span class="sxs-lookup"><span data-stu-id="f246c-113">If you set the value of the TimeSlice property to five minutes, instance A and instance B are grouped together.</span></span>  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a><span data-ttu-id="f246c-114">若要更改 BAM 配置文件中的 TimeSlice 值</span><span class="sxs-lookup"><span data-stu-id="f246c-114">To change the TimeSlice value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="f246c-115">更改 BAM 配置文件的这一行中的值：</span><span class="sxs-lookup"><span data-stu-id="f246c-115">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="f246c-116">若要更改 BAM_Metadata_Activities 表中的 TimeSlice 值</span><span class="sxs-lookup"><span data-stu-id="f246c-116">To change the TimeSlice value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="f246c-117">修改 RTATimeSlice 值，该值在 BAMPrimaryImport 数据库的 bam_Metadata_Activities 表中。</span><span class="sxs-lookup"><span data-stu-id="f246c-117">Modify the RTATimeSlice values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="f246c-118">如果一个或多个活动部署多个实时聚合 (RTA)，必须为每个 RTA 指定不同的时间窗口的选项。</span><span class="sxs-lookup"><span data-stu-id="f246c-118">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f246c-119">RTAWindow 的值必须是整数，时间单位始终为分钟。</span><span class="sxs-lookup"><span data-stu-id="f246c-119">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="timewindow"></a><span data-ttu-id="f246c-120">TimeWindow</span><span class="sxs-lookup"><span data-stu-id="f246c-120">TimeWindow</span></span>  
 <span data-ttu-id="f246c-121">当您运行 CubeUpdate DTS 包时，包将数据从 BAM 主导入数据库移到 BAM 多维数据集中。</span><span class="sxs-lookup"><span data-stu-id="f246c-121">When you run the CubeUpdate DTS package, the package moves data from the BAM primary import database into the BAM cubes.</span></span> <span data-ttu-id="f246c-122">包将移动实时聚合数据，因为 BAM 数据实例毕竟组中的数据的保留时间超过 RTA 时段属性中指定的期限。</span><span class="sxs-lookup"><span data-stu-id="f246c-122">The package moves real-time aggregation data as grouped BAM data instances after all of the data in the group is older than the age specified in the RTA window property.</span></span>  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a><span data-ttu-id="f246c-123">若要更改 BAM 配置文件中的 TimeWindow 值</span><span class="sxs-lookup"><span data-stu-id="f246c-123">To change the TimeWindow value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="f246c-124">更改 BAM 配置文件的这一行中的值：</span><span class="sxs-lookup"><span data-stu-id="f246c-124">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="f246c-125">若要更改 BAM_Metadata_Activities 表中的 TimeWindow 值</span><span class="sxs-lookup"><span data-stu-id="f246c-125">To change the TimeWindow value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="f246c-126">修改 RTAWindow 值，在 BAMPrimaryImport 数据库的 bam_Metadata_Activities 表中。</span><span class="sxs-lookup"><span data-stu-id="f246c-126">Modify the RTAWindow values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="f246c-127">如果一个或多个活动部署多个实时聚合 (RTA)，必须为每个 RTA 指定不同的时间窗口的选项。</span><span class="sxs-lookup"><span data-stu-id="f246c-127">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f246c-128">RTAWindow 的值必须是整数，时间单位始终为分钟。</span><span class="sxs-lookup"><span data-stu-id="f246c-128">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f246c-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f246c-129">See Also</span></span>  
 <span data-ttu-id="f246c-130">[BAM 配置架构](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="f246c-130">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 [<span data-ttu-id="f246c-131">BAM 安全建议</span><span class="sxs-lookup"><span data-stu-id="f246c-131">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)