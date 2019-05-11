---
title: 重新启动服务，或关闭的情况下的步骤 |Microsoft Docs
description: 启动、 停止、 暂停、 继续或重新启动 BizTalk Server 服务，或关闭的情况下 BizTalk Server 计算机
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
ms.openlocfilehash: 85e8c353e4a8fa157352aa62238b107a07831465
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333981"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a><span data-ttu-id="2c17b-103">重新启动 BizTalk 服务中，或关闭 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2c17b-103">Restart BizTalk services, or shut down the BizTalk Server</span></span>

<span data-ttu-id="2c17b-104">下表列出了可以启动、 停止、 暂停、 恢复或重新启动的 BizTalk Server 服务：</span><span class="sxs-lookup"><span data-stu-id="2c17b-104">The following table lists the BizTalk Server services that you can start, stop, pause, resume, or restart:</span></span>  
  
|<span data-ttu-id="2c17b-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="2c17b-105">Name</span></span>|<span data-ttu-id="2c17b-106">Description</span><span class="sxs-lookup"><span data-stu-id="2c17b-106">Description</span></span>|<span data-ttu-id="2c17b-107">启动类型</span><span class="sxs-lookup"><span data-stu-id="2c17b-107">Startup Type</span></span>|<span data-ttu-id="2c17b-108">依存关系</span><span class="sxs-lookup"><span data-stu-id="2c17b-108">Dependencies</span></span>|  
|----------|-----------------|------------------|------------------|  
|<span data-ttu-id="2c17b-109">BizTalk 服务 BizTalk 组：*\<BizTalkServerApplication\>*</span><span class="sxs-lookup"><span data-stu-id="2c17b-109">BizTalk Service BizTalk Group: *\<BizTalkServerApplication\>*</span></span>|<span data-ttu-id="2c17b-110">提供 BizTalk Server 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="2c17b-110">Provides the BizTalk Server application service.</span></span>|<span data-ttu-id="2c17b-111">自动</span><span class="sxs-lookup"><span data-stu-id="2c17b-111">Automatic</span></span>|<span data-ttu-id="2c17b-112">企业单一登录 (SSO) 服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-112">-   Enterprise Single Sign-On (SSO) Service</span></span><br /><span data-ttu-id="2c17b-113">事件日志</span><span class="sxs-lookup"><span data-stu-id="2c17b-113">-   Event Log</span></span><br /><span data-ttu-id="2c17b-114">-远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="2c17b-114">-   Remote Procedure Call (RPC)</span></span>|  
|<span data-ttu-id="2c17b-115">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-115">Enterprise Single Sign-On Service</span></span>|<span data-ttu-id="2c17b-116">提供对企业应用程序的单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="2c17b-116">Provides single sign-on services to enterprise applications.</span></span>|<span data-ttu-id="2c17b-117">自动</span><span class="sxs-lookup"><span data-stu-id="2c17b-117">Automatic</span></span>|<span data-ttu-id="2c17b-118">在本地安装的 SQL server:</span><span class="sxs-lookup"><span data-stu-id="2c17b-118">With SQL Server installed locally:</span></span><br /><br /> <span data-ttu-id="2c17b-119">-COM + 系统应用程序</span><span class="sxs-lookup"><span data-stu-id="2c17b-119">-   COM+ System Application</span></span><br /><span data-ttu-id="2c17b-120">-远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="2c17b-120">-   Remote Procedure Call (RPC)</span></span><br /><span data-ttu-id="2c17b-121">-   SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="2c17b-121">-   SQL Server (MSSQLSERVER)</span></span><br /><br /> <span data-ttu-id="2c17b-122">远程安装了 SQL server:</span><span class="sxs-lookup"><span data-stu-id="2c17b-122">With SQL Server installed remotely:</span></span><br /><br /> <span data-ttu-id="2c17b-123">-COM + 系统应用程序</span><span class="sxs-lookup"><span data-stu-id="2c17b-123">-   COM+ System Application</span></span><br /><span data-ttu-id="2c17b-124">-远程过程调用 (RPC) 无</span><span class="sxs-lookup"><span data-stu-id="2c17b-124">-   Remote Procedure Call (RPC)None</span></span>|  
|<span data-ttu-id="2c17b-125">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-125">Rule Engine Update Service</span></span>|<span data-ttu-id="2c17b-126">通知用户有关部署或取消部署策略的信息。</span><span class="sxs-lookup"><span data-stu-id="2c17b-126">Notifies users about the deployment or undeployment of policies.</span></span>|<span data-ttu-id="2c17b-127">Automatic</span><span class="sxs-lookup"><span data-stu-id="2c17b-127">Automatic</span></span>|<span data-ttu-id="2c17b-128">None</span><span class="sxs-lookup"><span data-stu-id="2c17b-128">None</span></span>|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a><span data-ttu-id="2c17b-129">启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-129">Start, stop, pause, resume, or restart a BizTalk Server service</span></span>  
 <span data-ttu-id="2c17b-130">可以启动、 停止、 暂停、 恢复或通过使用 Services.msc，或者使用命令提示符重新启动 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="2c17b-130">You can start, stop, pause, resume, or restart a BizTalk Server service by using Services.msc, or using the command prompt.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2c17b-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="2c17b-131">Prerequisites</span></span>  
 <span data-ttu-id="2c17b-132">若要执行此过程，您必须是本地计算机上 Administrators 组的成员或您必须被委派了适当的权限。</span><span class="sxs-lookup"><span data-stu-id="2c17b-132">To perform this procedure, you must be a member of the Administrators group on the local computer, or you must have been delegated the appropriate authority.</span></span> <span data-ttu-id="2c17b-133">如果将计算机加入到域中，Domain Admins 组的成员可以执行此过程。</span><span class="sxs-lookup"><span data-stu-id="2c17b-133">If the computer is joined to a domain, members of the Domain Admins group might be able to perform this procedure.</span></span> <span data-ttu-id="2c17b-134">作为安全性最佳实践，请考虑使用运行方式来执行此过程。</span><span class="sxs-lookup"><span data-stu-id="2c17b-134">As a security best practice, consider using Run as to perform this procedure.</span></span> 
  
