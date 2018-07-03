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
ms.openlocfilehash: 2a025ea29e13ef938a39f9555785177f2c64e922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023595"
---
# <a name="how-to-delete-a-messagebox-database"></a><span data-ttu-id="42e94-102">如何删除 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="42e94-102">How to Delete a MessageBox Database</span></span>
<span data-ttu-id="42e94-103">使用 BizTalk 管理控制台或 Windows 管理规范 (WMI) 可以从 BizTalk 组中删除 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-103">You use the BizTalk Administration Console or Windows Management Instrumentation (WMI) to remove a MessageBox database from a BizTalk group.</span></span> <span data-ttu-id="42e94-104">您可以从 BizTalk 组中删除 MessageBox 数据库，也可以从 BizTalk Server 部署中将其完全删除。</span><span class="sxs-lookup"><span data-stu-id="42e94-104">You can remove a MessageBox database from a BizTalk group, or you can delete it from your BizTalk Server deployment entirely.</span></span>  
  
 <span data-ttu-id="42e94-105">例如，可以删除您不再使用的 MessageBox 数据库，如用于测试目的的数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-105">For example, you can delete a MessageBox database you are no longer using, such as a database used for testing purposes.</span></span>  
  
 <span data-ttu-id="42e94-106">若要从 BizTalk Server 部署中永久并完全地删除 MessageBox 数据库，需要执行以下八个步骤：</span><span class="sxs-lookup"><span data-stu-id="42e94-106">There are eight steps to permanently and completely removing MessageBox databases from your BizTalk Server deployment:</span></span>  
  
1.  <span data-ttu-id="42e94-107">禁止发布新消息。</span><span class="sxs-lookup"><span data-stu-id="42e94-107">Disable new message publication.</span></span>  
  
     <span data-ttu-id="42e94-108">在删除 MessageBox 数据库之前，必须禁用新消息发布功能。</span><span class="sxs-lookup"><span data-stu-id="42e94-108">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="42e94-109">有关禁止发布新消息的信息，请参阅[如何禁用发布新消息](../core/how-to-disable-new-message-publication.md)。</span><span class="sxs-lookup"><span data-stu-id="42e94-109">For information about disabling new message publication, see [How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md).</span></span>  
  
2.  <span data-ttu-id="42e94-110">等待缓存刷新间隔过期。</span><span class="sxs-lookup"><span data-stu-id="42e94-110">Wait for the cache refresh interval to expire.</span></span>  
  
     <span data-ttu-id="42e94-111">在您禁用新消息发布功能之后，必须等待一定时间才能删除数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-111">After you disable the publication of new messages, you must wait before you delete the database.</span></span> <span data-ttu-id="42e94-112">该等待时间定义为 CacheRefreshInterval 的两倍时间。</span><span class="sxs-lookup"><span data-stu-id="42e94-112">The wait time is defined as twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="42e94-113">CacheRefreshInterval 的默认值是 60 秒。</span><span class="sxs-lookup"><span data-stu-id="42e94-113">The default value of CacheRefreshInterval is 60 seconds.</span></span> <span data-ttu-id="42e94-114">您使用**组属性**对话框可以更改缓存刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="42e94-114">You use the **Group Properties** dialog box to change the Cache Refresh.</span></span>  
  
3.  <span data-ttu-id="42e94-115">从 BizTalk 组中删除 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-115">Remove the MessageBox database from the BizTalk Group.</span></span>  
  
     <span data-ttu-id="42e94-116">从 BizTalk 组中删除 MessageBox 数据库会从 BizTalk 管理数据库中删除 MessageBox 引用。</span><span class="sxs-lookup"><span data-stu-id="42e94-116">Removing the MessageBox database from the BizTalk Group removes the MessageBox reference from the BizTalk Management database.</span></span>  
  
4.  <span data-ttu-id="42e94-117">重新启动包含指向 MessageBox 数据库的缓存连接的主机实例。</span><span class="sxs-lookup"><span data-stu-id="42e94-117">Restart host instances that contain cached connections to the MessageBox database.</span></span>  
  
     <span data-ttu-id="42e94-118">如果存在来自运行时引擎的缓存数据库连接，则必须重新启动相应的主机实例，才能在物理上从 SQL Server 中删除该数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-118">You must restart the host instance before physically deleting the database from SQL Server if cached database connections from the run-time engine are present.</span></span> <span data-ttu-id="42e94-119">有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="42e94-119">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span>  
  
