---
title: BizTalk Server 管理疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 11/30/2018
ms.prod: biztalk-server
ms.reviewer: niklase
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfb56b0-352f-4012-b030-087bbcfe09d4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87ecae986df0ee34ee697257a99097a00d525db2
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826461"
---
# <a name="troubleshooting-biztalk-server-administration"></a><span data-ttu-id="7fe25-102">故障排除的 BizTalk Server 管理</span><span class="sxs-lookup"><span data-stu-id="7fe25-102">Troubleshooting BizTalk Server Administration</span></span>
<span data-ttu-id="7fe25-103">本部分提供有关使用 BizTalk Server 管理控制台时遇到的常见问题的信息的一个集中的位置。</span><span class="sxs-lookup"><span data-stu-id="7fe25-103">This section provides a centralized location for information about common problems encountered while using the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="7fe25-104">除了以下已知问题[常见问题和解决方法与 BizTalk Server 管理控制台](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx)提供的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7fe25-104">In addition to the following Known Issues, [Common Issues and Resolutions With the BizTalk Server Administration Console](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx) provides additional information.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="7fe25-105">已知问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-105">Known Issues</span></span>  
  
#### <a name="delay-in-entsso-service-prevents-biztalk-server-service-from-starting"></a><span data-ttu-id="7fe25-106">ENTSSO 服务中的延迟会阻止 BizTalk Server 服务启动</span><span class="sxs-lookup"><span data-stu-id="7fe25-106">Delay in ENTSSO Service prevents BizTalk Server service from starting</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-107">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-107">Problem</span></span>  
 <span data-ttu-id="7fe25-108">使用 DTC 未设置为自动启动时重新启动您的计算机可能会阻止 BizTalk Server 服务启动。</span><span class="sxs-lookup"><span data-stu-id="7fe25-108">Rebooting your computer with DTC not set to automatic start-up may prevent the BizTalk Server service from starting.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-109">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-109">Cause</span></span>  
 <span data-ttu-id="7fe25-110">这是因为 ENTSSO 服务可能需要更多时间来启动超过了允许按 BizTalk Server 服务超时持续时间。</span><span class="sxs-lookup"><span data-stu-id="7fe25-110">This is because the ENTSSO service can take more time to start than is allowed by the BizTalk Server service timeout duration.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="7fe25-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="7fe25-111">Solution</span></span>  
 <span data-ttu-id="7fe25-112">若要解决此问题，请将 DTC 设置为自动。</span><span class="sxs-lookup"><span data-stu-id="7fe25-112">To resolve this issue, set DTC to automatic.</span></span> <span data-ttu-id="7fe25-113">如果群集化 DTC 之后，它应设置为手动启动时这是因为群集服务管理的开始和停止群集服务。</span><span class="sxs-lookup"><span data-stu-id="7fe25-113">If DTC is clustered, it should be set to manual start-up because the cluster service is managing the start and stop of clustered services.</span></span> 
  
#### <a name="sql-resources-may-become-locked"></a><span data-ttu-id="7fe25-114">SQL 资源可能会被锁定</span><span class="sxs-lookup"><span data-stu-id="7fe25-114">SQL resources may become locked</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-115">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-115">Problem</span></span>  
 <span data-ttu-id="7fe25-116">可能会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="7fe25-116">The following error may occur:</span></span>  
  
 <span data-ttu-id="7fe25-117">**事务（进程 ID 95）与另一进程在锁定资源上发生死锁，并且已被选为死锁牺牲品。重新运行事务。**</span><span class="sxs-lookup"><span data-stu-id="7fe25-117">**Transaction (Process ID 95) was deadlocked on lock resources with another process and has been chosen as the deadlock victim. Rerun the transaction.**</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-118">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-118">Cause</span></span>  
 <span data-ttu-id="7fe25-119">这种情况很少见，一名用户执行的管理操作导致另一用户被锁定，而无法进行数据库管理。</span><span class="sxs-lookup"><span data-stu-id="7fe25-119">This is a very rare situation in which administrative operations performed by one user result in another user being locked out of database administration.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="7fe25-120">解决方案</span><span class="sxs-lookup"><span data-stu-id="7fe25-120">Solution</span></span>  
 <span data-ttu-id="7fe25-121">该问题会在短时间内自我进行纠正。</span><span class="sxs-lookup"><span data-stu-id="7fe25-121">The problem should remedy itself shortly.</span></span> <span data-ttu-id="7fe25-122">请在几分钟后再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="7fe25-122">Try the operation again in a few minutes.</span></span>  
  
