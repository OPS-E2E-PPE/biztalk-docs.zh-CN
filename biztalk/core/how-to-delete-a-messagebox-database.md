---
title: 如何删除 MessageBox 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b5191d051e460217eccba93c0318a94357515b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338768"
---
# <a name="how-to-delete-a-messagebox-database"></a><span data-ttu-id="9a299-102">如何删除 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="9a299-102">How to Delete a MessageBox Database</span></span>
<span data-ttu-id="9a299-103">使用 BizTalk 管理控制台或 Windows Management Instrumentation (WMI) 从 BizTalk 组中删除 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-103">You use the BizTalk Administration Console or Windows Management Instrumentation (WMI) to remove a MessageBox database from a BizTalk group.</span></span> <span data-ttu-id="9a299-104">可以从 BizTalk 组中删除 MessageBox 数据库，或您可以完全将其删除从 BizTalk Server 部署。</span><span class="sxs-lookup"><span data-stu-id="9a299-104">You can remove a MessageBox database from a BizTalk group, or you can delete it from your BizTalk Server deployment entirely.</span></span>  
  
 <span data-ttu-id="9a299-105">例如，可以删除不再使用，例如用于测试目的的数据库的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-105">For example, you can delete a MessageBox database you are no longer using, such as a database used for testing purposes.</span></span>  
  
 <span data-ttu-id="9a299-106">从 BizTalk Server 部署中永久并完全地删除 MessageBox 数据库到有八个步骤：</span><span class="sxs-lookup"><span data-stu-id="9a299-106">There are eight steps to permanently and completely removing MessageBox databases from your BizTalk Server deployment:</span></span>  
  
1.  <span data-ttu-id="9a299-107">禁止发布新消息。</span><span class="sxs-lookup"><span data-stu-id="9a299-107">Disable new message publication.</span></span>  
  
     <span data-ttu-id="9a299-108">在删除 MessageBox 数据库之前，必须禁用新消息的发布。</span><span class="sxs-lookup"><span data-stu-id="9a299-108">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="9a299-109">有关禁止发布新消息的信息，请参阅[如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)。</span><span class="sxs-lookup"><span data-stu-id="9a299-109">For information about disabling new message publication, see [How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md).</span></span>  
  
2.  <span data-ttu-id="9a299-110">等待缓存刷新间隔过期。</span><span class="sxs-lookup"><span data-stu-id="9a299-110">Wait for the cache refresh interval to expire.</span></span>  
  
     <span data-ttu-id="9a299-111">禁止发布新消息后，必须等待，然后再删除数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-111">After you disable the publication of new messages, you must wait before you delete the database.</span></span> <span data-ttu-id="9a299-112">等待时间定义为 CacheRefreshInterval 的长度的两倍。</span><span class="sxs-lookup"><span data-stu-id="9a299-112">The wait time is defined as twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="9a299-113">CacheRefreshInterval 的默认值为 60 秒。</span><span class="sxs-lookup"><span data-stu-id="9a299-113">The default value of CacheRefreshInterval is 60 seconds.</span></span> <span data-ttu-id="9a299-114">您使用**组属性**对话框可以更改缓存刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="9a299-114">You use the **Group Properties** dialog box to change the Cache Refresh.</span></span>  
  
3.  <span data-ttu-id="9a299-115">从 BizTalk 组中删除 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-115">Remove the MessageBox database from the BizTalk Group.</span></span>  
  
     <span data-ttu-id="9a299-116">从 BizTalk 组中删除 MessageBox 数据库从 BizTalk 管理数据库中删除 MessageBox 引用。</span><span class="sxs-lookup"><span data-stu-id="9a299-116">Removing the MessageBox database from the BizTalk Group removes the MessageBox reference from the BizTalk Management database.</span></span>  
  
4.  <span data-ttu-id="9a299-117">重新启动包含到 MessageBox 数据库的缓存的连接的主机实例。</span><span class="sxs-lookup"><span data-stu-id="9a299-117">Restart host instances that contain cached connections to the MessageBox database.</span></span>  
  
     <span data-ttu-id="9a299-118">以物理方式删除从 SQL Server 数据库，从运行时引擎的缓存的数据库连接是否存在之前，必须重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="9a299-118">You must restart the host instance before physically deleting the database from SQL Server if cached database connections from the run-time engine are present.</span></span> <span data-ttu-id="9a299-119">有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="9a299-119">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span>  
  
