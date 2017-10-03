---
title: "如何确定 BAM 主导入数据库中的瓶颈 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decf27009eea6aff0ff5ed9088ae49ef2014b1cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a><span data-ttu-id="4f146-102">如何确定 BAM 主导入数据库中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="4f146-102">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>
<span data-ttu-id="4f146-103">若要确定业务活动监视 (BAM) 数据库中的瓶颈，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4f146-103">To identify bottlenecks in the Business Activity Monitoring (BAM) database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="4f146-104">确保活动实例数不再增加。</span><span class="sxs-lookup"><span data-stu-id="4f146-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2.  <span data-ttu-id="4f146-105">确保 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="4f146-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3.  <span data-ttu-id="4f146-106">如果配置 OLAP 分析，确保 BAM_AN_\<activityname > 应按定期间隔运行作业。</span><span class="sxs-lookup"><span data-stu-id="4f146-106">If OLAP Analysis is configured, ensure that the BAM_AN_\<activityname> job is running at periodic intervals.</span></span>  
  
4.  <span data-ttu-id="4f146-107">确保该 BAM_DM_\<activityname > （数据维护） 作业计划以定期间隔运行。</span><span class="sxs-lookup"><span data-stu-id="4f146-107">Ensure that BAM_DM_\<activityname> (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f146-108">在高使用率方案 BAM 数据库活动可能会影响其他 BizTalk Server 数据库，这将影响整体 BizTalk Server 性能的性能。</span><span class="sxs-lookup"><span data-stu-id="4f146-108">In high usage scenarios BAM database activity can impact the performance of other BizTalk Server databases, which will affect overall BizTalk Server performance.</span></span> <span data-ttu-id="4f146-109">在这种情况下，请考虑采取以下措施：</span><span class="sxs-lookup"><span data-stu-id="4f146-109">In this case consider taking the following actions:</span></span>  
    >   
    >  -   <span data-ttu-id="4f146-110">请考虑减少不再是默认值 （6 个月） 的所有 BAM 活动的持续时间为 1 个月或更少。</span><span class="sxs-lookup"><span data-stu-id="4f146-110">Consider decreasing the duration of all BAM activities from the default value (6 months) to 1 month or less.</span></span> <span data-ttu-id="4f146-111">这将减少为其 BAM 数据会保持在 BAMPrimaryImport 数据库在存档之前的时间段。</span><span class="sxs-lookup"><span data-stu-id="4f146-111">This will reduce the time period for which BAM data is maintained in the BAMPrimaryImport database before being archived.</span></span> <span data-ttu-id="4f146-112">使用 BAM 管理实用程序`set-activitywindow`命令来修改 BAM 活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4f146-112">Use the BAM Management Utility `set-activitywindow` command to modify the duration of BAM activities.</span></span> <span data-ttu-id="4f146-113">BAM 管理实用程序的活动管理有关的详细信息请参阅命令[活动管理命令](http://go.microsoft.com/fwlink/?LinkId=210417)(http://go.microsoft.com/fwlink/?LinkId=210417)。</span><span class="sxs-lookup"><span data-stu-id="4f146-113">For more information about the BAM Management Utility activity management commands see [Activity Management Commands](http://go.microsoft.com/fwlink/?LinkId=210417) (http://go.microsoft.com/fwlink/?LinkId=210417).</span></span>  
    > -   <span data-ttu-id="4f146-114">将 BAM 存档数据库移到未承载任何 BizTalk MessageBox 数据库的 SQL Server 的实例。</span><span class="sxs-lookup"><span data-stu-id="4f146-114">Move the BAM Archive database to an instance of SQL Server that does not host any BizTalk MessageBox databases.</span></span> <span data-ttu-id="4f146-115">这将防止这些数据库争用资源，并改进整体性能。</span><span class="sxs-lookup"><span data-stu-id="4f146-115">This will prevent these databases from competing for resources and improve overall performance.</span></span>  
  
5.  <span data-ttu-id="4f146-116">使用专用的主机，对其进行跟踪和度量值负载下的主机 Queue Length 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="4f146-116">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6.  <span data-ttu-id="4f146-117">随着时间的推移检查上升趋势的假脱机表大小性能计数器。</span><span class="sxs-lookup"><span data-stu-id="4f146-117">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7.  <span data-ttu-id="4f146-118">检查长执行时间的存档/清除作业执行持续时间。</span><span class="sxs-lookup"><span data-stu-id="4f146-118">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8.  <span data-ttu-id="4f146-119">检查磁盘响应能力 （读/写性能计数器每次磁盘） 上承载 BizTalk 跟踪数据库的磁盘。</span><span class="sxs-lookup"><span data-stu-id="4f146-119">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f146-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f146-120">See Also</span></span>  
 [<span data-ttu-id="4f146-121">数据库层中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="4f146-121">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)