#### <a name="sql-database-may-become-locked"></a><span data-ttu-id="7fe25-123">SQL 数据库可能会被锁定</span><span class="sxs-lookup"><span data-stu-id="7fe25-123">SQL database may become locked</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-124">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-124">Problem</span></span>  
 <span data-ttu-id="7fe25-125">用户可能被锁在 SQL 数据库之外。</span><span class="sxs-lookup"><span data-stu-id="7fe25-125">Users may be locked out of the SQL database.</span></span> <span data-ttu-id="7fe25-126">可能会返回一些不同的错误消息。</span><span class="sxs-lookup"><span data-stu-id="7fe25-126">A number of different error messages may be returned.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-127">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-127">Cause</span></span>  
 <span data-ttu-id="7fe25-128">在某些情况下，向数据库进行写入的一名用户会有效地将另一名用户锁在数据库之外。</span><span class="sxs-lookup"><span data-stu-id="7fe25-128">In some cases one user writing to the database will effectively lock another user out of the database.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="7fe25-129">解决方案</span><span class="sxs-lookup"><span data-stu-id="7fe25-129">Solution</span></span>  
 <span data-ttu-id="7fe25-130">该问题会在短时间内自我进行纠正。</span><span class="sxs-lookup"><span data-stu-id="7fe25-130">The problem should remedy itself shortly.</span></span> <span data-ttu-id="7fe25-131">请在几分钟后再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="7fe25-131">Try the operation again in a few minutes.</span></span>  
  
