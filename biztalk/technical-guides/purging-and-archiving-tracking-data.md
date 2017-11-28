---
title: "清除和存档跟踪数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a2560bc8a57a8f60bf2d1ebcddf68b62fd178a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="purging-and-archiving-tracking-data"></a><span data-ttu-id="e3798-102">清除和存档跟踪数据</span><span class="sxs-lookup"><span data-stu-id="e3798-102">Purging and Archiving Tracking Data</span></span>
<span data-ttu-id="e3798-103">务必要配置并启用 DTA 清除和存档 SQL 代理作业。</span><span class="sxs-lookup"><span data-stu-id="e3798-103">It is important to configure and enable the DTA Purge and Archive SQL Agent job.</span></span> <span data-ttu-id="e3798-104">此作业存档，并从 BizTalk 跟踪 (DTA) 数据库中清除旧数据。</span><span class="sxs-lookup"><span data-stu-id="e3798-104">This job archives and purges old data from the BizTalk Tracking (DTA) database.</span></span> <span data-ttu-id="e3798-105">这是必需的正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="e3798-105">This is essential for a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="e3798-106">大型的跟踪数据库将开始对跟踪主机和任何其他进程的性能影响该查询跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="e3798-106">A large Tracking database will begin to affect the performance of the tracking host and any other processes that query the Tracking database.</span></span> <span data-ttu-id="e3798-107">如果跟踪数据不会清除从跟踪数据库，数据库将继续增长。</span><span class="sxs-lookup"><span data-stu-id="e3798-107">If the tracking data is not purged from the Tracking database, the database will continue to grow.</span></span>  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a><span data-ttu-id="e3798-108">使用 DTA 的指导原则清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="e3798-108">Guidelines for Using the DTA Purge and Archive Job</span></span>  
  
-   <span data-ttu-id="e3798-109">**确保 DTA 清除和存档 SQL 代理作业正确配置和启用，并且已成功完成。**</span><span class="sxs-lookup"><span data-stu-id="e3798-109">**Ensure that the DTA Purge and Archive SQL Agent job is properly configured, enabled, and successfully completing.**</span></span>  
  
     <span data-ttu-id="e3798-110">默认情况下不启用此作业，因为你必须首先将其配置为包括可以在其中写入存档文件的目录。</span><span class="sxs-lookup"><span data-stu-id="e3798-110">This job is not enabled by default because you must first configure it to include a directory where the archive files can be written.</span></span>  
  
-   <span data-ttu-id="e3798-111">**如果你只需以清除旧数据并不需要将其存档在第一次，然后更改 SQL 代理作业调用存储的过程"dtasp_PurgeTrackingDatabase"。**</span><span class="sxs-lookup"><span data-stu-id="e3798-111">**If you only need to purge the old data and do not need to archive it first, then change the SQL Agent job to call the stored procedure “dtasp_PurgeTrackingDatabase”.**</span></span>  
  
     <span data-ttu-id="e3798-112">这跳过存档步骤中，并只是执行清除。</span><span class="sxs-lookup"><span data-stu-id="e3798-112">This skips the archive step, and just does the purge.</span></span> <span data-ttu-id="e3798-113">有关详细信息，有关此存储的过程和更改 SQL 代理作业以使用它，请参阅["如何清除数据从 BizTalk 跟踪数据库的"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。</span><span class="sxs-lookup"><span data-stu-id="e3798-113">For more information about this stored procedure and changing the SQL Agent job to use it, see ["How to Purge Data from the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817).</span></span>  
  
-   <span data-ttu-id="e3798-114">**确保作业能够快速生成传入的跟踪数据清除的跟踪数据。**</span><span class="sxs-lookup"><span data-stu-id="e3798-114">**Ensure that the job is able to purge the tracking data as fast as the incoming tracking data is generated.**</span></span>  
  
     <span data-ttu-id="e3798-115">是可以接受作业的计划全力支持在高峰负载，但它应始终能保持同步。</span><span class="sxs-lookup"><span data-stu-id="e3798-115">It is acceptable for the job to get behind during peak load times, but it should always be able to catch up.</span></span> <span data-ttu-id="e3798-116">如果清除作业获取，并且永远不会是能够赶上，跟踪数据库将不断变大，，性能将最终会受到不利影响。</span><span class="sxs-lookup"><span data-stu-id="e3798-116">If the purge job gets behind and is never able to catch up, the Tracking database will continue to grow, and performance will eventually be adversely affected.</span></span>  
  
-   <span data-ttu-id="e3798-117">**查看软清除并硬清除参数，以确保你保存的数据的最佳总时间。**</span><span class="sxs-lookup"><span data-stu-id="e3798-117">**Review the soft purge and hard purge parameters to ensure that you are keeping data for the optimal length of time.**</span></span>  
  
     <span data-ttu-id="e3798-118">有关这些参数的详细信息请参阅["存档和清除 BizTalk 跟踪数据库"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。</span><span class="sxs-lookup"><span data-stu-id="e3798-118">For more information about these parameters see ["Archiving and Purging the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816).</span></span>  
  
-   <span data-ttu-id="e3798-119">**如果你需要保留跟踪存档文件，请确保你有一个进程的位置，以成功还原并使用它们。**</span><span class="sxs-lookup"><span data-stu-id="e3798-119">**If you need to keep the tracking archive files, ensure that you have a process in place to successfully restore and use them.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3798-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3798-120">See Also</span></span>  
 [<span data-ttu-id="e3798-121">清单： 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3798-121">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)