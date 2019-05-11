---
title: 什么是 BAM WCF 和 WF 侦听器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cfa81307220a2685768e2ac13d1a4c922cf944
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244114"
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="66bf9-103">什么是 BAM WCF 和 WF 侦听器？</span><span class="sxs-lookup"><span data-stu-id="66bf9-103">What Are the BAM WCF and WF Interceptors?</span></span>
<span data-ttu-id="66bf9-104">业务活动监视 (BAM) 是一系列工具、 Api 和服务，可用于管理聚合、 警报和配置文件，以及提供实现自动化的过程来发送事件来监视相关业务度量。</span><span class="sxs-lookup"><span data-stu-id="66bf9-104">Business Activity Monitoring (BAM) is a collection of tools, APIs, and services that allow you to manage aggregations, alerts, and profiles, and to instrument automated processes to send events to monitor relevant business metrics.</span></span> <span data-ttu-id="66bf9-105">在一起，这些提供端到端可见性，业务流程，让大家随时了解业务流程状态和结果。</span><span class="sxs-lookup"><span data-stu-id="66bf9-105">Together, these provide end-to-end visibility into business processes and enable you to stay abreast of business process status and results.</span></span>  
  
 <span data-ttu-id="66bf9-106">BAM 侦听器将扩展到 Windows Workflow Foundation (WF)、 Windows Communication Foundation (WCF) 和其他运行时环境这一功能。</span><span class="sxs-lookup"><span data-stu-id="66bf9-106">BAM interceptors extend this same functionality into Windows Workflow Foundation (WF), Windows Communication Foundation (WCF), and other runtime environments.</span></span> <span data-ttu-id="66bf9-107">通过使用 BAM 侦听器，可以跟踪业务流程，无需重新编译 WF 或 WCF 解决方案，集成通过配置文件实现。</span><span class="sxs-lookup"><span data-stu-id="66bf9-107">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution—integration is done through a configuration file.</span></span>  
  
 <span data-ttu-id="66bf9-108">通过在项目中使用 BAM WF 或 WCF 侦听器，你可以：</span><span class="sxs-lookup"><span data-stu-id="66bf9-108">By using the BAM WF or WCF interceptor in your project, you can:</span></span>  
  
-   <span data-ttu-id="66bf9-109">使用 BAM 门户查看有关 WF 或 WCF 应用程序中运行的业务流程的信息。</span><span class="sxs-lookup"><span data-stu-id="66bf9-109">Use the BAM portal to view information about the business processes running in your WF or WCF application.</span></span>  
  
-   <span data-ttu-id="66bf9-110">使用 BAM 功能而无需额外的代码添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="66bf9-110">Use BAM functionality without adding additional code to your application.</span></span>  
  
-   <span data-ttu-id="66bf9-111">部署解决方案是使用熟悉的 BizTalk Server 工具和实用程序。</span><span class="sxs-lookup"><span data-stu-id="66bf9-111">Deploy your solution using familiar BizTalk Server tools and utilities.</span></span>  
  
-   <span data-ttu-id="66bf9-112">利用现有 BizTalk Server 环境的现有和新 WF 和 WCF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="66bf9-112">Leverage your existing BizTalk Server environment for existing and new WF and WCF applications.</span></span>  
  
## <a name="interceptor-components"></a><span data-ttu-id="66bf9-113">侦听器组件</span><span class="sxs-lookup"><span data-stu-id="66bf9-113">Interceptor Components</span></span>  
 <span data-ttu-id="66bf9-114">每个 BAM 侦听器的核心是公用侦听器基础的一组用于构建针对异类环境的自定义侦听器奠定了基础的组件。</span><span class="sxs-lookup"><span data-stu-id="66bf9-114">At the core of each BAM interceptor is the Common Interceptor Foundation, a set of components that provide the foundation for building custom interceptors for heterogeneous environments.</span></span> <span data-ttu-id="66bf9-115">公用侦听器基础包含下列共享的组件：</span><span class="sxs-lookup"><span data-stu-id="66bf9-115">The Common Interceptor Foundation contains the following shared components:</span></span>  
  
-   <span data-ttu-id="66bf9-116">**bm.exe**，BAM 部署实用工具的增强的版本扩展，用于修改侦听器配置，包括添加、 删除、 更新和列表的功能。</span><span class="sxs-lookup"><span data-stu-id="66bf9-116">**bm.exe**, an enhanced version of the BAM deployment utility extended to modify interceptor configurations including add, remove, update, and list functionality.</span></span>  
  