#### <a name="termination-of-multiple-service-instances-in-a-multiple-messagebox-environment-fails-with-an-error"></a><span data-ttu-id="7fe25-132">终止多个 messagebox 环境中的多个服务实例失败并出现错误</span><span class="sxs-lookup"><span data-stu-id="7fe25-132">Termination of multiple service instances in a multiple messagebox environment fails with an error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-133">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-133">Problem</span></span>  
 <span data-ttu-id="7fe25-134">尝试从 BizTalk Server 管理控制台终止多个服务实例失败，显示一个与以下所示内容类似的错误：</span><span class="sxs-lookup"><span data-stu-id="7fe25-134">Attempts to terminate multiple service instances from the BizTalk Server Administration console fail and an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="7fe25-135">SQL Server 阻止访问组件“Agent XPs”的“sys.xp_sqlagent_enum_jobs”过程，因为此组件作为此服务器的安全配置的一部分而被关闭。</span><span class="sxs-lookup"><span data-stu-id="7fe25-135">SQL Server blocked access to procedure 'sys.xp_sqlagent_enum_jobs' of component 'Agent XPs' because this component is turned off as part of the security configuration for this server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fe25-136">在 messagebox 环境中会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="7fe25-136">This problem occurs in a multiple messagebox environment.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-137">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-137">Cause</span></span>  
 <span data-ttu-id="7fe25-138">此问题可能在多个 messagebox 环境中，如果 SQL 代理作业 Operations_OperateOnInstances_OnMaster_\<*dbName*\>辅助 messagebox 数据库上未运行。</span><span class="sxs-lookup"><span data-stu-id="7fe25-138">This problem can occur in a multiple messagebox environment if the SQL agent job 'Operations_OperateOnInstances_OnMaster_\<*dbName*\>' is not running on the secondary messagebox databases.</span></span> <span data-ttu-id="7fe25-139">此作业必须正在运行，才能将信息从辅助 messagebox 数据库传播到主 messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="7fe25-139">This job must be running in order to propagate information from the secondary messagebox databases to the primary messagebox database.</span></span> <span data-ttu-id="7fe25-140">如果该作业未启用或者如果发生登录故障，则此作业将无法运行。</span><span class="sxs-lookup"><span data-stu-id="7fe25-140">This job will fail to run if it is not enabled or if a logon failure occurs.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="7fe25-141">解决方案</span><span class="sxs-lookup"><span data-stu-id="7fe25-141">Solution</span></span>  
 <span data-ttu-id="7fe25-142">如果使用 BizTalk 管理控制台中同时执行多个服务实例上的操作和 BizTalk Server 环境配置了多个 messagebox 数据库，请验证 SQL Server 代理作业名为 Operations_OperateOnInstances_OnMaster_\<*dbName*\>在所有辅助 （非主） messagebox 数据库上启用。</span><span class="sxs-lookup"><span data-stu-id="7fe25-142">If you are using the BizTalk Administration console to perform operations on multiple service instances simultaneously and your BizTalk Server environment is configured with multiple messagebox databases, verify that the SQL Server Agent job named 'Operations_OperateOnInstances_OnMaster_\<*dbName*\>' is enabled on all secondary (non-master) messagebox databases.</span></span> <span data-ttu-id="7fe25-143">此外，托管辅助 messagebox 数据库的 SQL Server 计算机上的 SQL Server 代理服务必须作为辅助 messagebox 数据库的 BTS_SQLAGENT_USER 数据库角色中包含的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="7fe25-143">Additionally, the SQL Server Agent service on the SQL Server computer that hosts the secondary messagebox databases must run as an account that is included in the BTS_SQLAGENT_USER database role of the secondary messagebox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fe25-144">\<*dbname* \>是 BizTalk messagebox 数据库的实际名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="7fe25-144">\<*dbname*\> is a placeholder for the actual name of the BizTalk messagebox database.</span></span>  
  
 <span data-ttu-id="7fe25-145">请按照以下步骤，将 SQL Server 代理服务帐户添加到辅助 messagebox 数据库的 BTS_SQLAGENT_USER 数据库角色</span><span class="sxs-lookup"><span data-stu-id="7fe25-145">Follow these steps to add the SQL Server Agent service account to the BTS_SQLAGENT_USER database role of the secondary messagebox database</span></span>  
  
 <span data-ttu-id="7fe25-146">**SQL Server 2008 上**</span><span class="sxs-lookup"><span data-stu-id="7fe25-146">**On SQL Server 2008**</span></span>  
  
1.  <span data-ttu-id="7fe25-147">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="7fe25-147">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="7fe25-148">出现提示时选择**服务器类型**的**数据库引擎**并输入或选择**服务器名称**托管辅助 messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="7fe25-148">When prompted choose the **Server type** of **Database Engine** and enter or select the **Server name** that hosts the secondary messagebox database.</span></span>  
  
3.  <span data-ttu-id="7fe25-149">单击此项可展开**数据库**，单击以展开辅助 messagebox 数据库，单击以展开**安全**，单击此项可展开**角色**，单击此项可展开**数据库角色**，然后双击 BTS_SQLAGENT_USER 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="7fe25-149">Click to expand **Databases**, click to expand the secondary messagebox database, click to expand **Security**, click to expand **Roles**, click to expand **Database Roles**, and then double-click the BTS_SQLAGENT_USER database role.</span></span>  
  
4.  <span data-ttu-id="7fe25-150">单击 **“添加”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="7fe25-150">Click the **Add** button.</span></span>  
  
5.  <span data-ttu-id="7fe25-151">单击**浏览**，选择 SQL Server 代理服务帐户是的成员的组，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7fe25-151">Click **Browse**, select a group that the SQL Server Agent service account is a member of, and then click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fe25-152">如果 SQL Server 代理服务帐户不是指定组的成员，则您需要将其添加到该组。</span><span class="sxs-lookup"><span data-stu-id="7fe25-152">If the SQL Server Agent service account is not a member of the specified group then you will need to add it to the group.</span></span>  
  