### <a name="use-services-in-control-panel"></a><span data-ttu-id="2c17b-135">使用控制面板中的服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-135">Use Services in Control Panel</span></span>  
  
1.  <span data-ttu-id="2c17b-136">打开服务。</span><span class="sxs-lookup"><span data-stu-id="2c17b-136">Open Services.</span></span> <span data-ttu-id="2c17b-137">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="2c17b-137">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
2.  <span data-ttu-id="2c17b-138">右键单击相应的 BizTalk Server 服务，然后单击**启动**，**停止**，**暂停**，**恢复**，或**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="2c17b-138">Right-click the appropriate BizTalk Server service and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
### <a name="use-a-command-prompt"></a><span data-ttu-id="2c17b-139">使用命令提示符</span><span class="sxs-lookup"><span data-stu-id="2c17b-139">Use a command prompt</span></span>  
  
1.  <span data-ttu-id="2c17b-140">从开始菜单中，右键单击**命令提示符**，选择**详细**，然后选择**以管理员身份运行**</span><span class="sxs-lookup"><span data-stu-id="2c17b-140">From the start menu, right-click **Command prompt**, select **More**, and select **Run as Administrator**</span></span>
  
2.  <span data-ttu-id="2c17b-141">键入以下内容，其中*ServiceName*是你想要启动、 停止、 暂停或恢复的 BizTalk Server 服务的名称：</span><span class="sxs-lookup"><span data-stu-id="2c17b-141">Type one of the following, where *ServiceName* is the name of the BizTalk Server service you want to start, stop, pause, or resume:</span></span>  
  
    -   <span data-ttu-id="2c17b-142">若要启动服务，请键入：</span><span class="sxs-lookup"><span data-stu-id="2c17b-142">To start a service, type:</span></span>  
  
         <span data-ttu-id="2c17b-143">**net start** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="2c17b-143">**net start** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="2c17b-144">若要停止服务，请键入：</span><span class="sxs-lookup"><span data-stu-id="2c17b-144">To stop a service, type:</span></span>  
  
         <span data-ttu-id="2c17b-145">**net stop** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="2c17b-145">**net stop** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="2c17b-146">若要暂停服务，请键入：</span><span class="sxs-lookup"><span data-stu-id="2c17b-146">To pause a service, type:</span></span>  
  
         <span data-ttu-id="2c17b-147">**net pause** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="2c17b-147">**net pause** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="2c17b-148">若要恢复服务，请键入：</span><span class="sxs-lookup"><span data-stu-id="2c17b-148">To resume a service, type:</span></span>  
  
         <span data-ttu-id="2c17b-149">**net continue** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="2c17b-149">**net continue** *ServiceName*</span></span>  

    |<span data-ttu-id="2c17b-150">BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-150">BizTalk service</span></span>|<span data-ttu-id="2c17b-151">ServiceName</span><span class="sxs-lookup"><span data-stu-id="2c17b-151">ServiceName</span></span>|  
    |---|---|  
    |<span data-ttu-id="2c17b-152">BizTalk 服务 BizTalk 组：BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="2c17b-152">BizTalk Service BizTalk Group: BizTalkServerApplication</span></span>|<span data-ttu-id="2c17b-153">btssvc$biztalkserverapplication</span><span class="sxs-lookup"><span data-stu-id="2c17b-153">btssvc$biztalkserverapplication</span></span>|  
    |<span data-ttu-id="2c17b-154">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-154">Enterprise Single Sign-On Service</span></span>|<span data-ttu-id="2c17b-155">Entsso</span><span class="sxs-lookup"><span data-stu-id="2c17b-155">Entsso</span></span>|  
    |<span data-ttu-id="2c17b-156">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="2c17b-156">Rule Engine Update Service</span></span>|<span data-ttu-id="2c17b-157">ruleengineupdateservice</span><span class="sxs-lookup"><span data-stu-id="2c17b-157">ruleengineupdateservice</span></span>|
  