5.  <span data-ttu-id="42e94-120">停止正在访问该数据库的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="42e94-120">Stop all in-progress host instances that access the database.</span></span> <span data-ttu-id="42e94-121">有关停止正在进行中的主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="42e94-121">For information about stopping an in-progress host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
     <span data-ttu-id="42e94-122">如果要删除非主 MessageBox 数据库，应在停止运行中的主机实例之前，先禁止向该 MessageBox 发布新消息，还要确保以下几项内容：</span><span class="sxs-lookup"><span data-stu-id="42e94-122">If you are removing a non-primary MessageBox database, before stopping an in-progress host instance, you should first disable publication of new messages to that message box and make sure that:</span></span>  
  
    -   <span data-ttu-id="42e94-123">在 MessageBox 中没有正在运行的服务实例。</span><span class="sxs-lookup"><span data-stu-id="42e94-123">There are no running service instances remaining in the message box.</span></span>  
  
    -   <span data-ttu-id="42e94-124">在 MessageBox 中没有挂起的（或任何其他遗留的）实例。</span><span class="sxs-lookup"><span data-stu-id="42e94-124">There are no suspended (or any other remaining) instances left in the message box.</span></span>  
  
    -   <span data-ttu-id="42e94-125">BAM 跟踪数据已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库（TrackingData 表应为空）。</span><span class="sxs-lookup"><span data-stu-id="42e94-125">BAM tracked data has been moved to the BizTalk Tracking (BizTalkDTADb) database (TrackingData table should be empty).</span></span>  
  
    -   <span data-ttu-id="42e94-126">跟踪的消息正文已移至 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-126">Tracked message bodies have been moved to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
6.  <span data-ttu-id="42e94-127">确保后台 SQL Server 代理作业完成。</span><span class="sxs-lookup"><span data-stu-id="42e94-127">Ensure that the background SQL Server Agent job is finished.</span></span>  
  
     <span data-ttu-id="42e94-128">从 BizTalk Server 部署中永久删除 MessageBox 数据库之前，应该首先确保后台 SQL Server 代理作业已经完成了将所有跟踪的消息正文传输到相应 TrackingSpool 表的工作，然后备份这些 TrackingSpool 表。</span><span class="sxs-lookup"><span data-stu-id="42e94-128">Before you permanently delete a MessageBox database from your BizTalk Server deployment, you should first ensure that the background SQL Server Agent job has finished transferring all tracked message bodies to the TrackingSpool table, and then back up the TrackingSpool tables.</span></span> <span data-ttu-id="42e94-129">有关检查后台 SQL Server 代理作业的状态的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="42e94-129">For information about checking the status of a background SQL Server Agent job, see SQL Server Books Online.</span></span>  
  
7.  <span data-ttu-id="42e94-130">备份 TrackingSpool 表。</span><span class="sxs-lookup"><span data-stu-id="42e94-130">Back up the TrackingSpool tables.</span></span>  
  
     <span data-ttu-id="42e94-131">除非您手动将各 TrackingSpool 表备份到外部存储器中，否则跟踪的消息正文仍会保留在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="42e94-131">Tracked message bodies remain in the MessageBox database until you manually back up the TrackingSpool tables into external storage.</span></span> <span data-ttu-id="42e94-132">在备份之前，后台 SQL Server 代理作业将把消息正文从 Spool 表传输到 TrackingSpool 表中。</span><span class="sxs-lookup"><span data-stu-id="42e94-132">Before the backup happens, a background SQL Server Agent job transfers the message bodies from the Spool table to the TrackingSpool table.</span></span> <span data-ttu-id="42e94-133">有关手动备份 SQL Server 表的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="42e94-133">For information about manually backing up SQL Server tables, see SQL Server Books Online.</span></span>  
  