#### <a name="changes-applied-in-one-instance-of-the-biztalk-administration-console-are-not-automatically-updated-in-other-instances-of-the-biztalk-administration-console"></a><span data-ttu-id="7fe25-153">BizTalk 管理控制台中的一个实例中应用的更改不会自动更新在其他情况下的 BizTalk 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7fe25-153">Changes applied in one instance of the BizTalk Administration console are not automatically updated in other instances of the BizTalk Administration console</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-154">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-154">Problem</span></span>  
 <span data-ttu-id="7fe25-155">如果 BizTalk 管理控制台中的多个实例同时连接到相同的 BizTalk Server 组中，BizTalk 管理控制台中的一个实例中所做的更改将不会自动反映在另一个实例的 BizTalk管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7fe25-155">If multiple instances of the BizTalk Administration console are simultaneously connected to the same BizTalk Server group, changes made in one instance of the BizTalk Administration console are not automatically reflected in the other instance(s) of the BizTalk Administration console.</span></span> <span data-ttu-id="7fe25-156">尝试修改项目显示在 BizTalk 管理控制台中的一个实例，如果项目的状态与项目存储在 BizTalk 管理数据库中的实际状态不匹配时，这会导致并发冲突错误。</span><span class="sxs-lookup"><span data-stu-id="7fe25-156">This can cause concurrency violation errors when attempting to modify an artifact displayed in an instance of the BizTalk Administration console if the state of the artifact does not match the actual state of the artifact as stored in the BizTalk management database.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-157">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-157">Cause</span></span>  
 <span data-ttu-id="7fe25-158">在 BizTalk 管理控制台的每个实例维护其自己的 BizTalk 组配置的缓存，并仅反映在缓存中的更改。</span><span class="sxs-lookup"><span data-stu-id="7fe25-158">Each instance of the BizTalk Administration console maintains its own cache of the BizTalk group configuration and only reflects changes in the cache.</span></span> <span data-ttu-id="7fe25-159">刷新 BizTalk 管理控制台视图时，才会更新缓存。</span><span class="sxs-lookup"><span data-stu-id="7fe25-159">The cache is only updated when the BizTalk Administration console view is refreshed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-160">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-160">Resolution</span></span>  
 <span data-ttu-id="7fe25-161">如果在 BizTalk 管理控制台中收到并发冲突错误，通过单击更新 BizTalk 管理控制台中的实例的缓存**刷新**在 BizTalk 管理控制台上的按钮工具栏或通过按**F5**密钥。</span><span class="sxs-lookup"><span data-stu-id="7fe25-161">If you receive concurrency violation errors in the BizTalk Administration console, update the cache for the instance of the BizTalk Administration console by clicking the **Refresh** button on the BizTalk Administration console toolbar or by pressing the **F5** key.</span></span>  
  
#### <a name="failed-to-execute-action-stop-error-occurs-when-you-attempt-to-stop-an-orchestration-with-the-biztalk-administration-console"></a><span data-ttu-id="7fe25-162">尝试通过 BizTalk 管理控制台停止业务流程时，出现无法执行“停止”操作的错误</span><span class="sxs-lookup"><span data-stu-id="7fe25-162">Failed to execute action 'Stop' error occurs when you attempt to stop an Orchestration with the BizTalk Administration console</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-163">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-163">Problem</span></span>  
 <span data-ttu-id="7fe25-164">当你尝试停止业务流程的 BizTalk 管理控制台中时，生成类似以下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="7fe25-164">When you attempt to stop an Orchestration in the BizTalk Administration console, an error message similar to the following is generated:</span></span>  
  
