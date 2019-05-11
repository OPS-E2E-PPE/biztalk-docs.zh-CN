---
title: 在 Operations Manager 控制台中查看信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6acdf425-4c36-4d89-9493-81b33481fe6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a03daf6612a3f31313d3826f95357d99d0841f73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249319"
---
# <a name="viewing-information-in-the-operations-manager-console"></a><span data-ttu-id="26907-102">在 Operations Manager 控制台中查看信息</span><span class="sxs-lookup"><span data-stu-id="26907-102">Viewing Information in the Operations Manager Console</span></span>
<span data-ttu-id="26907-103">使用与提供的视图[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，以了解当前可用性、 配置、 运行状况，以及 BizTalk Server 环境的性能。</span><span class="sxs-lookup"><span data-stu-id="26907-103">Use the views provided with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack to understand the current availability, configuration, health, and performance of your BizTalk Server environment.</span></span> <span data-ttu-id="26907-104">视图可能会包含很长的对象列表。</span><span class="sxs-lookup"><span data-stu-id="26907-104">A view can contain a lengthy list of objects.</span></span> <span data-ttu-id="26907-105">若要查找特定对象组，您可以使用 Operations Manager 工具栏上的作用域、 搜索和查找按钮。</span><span class="sxs-lookup"><span data-stu-id="26907-105">To find a specific object or group of objects, you can use the Scope, Search, and Find buttons on the Operations Manager toolbar.</span></span> <span data-ttu-id="26907-106">有关详细信息，请参阅如何管理监视数据使用作用域、 搜索，并在 Operations Manager 2007 R2\2012 帮助中查找主题。</span><span class="sxs-lookup"><span data-stu-id="26907-106">For more information, see the How to Manage Monitoring Data Using Scope, Search, and Find topic in Operations Manager 2007 R2\2012 Help.</span></span>  
  
 <span data-ttu-id="26907-107">以下视图正下方列出**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 在操作控制台的监视窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="26907-107">The following views are listed directly under **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** node in the Monitoring pane of the Operations Console.</span></span>  
  
-   <span data-ttu-id="26907-108">**应用程序视图**:BizTalk 管理员是希望监视的状态和运行状况的各种 BizTalk Server 项目和应用程序，如业务流程发送端口、 接收位置，依次类推。</span><span class="sxs-lookup"><span data-stu-id="26907-108">**Application Views**: A BizTalk administrator is interested in monitoring the state and health of various BizTalk Server artifacts and applications such as orchestrations send ports, receive locations, and so on.</span></span>  
  
-   <span data-ttu-id="26907-109">**部署视图**:企业 IT 管理员希望监视状态和各种企业部署托管 SQL Server 数据库，托管 SSO 服务、 主机实例计算机、 IIS 的计算机的计算机运行状况的网络服务等。</span><span class="sxs-lookup"><span data-stu-id="26907-109">**Deployment Views**: An enterprise IT administrator is interested in monitoring the state and health of the various enterprise deployments the machines hosting the SQL Server databases, machines hosting the SSO service, host instance machines, IIS, network services, and so on.</span></span>  
  
## <a name="application-views"></a><span data-ttu-id="26907-110">应用程序视图</span><span class="sxs-lookup"><span data-stu-id="26907-110">Application Views</span></span>  
 <span data-ttu-id="26907-111">应用程序视图包含下表中描述的元素。</span><span class="sxs-lookup"><span data-stu-id="26907-111">Application views contain the elements described in the following table.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-112">元素</span><span class="sxs-lookup"><span data-stu-id="26907-112">Elements</span></span>  
  
|<span data-ttu-id="26907-113">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-113">View Name</span></span>|<span data-ttu-id="26907-114">Description</span><span class="sxs-lookup"><span data-stu-id="26907-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-115">应用程序状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-115">Application State View</span></span>|<span data-ttu-id="26907-116">这是一个仪表板视图，显示 BizTalk 应用程序的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-116">This is a dashboard view that displays the health of a BizTalk application.</span></span> <span data-ttu-id="26907-117">BizTalk 应用程序的运行状况取决于其构成项目，如业务流程、 发送端口组、 发送端口、 接收端口和接收位置的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-117">The health of BizTalk application depends on the health of its constituent artifacts such as Orchestrations, Send Port Group, Send Port, Receive Port, and Receive Location.</span></span> <span data-ttu-id="26907-118">详细信息视图窗格提供托管的 BizTalk 应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-118">The Details View pane provides the properties of the hosted BizTalk application.</span></span>|  
|<span data-ttu-id="26907-119">组状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-119">Group State View</span></span>|<span data-ttu-id="26907-120">这是一个仪表板视图，显示 BizTalk 组的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-120">This is a dashboard view that displays the health of a BizTalk group.</span></span> <span data-ttu-id="26907-121">BizTalk 组的运行状况取决于 BizTalk 主机和 BizTalk 应用程序的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-121">The health of a BizTalk group depends on the health of BizTalk host and BizTalk applications.</span></span> <span data-ttu-id="26907-122">详细信息视图窗格提供了 BizTalk 组的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-122">The Details View pane provides the properties of the BizTalk group.</span></span>|  
|<span data-ttu-id="26907-123">主机状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-123">Host State View</span></span>|<span data-ttu-id="26907-124">这是一个仪表板视图，显示 BizTalk 主机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-124">This is a dashboard view that displays the health of a BizTalk host.</span></span> <span data-ttu-id="26907-125">BizTalk 主机的运行状况取决于宿主的 BizTalk 应用程序实例的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-125">The health of a BizTalk host depends on the health of the instances of the hosted BizTalk applications.</span></span> <span data-ttu-id="26907-126">详细信息视图窗格中提供的 BizTalk 主机的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-126">The Details View pane provides the properties of the BizTalk host.</span></span>|  
  
#### <a name="application-artifacts-views"></a><span data-ttu-id="26907-127">应用程序项目视图</span><span class="sxs-lookup"><span data-stu-id="26907-127">Application Artifacts Views</span></span>  
 <span data-ttu-id="26907-128">应用程序项目视图中所包含下表中描述的元素。</span><span class="sxs-lookup"><span data-stu-id="26907-128">Application artifacts views contain the elements described in the following table.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-129">元素</span><span class="sxs-lookup"><span data-stu-id="26907-129">Elements</span></span>  
  
|<span data-ttu-id="26907-130">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-130">View Name</span></span>|<span data-ttu-id="26907-131">Description</span><span class="sxs-lookup"><span data-stu-id="26907-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-132">业务流程状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-132">Orchestrations State View</span></span>|<span data-ttu-id="26907-133">显示的配置和运行时状态的业务流程的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="26907-133">Displays the configuration and runtime state of Orchestration for the hosted application.</span></span>|  
|<span data-ttu-id="26907-134">接收位置状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-134">Receive Location State View</span></span>|<span data-ttu-id="26907-135">显示的配置和运行时状态的接收位置承载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26907-135">Displays the configuration and runtime state of Receive Location for the hosted application.</span></span>|  
|<span data-ttu-id="26907-136">接收端口的状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-136">Receive Ports State View</span></span>|<span data-ttu-id="26907-137">显示的配置和运行时状态的接收端口的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="26907-137">Displays the configuration and runtime state of Receive Ports for the hosted application.</span></span>|  
|<span data-ttu-id="26907-138">发送端口组状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-138">Send Port Groups State View</span></span>|<span data-ttu-id="26907-139">显示的配置和运行时状态的发送端口组的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="26907-139">Displays the configuration and runtime state of Send Port Group for the hosted application.</span></span>|  
|<span data-ttu-id="26907-140">发送端口状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-140">Send Port State View</span></span>|<span data-ttu-id="26907-141">显示的配置和运行时状态的发送端口的托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="26907-141">Displays the configuration and runtime state of Send Port for the hosted application.</span></span>|  
  
## <a name="deployment-views"></a><span data-ttu-id="26907-142">部署视图</span><span class="sxs-lookup"><span data-stu-id="26907-142">Deployment Views</span></span>  
 <span data-ttu-id="26907-143">部署视图包含下表中描述的元素。</span><span class="sxs-lookup"><span data-stu-id="26907-143">Deployment views contain the elements described in the following table.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-144">元素</span><span class="sxs-lookup"><span data-stu-id="26907-144">Elements</span></span>  
  
|<span data-ttu-id="26907-145">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-145">View Name</span></span>|<span data-ttu-id="26907-146">Description</span><span class="sxs-lookup"><span data-stu-id="26907-146">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-147">部署状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-147">Deployment State View</span></span>|<span data-ttu-id="26907-148">这是显示 BizTalk 部署组的运行状况仪表板视图。</span><span class="sxs-lookup"><span data-stu-id="26907-148">This is a dashboard view that displays the health of a BizTalk deployment group.</span></span> <span data-ttu-id="26907-149">BizTalk 部署组的运行状况取决于其构成的运行时服务器组件，如 BAM 角色、 规则引擎角色、 BizTalk 运行时角色和 BizTalk 主机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-149">The health of the BizTalk deployment group depends on the health of its constituent runtime server components such as BAM Role, Rule Engine Role, BizTalk Run-time Role and BizTalk Host.</span></span> <span data-ttu-id="26907-150">详细信息视图窗格提供了 BizTalk 部署组的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-150">The Details View pane provides the properties of the BizTalk deployment group.</span></span>|  
|<span data-ttu-id="26907-151">主机状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-151">Hosts State View</span></span>|<span data-ttu-id="26907-152">这是一个仪表板视图，显示 BizTalk 主机的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-152">This is a dashboard view that displays the health of a BizTalk host.</span></span> <span data-ttu-id="26907-153">BizTalk 主机的运行状况取决于宿主的 BizTalk 应用程序实例的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-153">The health of a BizTalk host depends on the health of the instances of the hosted BizTalk applications.</span></span> <span data-ttu-id="26907-154">详细信息视图窗格中提供的 BizTalk 主机的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-154">The Details View pane provides the properties of the BizTalk host.</span></span>|  
|<span data-ttu-id="26907-155">规则引擎角色状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-155">Rule Engine Role State View</span></span>|<span data-ttu-id="26907-156">这是显示在运行时服务器运行的规则引擎服务的运行状况仪表板视图。</span><span class="sxs-lookup"><span data-stu-id="26907-156">This is a dashboard view that displays the health of a Rule Engine service that is running on the runtime servers.</span></span> <span data-ttu-id="26907-157">详细信息视图窗格提供了安装的规则引擎服务的运行时服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-157">The Details View pane provides the properties of the runtime servers that have Rule Engine service installed.</span></span>|  
|<span data-ttu-id="26907-158">运行时角色状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-158">Runtime Role State View</span></span>|<span data-ttu-id="26907-159">这是此仪表板视图显示已安装的运行时规则引擎服务的运行时服务器的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-159">This is a dashboard view that displays the health of the runtime servers that have runtime rule engine service installed.</span></span> <span data-ttu-id="26907-160">BizTalk 运行时角色的运行状况取决于其组件，如 SSO 服务、 管理数据库、 messagebox 数据库中，SSO 数据库和跟踪数据库的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-160">The health of a BizTalk Run-time Role depends on the health of its components such as SSO Service, management database, message box database, SSO database and tracking database.</span></span> <span data-ttu-id="26907-161">详细信息视图窗格提供了在运行时服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="26907-161">The Details View pane provides the properties of the runtime servers.</span></span>|  
  
### <a name="bam-component-views"></a><span data-ttu-id="26907-162">BAM 组件视图</span><span class="sxs-lookup"><span data-stu-id="26907-162">BAM Component Views</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-163">元素</span><span class="sxs-lookup"><span data-stu-id="26907-163">Elements</span></span>  
  
|<span data-ttu-id="26907-164">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-164">View Name</span></span>|<span data-ttu-id="26907-165">Description</span><span class="sxs-lookup"><span data-stu-id="26907-165">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-166">BAM 警报状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-166">BAM Alerts State View</span></span>|<span data-ttu-id="26907-167">显示 BizTalk BAM 警报组件的状态视图。</span><span class="sxs-lookup"><span data-stu-id="26907-167">Displays the state view of BizTalk BAM alerts component.</span></span>|  
|<span data-ttu-id="26907-168">BAM 分析状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-168">BAM Analysis State View</span></span>|<span data-ttu-id="26907-169">显示 BizTalk BAM 分析组件的状态视图。</span><span class="sxs-lookup"><span data-stu-id="26907-169">Displays the state view of BizTalk BAM analysis component.</span></span>|  
|<span data-ttu-id="26907-170">BAM 性能视图</span><span class="sxs-lookup"><span data-stu-id="26907-170">BAM Performance View</span></span>|<span data-ttu-id="26907-171">图例窗格显示有关 BAM 的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="26907-171">The Legend pane displays the performance counter for BAM.</span></span>|  
|<span data-ttu-id="26907-172">BAM 门户状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-172">BAM Portal State View</span></span>|<span data-ttu-id="26907-173">显示 BAM 门户的状态视图。</span><span class="sxs-lookup"><span data-stu-id="26907-173">Displays the state view of BAM portal.</span></span>|  
|<span data-ttu-id="26907-174">BAM 运行时状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-174">BAM Run-time State View</span></span>|<span data-ttu-id="26907-175">显示 BAM 运行时的状态视图。</span><span class="sxs-lookup"><span data-stu-id="26907-175">Displays the state view of BAM run-time.</span></span>|  
  
#### <a name="bam-alerts"></a><span data-ttu-id="26907-176">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="26907-176">BAM Alerts</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-177">元素</span><span class="sxs-lookup"><span data-stu-id="26907-177">Elements</span></span>  
  
|<span data-ttu-id="26907-178">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-178">View Name</span></span>|<span data-ttu-id="26907-179">Description</span><span class="sxs-lookup"><span data-stu-id="26907-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-180">BAM 警报状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-180">BAM Alerts State View</span></span>|<span data-ttu-id="26907-181">显示这是通知服务，当任何关键服务都不可用时，生成 BizTalk BAM 警报的列表。</span><span class="sxs-lookup"><span data-stu-id="26907-181">Displays a list of BizTalk BAM alerts which is a notification service and generated when any of the critical services are unavailable.</span></span>|  
  
##### <a name="runtime-component-views"></a><span data-ttu-id="26907-182">运行时组件视图</span><span class="sxs-lookup"><span data-stu-id="26907-182">Runtime Component Views</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-183">元素</span><span class="sxs-lookup"><span data-stu-id="26907-183">Elements</span></span>  
  
|<span data-ttu-id="26907-184">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-184">View Name</span></span>|<span data-ttu-id="26907-185">Description</span><span class="sxs-lookup"><span data-stu-id="26907-185">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-186">应用程序服务状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-186">Application Service State View</span></span>|<span data-ttu-id="26907-187">在 BizTalk 组中显示的所有主机实例的运行状况。</span><span class="sxs-lookup"><span data-stu-id="26907-187">Displays the health of all host instances in a BizTalk group.</span></span>|  
|<span data-ttu-id="26907-188">消息框性能状态视图</span><span class="sxs-lookup"><span data-stu-id="26907-188">Message Box Performance State View</span></span>|<span data-ttu-id="26907-189">图例窗格中显示的消息框跟踪数据大小的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="26907-189">The Legend pane displays the performance counter for Message Box Tracking Data Size.</span></span>|  
|<span data-ttu-id="26907-190">消息传送适配器性能视图</span><span class="sxs-lookup"><span data-stu-id="26907-190">Messaging Adapters Performance View</span></span>|<span data-ttu-id="26907-191">图例窗格中显示的性能计数器的 MSMQ 接收适配器接收的字节。</span><span class="sxs-lookup"><span data-stu-id="26907-191">The Legend pane displays the performance counter for MSMQ Receive Adapter Bytes Received.</span></span>|  
|<span data-ttu-id="26907-192">消息传送性能视图</span><span class="sxs-lookup"><span data-stu-id="26907-192">Messaging Performance View</span></span>|<span data-ttu-id="26907-193">图例窗格中显示为活动的接收位置的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="26907-193">The Legend pane displays the performance counter for Active Receive Locations.</span></span>|  
|<span data-ttu-id="26907-194">业务流程性能视图</span><span class="sxs-lookup"><span data-stu-id="26907-194">Orchestration Performance View</span></span>|<span data-ttu-id="26907-195">图例窗格中显示为可运行的业务流程的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="26907-195">The Legend pane displays the performance counter for Runnable Orchestrations.</span></span>|  
|<span data-ttu-id="26907-196">服务器资源使用情况视图</span><span class="sxs-lookup"><span data-stu-id="26907-196">Server Resource Usage View</span></span>|<span data-ttu-id="26907-197">图例窗格显示物理磁盘空闲时间百分比的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="26907-197">The Legend pane displays the performance counter for Physical Disk Percentage Idle Time.</span></span>|  
  
###### <a name="runtime-alerts"></a><span data-ttu-id="26907-198">运行时的警报</span><span class="sxs-lookup"><span data-stu-id="26907-198">Runtime Alerts</span></span>  
  
### <a name="elements"></a><span data-ttu-id="26907-199">元素</span><span class="sxs-lookup"><span data-stu-id="26907-199">Elements</span></span>  
  
|<span data-ttu-id="26907-200">视图名称</span><span class="sxs-lookup"><span data-stu-id="26907-200">View Name</span></span>|<span data-ttu-id="26907-201">Description</span><span class="sxs-lookup"><span data-stu-id="26907-201">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26907-202">核心警报视图</span><span class="sxs-lookup"><span data-stu-id="26907-202">Core Alerts View</span></span>|<span data-ttu-id="26907-203">显示 BizTalk 核心警报。</span><span class="sxs-lookup"><span data-stu-id="26907-203">Displays BizTalk core alerts.</span></span>|  
|<span data-ttu-id="26907-204">消息传送的警报视图</span><span class="sxs-lookup"><span data-stu-id="26907-204">Messaging Alerts View</span></span>|<span data-ttu-id="26907-205">显示 BizTalk 消息传送警报。</span><span class="sxs-lookup"><span data-stu-id="26907-205">Displays BizTalk messaging alerts.</span></span>|