## <a name="shut-down-biztalk-server"></a><span data-ttu-id="2c17b-158">关闭 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2c17b-158">Shut down BizTalk Server</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="2c17b-159">先决条件</span><span class="sxs-lookup"><span data-stu-id="2c17b-159">Prerequisites</span></span>  
-   <span data-ttu-id="2c17b-160">使用该帐户是你想要关闭的情况下在 BizTalk server 上的本地管理员组的成员登录。</span><span class="sxs-lookup"><span data-stu-id="2c17b-160">Sign in with an account that is a member of the local administrators group on the BizTalk server that you want to shut down.</span></span> <span data-ttu-id="2c17b-161">这是必需的因此可以停止服务。</span><span class="sxs-lookup"><span data-stu-id="2c17b-161">This is necessary so you can stop services.</span></span>  
-   <span data-ttu-id="2c17b-162">使用 BizTalk Server Administrators 组或 BizTalk Server Operators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="2c17b-162">Sign in with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> 

### <a name="task-overview"></a><span data-ttu-id="2c17b-163">任务概述</span><span class="sxs-lookup"><span data-stu-id="2c17b-163">Task overview</span></span>
1. <span data-ttu-id="2c17b-164">禁用接收位置，并停止业务流程和发送端口通过对每个活动的应用程序执行部分停止。</span><span class="sxs-lookup"><span data-stu-id="2c17b-164">Disable receive locations, and stop orchestrations and send ports by performing a partial stop on every active application.</span></span> <span data-ttu-id="2c17b-165">仅当你想要删除或重新部署应用程序，你应执行完全停止。</span><span class="sxs-lookup"><span data-stu-id="2c17b-165">You should perform a full stop only if you intend to remove or redeploy an application.</span></span> <span data-ttu-id="2c17b-166">有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2c17b-166">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
2. <span data-ttu-id="2c17b-167">停止主机实例。</span><span class="sxs-lookup"><span data-stu-id="2c17b-167">Stop host instances.</span></span> <span data-ttu-id="2c17b-168">有关详细信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="2c17b-168">For more information, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
3. <span data-ttu-id="2c17b-169">关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="2c17b-169">Shut down [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="2c17b-170">请参阅**如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services** （在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="2c17b-170">See **How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services** (in this topic).</span></span>
  
4. <span data-ttu-id="2c17b-171">关闭关闭 Internet 信息服务 (IIS) 或停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序池和网站。</span><span class="sxs-lookup"><span data-stu-id="2c17b-171">Shut down Internet Information Services (IIS), or stop [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application pools and Web sites.</span></span> <span data-ttu-id="2c17b-172">如果想要关闭服务器完全可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="2c17b-172">If you are going to shut down the server entirely you can skip this step.</span></span> <span data-ttu-id="2c17b-173">如果您要停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行维护或进行部署或取消部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序中，应执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="2c17b-173">If you are stopping [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for maintenance or to deploy or undeploy a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, you should perform this step.</span></span> <span data-ttu-id="2c17b-174">当停止网站和应用程序池与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，其他与 IIS 相关的进程将继续运行。</span><span class="sxs-lookup"><span data-stu-id="2c17b-174">When you stop only the Web sites and application pools associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], other IIS-related processes will continue to run.</span></span>  
  
    <span data-ttu-id="2c17b-175">如何继续进行此步骤取决于您所使用的 IIS 版本在某种程度上。</span><span class="sxs-lookup"><span data-stu-id="2c17b-175">How you proceed with this step depends to some extent on which version of IIS you are using.</span></span> <span data-ttu-id="2c17b-176">IIS 6 允许您停止应用程序池和网站。</span><span class="sxs-lookup"><span data-stu-id="2c17b-176">IIS 6 permits you to stop application pools and Web sites.</span></span> <span data-ttu-id="2c17b-177">使用 IIS 6 还可以停止 IIS 管理服务，以关闭包括应用程序池和网站的所有 IIS 活动。</span><span class="sxs-lookup"><span data-stu-id="2c17b-177">With IIS 6 you can also stop the IIS Admin Service to shut down all IIS activity including application pools and Web sites.</span></span> <span data-ttu-id="2c17b-178">IIS 7.0 比 IIS 6.0 更加模块化，并且没有可用于停止 IIS 7.0 的所有活动，因此将需要单独都停止网站和应用程序池的单个开关。</span><span class="sxs-lookup"><span data-stu-id="2c17b-178">IIS 7.0 is more modular than IIS 6.0, and there is no single switch you can use to stop all IIS 7.0 activities, so you will need to stop Web sites and application pools separately.</span></span>  
  
    <span data-ttu-id="2c17b-179">应用程序池和 BizTalk Server 使用的虚拟应用程序 （网站和 Web 服务） 的列表，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2c17b-179">For a list of application pools and virtual applications (Web sites and Web services) used by BizTalk Server, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
   <span data-ttu-id="2c17b-180">有关启动和停止应用程序池在 IIS 中的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=140513 ](http://go.microsoft.com/fwlink/?LinkID=140513)。</span><span class="sxs-lookup"><span data-stu-id="2c17b-180">For information about starting and stopping application pools in IIS, see [http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513).</span></span>  
  
   <span data-ttu-id="2c17b-181">有关启动和停止 IIS 中的 Web 服务器的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=140695 ](http://go.microsoft.com/fwlink/?LinkId=140695)。</span><span class="sxs-lookup"><span data-stu-id="2c17b-181">For information about starting and stopping the Web Server in IIS, see [http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c17b-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c17b-182">See Also</span></span>  
 <span data-ttu-id="2c17b-183">[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="2c17b-183">[How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="2c17b-184">如何停止主机实例</span><span class="sxs-lookup"><span data-stu-id="2c17b-184">How to Stop a Host Instance</span></span>](../core/how-to-stop-a-host-instance.md)   