```  
Failed to execute action 'Stop'.  
------------------------------  
ADDITIONAL INFORMATION:  
A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) (Microsoft SQL Server, Error: 10054)  
```  
  
 <span data-ttu-id="7fe25-165">如果满足以下条件，则可能会出现此问题：</span><span class="sxs-lookup"><span data-stu-id="7fe25-165">This problem may occur if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="7fe25-166">在 BizTalk 管理控制台已打开。</span><span class="sxs-lookup"><span data-stu-id="7fe25-166">The BizTalk Administration console is open.</span></span>  
  
-   <span data-ttu-id="7fe25-167">SQL Server 的群集实例上安装了 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="7fe25-167">The BizTalk management database is installed on a clustered instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="7fe25-168">SQL Server 的群集的实例故障转移。</span><span class="sxs-lookup"><span data-stu-id="7fe25-168">The clustered instance of SQL Server is failed over.</span></span>  
  
-   <span data-ttu-id="7fe25-169">在故障转移完成后，你尝试停止正在运行的业务流程使用 BizTalk 管理控制台实例。</span><span class="sxs-lookup"><span data-stu-id="7fe25-169">After the failover is complete, you attempt to stop a running instance of an orchestration using the BizTalk Administration console.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-170">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-170">Cause</span></span>  
 <span data-ttu-id="7fe25-171">BizTalk 管理控制台维护到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="7fe25-171">The BizTalk Administration console maintains a connection to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span> <span data-ttu-id="7fe25-172">到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的连接在故障转移期间中断时，某些管理任务会返回“无法连接”或“无法执行”错误，直到 BizTalk 管理控制台关闭或重新打开。</span><span class="sxs-lookup"><span data-stu-id="7fe25-172">When the connection to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database has been broken during the failover, some management tasks may return a "Failed to connect" or "Failed to execute" error until the BizTalk Administration console has been closed and reopened.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-173">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-173">Resolution</span></span>  
 <span data-ttu-id="7fe25-174">关闭并重新打开 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7fe25-174">Close and reopen the BizTalk Administration console.</span></span> <span data-ttu-id="7fe25-175">BizTalk 管理控制台重新打开后，将创建一个到指定的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的新连接。</span><span class="sxs-lookup"><span data-stu-id="7fe25-175">When the BizTalk Administration console is reopened it creates a new connection to the specified [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span>  
  
