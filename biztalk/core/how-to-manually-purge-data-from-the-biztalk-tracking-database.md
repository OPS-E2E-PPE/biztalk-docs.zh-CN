---
title: 如何从 BizTalk 跟踪数据库中手动清除数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb7b0eb838295e4abdc059a1437b6cf338d0a99
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993078"
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="4ec3f-102">如何从 BizTalk 跟踪数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="4ec3f-102">How to Manually Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="4ec3f-103">由于 DTA 存档和清除 SQL Server 代理作业不断清除 BizTalk 跟踪 (BizTalkDTADb) 数据库并对存储的跟踪数据进行压缩，因此可减少从该数据库中手动清除数据的需要。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-103">The DTA Archive and Purge SQL Server Agent job reduces the need to manually purge data from the BizTalk Tracking (BizTalkDTADb) database due to continuous purging of the database and compaction of stored tracking data.</span></span> <span data-ttu-id="4ec3f-104">但是，如果 BizTalk 跟踪 (BizTalkDTADb) 数据库迅速增长，从而导致性能持续下降以及 DTA 存档和清除作业无法跟上数据库的增长速度，则可能需要手动清除数据。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-104">You might need to manually purge data if your BizTalk Tracking (BizTalkDTADb) database has grown so much that sustained performance degradation is occurring and the DTA Archive and Purge job is unable to keep up with the database growth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4ec3f-105">执行此过程将会从 BizTalk 跟踪 (BizTalkDTADb) 数据库中删除已完成实例的所有跟踪数据，而不考虑这些实例的完成时间。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-105">Performing this procedure deletes all tracking data for completed instances from the BizTalk Tracking (BizTalkDTADb) database regardless of completion time.</span></span> <span data-ttu-id="4ec3f-106">在执行此过程之前，应将 BizTalk 跟踪 (BizTalkDTADb) 数据库与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库分开进行存档。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-106">Before performing this procedure, you should archive the BizTalk Tracking (BizTalkDTADb) database separately from the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ec3f-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="4ec3f-107">Prerequisites</span></span>  
 <span data-ttu-id="4ec3f-108">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="4ec3f-109">从 BizTalk 跟踪数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="4ec3f-109">To manually purge data from the BizTalk Tracking database</span></span>  
  
1. <span data-ttu-id="4ec3f-110">备份 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-110">Backup your BizTalk Server databases.</span></span>  
  
2. <span data-ttu-id="4ec3f-111">存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-111">Archive the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
3. <span data-ttu-id="4ec3f-112">打开“服务”控制台。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-112">Open the Services console.</span></span> <span data-ttu-id="4ec3f-113">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-113">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="4ec3f-114">如果**用户帐户控制**显示对话框中，单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-114">If a **User Account Control** dialog is displayed, click **Continue**.</span></span>  
  
4. <span data-ttu-id="4ec3f-115">“服务”控制台出现时，查找以下每个服务，然后将它们停止。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-115">When the Services console appears, locate and then stop each of the following services.</span></span> <span data-ttu-id="4ec3f-116">若要停止服务，右键单击服务中行**Services**窗格中，，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-116">To stop a service, right-click the service row in the **Services** pane, and then click **Stop**.</span></span>  
  
   -   <span data-ttu-id="4ec3f-117">BizTalkServiceBizTalkGroup: BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="4ec3f-117">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
   -   <span data-ttu-id="4ec3f-118">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="4ec3f-118">Enterprise Single Sign-On Service</span></span>  
  
        <span data-ttu-id="4ec3f-119">如果 BizTalkServiceBizTalkGroup: BizTalkServerApplication 服务正在运行时尝试关闭企业单一登录服务，**停止其他服务**将显示对话框。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-119">If the BizTalkServiceBizTalkGroup : BizTalkServerApplication service is running when you try to shut down the Enterprise Singe Sign-On Service, a **Stop Other Services** dialog will be displayed.</span></span> <span data-ttu-id="4ec3f-120">单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-120">Click **Yes**.</span></span>  
  
   -   <span data-ttu-id="4ec3f-121">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="4ec3f-121">Rule Engine Update Service</span></span>  
  
5. <span data-ttu-id="4ec3f-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span> <span data-ttu-id="4ec3f-123">如果**用户帐户控制**显示对话框中，验证所述的操作是您想要，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-123">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
6. <span data-ttu-id="4ec3f-124">在中**BizTalk Server 管理控制台**在窗口左侧的资源管理器窗格中，双击**BizTalk 组**若要展开它下面的列表，然后双击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-124">In the **BizTalk Server Administration Console** in the explorer pane on the left side of the window, double-click **BizTalk Group** to expand the list below it, then double-click **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="4ec3f-125">这将显示一系列主机实例 (**主机实例**窗格) 及相关的属性，在屏幕右侧。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-125">This will display a list of host instances (the **Host Instances** pane) and related properties, on the right side of the screen.</span></span>  
  
7. <span data-ttu-id="4ec3f-126">在中**主机实例**窗格中，右键单击每个正在运行的主机实例，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-126">In the **Host Instances** pane, right-click each running host instance, and then click **Stop**.</span></span>  
  
