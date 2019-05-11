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
ms.openlocfilehash: c696583f8e08ad9588e4e00fed24151646a727ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334093"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a><span data-ttu-id="eee03-102">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="eee03-102">How to Start and Stop a BizTalk Application</span></span>
<span data-ttu-id="eee03-103">本主题介绍如何使用 BizTalk Server 管理控制台来启动和停止 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eee03-103">This topic describes how to use the BizTalk Server Administration console to start and stop a BizTalk application.</span></span>  
  
 <span data-ttu-id="eee03-104">如中所述，可以启动应用程序之前，必须为它所包含的所有业务流程中配置绑定[如何配置业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="eee03-104">Before you can start an application, bindings must be configured for all orchestrations it contains, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="eee03-105">启动应用程序时，可以按如下所示选择一个或多个以下选项：</span><span class="sxs-lookup"><span data-stu-id="eee03-105">When you start an application, you can select one or more of the following options, as follows:</span></span>  
  
-   <span data-ttu-id="eee03-106">登记并启动所有业务流程。</span><span class="sxs-lookup"><span data-stu-id="eee03-106">Enlist and start all orchestrations.</span></span>  
  
-   <span data-ttu-id="eee03-107">登记并启动所有发送端口。</span><span class="sxs-lookup"><span data-stu-id="eee03-107">Enlist and start all send ports.</span></span>  
  
-   <span data-ttu-id="eee03-108">登记并启动所有发送端口组。</span><span class="sxs-lookup"><span data-stu-id="eee03-108">Enlist and start all send port groups.</span></span>  
  
-   <span data-ttu-id="eee03-109">启用所有接收位置。</span><span class="sxs-lookup"><span data-stu-id="eee03-109">Enable all receive locations.</span></span>  
  
-   <span data-ttu-id="eee03-110">启动所有关联的主机实例。</span><span class="sxs-lookup"><span data-stu-id="eee03-110">Start all associated host instances.</span></span>  
  
-   <span data-ttu-id="eee03-111">恢复挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="eee03-111">Resume suspended instances.</span></span>  
  
-   <span data-ttu-id="eee03-112">部署所有策略。</span><span class="sxs-lookup"><span data-stu-id="eee03-112">Deploy all policies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eee03-113">仅在应用程序中已发布的策略自动部署。</span><span class="sxs-lookup"><span data-stu-id="eee03-113">Only published policies in the application are deployed automatically.</span></span> <span data-ttu-id="eee03-114">如果策略未发布，它将不部署。</span><span class="sxs-lookup"><span data-stu-id="eee03-114">If a policy is not published, it will not be deployed.</span></span>  
  
 <span data-ttu-id="eee03-115">当你停止应用程序时，可以选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="eee03-115">When you stop an application, you can select one of the following options:</span></span>  
  
-   <span data-ttu-id="eee03-116">**部分停止-允许正在运行的实例以继续。**</span><span class="sxs-lookup"><span data-stu-id="eee03-116">**Partial Stop - Allow running instances to continue.**</span></span> <span data-ttu-id="eee03-117">此选项将禁用所有应用程序中的接收位置，但在其以前的状态中保留所有其他项目。</span><span class="sxs-lookup"><span data-stu-id="eee03-117">This option disables all receive locations in the application, but leaves all other artifacts in their previous state.</span></span> <span data-ttu-id="eee03-118">这允许正在运行的实例来完成当前正在系统处理消息。</span><span class="sxs-lookup"><span data-stu-id="eee03-118">This allows running instances to complete processing messages that are currently in the system.</span></span> <span data-ttu-id="eee03-119">请注意，是否消息事务需要多个输入，它可能不能使用此选项时完成。</span><span class="sxs-lookup"><span data-stu-id="eee03-119">Note that if a message transaction requires multiple inputs, it may not be able to complete when you use this option.</span></span>  
  
-   <span data-ttu-id="eee03-120">**部分停止-挂起正在运行的实例。**</span><span class="sxs-lookup"><span data-stu-id="eee03-120">**Partial Stop - Suspend running instances.**</span></span> <span data-ttu-id="eee03-121">此选项禁用所有接收位置并停止所有业务流程和发送端口的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="eee03-121">This option disables all receive locations and stops all orchestrations and send ports in the application.</span></span> <span data-ttu-id="eee03-122">它不会取消登记或取消部署任何项目。</span><span class="sxs-lookup"><span data-stu-id="eee03-122">It does not unenlist or undeploy any artifacts.</span></span> <span data-ttu-id="eee03-123">如果你想要暂时暂停应用程序，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="eee03-123">Use this option when you want to temporarily pause the application.</span></span>  
  
-   <span data-ttu-id="eee03-124">**完全停止-终止实例。**</span><span class="sxs-lookup"><span data-stu-id="eee03-124">**Full Stop - Terminate instances.**</span></span> <span data-ttu-id="eee03-125">此选项将禁用所有接收位置，停止和取消登记所有业务流程和发送端口，并取消部署该应用程序中的所有策略。</span><span class="sxs-lookup"><span data-stu-id="eee03-125">This option disables all receive locations, stops and unenlists all orchestrations and send ports, and undeploys all policies in the application.</span></span> <span data-ttu-id="eee03-126">如果你想要完全取消部署应用程序，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="eee03-126">Use this option when you want to completely undeploy an application.</span></span> <span data-ttu-id="eee03-127">请注意任何正在运行的实例仍在处理消息，将无法完成处理。</span><span class="sxs-lookup"><span data-stu-id="eee03-127">Note that any running instances that are still processing messages will not complete processing.</span></span> <span data-ttu-id="eee03-128">有关详细信息，请参阅[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="eee03-128">For more information, see [Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eee03-129">先决条件</span><span class="sxs-lookup"><span data-stu-id="eee03-129">Prerequisites</span></span>  
 <span data-ttu-id="eee03-130">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="eee03-130">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="eee03-131">BizTalk 操作员可以执行部分停止，但不是完全停止。</span><span class="sxs-lookup"><span data-stu-id="eee03-131">BizTalk Operators can perform a partial stop, but not a full stop.</span></span> <span data-ttu-id="eee03-132">此外，BizTalk 操作员可以启动应用程序，如果所有项目都已都登记。</span><span class="sxs-lookup"><span data-stu-id="eee03-132">In addition, BizTalk Operators can start an application if all artifacts are enlisted.</span></span> <span data-ttu-id="eee03-133">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="eee03-133">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-or-stop-a-biztalk-application"></a><span data-ttu-id="eee03-134">若要启动或停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="eee03-134">To start or stop a BizTalk application</span></span>  
  
1. <span data-ttu-id="eee03-135">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="eee03-135">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="eee03-136">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="eee03-136">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="eee03-137">右键单击你想要启动或停止，，然后单击 BizTalk 应用程序**启动**或**停止**。</span><span class="sxs-lookup"><span data-stu-id="eee03-137">Right-click the BizTalk application that you want to start or stop, and then click **Start** or **Stop**.</span></span>  
  
4. <span data-ttu-id="eee03-138">选择开始或停止选项，并单击**启动**或**停止**。</span><span class="sxs-lookup"><span data-stu-id="eee03-138">Select the start or stop options you want and click **Start** or **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee03-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="eee03-139">See Also</span></span>  
 <span data-ttu-id="eee03-140">[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="eee03-140">[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="eee03-141">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="eee03-141">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)