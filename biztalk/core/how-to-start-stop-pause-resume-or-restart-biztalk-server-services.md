---
title: 步骤重启服务，或关闭 |Microsoft 文档
description: 启动、 停止、 暂停、 继续或重新启动 BizTalk Server 服务，或关闭 BizTalk Server 计算机
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d6449ba-2892-49c6-a697-847608d10ec5
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9860625480c2c3e469736989415b4e1510cf6707
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973403"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a><span data-ttu-id="e5485-103">重新启动 BizTalk 服务，或关闭 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5485-103">Restart BizTalk services, or shut down the BizTalk Server</span></span>

<span data-ttu-id="e5485-104">下表列出了可以启动、停止、暂停、恢复或重新启动的 BizTalk Server 服务：</span><span class="sxs-lookup"><span data-stu-id="e5485-104">The following table lists the BizTalk Server services that you can start, stop, pause, resume, or restart:</span></span>  
  
|<span data-ttu-id="e5485-105">Name</span><span class="sxs-lookup"><span data-stu-id="e5485-105">Name</span></span>|<span data-ttu-id="e5485-106">说明</span><span class="sxs-lookup"><span data-stu-id="e5485-106">Description</span></span>|<span data-ttu-id="e5485-107">启动类型</span><span class="sxs-lookup"><span data-stu-id="e5485-107">Startup Type</span></span>|<span data-ttu-id="e5485-108">依赖关系</span><span class="sxs-lookup"><span data-stu-id="e5485-108">Dependencies</span></span>|  
|----------|-----------------|------------------|------------------|  
|<span data-ttu-id="e5485-109">BizTalk 服务 BizTalk 组：  *\<BizTalkServerApplication\>*</span><span class="sxs-lookup"><span data-stu-id="e5485-109">BizTalk Service BizTalk Group: *\<BizTalkServerApplication\>*</span></span>|<span data-ttu-id="e5485-110">提供 BizTalk Server 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="e5485-110">Provides the BizTalk Server application service.</span></span>|<span data-ttu-id="e5485-111">自动</span><span class="sxs-lookup"><span data-stu-id="e5485-111">Automatic</span></span>|<span data-ttu-id="e5485-112">-企业单一登录 (SSO) 服务</span><span class="sxs-lookup"><span data-stu-id="e5485-112">-   Enterprise Single Sign-On (SSO) Service</span></span><br /><span data-ttu-id="e5485-113">事件日志</span><span class="sxs-lookup"><span data-stu-id="e5485-113">-   Event Log</span></span><br /><span data-ttu-id="e5485-114">-远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="e5485-114">-   Remote Procedure Call (RPC)</span></span>|  
|<span data-ttu-id="e5485-115">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="e5485-115">Enterprise Single Sign-On Service</span></span>|<span data-ttu-id="e5485-116">提供对企业应用程序的单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="e5485-116">Provides single sign-on services to enterprise applications.</span></span>|<span data-ttu-id="e5485-117">自动</span><span class="sxs-lookup"><span data-stu-id="e5485-117">Automatic</span></span>|<span data-ttu-id="e5485-118">已在本地安装 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="e5485-118">With SQL Server installed locally:</span></span><br /><br /> <span data-ttu-id="e5485-119">的系统 COM + 应用程序</span><span class="sxs-lookup"><span data-stu-id="e5485-119">-   COM+ System Application</span></span><br /><span data-ttu-id="e5485-120">-远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="e5485-120">-   Remote Procedure Call (RPC)</span></span><br /><span data-ttu-id="e5485-121">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="e5485-121">-   SQL Server (MSSQLSERVER)</span></span><br /><br /> <span data-ttu-id="e5485-122">已远程安装 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="e5485-122">With SQL Server installed remotely:</span></span><br /><br /> <span data-ttu-id="e5485-123">的系统 COM + 应用程序</span><span class="sxs-lookup"><span data-stu-id="e5485-123">-   COM+ System Application</span></span><br /><span data-ttu-id="e5485-124">-远程过程调用 (RPC) 无</span><span class="sxs-lookup"><span data-stu-id="e5485-124">-   Remote Procedure Call (RPC)None</span></span>|  
|<span data-ttu-id="e5485-125">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="e5485-125">Rule Engine Update Service</span></span>|<span data-ttu-id="e5485-126">通知用户有关部署或取消部署策略的信息。</span><span class="sxs-lookup"><span data-stu-id="e5485-126">Notifies users about the deployment or undeployment of policies.</span></span>|<span data-ttu-id="e5485-127">Automatic</span><span class="sxs-lookup"><span data-stu-id="e5485-127">Automatic</span></span>|<span data-ttu-id="e5485-128">无</span><span class="sxs-lookup"><span data-stu-id="e5485-128">None</span></span>|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a><span data-ttu-id="e5485-129">启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务</span><span class="sxs-lookup"><span data-stu-id="e5485-129">Start, stop, pause, resume, or restart a BizTalk Server service</span></span>  
 <span data-ttu-id="e5485-130">你可以启动、 停止、 暂停、 恢复或通过使用 Services.msc，或者使用命令提示符重新启动 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="e5485-130">You can start, stop, pause, resume, or restart a BizTalk Server service by using Services.msc, or using the command prompt.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e5485-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="e5485-131">Prerequisites</span></span>  
 <span data-ttu-id="e5485-132">若要执行该过程，您必须是本地计算机上 Administrators 组的成员，或者您必须被委派了相应的权限。</span><span class="sxs-lookup"><span data-stu-id="e5485-132">To perform this procedure, you must be a member of the Administrators group on the local computer, or you must have been delegated the appropriate authority.</span></span> <span data-ttu-id="e5485-133">如果该计算机已加入域，则 Domain Admins 组的成员可能可以执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e5485-133">If the computer is joined to a domain, members of the Domain Admins group might be able to perform this procedure.</span></span> <span data-ttu-id="e5485-134">作为安全最佳实践，可考虑使用“运行”来执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e5485-134">As a security best practice, consider using Run as to perform this procedure.</span></span> 
  
