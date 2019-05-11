---
title: 从 BizTalk 跟踪数据库中清除数据 |Microsoft Docs
description: 配置 dtasp_PurgeTrackingDatabase 存储过程来清除在 BizTalk Server 中的跟踪数据库 (BizTalkDTADB)
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74a239f1b54ddf14cf0a9707868649a3df562cfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384450"
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="ca9d8-103">从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="ca9d8-103">Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="ca9d8-104">DTA 清除和存档作业清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中，当清除不同类型的跟踪信息，例如消息和服务实例信息、 业务流程事件信息和规则引擎跟踪数据从 BizTalk 跟踪 (BizTalkDTADb) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-104">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca9d8-105">使用此过程不存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-105">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ca9d8-106">如果异常是中捕获和处理业务流程未启用跟踪，与已启动状态和异常信息的孤立的跟踪实例可能会插入 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-106">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ca9d8-107">此记录在清除数据库后仍将保留。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-107">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca9d8-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="ca9d8-108">Prerequisites</span></span>  
<span data-ttu-id="ca9d8-109">使用 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-109">Sign in with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="ca9d8-110">清除 BizTalk 跟踪数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="ca9d8-110">Purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="ca9d8-111">在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-111">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span> 
  
2.  <span data-ttu-id="ca9d8-112">在中**连接到服务器**，输入 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 的名称、 输入身份验证类型，然后选择**Connect**以连接到 SQL server。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-112">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span> 
  
3.  <span data-ttu-id="ca9d8-113">双击**SQL Server 代理**，然后选择**作业**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-113">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="ca9d8-114">在中**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-114">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ca9d8-115">在中**作业属性-DTA 清除和存档 (BizTalkDTADb)** 下**选择页**，选择**步骤**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-115">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="ca9d8-116">在中**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-116">In **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="ca9d8-117">在中**作业步骤属性-存档和清除**，然后在**常规**页上，在**命令**框中，更改**exec dtasp_BackupAndPurgeTrackingDatabase**到**exec dtasp_PurgeTrackingDatabase**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-117">In **Job Step Properties - Archive and Purge**, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="ca9d8-118">**Exec dtasp_PurgeTrackingDatabase**存储的过程将不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-118">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ca9d8-119">然后再使用此选项，请确保不再需要存档的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-119">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="ca9d8-120">在中**命令**框中，更新以下参数，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-120">In the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="ca9d8-121">@nHours tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-121">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="ca9d8-122">@nDays tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-122">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="ca9d8-123">默认间隔为 1 天。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-123">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="ca9d8-124">@nHardDays tinyint — 将删除这一天的所有数据，即使数据不完整。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-124">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="ca9d8-125">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-125">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="ca9d8-126">数据生存时段是时间的你想要将 BizTalk 跟踪 (BizTalkDTADb) 数据库中保留跟踪数据间隔。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-126">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ca9d8-127">早于此时间间隔内有资格将在下一次存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-127">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="ca9d8-128">@dtLastBackup — 将其设置为**getutcdate （)** 从 BizTalk 跟踪 (BizTalkDTADb) 数据库清除数据。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-128">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ca9d8-129">如果设置为**NULL**，数据不从数据库中清除。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-129">When set to **NULL**, data is not purged from the database.</span></span>  

    -  <span data-ttu-id="ca9d8-130">@fHardDeleteRunningInstances int-默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-130">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="ca9d8-131">设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-131">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span>  
    
        > [!NOTE] 
        > <span data-ttu-id="ca9d8-132">@fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，并[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-132">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>   

    <span data-ttu-id="ca9d8-133">已编辑的脚本类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="ca9d8-133">Your edited script looks similar to the following:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. <span data-ttu-id="ca9d8-134">上**作业属性-DTA 清除和存档 (BizTalkDTADb)** 对话框中的**选择页**，选择**常规**，选择**已启用**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca9d8-134">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9d8-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca9d8-135">See Also</span></span>  
 [<span data-ttu-id="ca9d8-136">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="ca9d8-136">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
