---
title: "什么是 BAM WCF 和 WF 侦听器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c819d219a9796b485434101ee1c2f2d4be136ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="642d7-103">什么是 BAM WCF 和 WF 侦听器？</span><span class="sxs-lookup"><span data-stu-id="642d7-103">What Are the BAM WCF and WF Interceptors?</span></span>
<span data-ttu-id="642d7-104">业务活动监视 (BAM) 是一个由工具、API 和服务组成的集合，用于管理聚合、警报和配置文件，以及提供实现自动发送事件流程所需的工具，以监视相关业务度量。</span><span class="sxs-lookup"><span data-stu-id="642d7-104">Business Activity Monitoring (BAM) is a collection of tools, APIs, and services that allow you to manage aggregations, alerts, and profiles, and to instrument automated processes to send events to monitor relevant business metrics.</span></span> <span data-ttu-id="642d7-105">同时，还实现了对业务流程的端对端查看，使你可以了解业务流程的最新状态和结果。</span><span class="sxs-lookup"><span data-stu-id="642d7-105">Together, these provide end-to-end visibility into business processes and enable you to stay abreast of business process status and results.</span></span>  
  
 <span data-ttu-id="642d7-106">BAM 侦听器将这一功能扩展到 Windows Workflow Foundation (WF)、Windows Communication Foundation (WCF) 以及其他运行时环境中。</span><span class="sxs-lookup"><span data-stu-id="642d7-106">BAM interceptors extend this same functionality into Windows Workflow Foundation (WF), Windows Communication Foundation (WCF), and other runtime environments.</span></span> <span data-ttu-id="642d7-107">使用 BAM 侦听器，你无需重新编译 WF 或 WCF 解决方案即可跟踪业务流程，因为集成是通过配置文件实现的。</span><span class="sxs-lookup"><span data-stu-id="642d7-107">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution—integration is done through a configuration file.</span></span>  
  
 <span data-ttu-id="642d7-108">通过在项目中使用 BAM WF 或 WCF 侦听器，你可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="642d7-108">By using the BAM WF or WCF interceptor in your project, you can:</span></span>  
  
-   <span data-ttu-id="642d7-109">使用 BAM 门户查看有关在 WF 或 WCF 应用程序中运行的业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="642d7-109">Use the BAM portal to view information about the business processes running in your WF or WCF application.</span></span>  
  
-   <span data-ttu-id="642d7-110">在无需向应用程序添加额外代码的情况下使用 BAM 功能。</span><span class="sxs-lookup"><span data-stu-id="642d7-110">Use BAM functionality without adding additional code to your application.</span></span>  
  
-   <span data-ttu-id="642d7-111">使用你熟悉的 BizTalk Server 工具和实用工具部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="642d7-111">Deploy your solution using familiar BizTalk Server tools and utilities.</span></span>  
  
-   <span data-ttu-id="642d7-112">利用现有 BizTalk Server 环境改进现有和新增的 WF 和 WCF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="642d7-112">Leverage your existing BizTalk Server environment for existing and new WF and WCF applications.</span></span>  
  
## <a name="interceptor-components"></a><span data-ttu-id="642d7-113">侦听器组件</span><span class="sxs-lookup"><span data-stu-id="642d7-113">Interceptor Components</span></span>  
 <span data-ttu-id="642d7-114">每个 BAM 侦听器的核心是公用侦听器基础，公用侦听器基础是一个组件集，为构建用于异构环境的自定义侦听器奠定了基础。</span><span class="sxs-lookup"><span data-stu-id="642d7-114">At the core of each BAM interceptor is the Common Interceptor Foundation, a set of components that provide the foundation for building custom interceptors for heterogeneous environments.</span></span> <span data-ttu-id="642d7-115">公用侦听器基础包含下列共享组件：</span><span class="sxs-lookup"><span data-stu-id="642d7-115">The Common Interceptor Foundation contains the following shared components:</span></span>  
  
-   <span data-ttu-id="642d7-116">**bm.exe**，BAM 部署实用工具的增强的版本扩展以修改侦听器配置，包括添加、 删除、 更新和列表功能。</span><span class="sxs-lookup"><span data-stu-id="642d7-116">**bm.exe**, an enhanced version of the BAM deployment utility extended to modify interceptor configurations including add, remove, update, and list functionality.</span></span>  
  
