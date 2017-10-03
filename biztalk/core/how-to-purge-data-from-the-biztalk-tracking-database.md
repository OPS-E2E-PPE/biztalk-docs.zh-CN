---
title: "如何从 BizTalk 跟踪数据库清除数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging
- DTA Purge and Archive job, purging data
- purging, DTA Purge and Archive job
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c56629aaa0934010ba79637b4e4a134bf29f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="3db89-102">如何从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="3db89-102">How to Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="3db89-103">在清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据时，DTA 清除和存档作业将从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息和规则引擎跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="3db89-103">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3db89-104">使用此过程将不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="3db89-104">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3db89-105">如果未启用跟踪就在业务流程中捕获和处理了异常，则可以将具有“已启动”状态和异常信息的孤立跟踪实例插入 BizTalk 跟踪 (BizTalkDTADb) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="3db89-105">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="3db89-106">在清除数据库后，此记录仍将保留。</span><span class="sxs-lookup"><span data-stu-id="3db89-106">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3db89-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="3db89-107">Prerequisites</span></span>  
 <span data-ttu-id="3db89-108">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3db89-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="3db89-109">从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="3db89-109">To purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="3db89-110">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="3db89-110">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="3db89-111">在**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL Server 和适当的身份验证类型的名称，然后单击**连接**到连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3db89-111">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the SQL Server.</span></span>  
  
3.  <span data-ttu-id="3db89-112">在**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。</span><span class="sxs-lookup"><span data-stu-id="3db89-112">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="3db89-113">在**对象资源管理器详细信息**窗格中，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3db89-113">In the **Object Explorer Details** pane, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3db89-114">在**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**步骤**。</span><span class="sxs-lookup"><span data-stu-id="3db89-114">In the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="3db89-115">在**作业步骤列表**，单击**存档和清除**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="3db89-115">In the **Job step list**, click **Archive and Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="3db89-116">在**作业步骤属性-存档和清除**对话框中，在**常规**页上，在**命令**框中，更改**exec dtasp_BackupAndPurgeTrackingDatabase**到**exec dtasp_PurgeTrackingDatabase**。</span><span class="sxs-lookup"><span data-stu-id="3db89-116">In the **Job Step Properties - Archive and Purge** dialog box, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="3db89-117">**Exec dtasp_PurgeTrackingDatabase**存储的过程不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="3db89-117">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="3db89-118">在使用此选项之前，应确保不再需要存档跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="3db89-118">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="3db89-119">在**命令**框中，编辑以下参数视情况而定，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3db89-119">In the **Command** box, edit the following parameters as appropriate, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="3db89-120">@nHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="3db89-120">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="3db89-121">@nDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="3db89-121">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="3db89-122">默认间隔为 1 天。</span><span class="sxs-lookup"><span data-stu-id="3db89-122">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="3db89-123">@nHardDaystinyint-将删除早于这一天的所有数据，即使数据不完整。</span><span class="sxs-lookup"><span data-stu-id="3db89-123">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="3db89-124">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="3db89-124">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="3db89-125">数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="3db89-125">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="3db89-126">早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="3db89-126">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="3db89-127">@dtLastBackup-将此设置为**GetUTCDate()**要从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除数据。</span><span class="sxs-lookup"><span data-stu-id="3db89-127">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="3db89-128">当设置为**NULL**，数据不会清除从数据库。</span><span class="sxs-lookup"><span data-stu-id="3db89-128">When set to **NULL**, data is not purged from the database.</span></span>  
  
     <span data-ttu-id="3db89-129">您编辑的脚本应类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="3db89-129">Your edited script should look similar to this:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
    ```  
  
9. <span data-ttu-id="3db89-130">上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**常规**，选择**已启用**复选框，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="3db89-130">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **General**, select the **Enabled** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db89-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3db89-131">See Also</span></span>  
 [<span data-ttu-id="3db89-132">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="3db89-132">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)