5.  <span data-ttu-id="9a299-120">停止所有的访问的数据库中的主机实例。</span><span class="sxs-lookup"><span data-stu-id="9a299-120">Stop all in-progress host instances that access the database.</span></span> <span data-ttu-id="9a299-121">有关停止正在进行中的主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="9a299-121">For information about stopping an in-progress host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
     <span data-ttu-id="9a299-122">如果要删除非主 MessageBox 数据库，停止正在进行中的主机实例之前，你首先应禁止发布新消息到该消息框，请确保：</span><span class="sxs-lookup"><span data-stu-id="9a299-122">If you are removing a non-primary MessageBox database, before stopping an in-progress host instance, you should first disable publication of new messages to that message box and make sure that:</span></span>  
  
    -   <span data-ttu-id="9a299-123">没有正在运行服务实例在消息框中。</span><span class="sxs-lookup"><span data-stu-id="9a299-123">There are no running service instances remaining in the message box.</span></span>  
  
    -   <span data-ttu-id="9a299-124">有没有挂起 （或任何其他遗留） 实例中的消息框的左侧。</span><span class="sxs-lookup"><span data-stu-id="9a299-124">There are no suspended (or any other remaining) instances left in the message box.</span></span>  
  
    -   <span data-ttu-id="9a299-125">BAM 跟踪数据已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库 （TrackingData 表应为空）。</span><span class="sxs-lookup"><span data-stu-id="9a299-125">BAM tracked data has been moved to the BizTalk Tracking (BizTalkDTADb) database (TrackingData table should be empty).</span></span>  
  
    -   <span data-ttu-id="9a299-126">跟踪的消息正文已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-126">Tracked message bodies have been moved to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
6.  <span data-ttu-id="9a299-127">确保后台 SQL Server 代理作业已完成。</span><span class="sxs-lookup"><span data-stu-id="9a299-127">Ensure that the background SQL Server Agent job is finished.</span></span>  
  
     <span data-ttu-id="9a299-128">从 BizTalk Server 部署永久删除 MessageBox 数据库之前，应该首先确保后台 SQL Server 代理作业已完成传输所有跟踪消息正文到 TrackingSpool 表，然后备份TrackingSpool 表。</span><span class="sxs-lookup"><span data-stu-id="9a299-128">Before you permanently delete a MessageBox database from your BizTalk Server deployment, you should first ensure that the background SQL Server Agent job has finished transferring all tracked message bodies to the TrackingSpool table, and then back up the TrackingSpool tables.</span></span> <span data-ttu-id="9a299-129">有关检查后台 SQL Server 代理作业的状态信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="9a299-129">For information about checking the status of a background SQL Server Agent job, see SQL Server Books Online.</span></span>  
  
7.  <span data-ttu-id="9a299-130">备份 TrackingSpool 表。</span><span class="sxs-lookup"><span data-stu-id="9a299-130">Back up the TrackingSpool tables.</span></span>  
  
     <span data-ttu-id="9a299-131">跟踪的消息正文会保留在 MessageBox 数据库，直到您手动备份 TrackingSpool 表到外部存储。</span><span class="sxs-lookup"><span data-stu-id="9a299-131">Tracked message bodies remain in the MessageBox database until you manually back up the TrackingSpool tables into external storage.</span></span> <span data-ttu-id="9a299-132">在备份之前，后台 SQL Server 代理作业会将消息正文从 Spool 表传输到 TrackingSpool 表。</span><span class="sxs-lookup"><span data-stu-id="9a299-132">Before the backup happens, a background SQL Server Agent job transfers the message bodies from the Spool table to the TrackingSpool table.</span></span> <span data-ttu-id="9a299-133">有关手动备份 SQL Server 表的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="9a299-133">For information about manually backing up SQL Server tables, see SQL Server Books Online.</span></span>  
  