-   <span data-ttu-id="642d7-117">**CommonInterceptorConfiguration.xsd**，常见的侦听器 Foundation 配置 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="642d7-117">**CommonInterceptorConfiguration.xsd**, the Common Interceptor Foundation configuration XML schema.</span></span> <span data-ttu-id="642d7-118">所有侦听器配置都必须至少根据此架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="642d7-118">At minimum, all interceptor configurations must validate against this schema.</span></span>  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a><span data-ttu-id="642d7-119">Windows Workflow Foundation (WF) 侦听器</span><span class="sxs-lookup"><span data-stu-id="642d7-119">Windows Workflow Foundation (WF) Interceptor</span></span>  
 <span data-ttu-id="642d7-120">通过 Windows Workflow Foundation 侦听器，你可以以透明方式向新增和现有 WF 应用程序添加 BAM 跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="642d7-120">The Windows Workflow Foundation interceptor enables you to transparently add BAM tracking functionality to new and existing WF applications.</span></span> <span data-ttu-id="642d7-121">在将侦听器配置部署到 BAM 主导入数据库，并将 WF 应用程序的每个实例配置为加载 BAM WF 侦听器之后，工作流数据便会写入到 BAM，无需额外代码。</span><span class="sxs-lookup"><span data-stu-id="642d7-121">After the interceptor configuration has been deployed to the BAM Primary Import database and each instance of the WF application has been configured to load the BAM WF Interceptor, workflow data will be written to BAM with no additional code.</span></span> <span data-ttu-id="642d7-122">WF 侦听器提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="642d7-122">The WF interceptor provides the following functionality:</span></span>  
  
-   <span data-ttu-id="642d7-123">在不需要更改或重新编译代码的情况下插入到现有 WF 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="642d7-123">Plugs into existing WF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="642d7-124">允许对已更改的配置文件进行运行时检测和支持。</span><span class="sxs-lookup"><span data-stu-id="642d7-124">Enables run-time detection and support for changed configuration files.</span></span> <span data-ttu-id="642d7-125">如果检测到新版本的侦听器配置文件，新工作流实例将使用新配置，而旧工作流实例将完成对旧配置的使用。</span><span class="sxs-lookup"><span data-stu-id="642d7-125">If a new version of an interceptor configuration file is detected, new workflow instances will use the new configuration while old workflow instances will complete using the old configuration.</span></span>  
  
-   <span data-ttu-id="642d7-126">支持事务。</span><span class="sxs-lookup"><span data-stu-id="642d7-126">Supports transactions.</span></span> <span data-ttu-id="642d7-127">WF 侦听器以一种在事务性上与 WF 事务一致的方式来保留跟踪项。</span><span class="sxs-lookup"><span data-stu-id="642d7-127">The WF interceptor persists tracked items in a transactionally consistent way with WF transactions.</span></span> <span data-ttu-id="642d7-128">仅当 WF 事务和侦听器事务成功完成时，才会保留跟踪项。</span><span class="sxs-lookup"><span data-stu-id="642d7-128">Tracked items are only persisted when the WF transaction and the interceptor trasaction complete successfully.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="642d7-129">Windows Workflow 侦听器不支持 SharedConnectionWorkflowCommitWorkBatchService，后者对跟踪和持久性服务使用相同的 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="642d7-129">The Windows Workflow interceptor does not support SharedConnectionWorkflowCommitWorkBatchService which uses the same SQL connection for both the tracking and persistence services.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="642d7-130">在 BizTalk Server 中 Windows Workflow Foundation (WF) 拦截器不会使用.NET Framework 4 中的新 WF 引擎。</span><span class="sxs-lookup"><span data-stu-id="642d7-130">In BizTalk Server, the Windows Workflow Foundation (WF) interceptor will not work with the new WF engine in .NET Framework 4.</span></span> <span data-ttu-id="642d7-131">WF 拦截器将继续在.NET Framework 3.5 SP2 中工作。</span><span class="sxs-lookup"><span data-stu-id="642d7-131">The WF interceptor will continue to work in .NET Framework 3.5 SP2.</span></span>  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a><span data-ttu-id="642d7-132">Windows Communication Foundation (WCF) 侦听器</span><span class="sxs-lookup"><span data-stu-id="642d7-132">Windows Communication Foundation (WCF) Interceptor</span></span>  
 <span data-ttu-id="642d7-133">Windows Communication Foundation 侦听器向 WCF 应用程序提供 BAM 跟踪功能，</span><span class="sxs-lookup"><span data-stu-id="642d7-133">The Windows Communication Foundation interceptor provides BAM tracking functionality to your WCF applications.</span></span> <span data-ttu-id="642d7-134">它提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="642d7-134">It provides the following functionality:</span></span>  
  
-   <span data-ttu-id="642d7-135">在不需要更改或重新编译代码的情况下插入到现有 WCF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="642d7-135">Plugs into existing WCF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="642d7-136">跟踪 WCF 服务调用中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="642d7-136">Tracks messages contained in WCF service calls.</span></span>  
  
-   <span data-ttu-id="642d7-137">跟踪 WCF 服务调用中各消息中的信息。</span><span class="sxs-lookup"><span data-stu-id="642d7-137">Tracks information from messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="642d7-138">参与从客户端流入的事务或针对事务服务调用从内部启动的事务。</span><span class="sxs-lookup"><span data-stu-id="642d7-138">Participates in transactions flowed from the client or initiated internally for transacted service calls.</span></span>