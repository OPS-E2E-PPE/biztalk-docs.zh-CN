---
title: "如何配置 DTA 清除和存档作业 |Microsoft 文档"
ms.custom: 
ms.date: 2015-11-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, configuring
- DTA Purge and Archive job, configuring
- archiving [Tracking database], DTA Purge and Archive job
- archiving [Tracking database], configuring
- purging, DTA Purge and Archive job
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f4985e657f26945aa2fdc168b273dbfdb159efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="68cbb-102">如何配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="68cbb-102">How to Configure the DTA Purge and Archive Job</span></span>
<span data-ttu-id="68cbb-103">在对 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据进行存档或清除之前，必须首先配置 DTA 清除和存档 (BizTalkDTADb) 作业。</span><span class="sxs-lookup"><span data-stu-id="68cbb-103">Before you can archive or purge data from the BizTalk Tracking (BizTalkDTADb) database, you must configure the DTA Purge and Archive (BizTalkDTADb) job.</span></span> <span data-ttu-id="68cbb-104">此作业被配置为调用 dtasp_BackupAndPurgeTrackingDatabase 存储过程中，使用六个参数必须配置。</span><span class="sxs-lookup"><span data-stu-id="68cbb-104">This job is configured to call the dtasp_BackupAndPurgeTrackingDatabase store procedure, which uses six parameters you must configure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="68cbb-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="68cbb-105">Prerequisites</span></span>  
 <span data-ttu-id="68cbb-106">你必须是 SQL Server sysadmin 固定服务器角色的成员才能执行这些步骤的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="68cbb-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to follow these steps.</span></span>  
  
### <a name="to-configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="68cbb-107">配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="68cbb-107">To configure the DTA purge and archive job</span></span>  
  
1.  <span data-ttu-id="68cbb-108">在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-108">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="68cbb-109">在**连接到服务器**，输入 SQL 服务器的名称跟踪 (BizTalkDTADb) BizTalk 数据库所在的位置，输入身份验证类型，然后选择**连接**以连接到 SQL server。</span><span class="sxs-lookup"><span data-stu-id="68cbb-109">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span>  
  
3.  <span data-ttu-id="68cbb-110">在**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-110">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="68cbb-111">在**对象资源管理器详细信息**窗格中，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-111">In the **Object Explorer Details** pane, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="68cbb-112">在**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**步骤**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-112">In the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="68cbb-113">在**作业步骤列表**，单击**存档和清除**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-113">In the **Job step list**, click **Archive and Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="68cbb-114">上**常规**页上，在**命令**框中，编辑以下参数视情况而定，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-114">On the **General** page, in the **Command** box, edit the following parameters as appropriate, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="68cbb-115">@nLiveHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="68cbb-115">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="68cbb-116">这是没有默认值的必需的参数。</span><span class="sxs-lookup"><span data-stu-id="68cbb-116">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="68cbb-117">@nLiveDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="68cbb-117">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="68cbb-118">默认间隔为 0 天。</span><span class="sxs-lookup"><span data-stu-id="68cbb-118">Default interval is 0 days.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="68cbb-119">对于 BizTalk 跟踪 (BizTalkDTADb) 数据库来说，LiveHours 与 LiveDays 相加之和即为要在 BizTalk Server 环境中维护的数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="68cbb-119">For the purposes of the BizTalk Tracking (BizTalkDTADb) database, the sum of LiveHours plus LiveDays is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="68cbb-120">将删除与在数据生存时段之前完成的实例相关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="68cbb-120">All data associated with a completed instance older than the live window of data is deleted.</span></span>  
  
    -   <span data-ttu-id="68cbb-121">@nHardDeleteDaystinyint-所有数据 （即使不完整） 较旧，这将被删除。</span><span class="sxs-lookup"><span data-stu-id="68cbb-121">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="68cbb-122">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="68cbb-122">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="68cbb-123">数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="68cbb-123">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="68cbb-124">早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="68cbb-124">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="68cbb-125">默认值为 0 天。</span><span class="sxs-lookup"><span data-stu-id="68cbb-125">Default is 0 days.</span></span>  
  
    -   <span data-ttu-id="68cbb-126">@nvcFoldernvarchar(1024) — 在其中放入备份文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="68cbb-126">@nvcFolder nvarchar(1024) — Folder in which to put the backup files.</span></span> <span data-ttu-id="68cbb-127">这是没有默认值的必需的参数。</span><span class="sxs-lookup"><span data-stu-id="68cbb-127">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="68cbb-128">@nvcValidatingServersysname-将在其执行验证的服务器。</span><span class="sxs-lookup"><span data-stu-id="68cbb-128">@nvcValidatingServer sysname — Server on which validation will be done.</span></span> <span data-ttu-id="68cbb-129">NULL 值表示不执行任何验证。</span><span class="sxs-lookup"><span data-stu-id="68cbb-129">NULL value indicates no validation is being done.</span></span> <span data-ttu-id="68cbb-130">默认值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="68cbb-130">Default is NULL.</span></span>  
  
    -   <span data-ttu-id="68cbb-131">@fForceBackupint-默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="68cbb-131">@fForceBackup int — Default is 0.</span></span> <span data-ttu-id="68cbb-132">这被保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="68cbb-132">This is reserved for future use.</span></span>  
  
     <span data-ttu-id="68cbb-133">编辑的命令应如下所示。</span><span class="sxs-lookup"><span data-stu-id="68cbb-133">The edited command should look similar to the following.</span></span> <span data-ttu-id="68cbb-134">在下面的示例中，没有 1 小时的实时窗口和 1 天硬清除：</span><span class="sxs-lookup"><span data-stu-id="68cbb-134">In the following example, there is a live window of 1 hour and a hard purge of 1 day:</span></span>  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0  
    ```  
  
8.  <span data-ttu-id="68cbb-135">上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**常规**，选择**已启用**复选框，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="68cbb-135">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **General**, select the **Enabled** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68cbb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68cbb-136">See Also</span></span>  
 [<span data-ttu-id="68cbb-137">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="68cbb-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)