---
title: 如何启动和停止 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting
- starting, applications
- managing [applications], starting
- managing [applications], stopping
- applications, starting
- stopping, applications
- applications, stopping
- stopping
ms.assetid: f9f83e99-a1e2-4dfd-b3be-60d3ec2cbcc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979de8e8614d05ba97223e43c90ed0ec83cefc4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968726"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a><span data-ttu-id="38bf1-102">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="38bf1-102">How to Start and Stop a BizTalk Application</span></span>
<span data-ttu-id="38bf1-103">本主题介绍如何使用 BizTalk Server 管理控制台启动和停止 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="38bf1-103">This topic describes how to use the BizTalk Server Administration console to start and stop a BizTalk application.</span></span>  
  
 <span data-ttu-id="38bf1-104">如中所述，可以启动应用程序之前，必须为它所包含的所有业务流程中配置绑定[如何配置业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf1-104">Before you can start an application, bindings must be configured for all orchestrations it contains, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="38bf1-105">启动应用程序时，可以选择如下所示的一个或多个选项：</span><span class="sxs-lookup"><span data-stu-id="38bf1-105">When you start an application, you can select one or more of the following options, as follows:</span></span>  
  
-   <span data-ttu-id="38bf1-106">登记并启动所有业务流程。</span><span class="sxs-lookup"><span data-stu-id="38bf1-106">Enlist and start all orchestrations.</span></span>  
  
-   <span data-ttu-id="38bf1-107">登记并启动所有发送端口。</span><span class="sxs-lookup"><span data-stu-id="38bf1-107">Enlist and start all send ports.</span></span>  
  
-   <span data-ttu-id="38bf1-108">登记并启动所有发送端口组。</span><span class="sxs-lookup"><span data-stu-id="38bf1-108">Enlist and start all send port groups.</span></span>  
  
-   <span data-ttu-id="38bf1-109">启用所有接收位置。</span><span class="sxs-lookup"><span data-stu-id="38bf1-109">Enable all receive locations.</span></span>  
  
-   <span data-ttu-id="38bf1-110">启动所有关联的主机实例。</span><span class="sxs-lookup"><span data-stu-id="38bf1-110">Start all associated host instances.</span></span>  
  
-   <span data-ttu-id="38bf1-111">恢复挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="38bf1-111">Resume suspended instances.</span></span>  
  
-   <span data-ttu-id="38bf1-112">部署所有策略。</span><span class="sxs-lookup"><span data-stu-id="38bf1-112">Deploy all policies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38bf1-113">只有应用程序中已发布的策略才会自动进行部署。</span><span class="sxs-lookup"><span data-stu-id="38bf1-113">Only published policies in the application are deployed automatically.</span></span> <span data-ttu-id="38bf1-114">如果某个策略未发布，则不会对它进行部署。</span><span class="sxs-lookup"><span data-stu-id="38bf1-114">If a policy is not published, it will not be deployed.</span></span>  
  
 <span data-ttu-id="38bf1-115">停止应用程序时，可以选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="38bf1-115">When you stop an application, you can select one of the following options:</span></span>  
  
-   <span data-ttu-id="38bf1-116">**部分停止-允许正在运行的实例以继续。**</span><span class="sxs-lookup"><span data-stu-id="38bf1-116">**Partial Stop - Allow running instances to continue.**</span></span> <span data-ttu-id="38bf1-117">此选项禁用该应用程序中的所有接收位置，但会使所有其他项目保留其以前的状态不变。</span><span class="sxs-lookup"><span data-stu-id="38bf1-117">This option disables all receive locations in the application, but leaves all other artifacts in their previous state.</span></span> <span data-ttu-id="38bf1-118">这样就允许正在运行的实例处理完系统中当前存在的消息。</span><span class="sxs-lookup"><span data-stu-id="38bf1-118">This allows running instances to complete processing messages that are currently in the system.</span></span> <span data-ttu-id="38bf1-119">请注意，如果某一消息事务需要多个输入，则当您使用此选项时此消息事务可能无法完成。</span><span class="sxs-lookup"><span data-stu-id="38bf1-119">Note that if a message transaction requires multiple inputs, it may not be able to complete when you use this option.</span></span>  
  
-   <span data-ttu-id="38bf1-120">**部分停止-挂起正在运行的实例。**</span><span class="sxs-lookup"><span data-stu-id="38bf1-120">**Partial Stop - Suspend running instances.**</span></span> <span data-ttu-id="38bf1-121">此选项禁用该应用程序中的所有接收位置并停止该应用程序中的所有业务流程和发送端口。</span><span class="sxs-lookup"><span data-stu-id="38bf1-121">This option disables all receive locations and stops all orchestrations and send ports in the application.</span></span> <span data-ttu-id="38bf1-122">它不会取消登记或取消部署任何项目。</span><span class="sxs-lookup"><span data-stu-id="38bf1-122">It does not unenlist or undeploy any artifacts.</span></span> <span data-ttu-id="38bf1-123">如果希望临时暂停应用程序，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="38bf1-123">Use this option when you want to temporarily pause the application.</span></span>  
  
-   <span data-ttu-id="38bf1-124">**完全停止-终止实例。**</span><span class="sxs-lookup"><span data-stu-id="38bf1-124">**Full Stop - Terminate instances.**</span></span> <span data-ttu-id="38bf1-125">此选项禁用应用程序中的所有接收位置，停止并取消登记应用程序中的所有业务流程和发送端口，并取消部署应用程序中的所有策略。</span><span class="sxs-lookup"><span data-stu-id="38bf1-125">This option disables all receive locations, stops and unenlists all orchestrations and send ports, and undeploys all policies in the application.</span></span> <span data-ttu-id="38bf1-126">如果希望完全取消部署应用程序，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="38bf1-126">Use this option when you want to completely undeploy an application.</span></span> <span data-ttu-id="38bf1-127">请注意，任何仍在处理消息的正在运行的实例将不会完成处理。</span><span class="sxs-lookup"><span data-stu-id="38bf1-127">Note that any running instances that are still processing messages will not complete processing.</span></span> <span data-ttu-id="38bf1-128">有关详细信息，请参阅[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf1-128">For more information, see [Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="38bf1-129">必要條件</span><span class="sxs-lookup"><span data-stu-id="38bf1-129">Prerequisites</span></span>  
 <span data-ttu-id="38bf1-130">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="38bf1-130">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="38bf1-131">BizTalk 操作员可以执行部分停止，但不能执行完全停止。</span><span class="sxs-lookup"><span data-stu-id="38bf1-131">BizTalk Operators can perform a partial stop, but not a full stop.</span></span> <span data-ttu-id="38bf1-132">此外，如果所有项目都已登记，则 BizTalk 操作员可以启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="38bf1-132">In addition, BizTalk Operators can start an application if all artifacts are enlisted.</span></span> <span data-ttu-id="38bf1-133">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf1-133">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-or-stop-a-biztalk-application"></a><span data-ttu-id="38bf1-134">启动或停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="38bf1-134">To start or stop a BizTalk application</span></span>  
  
1. <span data-ttu-id="38bf1-135">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="38bf1-135">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="38bf1-136">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="38bf1-136">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="38bf1-137">右键单击你想要启动或停止，，然后单击 BizTalk 应用程序**启动**或**停止**。</span><span class="sxs-lookup"><span data-stu-id="38bf1-137">Right-click the BizTalk application that you want to start or stop, and then click **Start** or **Stop**.</span></span>  
  
4. <span data-ttu-id="38bf1-138">选择开始或停止选项，并单击**启动**或**停止**。</span><span class="sxs-lookup"><span data-stu-id="38bf1-138">Select the start or stop options you want and click **Start** or **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38bf1-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="38bf1-139">See Also</span></span>  
 <span data-ttu-id="38bf1-140">[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="38bf1-140">[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="38bf1-141">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="38bf1-141">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)