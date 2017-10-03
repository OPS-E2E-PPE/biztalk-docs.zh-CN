---
title: "将主导入数据库数据存档 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0fdfd55681fabd1b6cfc72f68b7e33150a121f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="archiving-primary-import-database-data"></a><span data-ttu-id="2d0d8-102">将主导入数据库数据存档</span><span class="sxs-lookup"><span data-stu-id="2d0d8-102">Archiving Primary Import Database Data</span></span>
<span data-ttu-id="2d0d8-103">管理员可以指定存档主导入数据库中的活动实例数据的时段。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-103">An administrator can specify the time window for archiving activity instance data in the primary import database.</span></span> <span data-ttu-id="2d0d8-104">您可以在 BAMPrimaryImport 数据库的 BAM_Metadata_Activities 表中使用 OnlineWindowTimeUnit 和 OnlineWindowTimeLength 属性。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-104">You use the OnlineWindowTimeUnit and OnlineWindowTimeLength properties in the BAM_Metadata_Activities table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="2d0d8-105">如果业务用户已部署了多个活动，则可为每个活动指定不同时段。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-105">If business users have deployed multiple activities, you can specify a different time window for each activity.</span></span> <span data-ttu-id="2d0d8-106">有关部署活动的信息，请参阅"定义业务活动"中*信息工作者用户指南*。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-106">For information about deploying activities, see "Defining a Business Activity" in *Information Workers Users Guide*.</span></span>  
  
 <span data-ttu-id="2d0d8-107">下表说明了可用于 OnlineWindowTimeUnit 和 OnlineWindowTimeLength 的值。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-107">The following table describes the values you can use for OnlineWindowTimeUnit and OnlineWindowTimeLength.</span></span>  
  
|<span data-ttu-id="2d0d8-108">属性</span><span class="sxs-lookup"><span data-stu-id="2d0d8-108">Property</span></span>|<span data-ttu-id="2d0d8-109">值</span><span class="sxs-lookup"><span data-stu-id="2d0d8-109">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="2d0d8-110">OnlineWindowTimeUnit</span><span class="sxs-lookup"><span data-stu-id="2d0d8-110">OnlineWindowTimeUnit</span></span>|<span data-ttu-id="2d0d8-111">此属性可以是： 月、 日、 小时或分钟。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-111">This property can be: month, day, hour, or minute.</span></span> <span data-ttu-id="2d0d8-112">此属性的默认值为“月”。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-112">The default value of this property is month.</span></span>|  
|<span data-ttu-id="2d0d8-113">OnlineWindowTimeLength</span><span class="sxs-lookup"><span data-stu-id="2d0d8-113">OnlineWindowTimeLength</span></span>|<span data-ttu-id="2d0d8-114">此属性必须为整数。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-114">This property must be an integer.</span></span> <span data-ttu-id="2d0d8-115">此属性的默认值为 6。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-115">The default value of this property is 6.</span></span>|  
  
 <span data-ttu-id="2d0d8-116">当分区为早于联机窗口 （当前时间-OnlineWindowTimeLength OnlineWindowTimeUnit） 时，BAM 按分区，移动数据从 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-116">BAM moves data out of the BAM primary import database by partition, when the partition is older than the online window (current time - OnlineWindowTimeLength of OnlineWindowTimeUnit).</span></span> <span data-ttu-id="2d0d8-117">例如，对于 OnlineWindowTimeLength = 5 和 OnlineWindowTimeUnit 不是删除 5 天 = 日，较旧的分区。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-117">For example, for OnlineWindowTimeLength = 5 and OnlineWindowTimeUnit = day, partitions older than 5 days are removed.</span></span>  
  
 <span data-ttu-id="2d0d8-118">BAM 将存档的活动实例数据移动到 BAM 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-118">BAM moves archived activity instance data into the BAM archiving database.</span></span> <span data-ttu-id="2d0d8-119">指定 BAM 数据库存档在 BizTalk BAM 配置过程。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-119">You specify the BAM archiving database during BizTalk BAM Configuration.</span></span> <span data-ttu-id="2d0d8-120">有关 BizTalk BAM 配置的信息，请参阅[BAM 配置架构](../core/bam-configuration-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-120">For information about BizTalk BAM configuration, see [BAM Configuration Schema](../core/bam-configuration-schema.md).</span></span>  
  
 <span data-ttu-id="2d0d8-121">BAM 将存档活动实例数据，如果你尚未运行 BAM 多维数据集更新到活动多维数据集处理实例数据的数据转换服务 (DTS) 包。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-121">BAM will not archive activity instance data if you have not run the BAM cube update Data Transformation Services (DTS) package, which processes the instance data into the activity cube.</span></span>  
  
 <span data-ttu-id="2d0d8-122">有关运行 BAM 数据维护 DTS 包的信息，请参阅[BAM DTS 包](../core/bam-dts-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-122">For information about running the BAM data maintenance DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
 <span data-ttu-id="2d0d8-123">随着时间的推移，BAMArchive 数据库的大小会随着活动实例数据的添加而增大。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-123">Over time the BAMArchive database will grow in size as activity instance data is added.</span></span> <span data-ttu-id="2d0d8-124">尽管没有简便的方法来截断整个数据库，但可以定期截断数据库事务日志以减少存储需求，也可以定期备份和存档整个 BAMArchive 数据库。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-124">Although there is no straightforward way to truncate an entire database, you can periodically truncate the database transaction log to reduce the storage requirements, and you can periodically back up and archive the entire BAMArchive database.</span></span> <span data-ttu-id="2d0d8-125">有关详细信息，请参阅 SQL Server 联机丛书中的“截断事务日志”。</span><span class="sxs-lookup"><span data-stu-id="2d0d8-125">See “Truncating the transaction log” in SQL Server Books Online for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d0d8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d0d8-126">See Also</span></span>  
 <span data-ttu-id="2d0d8-127">[定义时间窗口中，然后时间切片属性](../core/defining-the-time-window-and-time-slice-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2d0d8-127">[Defining the Time Window and Time Slice Properties](../core/defining-the-time-window-and-time-slice-properties.md) </span></span>  
 [<span data-ttu-id="2d0d8-128">管理 BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="2d0d8-128">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)