#### <a name="windows-group-names-that-were-previously-deleted-do-not-have-access-to-the-biztalk-server-databases"></a><span data-ttu-id="7fe25-176">以前删除的 Windows 组名称不能访问到 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7fe25-176">Windows group names that were previously deleted do not have access to the BizTalk Server databases</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-177">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-177">Problem</span></span>  
 <span data-ttu-id="7fe25-178">如果在重新安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，使用以前删除的 Windows 组名，该 Windows 组将不具有对 BizTalk Server 数据库的访问权。</span><span class="sxs-lookup"><span data-stu-id="7fe25-178">If, when reinstalling [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you use a Windows group name that was previously deleted, the Windows group will not have access to the BizTalk Server databases.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-179">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-179">Cause</span></span>  
 <span data-ttu-id="7fe25-180">删除 Windows 组并具有相同名称创建一个 Windows 组生成的 Windows 组一个新安全标识符 (SID)。</span><span class="sxs-lookup"><span data-stu-id="7fe25-180">Deleting a Windows group and then creating a Windows group with the same name produces a new Security Identifier (SID) for the Windows group.</span></span> <span data-ttu-id="7fe25-181">但是的旧 SID 是仍缓存在 SQL Server 中，因此新的 Windows 组不能登录到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7fe25-181">However the old SID is still cached in SQL Server, so the new Windows group cannot log on to SQL Server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-182">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-182">Resolution</span></span>  
 <span data-ttu-id="7fe25-183">删除 Windows 组时，还必须删除的 Windows 组的 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="7fe25-183">When you delete the Windows group, you must also remove the SQL Server login for the Windows group.</span></span>  
  
#### <a name="biztalk-administrator-cannot-start-the-biztalk-server-administration-console"></a><span data-ttu-id="7fe25-184">BizTalk 管理员不能启动 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7fe25-184">BizTalk Administrator cannot start the BizTalk Server Administration console</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-185">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-185">Problem</span></span>  
 <span data-ttu-id="7fe25-186">BizTalk 管理员 （BizTalk 管理员 Windows 组的成员） 可能不能打开 BizTalk Server 管理控制台中，如果该用户不是本地计算机上 Windows Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="7fe25-186">A BizTalk Administrator (member of the BizTalk Administrators Windows group) may not be able to open the BizTalk Server Administration console if that user is not a member of the Windows Administrators group on the local computer.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-187">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-187">Cause</span></span>  
 <span data-ttu-id="7fe25-188">如果重新安装或重新配置 BizTalk Server，则可以会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="7fe25-188">This problem can occur if you have reinstalled or reconfigured BizTalk Server.</span></span> <span data-ttu-id="7fe25-189">这是因为 SQL Server 使用缓存的安全 Id。</span><span class="sxs-lookup"><span data-stu-id="7fe25-189">This is because SQL Server used cached security IDs.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-190">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-190">Resolution</span></span>  
 <span data-ttu-id="7fe25-191">暂时将 BizTalk 管理员添加到本地计算机上的本地 Windows 管理员组。</span><span class="sxs-lookup"><span data-stu-id="7fe25-191">Temporarily add the BizTalk Administrator to the local Windows Administrators group on the local computer.</span></span> <span data-ttu-id="7fe25-192">已成功打开后在 BizTalk Server 管理控制台，从本地计算机上的本地 Windows 管理员组中删除 BizTalk 管理员。</span><span class="sxs-lookup"><span data-stu-id="7fe25-192">After successfully opening the BizTalk Server Administration console, remove the BizTalk Administrator from the local Windows Administrators group on the local computer.</span></span>  
  
#### <a name="cannot-start-a-host-instance-on-a-remote-computer"></a><span data-ttu-id="7fe25-193">无法在远程计算机上启动主机实例</span><span class="sxs-lookup"><span data-stu-id="7fe25-193">Cannot start a host instance on a remote computer</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-194">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-194">Problem</span></span>  
 <span data-ttu-id="7fe25-195">当在远程计算机上创建 BizTalk 主机实例时，在启动 BizTalk 主机实例时，可能会看到以下错误:"由于启动失败登录失败。"</span><span class="sxs-lookup"><span data-stu-id="7fe25-195">When you create a BizTalk Host instance on a remote computer, you may see the following error when you start the BizTalk Host instance: "Failed to start due to logon failure."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-196">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-196">Cause</span></span>  
 <span data-ttu-id="7fe25-197">如果为运行 BizTalk 主机实例时使用的服务帐号输入了无效凭据，或者该服务帐号没有“以服务方式登录”权限，会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="7fe25-197">This error can occur if you entered invalid credentials for the service account under which the BizTalk Host instance is running, or the service account does not have logon as service rights.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-198">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-198">Resolution</span></span>  
 <span data-ttu-id="7fe25-199">启动 BizTalk 主机实例之前，为远程计算机中的服务帐户分配“以服务方式登录”权限。</span><span class="sxs-lookup"><span data-stu-id="7fe25-199">Assign logon as a service right to the service account in the remote computer before you start the BizTalk Host instance.</span></span> <span data-ttu-id="7fe25-200">这在本地计算机上自动完成，但必须在远程计算机上手动完成。</span><span class="sxs-lookup"><span data-stu-id="7fe25-200">This is done automatically on a local computer, but must be done manually on a remote computer.</span></span>  
  
#### <a name="creating-or-configuring-a-host-instance-on-an-x64-computer-with-the-32-bit-only-option-selected-fails"></a><span data-ttu-id="7fe25-201">在选择了“仅限 32 位”选项的 X64 计算机上创建或配置主机实例失败</span><span class="sxs-lookup"><span data-stu-id="7fe25-201">Creating or configuring a host instance on an X64 computer with the 32-bit only option selected fails</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-202">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-202">Problem</span></span>  
 <span data-ttu-id="7fe25-203">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，在选择了“仅限 32 位”选项（默认选项）的 X64 计算机上创建 BizTalk 主机实例可能会失败。</span><span class="sxs-lookup"><span data-stu-id="7fe25-203">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, creating a BizTalk Host instance on an X64 computer with the 32-bit only option selected (default) may fail.</span></span>  
  
 <span data-ttu-id="7fe25-204">在 BizTalk Server 配置管理器中在 X64 计算机上配置 BizTalk Server 运行时时，在选择了“仅限 32 位”选项的情况下创建进程内或独立的主机实例可能导致服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="7fe25-204">In BizTalk Server Configuration Manager, when configuring the BizTalk Server Runtime on an X64 computer, creating an in-process or isolated host instance with the 32-bit only option selected can cause the service to fail to start.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-205">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-205">Cause</span></span>  
 <span data-ttu-id="7fe25-206">Unknown</span><span class="sxs-lookup"><span data-stu-id="7fe25-206">Unknown</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-207">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-207">Resolution</span></span>  
 <span data-ttu-id="7fe25-208">此问题是间歇性的。</span><span class="sxs-lookup"><span data-stu-id="7fe25-208">This issue is intermittent.</span></span> <span data-ttu-id="7fe25-209">尝试再次创建或配置主机，或者取消选中“仅限 32 位”选项。</span><span class="sxs-lookup"><span data-stu-id="7fe25-209">Attempt to create or configure the host again or deselect the 32-bit only option.</span></span>  
  
#### <a name="host-instance-deletion-does-not-clear-registry-information"></a><span data-ttu-id="7fe25-210">删除主机实例将不会清除注册表信息</span><span class="sxs-lookup"><span data-stu-id="7fe25-210">Host instance deletion does not clear registry information</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-211">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-211">Problem</span></span>  
 <span data-ttu-id="7fe25-212">如果你不是管理员在本地计算机上的删除进程内或独立的主机时，会出现访问被拒绝的错误消息。</span><span class="sxs-lookup"><span data-stu-id="7fe25-212">If you are not an administrator on the local computer, when you delete an in-process or isolated host, an access denied error message appears.</span></span> <span data-ttu-id="7fe25-213">您可以强制删除该主机。</span><span class="sxs-lookup"><span data-stu-id="7fe25-213">You can forcibly delete the host.</span></span> <span data-ttu-id="7fe25-214">但是，删除以这种方式主机不会清除所有相关的注册表信息。</span><span class="sxs-lookup"><span data-stu-id="7fe25-214">However, deleting the host in this manner does not clear all of the related registry information.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-215">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-215">Cause</span></span>  
 <span data-ttu-id="7fe25-216">删除的主机实例相关的注册表信息需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="7fe25-216">Deletion of the registry information related to a host instance requires Administrator privileges.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-217">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-217">Resolution</span></span>  
 <span data-ttu-id="7fe25-218">登录以本地管理员帐户，以便相关的注册表信息也会删除在删除主机之前。</span><span class="sxs-lookup"><span data-stu-id="7fe25-218">Log on as a local Administrator account before deleting the host so that the related registry information is also removed.</span></span>  
  
#### <a name="cannot-delete-a-messagebox-database"></a><span data-ttu-id="7fe25-219">无法删除 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="7fe25-219">Cannot delete a MessageBox database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="7fe25-220">问题</span><span class="sxs-lookup"><span data-stu-id="7fe25-220">Problem</span></span>  
 <span data-ttu-id="7fe25-221">您不能删除 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="7fe25-221">You may not be able to delete a MessageBox database.</span></span> <span data-ttu-id="7fe25-222">如果删除操作失败，可能是负责以下问题之一：</span><span class="sxs-lookup"><span data-stu-id="7fe25-222">If the deletion fails, one of the following issues may be responsible:</span></span>  
  
- <span data-ttu-id="7fe25-223">缓存刷新间隔尚未过期。</span><span class="sxs-lookup"><span data-stu-id="7fe25-223">The cache refresh interval has not expired.</span></span>  
  
- <span data-ttu-id="7fe25-224">MessageBox 数据库包含未完成的实例。</span><span class="sxs-lookup"><span data-stu-id="7fe25-224">The MessageBox database contains incomplete instances.</span></span>  
  
  <span data-ttu-id="7fe25-225">删除失败时缓存刷新间隔尚未过期，如果出现以下错误消息:"由于那里无法剩余工作到 MessageBox 中的，无法删除 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7fe25-225">If the cache refresh interval has not yet expired, the following error message appears when the deletion fails: "MessageBox cannot be deleted since there could be remaining work in the MessageBox.</span></span> <span data-ttu-id="7fe25-226">请确保在 MessageBox 中没有其他未完成的实例，然后重试。"</span><span class="sxs-lookup"><span data-stu-id="7fe25-226">Please ensure that there are no more incomplete instances in the MessageBox, and try again."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="7fe25-227">原因</span><span class="sxs-lookup"><span data-stu-id="7fe25-227">Cause</span></span>  
 <span data-ttu-id="7fe25-228">缓存刷新间隔必须过期禁用 MessageBox 数据库中的发布新消息的时间和删除数据库的时间之间。</span><span class="sxs-lookup"><span data-stu-id="7fe25-228">The cache refresh interval must expire between the time you disable new message publication in the MessageBox database and the time you delete the database.</span></span> <span data-ttu-id="7fe25-229">默认情况下，缓存刷新间隔为 60 秒。</span><span class="sxs-lookup"><span data-stu-id="7fe25-229">By default, the cache refresh interval is 60 seconds.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="7fe25-230">解决方法</span><span class="sxs-lookup"><span data-stu-id="7fe25-230">Resolution</span></span>  
 <span data-ttu-id="7fe25-231">若要删除的 MessageBox 数据库，必须首先禁用该 MessageBox 数据库，发布新消息和缓存刷新间隔过期，然后再删除 MessageBox 数据库，然后等待。</span><span class="sxs-lookup"><span data-stu-id="7fe25-231">To delete a MessageBox database, you must first disable new message publication for that MessageBox database, and then wait until the cache refresh interval expires, before you delete the MessageBox database.</span></span>  
  
 <span data-ttu-id="7fe25-232">如果 MessageBox 数据库包含不完整的服务实例，出现以下错误消息:"由于它可能仍然包含未完成的实例，无法删除 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7fe25-232">If the MessageBox database contains incomplete service instances, the following error message appears: "The MessageBox cannot be deleted because it may still contain incomplete instances.</span></span> <span data-ttu-id="7fe25-233">确保在 MessageBox 中没有未完成的实例，然后重试"。</span><span class="sxs-lookup"><span data-stu-id="7fe25-233">Ensure that there are no incomplete instances in the MessageBox, and try again".</span></span>  
  
 <span data-ttu-id="7fe25-234">您可以使用 BizTalk Server 管理控制台中的“组中心”页查看 MessageBox 数据库中不完整的服务实例。</span><span class="sxs-lookup"><span data-stu-id="7fe25-234">You can view incomplete service instances in the MessageBox database using the Group Hub page in the BizTalk Server Administration Console.</span></span> <span data-ttu-id="7fe25-235">在组中心页中查看服务实例的状态的信息，请参阅[如何搜索跟踪的服务实例](../core/how-to-search-for-tracked-service-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="7fe25-235">For information about viewing the status of service instances in the Group Hub page, see [How to Search for Tracked Service Instances](../core/how-to-search-for-tracked-service-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe25-236">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fe25-236">See Also</span></span>  
 [<span data-ttu-id="7fe25-237">故障排除</span><span class="sxs-lookup"><span data-stu-id="7fe25-237">Troubleshooting</span></span>](../core/troubleshooting.md)