8.  <span data-ttu-id="9a299-134">从 SQL Server 中删除数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-134">Remove the database from SQL Server.</span></span>  
  
     <span data-ttu-id="9a299-135">从 BizTalk 组中删除 MessageBox 数据库不会以物理方式删除数据库从 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="9a299-135">Deleting a MessageBox database from a BizTalk Group does not physically remove the database from Microsoft SQL Server.</span></span> <span data-ttu-id="9a299-136">若要永久删除 MessageBox 数据库，必须通过使用 SQL Server 企业管理器或 SQL Server Management Studio 从 BizTalk 组中删除后删除。</span><span class="sxs-lookup"><span data-stu-id="9a299-136">To permanently delete the MessageBox database, you must remove it by using SQL Server Enterprise Manager or SQL Server Management Studio after it is removed from the BizTalk Group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a299-137">先决条件</span><span class="sxs-lookup"><span data-stu-id="9a299-137">Prerequisites</span></span>  
 <span data-ttu-id="9a299-138">管理 MessageBox 数据库管理员必须具有所需的用户权限。</span><span class="sxs-lookup"><span data-stu-id="9a299-138">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="9a299-139">必须具有以下的用户权限，才能管理 MessageBox 数据库并禁止发布新消息：</span><span class="sxs-lookup"><span data-stu-id="9a299-139">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="9a299-140">您必须以 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="9a299-140">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="9a299-141">您必须在数据库所在的计算机上的 SQL Server 管理员。</span><span class="sxs-lookup"><span data-stu-id="9a299-141">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a><span data-ttu-id="9a299-142">若要从 BizTalk 组中删除 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="9a299-142">To delete a MessageBox database from a BizTalk Group</span></span>  
  
1. <span data-ttu-id="9a299-143">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9a299-143">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9a299-144">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**消息框**。</span><span class="sxs-lookup"><span data-stu-id="9a299-144">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3. <span data-ttu-id="9a299-145">在详细信息窗格中，右键单击你想要删除，然后单击该消息框数据库**属性**。</span><span class="sxs-lookup"><span data-stu-id="9a299-145">In the details pane, right-click the message box database you want to remove, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="9a299-146">在中**消息框属性**对话框中，选择**禁止发布新消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="9a299-146">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box.</span></span>  
  
5. <span data-ttu-id="9a299-147">使用 BizTalk Server 管理控制台中的组中心页以验证消息实例都已冻结或挂起的要删除的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-147">Use the Group Hub page in the BizTalk Server Administration Console to verify that no message instances are dehydrated or suspended on the MessageBox database you are deleting.</span></span>  
  
6. <span data-ttu-id="9a299-148">等待一段时间内 CacheRefreshInterval 的长度的两倍。</span><span class="sxs-lookup"><span data-stu-id="9a299-148">Wait for a period of time twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="9a299-149">CacheRefreshInterval 的默认值为 60 秒。</span><span class="sxs-lookup"><span data-stu-id="9a299-149">The default value of CacheRefreshInterval is 60 seconds.</span></span>  
  
7. <span data-ttu-id="9a299-150">在细节窗格中，右键单击你想要删除，并单击 MessageBox 数据库**删除**。</span><span class="sxs-lookup"><span data-stu-id="9a299-150">In the details pane, right-click the MessageBox database that you want to delete, and click **Delete**.</span></span>  
  
8. <span data-ttu-id="9a299-151">阅读警告消息之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a299-151">After reading the warning message, click **OK**.</span></span>  
  
9. <span data-ttu-id="9a299-152">在控制台树中，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="9a299-152">In the console tree, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
10. <span data-ttu-id="9a299-153">在详细信息窗格中，右键单击正在运行的所有主机实例，并停止并重新启动每一个。</span><span class="sxs-lookup"><span data-stu-id="9a299-153">In the details pane, right-click all running host instances, and stop and restart each one.</span></span>  
  
11. <span data-ttu-id="9a299-154">在 MessageBox 数据库所在的服务器上，打开 SQL Server 企业管理器或 SQL Server Management Studio，具体取决于哪个版本的 SQL Server 使用的，然后删除该数据库。</span><span class="sxs-lookup"><span data-stu-id="9a299-154">On the server where the MessageBox database resides, open SQL Server Enterprise Manager or SQL Server Management Studio, depending on which version of SQL Server you are using, and then delete the database.</span></span>  
  
     <span data-ttu-id="9a299-155">有关如何删除 SQL Server 中的数据库的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="9a299-155">For information about how to delete a database in SQL Server, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a299-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a299-156">See Also</span></span>  
 <span data-ttu-id="9a299-157">[管理 MessageBox 数据库](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="9a299-157">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="9a299-158">[如何添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="9a299-158">[How to Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="9a299-159">[如何禁用发布新消息](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="9a299-159">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 [<span data-ttu-id="9a299-160">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="9a299-160">The MessageBox Database</span></span>](../core/the-messagebox-database.md)