-   <span data-ttu-id="66bf9-117">**CommonInterceptorConfiguration.xsd**，公用侦听器基础配置 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="66bf9-117">**CommonInterceptorConfiguration.xsd**, the Common Interceptor Foundation configuration XML schema.</span></span> <span data-ttu-id="66bf9-118">最小值，必须根据此架构验证所有侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="66bf9-118">At minimum, all interceptor configurations must validate against this schema.</span></span>  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a><span data-ttu-id="66bf9-119">Windows Workflow Foundation (WF) 侦听器</span><span class="sxs-lookup"><span data-stu-id="66bf9-119">Windows Workflow Foundation (WF) Interceptor</span></span>  
 <span data-ttu-id="66bf9-120">Windows Workflow Foundation 侦听器可以以透明方式添加 BAM 跟踪到新的和现有 WF 应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="66bf9-120">The Windows Workflow Foundation interceptor enables you to transparently add BAM tracking functionality to new and existing WF applications.</span></span> <span data-ttu-id="66bf9-121">在将侦听器配置已部署到 BAM 主导入数据库和 WF 应用程序的每个实例已配置为加载 BAM WF 侦听器，则工作流数据将写入到 BAM，无额外代码。</span><span class="sxs-lookup"><span data-stu-id="66bf9-121">After the interceptor configuration has been deployed to the BAM Primary Import database and each instance of the WF application has been configured to load the BAM WF Interceptor, workflow data will be written to BAM with no additional code.</span></span> <span data-ttu-id="66bf9-122">WF 侦听器提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="66bf9-122">The WF interceptor provides the following functionality:</span></span>  
  
-   <span data-ttu-id="66bf9-123">插入到现有 WF 应用程序，而无需更改代码或重新编译。</span><span class="sxs-lookup"><span data-stu-id="66bf9-123">Plugs into existing WF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="66bf9-124">启用运行时检测和支持的更改的配置文件。</span><span class="sxs-lookup"><span data-stu-id="66bf9-124">Enables run-time detection and support for changed configuration files.</span></span> <span data-ttu-id="66bf9-125">如果检测到的侦听器配置文件的新版本，则新工作流实例将使用新配置，而旧工作流实例将使用旧的配置完成。</span><span class="sxs-lookup"><span data-stu-id="66bf9-125">If a new version of an interceptor configuration file is detected, new workflow instances will use the new configuration while old workflow instances will complete using the old configuration.</span></span>  
  
-   <span data-ttu-id="66bf9-126">支持事务。</span><span class="sxs-lookup"><span data-stu-id="66bf9-126">Supports transactions.</span></span> <span data-ttu-id="66bf9-127">WF 侦听器事务上一致的方式与 WF 事务保留跟踪的项。</span><span class="sxs-lookup"><span data-stu-id="66bf9-127">The WF interceptor persists tracked items in a transactionally consistent way with WF transactions.</span></span> <span data-ttu-id="66bf9-128">当 WF 事务和侦听器事务成功完成时，才会保留跟踪的项。</span><span class="sxs-lookup"><span data-stu-id="66bf9-128">Tracked items are only persisted when the WF transaction and the interceptor trasaction complete successfully.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66bf9-129">Windows Workflow 侦听器不支持 SharedConnectionWorkflowCommitWorkBatchService，后者跟踪和持久性服务使用相同的 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="66bf9-129">The Windows Workflow interceptor does not support SharedConnectionWorkflowCommitWorkBatchService which uses the same SQL connection for both the tracking and persistence services.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66bf9-130">在 BizTalk Server 中，Windows Workflow Foundation (WF) 侦听器会不会与.NET Framework 4 中的新 WF 引擎协同工作。</span><span class="sxs-lookup"><span data-stu-id="66bf9-130">In BizTalk Server, the Windows Workflow Foundation (WF) interceptor will not work with the new WF engine in .NET Framework 4.</span></span> <span data-ttu-id="66bf9-131">WF 侦听器会继续在.NET Framework 3.5 SP2 中工作。</span><span class="sxs-lookup"><span data-stu-id="66bf9-131">The WF interceptor will continue to work in .NET Framework 3.5 SP2.</span></span>  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a><span data-ttu-id="66bf9-132">Windows Communication Foundation (WCF) 侦听器</span><span class="sxs-lookup"><span data-stu-id="66bf9-132">Windows Communication Foundation (WCF) Interceptor</span></span>  
 <span data-ttu-id="66bf9-133">Windows Communication Foundation 侦听器提供 BAM 跟踪对 WCF 应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="66bf9-133">The Windows Communication Foundation interceptor provides BAM tracking functionality to your WCF applications.</span></span> <span data-ttu-id="66bf9-134">它提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="66bf9-134">It provides the following functionality:</span></span>  
  
-   <span data-ttu-id="66bf9-135">插入到现有 WCF 应用程序，而无需更改代码或重新编译。</span><span class="sxs-lookup"><span data-stu-id="66bf9-135">Plugs into existing WCF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="66bf9-136">跟踪 WCF 服务调用中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="66bf9-136">Tracks messages contained in WCF service calls.</span></span>  
  
-   <span data-ttu-id="66bf9-137">从 WCF 服务调用中的消息跟踪的信息。</span><span class="sxs-lookup"><span data-stu-id="66bf9-137">Tracks information from messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="66bf9-138">参与事务从客户端流入或在内部启动针对事务的服务调用。</span><span class="sxs-lookup"><span data-stu-id="66bf9-138">Participates in transactions flowed from the client or initiated internally for transacted service calls.</span></span>