8. <span data-ttu-id="4ec3f-127">单击**启动**，请转到**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-127">Click **Start**, go to **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="4ec3f-128">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="4ec3f-128">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="4ec3f-129">**net 停止 iisadmin /y**</span><span class="sxs-lookup"><span data-stu-id="4ec3f-129">**net stop iisadmin /y**</span></span>  
  
     <span data-ttu-id="4ec3f-130">这将逐一停止 IIS 管理服务及所有依存的服务，并在清除数据期间阻止向 BizTalkDTADb 写入新数据。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-130">This stops the IIS Admin Service and all dependent services, one-by-one and prevents new data from being written to the BizTalkDTADb while data is being purged.</span></span> <span data-ttu-id="4ec3f-131">在停止每个服务时，请记下这些服务的列表。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-131">Write down the list of services as each one is stopped.</span></span> <span data-ttu-id="4ec3f-132">以后重新启动 IIS 时，将需要使用此服务列表。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-132">You will need to use this list of services later when you restart IIS.</span></span>  
  
     <span data-ttu-id="4ec3f-133">以下是一个在发出此命令后将显示的输出示例（您的计算机上列出的依存服务可能会有所不同）：</span><span class="sxs-lookup"><span data-stu-id="4ec3f-133">Below is an example of the output you will see after issuing this command (the dependent services listed on your computer may vary):</span></span>  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. <span data-ttu-id="4ec3f-134">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-134">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
11. <span data-ttu-id="4ec3f-135">在中**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL 服务器和相应的验证类型的名称，然后单击**Connect**到连接到相应的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-135">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
12. <span data-ttu-id="4ec3f-136">在中**Microsoft SQL Server Management Studio**，双击**数据库**，双击**BizTalkDTADb**数据库中，双击**可编程性**，然后单击**存储过程**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-136">In **Microsoft SQL Server Management Studio**, double-click **Databases**, double-click the **BizTalkDTADb** database, double-click **Programmability**, and then click **Stored Procedures**.</span></span>  
  
13. <span data-ttu-id="4ec3f-137">在中**对象资源管理器详细信息**窗格中，右键单击**dtasp_PurgeAllCompletedTrackingData**，然后单击**执行存储过程**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-137">In the **Object Explorer Details** pane, right-click **dtasp_PurgeAllCompletedTrackingData**, and then click **Execute Stored Procedure**.</span></span>  
  
14. <span data-ttu-id="4ec3f-138">在中**执行过程**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-138">In the **Execute Procedure** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="4ec3f-139">此存储过程将删除与完成的实例相关联的所有跟踪数据，而不考虑其完成时间。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-139">This stored procedure deletes all tracking data associated with completed instances regardless of their completion time.</span></span>  
  
15. <span data-ttu-id="4ec3f-140">打开“服务”。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-140">Open Services.</span></span> <span data-ttu-id="4ec3f-141">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-141">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="4ec3f-142">如果**用户帐户控制**显示对话框中，验证所述的操作是您想要，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-142">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
16. <span data-ttu-id="4ec3f-143">右键单击每个以下的服务，然后依次**启动**:</span><span class="sxs-lookup"><span data-stu-id="4ec3f-143">Right-click each of the following services, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="4ec3f-144">BizTalkServiceBizTalkGroup: BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="4ec3f-144">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
    -   <span data-ttu-id="4ec3f-145">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="4ec3f-145">Enterprise Single Sign-On Service</span></span>  
  
    -   <span data-ttu-id="4ec3f-146">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="4ec3f-146">Rule Engine Update Service</span></span>  
  
17. <span data-ttu-id="4ec3f-147">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-147">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="4ec3f-148">在中**BizTalk Server 管理控制台**，双击**BizTalk 组**，双击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-148">In the **BizTalk Server Administration Console**, double-click the **BizTalk Group**, double-click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
19. <span data-ttu-id="4ec3f-149">在中**对象资源管理器详细信息**窗格中，右键单击每个停止的主机实例，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-149">In the **Object Explorer Details** pane, right-click each stopped host instance, and then click **Start**.</span></span>  
  
20. <span data-ttu-id="4ec3f-150">如上面的步骤 8 中所述，启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-150">Start a command prompt, as described in step 8 above.</span></span>  
  
21. <span data-ttu-id="4ec3f-151">在命令提示符下，在重新启动停止 IIS 服务的每个步骤 4。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-151">At the command prompt, restart each of the IIS services that you stopped in step 4.</span></span> <span data-ttu-id="4ec3f-152">类型：</span><span class="sxs-lookup"><span data-stu-id="4ec3f-152">Type:</span></span>  
  
     <span data-ttu-id="4ec3f-153">**net start**  *\<IISserviceName\>*</span><span class="sxs-lookup"><span data-stu-id="4ec3f-153">**net start** *\<IISserviceName\>*</span></span>  
  
     <span data-ttu-id="4ec3f-154">其中*\<IISserviceName\>* 是你想要重新启动 IIS 服务的名称。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-154">Where *\<IISserviceName\>* is the name of the IIS service you want to restart.</span></span> <span data-ttu-id="4ec3f-155">您必须对每个 IIS 服务重复执行此命令。</span><span class="sxs-lookup"><span data-stu-id="4ec3f-155">You must repeat this command for each of the IIS services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec3f-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ec3f-156">See Also</span></span>  
 <span data-ttu-id="4ec3f-157">[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="4ec3f-157">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="4ec3f-158">[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4ec3f-158">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="4ec3f-159">如何启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务</span><span class="sxs-lookup"><span data-stu-id="4ec3f-159">How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services</span></span>](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)