### <a name="use-services-in-control-panel"></a><span data-ttu-id="e5485-135">使用控制面板中的服务</span><span class="sxs-lookup"><span data-stu-id="e5485-135">Use Services in Control Panel</span></span>  
  
1.  <span data-ttu-id="e5485-136">打开“服务”。</span><span class="sxs-lookup"><span data-stu-id="e5485-136">Open Services.</span></span> <span data-ttu-id="e5485-137">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="e5485-137">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
2.  <span data-ttu-id="e5485-138">右键单击相应的 BizTalk Server 服务，然后单击**启动**，**停止**，**暂停**，**恢复**，或**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="e5485-138">Right-click the appropriate BizTalk Server service and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
### <a name="use-a-command-prompt"></a><span data-ttu-id="e5485-139">使用命令提示符</span><span class="sxs-lookup"><span data-stu-id="e5485-139">Use a command prompt</span></span>  
  
1.  <span data-ttu-id="e5485-140">从开始菜单中，右键单击**命令提示符**，选择**详细**，然后选择**以管理员身份运行**</span><span class="sxs-lookup"><span data-stu-id="e5485-140">From the start menu, right-click **Command prompt**, select **More**, and select **Run as Administrator**</span></span>
  
2.  <span data-ttu-id="e5485-141">键入以下内容，其中*ServiceName*是你想要启动、 停止、 暂停或恢复的 BizTalk Server 服务的名称：</span><span class="sxs-lookup"><span data-stu-id="e5485-141">Type one of the following, where *ServiceName* is the name of the BizTalk Server service you want to start, stop, pause, or resume:</span></span>  
  
    -   <span data-ttu-id="e5485-142">若要启动服务，则键入：</span><span class="sxs-lookup"><span data-stu-id="e5485-142">To start a service, type:</span></span>  
  
         <span data-ttu-id="e5485-143">**net 开始** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="e5485-143">**net start** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="e5485-144">若要停止服务，则键入：</span><span class="sxs-lookup"><span data-stu-id="e5485-144">To stop a service, type:</span></span>  
  
         <span data-ttu-id="e5485-145">**net stop** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="e5485-145">**net stop** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="e5485-146">若要暂停服务，则键入：</span><span class="sxs-lookup"><span data-stu-id="e5485-146">To pause a service, type:</span></span>  
  
         <span data-ttu-id="e5485-147">**net 暂停** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="e5485-147">**net pause** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="e5485-148">若要恢复服务，则键入：</span><span class="sxs-lookup"><span data-stu-id="e5485-148">To resume a service, type:</span></span>  
  
         <span data-ttu-id="e5485-149">**net 继续** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="e5485-149">**net continue** *ServiceName*</span></span>  

    |<span data-ttu-id="e5485-150">BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="e5485-150">BizTalk service</span></span>|<span data-ttu-id="e5485-151">ServiceName</span><span class="sxs-lookup"><span data-stu-id="e5485-151">ServiceName</span></span>|  
    |---|---|  
    |<span data-ttu-id="e5485-152">BizTalk 服务 BizTalk 组：BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="e5485-152">BizTalk Service BizTalk Group: BizTalkServerApplication</span></span>|<span data-ttu-id="e5485-153">btssvc$biztalkserverapplication</span><span class="sxs-lookup"><span data-stu-id="e5485-153">btssvc$biztalkserverapplication</span></span>|  
    |<span data-ttu-id="e5485-154">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="e5485-154">Enterprise Single Sign-On Service</span></span>|<span data-ttu-id="e5485-155">Entsso</span><span class="sxs-lookup"><span data-stu-id="e5485-155">Entsso</span></span>|  
    |<span data-ttu-id="e5485-156">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="e5485-156">Rule Engine Update Service</span></span>|<span data-ttu-id="e5485-157">ruleengineupdateservice</span><span class="sxs-lookup"><span data-stu-id="e5485-157">ruleengineupdateservice</span></span>|
  
