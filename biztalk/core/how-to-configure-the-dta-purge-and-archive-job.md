---
title: "配置 DTA 清除和存档作业 |Microsoft 文档"
description: "在 SQL Server 代理来维护 BizTalk Server 中的跟踪数据库中设置 DTA 清除和存档作业参数"
ms.custom: 
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149719b7eea50ce53c14298597c94729162d43b0
ms.sourcegitcommit: 1fb633fcf919ce3124405420a5d9faa79d9d508e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2017
---
# <a name="configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="56367-103">配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="56367-103">Configure the DTA Purge and Archive Job</span></span>
<span data-ttu-id="56367-104">在对 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据进行存档或清除之前，必须首先配置 DTA 清除和存档 (BizTalkDTADb) 作业。</span><span class="sxs-lookup"><span data-stu-id="56367-104">Before you can archive or purge data from the BizTalk Tracking (BizTalkDTADb) database, you must configure the DTA Purge and Archive (BizTalkDTADb) job.</span></span> <span data-ttu-id="56367-105">此作业被配置为调用 dtasp_BackupAndPurgeTrackingDatabase 存储过程中，使用六个参数必须配置。</span><span class="sxs-lookup"><span data-stu-id="56367-105">This job is configured to call the dtasp_BackupAndPurgeTrackingDatabase store procedure, which uses six parameters you must configure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56367-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="56367-106">Prerequisites</span></span>  
 <span data-ttu-id="56367-107">使用 SQL Server sysadmin 固定服务器角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="56367-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="56367-108">配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="56367-108">Configure the DTA purge and archive job</span></span>  
  
1.  <span data-ttu-id="56367-109">在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="56367-109">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="56367-110">在**连接到服务器**，输入 SQL 服务器的名称跟踪 (BizTalkDTADb) BizTalk 数据库所在的位置，输入身份验证类型，然后选择**连接**以连接到 SQL server。</span><span class="sxs-lookup"><span data-stu-id="56367-110">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span>  
  
3. <span data-ttu-id="56367-111">双击**SQL Server 代理**，然后选择**作业**。</span><span class="sxs-lookup"><span data-stu-id="56367-111">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="56367-112">在**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="56367-112">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="56367-113">在**作业属性-DTA 清除和存档 (BizTalkDTADb)**下**选择页**，选择**步骤**。</span><span class="sxs-lookup"><span data-stu-id="56367-113">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="56367-114">在**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="56367-114">In the **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="56367-115">在**常规**中**命令**框中，更新的以下参数，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="56367-115">In **General**, in the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="56367-116">@nLiveHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="56367-116">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="56367-117">这是没有默认值的必需的参数。</span><span class="sxs-lookup"><span data-stu-id="56367-117">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="56367-118">@nLiveDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="56367-118">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="56367-119">默认间隔为 0 天。</span><span class="sxs-lookup"><span data-stu-id="56367-119">Default interval is 0 days.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="56367-120">对于 BizTalk 跟踪 (BizTalkDTADb) 数据库来说，LiveHours 与 LiveDays 相加之和即为要在 BizTalk Server 环境中维护的数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="56367-120">For the purposes of the BizTalk Tracking (BizTalkDTADb) database, the sum of LiveHours plus LiveDays is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="56367-121">将删除与在数据生存时段之前完成的实例相关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="56367-121">All data associated with a completed instance older than the live window of data is deleted.</span></span>  
  
    -   <span data-ttu-id="56367-122">@nHardDeleteDaystinyint-所有数据 （即使不完整） 较旧，这将被删除。</span><span class="sxs-lookup"><span data-stu-id="56367-122">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="56367-123">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="56367-123">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="56367-124">数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="56367-124">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="56367-125">早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="56367-125">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="56367-126">默认值为 0 天。</span><span class="sxs-lookup"><span data-stu-id="56367-126">Default is 0 days.</span></span>  
  
    -   <span data-ttu-id="56367-127">@nvcFoldernvarchar(1024) — 在其中放入备份文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="56367-127">@nvcFolder nvarchar(1024) — Folder in which to put the backup files.</span></span> <span data-ttu-id="56367-128">这是没有默认值的必需的参数。</span><span class="sxs-lookup"><span data-stu-id="56367-128">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="56367-129">@nvcValidatingServersysname-将在其执行验证的服务器。</span><span class="sxs-lookup"><span data-stu-id="56367-129">@nvcValidatingServer sysname — Server on which validation will be done.</span></span> <span data-ttu-id="56367-130">NULL 值表示不执行任何验证。</span><span class="sxs-lookup"><span data-stu-id="56367-130">NULL value indicates no validation is being done.</span></span> <span data-ttu-id="56367-131">默认值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="56367-131">Default is NULL.</span></span>  
  
    -   <span data-ttu-id="56367-132">@fForceBackupint-默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="56367-132">@fForceBackup int — Default is 0.</span></span> <span data-ttu-id="56367-133">这被保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="56367-133">This is reserved for future use.</span></span>  
  
    -   <span data-ttu-id="56367-134">@fHardDeleteRunningInstancesint-默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="56367-134">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="56367-135">设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。</span><span class="sxs-lookup"><span data-stu-id="56367-135">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="56367-136">@fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，和[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="56367-136">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>  
  
    <span data-ttu-id="56367-137">编辑的命令应类似于以下。</span><span class="sxs-lookup"><span data-stu-id="56367-137">Your edited command should look similar to the following.</span></span> <span data-ttu-id="56367-138">在以下示例中，没有 1 小时的实时窗口、 1 天和删除的硬清除所有正在运行服务实例超过 1 天：</span><span class="sxs-lookup"><span data-stu-id="56367-138">In the following example, there is a live window of 1 hour, a hard purge of 1 day, and deletes all running service instances older than 1 day:</span></span>  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  <span data-ttu-id="56367-139">上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，选择**常规**，选择**已启用**复选框，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="56367-139">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56367-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56367-140">See Also</span></span>  
 [<span data-ttu-id="56367-141">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="56367-141">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