8.  <span data-ttu-id="42e94-134">从 SQL Server 中删除该数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-134">Remove the database from SQL Server.</span></span>  
  
     <span data-ttu-id="42e94-135">从 BizTalk 组中删除 MessageBox 数据库不会在物理上从 Microsoft SQL Server 中删除该数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-135">Deleting a MessageBox database from a BizTalk Group does not physically remove the database from Microsoft SQL Server.</span></span> <span data-ttu-id="42e94-136">若要永久删除 MessageBox 数据库，在将其从 BizTalk 组中删除之后必须通过使用 SQL Server 企业管理器或 SQL Server Management Studio 来删除它。</span><span class="sxs-lookup"><span data-stu-id="42e94-136">To permanently delete the MessageBox database, you must remove it by using SQL Server Enterprise Manager or SQL Server Management Studio after it is removed from the BizTalk Group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42e94-137">必要條件</span><span class="sxs-lookup"><span data-stu-id="42e94-137">Prerequisites</span></span>  
 <span data-ttu-id="42e94-138">管理 MessageBox 数据库的管理员必须具有所需的用户权限。</span><span class="sxs-lookup"><span data-stu-id="42e94-138">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="42e94-139">必须具有以下用户权限才能管理 MessageBox 数据库并禁用新消息发布：</span><span class="sxs-lookup"><span data-stu-id="42e94-139">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="42e94-140">必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="42e94-140">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="42e94-141">必须是该数据库所在的计算机的 SQL Server 管理员。</span><span class="sxs-lookup"><span data-stu-id="42e94-141">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a><span data-ttu-id="42e94-142">若要从 BizTalk 组中删除 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="42e94-142">To delete a MessageBox database from a BizTalk Group</span></span>  
  
1. <span data-ttu-id="42e94-143">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="42e94-143">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="42e94-144">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**消息框**。</span><span class="sxs-lookup"><span data-stu-id="42e94-144">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3. <span data-ttu-id="42e94-145">在详细信息窗格中，右键单击你想要删除，然后单击该消息框数据库**属性**。</span><span class="sxs-lookup"><span data-stu-id="42e94-145">In the details pane, right-click the message box database you want to remove, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="42e94-146">在中**消息框属性**对话框中，选择**禁止发布新消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="42e94-146">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box.</span></span>  
  
5. <span data-ttu-id="42e94-147">使用 BizTalk Server 管理控制台中的组中心页可以确定要删除的 MessageBox 数据库是否具有已冻结或挂起的消息实例。</span><span class="sxs-lookup"><span data-stu-id="42e94-147">Use the Group Hub page in the BizTalk Server Administration Console to verify that no message instances are dehydrated or suspended on the MessageBox database you are deleting.</span></span>  
  
6. <span data-ttu-id="42e94-148">等待 CacheRefreshInterval 的两倍时间。</span><span class="sxs-lookup"><span data-stu-id="42e94-148">Wait for a period of time twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="42e94-149">CacheRefreshInterval 的默认值是 60 秒。</span><span class="sxs-lookup"><span data-stu-id="42e94-149">The default value of CacheRefreshInterval is 60 seconds.</span></span>  
  
7. <span data-ttu-id="42e94-150">在细节窗格中，右键单击你想要删除，并单击 MessageBox 数据库**删除**。</span><span class="sxs-lookup"><span data-stu-id="42e94-150">In the details pane, right-click the MessageBox database that you want to delete, and click **Delete**.</span></span>  
  
8. <span data-ttu-id="42e94-151">阅读警告消息之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="42e94-151">After reading the warning message, click **OK**.</span></span>  
  
9. <span data-ttu-id="42e94-152">在控制台树中，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="42e94-152">In the console tree, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
10. <span data-ttu-id="42e94-153">在详细信息窗格中，右键单击所有运行的主机实例，然后停止并重新启动每一个主机实例。</span><span class="sxs-lookup"><span data-stu-id="42e94-153">In the details pane, right-click all running host instances, and stop and restart each one.</span></span>  
  
11. <span data-ttu-id="42e94-154">在 MessageBox 数据库驻留的服务器上，打开 SQL Server 企业管理器或 SQL Server Management Studio（取决于您使用的 SQL Server 的版本），然后删除该数据库。</span><span class="sxs-lookup"><span data-stu-id="42e94-154">On the server where the MessageBox database resides, open SQL Server Enterprise Manager or SQL Server Management Studio, depending on which version of SQL Server you are using, and then delete the database.</span></span>  
  
     <span data-ttu-id="42e94-155">有关如何删除 SQL Server 中的数据库的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="42e94-155">For information about how to delete a database in SQL Server, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e94-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="42e94-156">See Also</span></span>  
 <span data-ttu-id="42e94-157">[管理 MessageBox 数据库](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="42e94-157">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="42e94-158">[如何添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="42e94-158">[How to Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="42e94-159">[如何禁用发布新消息](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="42e94-159">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 [<span data-ttu-id="42e94-160">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="42e94-160">The MessageBox Database</span></span>](../core/the-messagebox-database.md)