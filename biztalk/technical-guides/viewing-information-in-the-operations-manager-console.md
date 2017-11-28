---
title: "在 Operations Manager 控制台中查看信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6acdf425-4c36-4d89-9493-81b33481fe6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 687932839c379ed9589a51baae0ae8562f4af705
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-information-in-the-operations-manager-console"></a><span data-ttu-id="3e7df-102">在 Operations Manager 控制台中查看信息</span><span class="sxs-lookup"><span data-stu-id="3e7df-102">Viewing Information in the Operations Manager Console</span></span>
<span data-ttu-id="3e7df-103">使用提供的视图[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，以了解当前的可用性、 配置、 运行状况，以及 BizTalk Server 环境的性能。</span><span class="sxs-lookup"><span data-stu-id="3e7df-103">Use the views provided with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack to understand the current availability, configuration, health, and performance of your BizTalk Server environment.</span></span> <span data-ttu-id="3e7df-104">视图可能会包含很长的对象列表。</span><span class="sxs-lookup"><span data-stu-id="3e7df-104">A view can contain a lengthy list of objects.</span></span> <span data-ttu-id="3e7df-105">若要查找特定对象或对象组，您可以使用 Operations Manager 工具栏上的“作用域”、“搜索”和“查找”按钮。</span><span class="sxs-lookup"><span data-stu-id="3e7df-105">To find a specific object or group of objects, you can use the Scope, Search, and Find buttons on the Operations Manager toolbar.</span></span> <span data-ttu-id="3e7df-106">有关详细信息，请参阅如何管理监视数据使用作用域、 搜索，并在 Operations Manager 2007 R2\2012 帮助中查找主题。</span><span class="sxs-lookup"><span data-stu-id="3e7df-106">For more information, see the How to Manage Monitoring Data Using Scope, Search, and Find topic in Operations Manager 2007 R2\2012 Help.</span></span>  
  
 <span data-ttu-id="3e7df-107">以下视图正下方列出 **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 在操作控制台的监视窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="3e7df-107">The following views are listed directly under **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** node in the Monitoring pane of the Operations Console.</span></span>  
  
-   <span data-ttu-id="3e7df-108">**应用程序视图**: BizTalk 管理员有兴趣监视状态和运行状况的各种 BizTalk 服务器项目，如业务流程的应用程序发送端口、 接收位置，依此类推。</span><span class="sxs-lookup"><span data-stu-id="3e7df-108">**Application Views**: A BizTalk administrator is interested in monitoring the state and health of various BizTalk Server artifacts and applications such as orchestrations send ports, receive locations, and so on.</span></span>  
  
-   <span data-ttu-id="3e7df-109">**部署视图**： 企业 IT 管理员感兴趣的状态和承载 SQL Server 的机数据库，SSO 服务，主机实例机，IIS 承载的计算机的各种企业部署的运行状况监视网络服务，依次类推。</span><span class="sxs-lookup"><span data-stu-id="3e7df-109">**Deployment Views**: An enterprise IT administrator is interested in monitoring the state and health of the various enterprise deployments the machines hosting the SQL Server databases, machines hosting the SSO service, host instance machines, IIS, network services, and so on.</span></span>  
  
## <a name="application-views"></a><span data-ttu-id="3e7df-110">应用程序视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-110">Application Views</span></span>  
 <span data-ttu-id="3e7df-111">应用程序视图包含下表中描述的元素。</span><span class="sxs-lookup"><span data-stu-id="3e7df-111">Application views contain the elements described in the following table.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-112">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-112">Elements</span></span>  
  
|<span data-ttu-id="3e7df-113">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-113">View Name</span></span>|<span data-ttu-id="3e7df-114">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-115">应用程序状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-115">Application State View</span></span>|<span data-ttu-id="3e7df-116">这是一个仪表板视图，显示 BizTalk 应用程序的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-116">This is a dashboard view that displays the health of a BizTalk application.</span></span> <span data-ttu-id="3e7df-117">BizTalk 应用程序的运行状况取决于其构成的项目，比如业务流程，发送端口组、 发送端口、 接收端口和接收位置的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-117">The health of BizTalk application depends on the health of its constituent artifacts such as Orchestrations, Send Port Group, Send Port, Receive Port, and Receive Location.</span></span> <span data-ttu-id="3e7df-118">详细信息视图窗格中提供的托管的 BizTalk 应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-118">The Details View pane provides the properties of the hosted BizTalk application.</span></span>|  
|<span data-ttu-id="3e7df-119">组状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-119">Group State View</span></span>|<span data-ttu-id="3e7df-120">这是一个仪表板视图，显示 BizTalk 组的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-120">This is a dashboard view that displays the health of a BizTalk group.</span></span> <span data-ttu-id="3e7df-121">BizTalk 组的运行状况取决于 BizTalk 主机和 BizTalk 应用程序的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-121">The health of a BizTalk group depends on the health of BizTalk host and BizTalk applications.</span></span> <span data-ttu-id="3e7df-122">详细信息视图窗格中提供的 BizTalk 组的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-122">The Details View pane provides the properties of the BizTalk group.</span></span>|  
|<span data-ttu-id="3e7df-123">主机状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-123">Host State View</span></span>|<span data-ttu-id="3e7df-124">这是一个仪表板视图，显示 BizTalk 主机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-124">This is a dashboard view that displays the health of a BizTalk host.</span></span> <span data-ttu-id="3e7df-125">BizTalk 主机的运行状况取决于的托管的 BizTalk 应用程序实例的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-125">The health of a BizTalk host depends on the health of the instances of the hosted BizTalk applications.</span></span> <span data-ttu-id="3e7df-126">详细信息视图窗格提供 BizTalk 主机的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-126">The Details View pane provides the properties of the BizTalk host.</span></span>|  
  
#### <a name="application-artifacts-views"></a><span data-ttu-id="3e7df-127">应用程序项目视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-127">Application Artifacts Views</span></span>  
 <span data-ttu-id="3e7df-128">应用程序项目视图中所包含下表中描述的元素。</span><span class="sxs-lookup"><span data-stu-id="3e7df-128">Application artifacts views contain the elements described in the following table.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-129">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-129">Elements</span></span>  
  
|<span data-ttu-id="3e7df-130">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-130">View Name</span></span>|<span data-ttu-id="3e7df-131">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-132">业务流程状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-132">Orchestrations State View</span></span>|<span data-ttu-id="3e7df-133">显示的配置和运行时状态的业务流程的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e7df-133">Displays the configuration and runtime state of Orchestration for the hosted application.</span></span>|  
|<span data-ttu-id="3e7df-134">接收位置状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-134">Receive Location State View</span></span>|<span data-ttu-id="3e7df-135">显示的配置和运行时状态的接收位置的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e7df-135">Displays the configuration and runtime state of Receive Location for the hosted application.</span></span>|  
|<span data-ttu-id="3e7df-136">接收端口状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-136">Receive Ports State View</span></span>|<span data-ttu-id="3e7df-137">显示的配置和运行时状态接收端口的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e7df-137">Displays the configuration and runtime state of Receive Ports for the hosted application.</span></span>|  
|<span data-ttu-id="3e7df-138">发送端口组状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-138">Send Port Groups State View</span></span>|<span data-ttu-id="3e7df-139">显示的配置和运行时状态发送端口组的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e7df-139">Displays the configuration and runtime state of Send Port Group for the hosted application.</span></span>|  
|<span data-ttu-id="3e7df-140">发送端口状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-140">Send Port State View</span></span>|<span data-ttu-id="3e7df-141">显示的配置和运行时状态发送端口的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e7df-141">Displays the configuration and runtime state of Send Port for the hosted application.</span></span>|  
  
## <a name="deployment-views"></a><span data-ttu-id="3e7df-142">部署视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-142">Deployment Views</span></span>  
 <span data-ttu-id="3e7df-143">部署视图包含下表中描述的元素。</span><span class="sxs-lookup"><span data-stu-id="3e7df-143">Deployment views contain the elements described in the following table.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-144">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-144">Elements</span></span>  
  
|<span data-ttu-id="3e7df-145">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-145">View Name</span></span>|<span data-ttu-id="3e7df-146">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-146">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-147">部署状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-147">Deployment State View</span></span>|<span data-ttu-id="3e7df-148">这是一个仪表板视图，显示 BizTalk 部署组的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-148">This is a dashboard view that displays the health of a BizTalk deployment group.</span></span> <span data-ttu-id="3e7df-149">BizTalk 部署组的运行状况取决于其构成的运行时服务器组件，如 BAM 角色、 规则引擎角色、 BizTalk 运行时角色和 BizTalk 主机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-149">The health of the BizTalk deployment group depends on the health of its constituent runtime server components such as BAM Role, Rule Engine Role, BizTalk Run-time Role and BizTalk Host.</span></span> <span data-ttu-id="3e7df-150">详细信息视图窗格提供 BizTalk 部署组的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-150">The Details View pane provides the properties of the BizTalk deployment group.</span></span>|  
|<span data-ttu-id="3e7df-151">主机状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-151">Hosts State View</span></span>|<span data-ttu-id="3e7df-152">这是一个仪表板视图，显示 BizTalk 主机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-152">This is a dashboard view that displays the health of a BizTalk host.</span></span> <span data-ttu-id="3e7df-153">BizTalk 主机的运行状况取决于的托管的 BizTalk 应用程序实例的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-153">The health of a BizTalk host depends on the health of the instances of the hosted BizTalk applications.</span></span> <span data-ttu-id="3e7df-154">详细信息视图窗格提供 BizTalk 主机的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-154">The Details View pane provides the properties of the BizTalk host.</span></span>|  
|<span data-ttu-id="3e7df-155">规则引擎角色状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-155">Rule Engine Role State View</span></span>|<span data-ttu-id="3e7df-156">这是显示在运行时服务器运行的规则引擎服务的运行状况仪表板视图。</span><span class="sxs-lookup"><span data-stu-id="3e7df-156">This is a dashboard view that displays the health of a Rule Engine service that is running on the runtime servers.</span></span> <span data-ttu-id="3e7df-157">详细信息视图窗格中提供的已安装的规则引擎服务的运行时服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-157">The Details View pane provides the properties of the runtime servers that have Rule Engine service installed.</span></span>|  
|<span data-ttu-id="3e7df-158">运行时角色状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-158">Runtime Role State View</span></span>|<span data-ttu-id="3e7df-159">这是此仪表板视图显示已安装的运行时规则引擎服务运行时服务器的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-159">This is a dashboard view that displays the health of the runtime servers that have runtime rule engine service installed.</span></span> <span data-ttu-id="3e7df-160">BizTalk 运行时角色的运行状况取决于其组件，如 SSO 服务、 管理数据库、 消息框数据库、 SSO 数据库和跟踪数据库的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-160">The health of a BizTalk Run-time Role depends on the health of its components such as SSO Service, management database, message box database, SSO database and tracking database.</span></span> <span data-ttu-id="3e7df-161">详细信息视图窗格中提供的运行时服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="3e7df-161">The Details View pane provides the properties of the runtime servers.</span></span>|  
  
### <a name="bam-component-views"></a><span data-ttu-id="3e7df-162">BAM 组件视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-162">BAM Component Views</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-163">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-163">Elements</span></span>  
  
|<span data-ttu-id="3e7df-164">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-164">View Name</span></span>|<span data-ttu-id="3e7df-165">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-165">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-166">BAM 警报状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-166">BAM Alerts State View</span></span>|<span data-ttu-id="3e7df-167">显示 BizTalk BAM 警报组件的状态视图。</span><span class="sxs-lookup"><span data-stu-id="3e7df-167">Displays the state view of BizTalk BAM alerts component.</span></span>|  
|<span data-ttu-id="3e7df-168">BAM 分析状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-168">BAM Analysis State View</span></span>|<span data-ttu-id="3e7df-169">显示 BizTalk BAM 分析组件的状态视图。</span><span class="sxs-lookup"><span data-stu-id="3e7df-169">Displays the state view of BizTalk BAM analysis component.</span></span>|  
|<span data-ttu-id="3e7df-170">BAM 性能视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-170">BAM Performance View</span></span>|<span data-ttu-id="3e7df-171">图例窗格显示 BAM 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="3e7df-171">The Legend pane displays the performance counter for BAM.</span></span>|  
|<span data-ttu-id="3e7df-172">BAM 门户状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-172">BAM Portal State View</span></span>|<span data-ttu-id="3e7df-173">显示 BAM 门户的状态视图。</span><span class="sxs-lookup"><span data-stu-id="3e7df-173">Displays the state view of BAM portal.</span></span>|  
|<span data-ttu-id="3e7df-174">BAM 运行时状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-174">BAM Run-time State View</span></span>|<span data-ttu-id="3e7df-175">显示 BAM 运行时的状态视图。</span><span class="sxs-lookup"><span data-stu-id="3e7df-175">Displays the state view of BAM run-time.</span></span>|  
  
#### <a name="bam-alerts"></a><span data-ttu-id="3e7df-176">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="3e7df-176">BAM Alerts</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-177">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-177">Elements</span></span>  
  
|<span data-ttu-id="3e7df-178">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-178">View Name</span></span>|<span data-ttu-id="3e7df-179">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-180">BAM 警报状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-180">BAM Alerts State View</span></span>|<span data-ttu-id="3e7df-181">显示 BizTalk BAM 警报的列表，也不能是一项通知服务生成的任何关键的服务都不可用时。</span><span class="sxs-lookup"><span data-stu-id="3e7df-181">Displays a list of BizTalk BAM alerts which is a notification service and generated when any of the critical services are unavailable.</span></span>|  
  
##### <a name="runtime-component-views"></a><span data-ttu-id="3e7df-182">运行时组件视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-182">Runtime Component Views</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-183">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-183">Elements</span></span>  
  
|<span data-ttu-id="3e7df-184">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-184">View Name</span></span>|<span data-ttu-id="3e7df-185">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-185">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-186">应用程序服务状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-186">Application Service State View</span></span>|<span data-ttu-id="3e7df-187">显示 BizTalk 组中的所有主机实例的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3e7df-187">Displays the health of all host instances in a BizTalk group.</span></span>|  
|<span data-ttu-id="3e7df-188">消息框性能状态视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-188">Message Box Performance State View</span></span>|<span data-ttu-id="3e7df-189">图例窗格中显示的消息框跟踪数据大小的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="3e7df-189">The Legend pane displays the performance counter for Message Box Tracking Data Size.</span></span>|  
|<span data-ttu-id="3e7df-190">消息传送适配器性能视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-190">Messaging Adapters Performance View</span></span>|<span data-ttu-id="3e7df-191">图例窗格显示有关 MSMQ 接收适配器接收的字节数的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="3e7df-191">The Legend pane displays the performance counter for MSMQ Receive Adapter Bytes Received.</span></span>|  
|<span data-ttu-id="3e7df-192">消息传递性能视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-192">Messaging Performance View</span></span>|<span data-ttu-id="3e7df-193">图例窗格中显示的活动接收位置的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="3e7df-193">The Legend pane displays the performance counter for Active Receive Locations.</span></span>|  
|<span data-ttu-id="3e7df-194">业务流程性能视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-194">Orchestration Performance View</span></span>|<span data-ttu-id="3e7df-195">图例窗格中显示的性能计数器可运行的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3e7df-195">The Legend pane displays the performance counter for Runnable Orchestrations.</span></span>|  
|<span data-ttu-id="3e7df-196">服务器资源使用量视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-196">Server Resource Usage View</span></span>|<span data-ttu-id="3e7df-197">图例窗格显示物理磁盘空闲时间百分比性能计数器。</span><span class="sxs-lookup"><span data-stu-id="3e7df-197">The Legend pane displays the performance counter for Physical Disk Percentage Idle Time.</span></span>|  
  
###### <a name="runtime-alerts"></a><span data-ttu-id="3e7df-198">运行时的警报</span><span class="sxs-lookup"><span data-stu-id="3e7df-198">Runtime Alerts</span></span>  
  
### <a name="elements"></a><span data-ttu-id="3e7df-199">元素</span><span class="sxs-lookup"><span data-stu-id="3e7df-199">Elements</span></span>  
  
|<span data-ttu-id="3e7df-200">视图名称</span><span class="sxs-lookup"><span data-stu-id="3e7df-200">View Name</span></span>|<span data-ttu-id="3e7df-201">Description</span><span class="sxs-lookup"><span data-stu-id="3e7df-201">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e7df-202">核心警报视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-202">Core Alerts View</span></span>|<span data-ttu-id="3e7df-203">显示 BizTalk 核心警报。</span><span class="sxs-lookup"><span data-stu-id="3e7df-203">Displays BizTalk core alerts.</span></span>|  
|<span data-ttu-id="3e7df-204">消息传送警报视图</span><span class="sxs-lookup"><span data-stu-id="3e7df-204">Messaging Alerts View</span></span>|<span data-ttu-id="3e7df-205">显示 BizTalk 消息的警报。</span><span class="sxs-lookup"><span data-stu-id="3e7df-205">Displays BizTalk messaging alerts.</span></span>|