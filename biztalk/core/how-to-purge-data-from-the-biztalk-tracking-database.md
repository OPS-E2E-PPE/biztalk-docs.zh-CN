---
title: 从 BizTalk 跟踪数据库清除数据 |Microsoft 文档
description: 配置 dtasp_PurgeTrackingDatabase 存储过程以清除 BizTalk Server 中的跟踪数据库 (BizTalkDTADB)
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
ms.openlocfilehash: 06217a7d5012eb402698ad35e76ccfc886952f6e
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "23129702"
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="63039-103">从 BizTalk 跟踪数据库清除数据</span><span class="sxs-lookup"><span data-stu-id="63039-103">Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="63039-104">在清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据时，DTA 清除和存档作业将从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息和规则引擎跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="63039-104">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63039-105">使用此过程将不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="63039-105">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="63039-106">如果未启用跟踪就在业务流程中捕获和处理了异常，则可以将具有“已启动”状态和异常信息的孤立跟踪实例插入 BizTalk 跟踪 (BizTalkDTADb) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="63039-106">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="63039-107">在清除数据库后，此记录仍将保留。</span><span class="sxs-lookup"><span data-stu-id="63039-107">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="63039-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="63039-108">Prerequisites</span></span>  
<span data-ttu-id="63039-109">使用 SQL Server sysadmin 固定服务器角色的成员，才能执行此过程的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="63039-109">Sign in with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="63039-110">从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="63039-110">Purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="63039-111">在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="63039-111">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span> 
  
2.  <span data-ttu-id="63039-112">在 **连接到服务器**, ，输入 SQL 服务器的名称跟踪 (BizTalkDTADb) BizTalk 数据库所在的位置，输入身份验证类型，然后选择 **连接** 以连接到 SQL server。</span><span class="sxs-lookup"><span data-stu-id="63039-112">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span> 
  
3.  <span data-ttu-id="63039-113">双击**SQL Server 代理**，然后选择**作业**。</span><span class="sxs-lookup"><span data-stu-id="63039-113">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="63039-114">在**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="63039-114">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="63039-115">在**作业属性-DTA 清除和存档 (BizTalkDTADb)** 下**选择页**，选择**步骤**。</span><span class="sxs-lookup"><span data-stu-id="63039-115">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="63039-116">在**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="63039-116">In **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="63039-117">在**作业步骤属性-存档和清除**上**常规**页上，在**命令**框中，更改**exec dtasp_BackupAndPurgeTrackingDatabase**到**exec dtasp_PurgeTrackingDatabase**。</span><span class="sxs-lookup"><span data-stu-id="63039-117">In **Job Step Properties - Archive and Purge**, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="63039-118">**Exec dtasp_PurgeTrackingDatabase** 存储的过程不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="63039-118">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="63039-119">在使用此选项之前，应确保不再需要存档跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="63039-119">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="63039-120">在**命令**框中，更新的以下参数，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="63039-120">In the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="63039-121">@nHours tinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="63039-121">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="63039-122">@nDays tinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="63039-122">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="63039-123">默认间隔为 1 天。</span><span class="sxs-lookup"><span data-stu-id="63039-123">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="63039-124">@nHardDays tinyint-将删除早于这一天的所有数据，即使数据不完整。</span><span class="sxs-lookup"><span data-stu-id="63039-124">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="63039-125">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="63039-125">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="63039-126">数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="63039-126">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="63039-127">早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="63039-127">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="63039-128">@dtLastBackup -将此设置为 **GetUTCDate()** 要从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除数据。</span><span class="sxs-lookup"><span data-stu-id="63039-128">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="63039-129">当设置为 **NULL**, ，数据不会清除从数据库。</span><span class="sxs-lookup"><span data-stu-id="63039-129">When set to **NULL**, data is not purged from the database.</span></span>  

    -  <span data-ttu-id="63039-130">@fHardDeleteRunningInstances int-默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="63039-130">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="63039-131">设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。</span><span class="sxs-lookup"><span data-stu-id="63039-131">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span>  
    
        > [!NOTE] 
        > <span data-ttu-id="63039-132">@fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，和[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="63039-132">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>   

    <span data-ttu-id="63039-133">你已编辑的脚本与以下类似：</span><span class="sxs-lookup"><span data-stu-id="63039-133">Your edited script looks similar to the following:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. <span data-ttu-id="63039-134">上**作业属性-DTA 清除和存档 (BizTalkDTADb)** 对话框中，在**选择页**，选择**常规**，选择**已启用**复选框，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="63039-134">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63039-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63039-135">See Also</span></span>  
 [<span data-ttu-id="63039-136">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="63039-136">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
