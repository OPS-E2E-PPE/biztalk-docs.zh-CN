---
title: 管理业务流程 |Microsoft Docs
description: 若要使用业务流程在 BizTalk Server 中，包括启动、 停止、 绑定、 配置、 启用跟踪、 挂起的链接和的详细信息
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a989cb7853e63e1e603febf44db45288276ecd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976478"
---
# <a name="manage-orchestrations"></a><span data-ttu-id="f881d-103">管理业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-103">Manage Orchestrations</span></span>

## <a name="overview"></a><span data-ttu-id="f881d-104">概述</span><span class="sxs-lookup"><span data-stu-id="f881d-104">Overview</span></span>
<span data-ttu-id="f881d-105">本部分说明如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理业务流程。</span><span class="sxs-lookup"><span data-stu-id="f881d-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage orchestrations.</span></span> <span data-ttu-id="f881d-106">业务流程是一个可执行的业务程序。</span><span class="sxs-lookup"><span data-stu-id="f881d-106">An orchestration is an executable business process.</span></span> <span data-ttu-id="f881d-107">有关业务流程的背景信息，请参阅[业务流程](../core/orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="f881d-107">For background information about orchestrations, see [Orchestrations](../core/orchestrations.md).</span></span>  

## <a name="add-to-application"></a><span data-ttu-id="f881d-108">将添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="f881d-108">Add to application</span></span>  
 <span data-ttu-id="f881d-109">业务流程内置的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="f881d-109">Orchestrations are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="f881d-110">不能向应用程序中单独地添加业务流程，而应按照以下方式向应用程序中添加业务流程：</span><span class="sxs-lookup"><span data-stu-id="f881d-110">You cannot add an orchestration to an application individually; an orchestration is added to an application as follows:</span></span>  
  
- <span data-ttu-id="f881d-111">当添加包含到应用程序，业务流程的 BizTalk 程序集，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f881d-111">When you add a BizTalk assembly containing an orchestration to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="f881d-112">某一.msi 文件导入包含 BizTalk 程序集包含业务流程中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f881d-112">When you import an .msi file into an application that includes a BizTalk assembly containing an orchestration, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="f881d-113">当开发人员部署到应用程序包含从业务流程的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f881d-113">When a developer deploys into an application an assembly containing an orchestration from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="biztalk-administration-tasks"></a><span data-ttu-id="f881d-114">BizTalk 管理任务</span><span class="sxs-lookup"><span data-stu-id="f881d-114">BizTalk Administration tasks</span></span>  
 <span data-ttu-id="f881d-115">如本部分所述，使用管理控制台可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f881d-115">You use the administration console to perform the following actions, as described in this section:</span></span>  
  
-   <span data-ttu-id="f881d-116">通过将业务流程绑定到适当的发送端口、接收端口和主机，可配置业务流程绑定，或删除业务流程绑定。</span><span class="sxs-lookup"><span data-stu-id="f881d-116">Configure bindings for the orchestration by binding the orchestration to the appropriate send and receive ports and host, or remove these bindings from the orchestration.</span></span>  
  
-   <span data-ttu-id="f881d-117">为业务流程配置消息跟踪。</span><span class="sxs-lookup"><span data-stu-id="f881d-117">Configure message tracking for the orchestration.</span></span>  
  
-   <span data-ttu-id="f881d-118">查看业务流程的实例信息。</span><span class="sxs-lookup"><span data-stu-id="f881d-118">View instance information for the orchestration.</span></span>  
  
-   <span data-ttu-id="f881d-119">将业务流程登记到适当的主机，或从主机取消登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="f881d-119">Enlist the orchestration to the appropriate host or unenlist the orchestration from the host.</span></span>  
  
-   <span data-ttu-id="f881d-120">启动或停止业务流程，以便启动或停止消息的处理过程。</span><span class="sxs-lookup"><span data-stu-id="f881d-120">Start or stop the orchestration so that it starts or stops processing messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f881d-121">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="f881d-121">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="f881d-122">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="f881d-122">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
> 
> [!NOTE]
>  <span data-ttu-id="f881d-123">开发人员使用业务流程设计器来创建业务流程，如中所述[业务流程使用业务流程设计器创建](../core/creating-orchestrations-using-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="f881d-123">The developer uses Orchestration Designer to create orchestrations, as described in [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span> <span data-ttu-id="f881d-124">开发人员可以通过在开发过程中使用管理控制台来管理业务流程，如本部分所述。</span><span class="sxs-lookup"><span data-stu-id="f881d-124">The developer can manage orchestrations during the development process by using the administration console, as described in this section.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f881d-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f881d-125">Next steps</span></span>
  
-   [<span data-ttu-id="f881d-126">为业务流程配置绑定</span><span class="sxs-lookup"><span data-stu-id="f881d-126">Configure Bindings for an Orchestration</span></span>](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-127">取消绑定业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-127">Unbind an Orchestration</span></span>](../core/how-to-unbind-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-128">为业务流程配置跟踪</span><span class="sxs-lookup"><span data-stu-id="f881d-128">Configure Tracking for an Orchestration</span></span>](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-129">查看业务流程的实例信息</span><span class="sxs-lookup"><span data-stu-id="f881d-129">View Instance Information for an Orchestration</span></span>](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-130">从应用程序中删除业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-130">Remove an Orchestration from an Application</span></span>](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [<span data-ttu-id="f881d-131">登记业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-131">Enlist an Orchestration</span></span>](../core/how-to-enlist-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-132">取消登记业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-132">Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-133">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-133">Start an Orchestration</span></span>](../core/how-to-start-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-134">停止业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-134">Stop an Orchestration</span></span>](../core/how-to-stop-an-orchestration.md)  
  
-   [<span data-ttu-id="f881d-135">暂停、恢复和终止业务流程实例</span><span class="sxs-lookup"><span data-stu-id="f881d-135">Suspend, Resume, and Terminate Orchestration Instances</span></span>](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [<span data-ttu-id="f881d-136">更新业务流程</span><span class="sxs-lookup"><span data-stu-id="f881d-136">Upgrade an Orchestration</span></span>](../core/how-to-upgrade-an-orchestration.md)