## <a name="shut-down-biztalk-server"></a><span data-ttu-id="e5485-158">关闭 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5485-158">Shut down BizTalk Server</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="e5485-159">先决条件</span><span class="sxs-lookup"><span data-stu-id="e5485-159">Prerequisites</span></span>  
-   <span data-ttu-id="e5485-160">使用是你想要关闭的 BizTalk server 上的本地管理员组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e5485-160">Sign in with an account that is a member of the local administrators group on the BizTalk server that you want to shut down.</span></span> <span data-ttu-id="e5485-161">这是必需的，这样您才能停止服务。</span><span class="sxs-lookup"><span data-stu-id="e5485-161">This is necessary so you can stop services.</span></span>  
-   <span data-ttu-id="e5485-162">使用 BizTalk Server Administrators 组或 BizTalk Server Operators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e5485-162">Sign in with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> 

### <a name="task-overview"></a><span data-ttu-id="e5485-163">任务概述</span><span class="sxs-lookup"><span data-stu-id="e5485-163">Task overview</span></span>
1.  <span data-ttu-id="e5485-164">禁用接收位置，并通过对每个活动应用程序执行部分停止来停止业务流程和发送端口。</span><span class="sxs-lookup"><span data-stu-id="e5485-164">Disable receive locations, and stop orchestrations and send ports by performing a partial stop on every active application.</span></span> <span data-ttu-id="e5485-165">仅当您要删除或重新部署应用程序时才应执行完全停止。</span><span class="sxs-lookup"><span data-stu-id="e5485-165">You should perform a full stop only if you intend to remove or redeploy an application.</span></span> <span data-ttu-id="e5485-166">有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e5485-166">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
2.  <span data-ttu-id="e5485-167">停止主机实例。</span><span class="sxs-lookup"><span data-stu-id="e5485-167">Stop host instances.</span></span> <span data-ttu-id="e5485-168">有关详细信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="e5485-168">For more information, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
3.  <span data-ttu-id="e5485-169">关闭 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="e5485-169">Shut down [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="e5485-170">请参阅**如何开始、 停止、 暂停、 继续或重新启动 BizTalk Server Services** （本主题中）。</span><span class="sxs-lookup"><span data-stu-id="e5485-170">See **How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services** (in this topic).</span></span>
  
4.  <span data-ttu-id="e5485-171">关闭 Internet 信息服务 (IIS)，或停止 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序池和网站。</span><span class="sxs-lookup"><span data-stu-id="e5485-171">Shut down Internet Information Services (IIS), or stop [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application pools and Web sites.</span></span> <span data-ttu-id="e5485-172">如果您要完全关闭服务器，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="e5485-172">If you are going to shut down the server entirely you can skip this step.</span></span> <span data-ttu-id="e5485-173">如果您停止 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的目的是进行维护或者是部署或取消部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序，则应当执行该步骤。</span><span class="sxs-lookup"><span data-stu-id="e5485-173">If you are stopping [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for maintenance or to deploy or undeploy a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, you should perform this step.</span></span> <span data-ttu-id="e5485-174">当您仅停止与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 相关的网站和应用程序池时，其他 IIS 相关进程将继续运行。</span><span class="sxs-lookup"><span data-stu-id="e5485-174">When you stop only the Web sites and application pools associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], other IIS-related processes will continue to run.</span></span>  
  
     <span data-ttu-id="e5485-175">如何继续执行此步骤在某种程度上取决于您使用的 IIS 版本。</span><span class="sxs-lookup"><span data-stu-id="e5485-175">How you proceed with this step depends to some extent on which version of IIS you are using.</span></span> <span data-ttu-id="e5485-176">IIS 6 允许您停止应用程序池和网站。</span><span class="sxs-lookup"><span data-stu-id="e5485-176">IIS 6 permits you to stop application pools and Web sites.</span></span> <span data-ttu-id="e5485-177">通过 IIS 6，您还可以停止 IIS 管理服务，以关闭包括应用程序池和网站在内的所有 IIS 活动。</span><span class="sxs-lookup"><span data-stu-id="e5485-177">With IIS 6 you can also stop the IIS Admin Service to shut down all IIS activity including application pools and Web sites.</span></span> <span data-ttu-id="e5485-178">IIS 7.0 比 IIS 6.0 更加模块化 ， 而且没有可用于停止所有 IIS 7.0 活动的单个开关 ， 因此您需要单独停止网站和应用程序池 。</span><span class="sxs-lookup"><span data-stu-id="e5485-178">IIS 7.0 is more modular than IIS 6.0, and there is no single switch you can use to stop all IIS 7.0 activities, so you will need to stop Web sites and application pools separately.</span></span>  
  
     <span data-ttu-id="e5485-179">应用程序池和 BizTalk Server 使用的虚拟应用程序 （网站和 Web 服务） 的列表，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e5485-179">For a list of application pools and virtual applications (Web sites and Web services) used by BizTalk Server, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="e5485-180">有关启动和停止在 IIS 中的应用程序池的信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513)。</span><span class="sxs-lookup"><span data-stu-id="e5485-180">For information about starting and stopping application pools in IIS, see [http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513).</span></span>  
  
 <span data-ttu-id="e5485-181">有关启动和停止 IIS 中的 Web 服务器的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695)。</span><span class="sxs-lookup"><span data-stu-id="e5485-181">For information about starting and stopping the Web Server in IIS, see [http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5485-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5485-182">See Also</span></span>  
 <span data-ttu-id="e5485-183">[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="e5485-183">[How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="e5485-184">如何停止主机实例</span><span class="sxs-lookup"><span data-stu-id="e5485-184">How to Stop a Host Instance</span></span>](../core/how-to-stop-a-host-instance.md)   