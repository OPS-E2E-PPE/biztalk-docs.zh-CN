---
title: 如何配置 Workflow Foundation 应用程序用于侦听 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6929161360b2b3af1bfe221e9fa3583d93b566
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967800"
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a><span data-ttu-id="5e0d3-102">如何配置 Workflow Foundation 应用程序用于侦听</span><span class="sxs-lookup"><span data-stu-id="5e0d3-102">How to Configure a Workflow Foundation Application for Interception</span></span>
<span data-ttu-id="5e0d3-103">必须安装 BAM 侦听器软件并配置应用程序以使用[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器服务，然后才能开始收集 BAM 活动数据。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-103">You must install the BAM interceptor software and configure your application to use the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor service before you can begin collecting BAM activity data.</span></span> <span data-ttu-id="5e0d3-104">我们假定您已成功安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 及其依存关系，并至少创建了一个 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-104">It is assumed that you have successfully installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and its dependencies and have created at least one BizTalk group.</span></span>  
  
## <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="5e0d3-105">安装 Bam-eventing 软件</span><span class="sxs-lookup"><span data-stu-id="5e0d3-105">Installing the BAM-Eventing Software</span></span>  
 <span data-ttu-id="5e0d3-106">在可以将您的 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 应用程序配置为对 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 使用 BAM 侦听器之前，您必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序安装 BAM-Eventing 软件。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-106">Before you can configure your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application to use the BAM interceptor for [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="5e0d3-107">有关安装 Bam-eventing 软件和注册性能计数器的详细信息，请参阅[安装 Bam-eventing 软件](../core/installing-the-bam-eventing-software.md)。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-107">For more information about installing the BAM-Eventing software and registering the performance counters, see [Installing the BAM-Eventing Software](../core/installing-the-bam-eventing-software.md).</span></span>  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a><span data-ttu-id="5e0d3-108">配置 Windows Workflow Foundation 应用程序用于跟踪</span><span class="sxs-lookup"><span data-stu-id="5e0d3-108">Configuring a Windows Workflow Foundation Application for Tracking</span></span>  
 <span data-ttu-id="5e0d3-109">必须完成四项任务后，[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 应用程序才能开始编写 BAM 事件信息：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-109">Four tasks must be completed before your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application can begin writing BAM event information:</span></span>  
  
- <span data-ttu-id="5e0d3-110">必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM 工具创建观察模型，然后使用 BAM 管理器命令行工具 (bm.exe) 部署该模型。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-110">An observation model must be created by using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM tools and then deployed by using the BAM Manager command-line tool (bm.exe).</span></span>  
  
- <span data-ttu-id="5e0d3-111">必须创建和使用 BAM 管理器命令行的工具 (bm.exe) 部署侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-111">An interceptor configuration file must be created and deployed by using the BAM Manager command line-tool (bm.exe).</span></span>  
  
- <span data-ttu-id="5e0d3-112">运行主机应用程序的用户必须是相应的 BAM 活动事件编写器的成员 (bam_\<活动\>_EventWriter) SQL Server 角色，以使应用程序读取侦听器配置信息和写入到 BAM 活动中。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-112">The user running the host application must be a member of the appropriate BAM activity event writer (bam_\<activity\>_EventWriter) SQL Server roles to enable the application to read the interceptor configuration information and write to the BAM activities.</span></span>  
  
- <span data-ttu-id="5e0d3-113">必须修改 App.config 文件和该应用程序本身才能加载 BAM 跟踪服务并重新启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-113">The App.config file or the application itself must be modified to load the BAM tracking service and then restart the application.</span></span>  
  
  <span data-ttu-id="5e0d3-114">只有成功完成这些任务之后，事件才开始出现在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-114">Only after these tasks have been successfully completed will events begin appearing in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM database.</span></span>  
  
### <a name="deploying-an-observation-model"></a><span data-ttu-id="5e0d3-115">部署观察模型</span><span class="sxs-lookup"><span data-stu-id="5e0d3-115">Deploying an Observation Model</span></span>  
 <span data-ttu-id="5e0d3-116">您必须先部署观察模型，然后才能在应用程序中部署侦听器配置文件或捕获 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-116">You must have an observation model deployed before you can deploy an interceptor configuration file or capture BAM activities in your application.</span></span>  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a><span data-ttu-id="5e0d3-117">若要使用 bm.exe 部署观察模型</span><span class="sxs-lookup"><span data-stu-id="5e0d3-117">To deploy an observation model by using bm.exe</span></span>  
  
1. <span data-ttu-id="5e0d3-118">单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-118">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  
  
2. <span data-ttu-id="5e0d3-119">类型**cmd**中**打开**字段，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-119">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="5e0d3-120">使用更改目录命令转至包含要部署的观察模型的目录。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-120">Use the change directory command to move to the directory containing the observation model to deploy.</span></span> <span data-ttu-id="5e0d3-121">例如， **cd c:\businessprocess\Orders**。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-121">For example, **cd c:\businessprocess\Orders**.</span></span>  
  
4. <span data-ttu-id="5e0d3-122">使用 bm.exe 部署观察模型：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-122">Deploy the observation model by using bm.exe:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="5e0d3-123">Tracking\BM.exe 部署所有-definitionfile:\<*definitionfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="5e0d3-123">Tracking\BM.exe deploy-all -definitionfile:\<*definitionfile.xml*\></span></span>  
  
    <span data-ttu-id="5e0d3-124">请确保您替换\< *definitionfile.xml* \>与你想要部署的观察文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-124">Make sure you replace \<*definitionfile.xml*\> with the name of the observation file you want to deploy.</span></span> <span data-ttu-id="5e0d3-125">有关更多选项，请参阅[侦听器管理命令](../core/interceptor-management-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-125">For more options see [Interceptor Management Commands](../core/interceptor-management-commands.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5e0d3-126">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="5e0d3-127">类型**退出**，然后按 ENTER 以关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-127">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
### <a name="deploying-an-interceptor-configuration-file"></a><span data-ttu-id="5e0d3-128">部署侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="5e0d3-128">Deploying an Interceptor Configuration File</span></span>  
 <span data-ttu-id="5e0d3-129">你的应用程序可以捕获 BAM 活动之前，必须部署侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-129">You must deploy an interceptor configuration file before your application can capture BAM activities.</span></span>  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a><span data-ttu-id="5e0d3-130">若要使用 bm.exe 部署侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="5e0d3-130">To deploy an interceptor configuration file by using bm.exe</span></span>  
  
1. <span data-ttu-id="5e0d3-131">单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-131">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  
  
2. <span data-ttu-id="5e0d3-132">类型**cmd**中**打开**字段，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-132">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="5e0d3-133">使用更改目录命令转至包含要部署的侦听器配置文件的目录。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-133">Use the change directory command to move to the directory containing the interceptor configuration file to deploy.</span></span> <span data-ttu-id="5e0d3-134">例如， **cd c:\businessprocess\Orders**。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-134">For example, **cd c:\businessprocess\Orders**.</span></span>  
  
4. <span data-ttu-id="5e0d3-135">使用 bm.exe 部署侦听器配置文件：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-135">Deploy the interceptor configuration file by using bm.exe:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="5e0d3-136">Tracking\BM.exe 部署侦听器-filename:\<*icfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="5e0d3-136">Tracking\BM.exe deploy-interceptor -filename:\<*icfile.xml*\></span></span>  
  
    <span data-ttu-id="5e0d3-137">请确保您替换\< *icfile.xml* \>具有你想要部署侦听器配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-137">Make sure you replace \<*icfile.xml*\> with the name of the interceptor configuration file you want to deploy.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5e0d3-138">可以使用 **-Force: True**标志来覆盖具有名称相同的侦听器配置文件中的现有事件源。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-138">You can use the **-Force:True** flag to override existing event sources with the same name(s) as those in your interceptor configuration file.</span></span> <span data-ttu-id="5e0d3-139">如果这样做，请确保使用备份现有配置**get 侦听器**命令。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-139">If you do so, make sure you back up the existing configuration by using the **get-interceptor** command.</span></span> <span data-ttu-id="5e0d3-140">使用 -Force:True 标志可能会删除所有引用被覆盖的事件源的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-140">Using the -Force:True flag could delete any interceptor configurations that reference the event sources being overwritten.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5e0d3-141">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="5e0d3-142">类型**退出**，然后按 ENTER 以关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-142">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
   <span data-ttu-id="5e0d3-143">如果已部署了你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序中，直到下一个轮询间隔将不加载新配置。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-143">If you have already deployed your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application, the new configuration will not be loaded until the next polling interval.</span></span> <span data-ttu-id="5e0d3-144">但是，如果对应用程序进行配置后重新启动它，则将立即提取该配置。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-144">However, if you configure your application and restart it, the configuration will be picked up immediately.</span></span>  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a><span data-ttu-id="5e0d3-145">将用户添加到相应的 BAM 活动角色</span><span class="sxs-lookup"><span data-stu-id="5e0d3-145">Adding the User to the Appropriate BAM Activity Role</span></span>  
 <span data-ttu-id="5e0d3-146">BAM 侦听器框架使用每个活动的 SQL Server 角色控制对活动和配置信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-146">The BAM Interceptor Framework uses per-activity SQL Server roles to control access to activities and configuration information.</span></span> <span data-ttu-id="5e0d3-147">必须添加运行的用户帐户在[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]到 BAM 主导入数据库中相应的 BAM 活动角色的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-147">You must add the user account running your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application to the appropriate BAM activity role(s) in the BAM Primary Import database.</span></span>  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a><span data-ttu-id="5e0d3-148">将该应用程序配置为加载 BAM 跟踪服务</span><span class="sxs-lookup"><span data-stu-id="5e0d3-148">Configuring the Application to Load the BAM Tracking Service</span></span>  
 <span data-ttu-id="5e0d3-149">有三种方案用于加载 BAM 跟踪服务中的你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-149">There are three scenarios for loading the BAM tracking service in your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application:</span></span>  
  
- <span data-ttu-id="5e0d3-150">如果你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序已使用 WorkflowRuntime 加载[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]配置部分中，可以添加 BAM 跟踪服务信息对现有节。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-150">If your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application already uses WorkflowRuntime to load a [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] configuration section, you can added BAM tracking service information to the existing section.</span></span>  
  
- <span data-ttu-id="5e0d3-151">如果你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序不使用 WorkflowRuntime 加载[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]配置部分中，你将需要添加代码以从应用程序配置文件加载自定义部分。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-151">If your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application does not use WorkflowRuntime to load a [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] configuration section, you will have to add code to load a custom section from your application configuration file.</span></span> <span data-ttu-id="5e0d3-152">您必须创建该配置部分，然后将 BAM 跟踪服务信息添加到该配置部分。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-152">You will have to create the section and add the BAM tracking service information to it.</span></span>  
  
- <span data-ttu-id="5e0d3-153">如果您愿意硬编码配置，则可以使用[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]API 以编程方式加载的跟踪服务不使用配置文件，或若要从自定义源加载配置。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-153">If you prefer to hard-code the configuration, you can use the [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] API to programmatically load the tracking service without a configuration file, or to load the configuration from a custom source.</span></span>  
  
  <span data-ttu-id="5e0d3-154">配置时[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-154">When configuring the [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application, note the following considerations:</span></span>  
  
- <span data-ttu-id="5e0d3-155">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]侦听器支持一个 WorkflowRuntime 添加仅一个 BamTrackingService。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-155">The [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] interceptor supports only one BamTrackingService per one WorkflowRuntime.</span></span>  
  
- <span data-ttu-id="5e0d3-156">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]侦听器支持每个应用程序域的多个 BamTrackingService 实例。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-156">The [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] interceptor supports multiple BamTrackingService instances per application domain.</span></span>  
  
  -   <span data-ttu-id="5e0d3-157">N 个 WorkflowRuntime 支持 N 个 BamTrackingService。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-157">N number of BamTrackingService is supported for N number of WorkflowRuntime.</span></span>  
  
- <span data-ttu-id="5e0d3-158">如果不同的连接字符串用于同一应用程序域中的不同 BamTrackingService 实例，侦听器将引发异常。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-158">The interceptor raises an exception if different connection strings are used for separate BamTrackingService instances in the same application domain.</span></span>  
  
- <span data-ttu-id="5e0d3-159">侦听器从其启动的首个 BamTrackingService 实例获取 IC 轮询间隔值。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-159">The interceptor obtains the IC polling interval value from the first BamTrackingService instance that starts.</span></span>  
  
- <span data-ttu-id="5e0d3-160">应用程序域中的最后一个 BamTrackingService 停止后，侦听器将停止 IC 轮询线程</span><span class="sxs-lookup"><span data-stu-id="5e0d3-160">The interceptor stops the IC polling thread when last BamTrackingService in application domain is stopped</span></span>  
  
  <span data-ttu-id="5e0d3-161">有关 WorkflowRuntime 和加载配置信息的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=83314 ](http://go.microsoft.com/fwlink/?LinkId=83314)。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-161">For more information on WorkflowRuntime and loading configuration information, see [http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314).</span></span>  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a><span data-ttu-id="5e0d3-162">为 BAM 跟踪服务配置 App.config 文件</span><span class="sxs-lookup"><span data-stu-id="5e0d3-162">To configure the App.config file for the BAM tracking service</span></span>  
  
1.  <span data-ttu-id="5e0d3-163">打开与您的应用程序关联的 App.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-163">Open the App.config file associated with your application.</span></span> <span data-ttu-id="5e0d3-164">可以使用 Notepad.exe 或其他文本编辑器执行此任务。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-164">You can use Notepad.exe or another text editor for this task.</span></span>  
  
2.  <span data-ttu-id="5e0d3-165">添加 BAM 跟踪服务，方法为将以下配置信息插入 App.config 文件。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-165">Add the BAM Tracking service by inserting the following configuration information into the App.config file.</span></span> <span data-ttu-id="5e0d3-166">此类信息应放置为 `configuration` 元素的子级。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-166">It should be positioned so that it is a child of the `configuration` element.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e0d3-167">此部分元素应与在使用 WorkflowRuntime 类时您的应用程序代码所使用的名称对应。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-167">The section element should correspond to the name used by your application code when using the WorkflowRuntime class.</span></span>  
  
    ```  
    <!-- The element name must match the one expected by WorkflowRuntime in your WF application -->  
    <WorkflowServiceContainer>  
      <Services>  
        <add type="Microsoft.BizTalk.Bam.Interceptors.Workflow.BamTrackingService, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  
       ConnectionString="Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"   
          PollingIntervalSec="5"/>  
        </Services>  
    </WorkflowServiceContainer>  
    ```  
  
3.  <span data-ttu-id="5e0d3-168">修改**ConnectionString**属性以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-168">Modify the **ConnectionString** attribute to match your environment.</span></span>  
  
4.  <span data-ttu-id="5e0d3-169">重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-169">Restart your application.</span></span>  
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a><span data-ttu-id="5e0d3-170">修改应用程序以加载自定义配置部分</span><span class="sxs-lookup"><span data-stu-id="5e0d3-170">To modify your application to load a custom configuration section</span></span>  
  
1.  <span data-ttu-id="5e0d3-171">在 Visual Studio 中打开 Windows Workflow Foundation 项目。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-171">Open your Windows Workflow Foundation project in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5e0d3-172">将带有适当参数的 BamTrackingService 新实例添加到应用程序的 WorkflowRuntime 实例：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-172">Add a new instance of BamTrackingService with appropriate parameters to the application's instance of WorkflowRuntime:</span></span>  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  <span data-ttu-id="5e0d3-173">重新编译并部署修改后的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-173">Recompile and deploy the modified application.</span></span>  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a><span data-ttu-id="5e0d3-174">修改应用程序以通过编程方式加载 BAM 跟踪服务</span><span class="sxs-lookup"><span data-stu-id="5e0d3-174">To modify your application to programmatically load the BAM tracking service</span></span>  
  
1.  <span data-ttu-id="5e0d3-175">在 Visual Studio 中打开 Windows Workflow Foundation 项目。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-175">Open your Windows Workflow Foundation project in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5e0d3-176">将带有适当参数的 BamTrackingService 新实例添加到应用程序的 WorkflowRuntime 实例：</span><span class="sxs-lookup"><span data-stu-id="5e0d3-176">Add a new instance of BamTrackingService with appropriate parameters to the application's instance of WorkflowRuntime:</span></span>  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     <span data-ttu-id="5e0d3-177">根据环境的具体情况，您可以添加或删除参数。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-177">You can add or remove parameters based on your specific environment.</span></span>  
  
3.  <span data-ttu-id="5e0d3-178">重新编译并部署修改后的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e0d3-178">Recompile and deploy the modified application.</span></span>