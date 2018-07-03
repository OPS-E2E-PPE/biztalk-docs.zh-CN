---
title: 步骤 2： 配置并启动应用程序 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8edeb1cdb1f24774ec7c1e615377d81e4393c9dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024547"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="d88bc-102">步骤 2： 配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="d88bc-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="d88bc-103">![步骤 2 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="d88bc-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="d88bc-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="d88bc-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="d88bc-105">**目标：** 在此步骤中，配置并启动 EAISolution 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d88bc-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="d88bc-106">**目的：** 的配置是主要是关于绑定。</span><span class="sxs-lookup"><span data-stu-id="d88bc-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="d88bc-107">绑定可以在逻辑终结点（如业务流程端口或角色链接）与物理终结点（如发送/接收端口或参与方）之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="d88bc-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="d88bc-108">这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="d88bc-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="d88bc-109">使用 BizTalk Server 管理控制台可以创建绑定。</span><span class="sxs-lookup"><span data-stu-id="d88bc-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d88bc-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="d88bc-110">Prerequisites</span></span>  
 <span data-ttu-id="d88bc-111">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="d88bc-111">Note the following requirements before you begin this step:</span></span>  
  
- <span data-ttu-id="d88bc-112">在开始此步骤之前，必须完成[步骤 1： 将项目部署](../core/step-1-deploy-the-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="d88bc-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
- <span data-ttu-id="d88bc-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="d88bc-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d88bc-114">过程</span><span class="sxs-lookup"><span data-stu-id="d88bc-114">Procedures</span></span>  
 <span data-ttu-id="d88bc-115">BizTalk 应用程序是 BizTalk Server 的一项功能，可使你更快、更轻松地对 BizTalk Server 业务解决方案进行部署、管理和故障排除。</span><span class="sxs-lookup"><span data-stu-id="d88bc-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="d88bc-116">BizTalk 应用程序是 BizTalk Server 业务解决方案中使用的项（称为“项目”）的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="d88bc-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="d88bc-117">有关详细信息，请参阅[什么是 BizTalk 应用程序？](../core/what-is-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d88bc-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="d88bc-118">在中[步骤 1： 将项目部署](../core/step-1-deploy-the-projects.md)，我们配置的应用程序名称为"EAISolution"，然后再部署项目。</span><span class="sxs-lookup"><span data-stu-id="d88bc-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="d88bc-119">因此，EAISolution 应用程序中包含一个业务流程、两个架构和一个映射。</span><span class="sxs-lookup"><span data-stu-id="d88bc-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="d88bc-120">从 BizTalk Server 管理控制台打开 EAISolution 应用程序</span><span class="sxs-lookup"><span data-stu-id="d88bc-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1. <span data-ttu-id="d88bc-121">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d88bc-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="d88bc-122">在控制台树中的左侧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="d88bc-123">展开**BizTalk 组**，展开**应用程序**，然后单击**EAISolution**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
   <span data-ttu-id="d88bc-124">在中[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)，我们创建了业务流程。</span><span class="sxs-lookup"><span data-stu-id="d88bc-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="d88bc-125">在此业务流程中，我们定义了逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="d88bc-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="d88bc-126">在下面的过程中，您将定义物理端口并将物理端口绑定到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="d88bc-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="d88bc-127">创建 ReceiveRequest 端口</span><span class="sxs-lookup"><span data-stu-id="d88bc-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="d88bc-128">从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="d88bc-129">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d88bc-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-130">Use this</span></span>|<span data-ttu-id="d88bc-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-132">**名称**</span><span class="sxs-lookup"><span data-stu-id="d88bc-132">**Name**</span></span>|<span data-ttu-id="d88bc-133">类型**EAISolutionReceiveRequestPort**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="d88bc-134">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="d88bc-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="d88bc-135">（清除）</span><span class="sxs-lookup"><span data-stu-id="d88bc-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="d88bc-136">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="d88bc-137">从接收位置 1 – 接收位置属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d88bc-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-138">Use this</span></span>|<span data-ttu-id="d88bc-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="d88bc-140">**Name**</span></span>|<span data-ttu-id="d88bc-141">类型**EAISolutionReceiveRequestLocation**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="d88bc-142">**类型**</span><span class="sxs-lookup"><span data-stu-id="d88bc-142">**Type**</span></span>|<span data-ttu-id="d88bc-143">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-143">Select **File**.</span></span>|  
    |<span data-ttu-id="d88bc-144">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="d88bc-144">**Receive handler**</span></span>|<span data-ttu-id="d88bc-145">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="d88bc-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d88bc-146">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="d88bc-146">**Receive pipeline**</span></span>|<span data-ttu-id="d88bc-147">选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="d88bc-148">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d88bc-149">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d88bc-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-150">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-150">Use this</span></span>|<span data-ttu-id="d88bc-151">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-152">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="d88bc-152">**Receive folder**</span></span>|<span data-ttu-id="d88bc-153">类型**C:\BTSTutorials\WareHouse\Request**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="d88bc-154">单击**确定**三次。</span><span class="sxs-lookup"><span data-stu-id="d88bc-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="d88bc-155">若要创建 SendDecline 端口</span><span class="sxs-lookup"><span data-stu-id="d88bc-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="d88bc-156">从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="d88bc-157">在“常规”选项卡上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d88bc-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-158">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-158">Use this</span></span>|<span data-ttu-id="d88bc-159">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-160">**名称**</span><span class="sxs-lookup"><span data-stu-id="d88bc-160">**Name**</span></span>|<span data-ttu-id="d88bc-161">类型**EAISolutionSendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="d88bc-162">**类型**</span><span class="sxs-lookup"><span data-stu-id="d88bc-162">**Type**</span></span>|<span data-ttu-id="d88bc-163">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-163">Select **File**.</span></span>|  
    |<span data-ttu-id="d88bc-164">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="d88bc-164">**Send handler**</span></span>|<span data-ttu-id="d88bc-165">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="d88bc-166">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d88bc-166">**Send pipeline**</span></span>|<span data-ttu-id="d88bc-167">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="d88bc-168">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="d88bc-169">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d88bc-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-170">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-170">Use this</span></span>|<span data-ttu-id="d88bc-171">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-172">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="d88bc-172">**Receive folder**</span></span>|<span data-ttu-id="d88bc-173">类型**C:\BTSTutorials\WareHouse\RequestDecline**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="d88bc-174">**文件名**</span><span class="sxs-lookup"><span data-stu-id="d88bc-174">**File name**</span></span>|<span data-ttu-id="d88bc-175">类型**RequestDecline_%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="d88bc-176">单击两次 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d88bc-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="d88bc-177">若要创建 SendToERP 端口</span><span class="sxs-lookup"><span data-stu-id="d88bc-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="d88bc-178">从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="d88bc-179">在“常规”选项卡上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d88bc-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-180">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-180">Use this</span></span>|<span data-ttu-id="d88bc-181">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-182">**名称**</span><span class="sxs-lookup"><span data-stu-id="d88bc-182">**Name**</span></span>|<span data-ttu-id="d88bc-183">类型**EAISolutionSendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="d88bc-184">**类型**</span><span class="sxs-lookup"><span data-stu-id="d88bc-184">**Type**</span></span>|<span data-ttu-id="d88bc-185">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-185">Select **File**.</span></span>|  
    |<span data-ttu-id="d88bc-186">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="d88bc-186">**Send handler**</span></span>|<span data-ttu-id="d88bc-187">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="d88bc-188">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d88bc-188">**Send pipeline**</span></span>|<span data-ttu-id="d88bc-189">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="d88bc-190">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="d88bc-191">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d88bc-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-192">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-192">Use this</span></span>|<span data-ttu-id="d88bc-193">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-194">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="d88bc-194">**Receive folder**</span></span>|<span data-ttu-id="d88bc-195">类型**C:\BTSTutorials\ERP\Request**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="d88bc-196">**文件名**</span><span class="sxs-lookup"><span data-stu-id="d88bc-196">**File name**</span></span>|<span data-ttu-id="d88bc-197">类型**Request_%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="d88bc-198">单击两次 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d88bc-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="d88bc-199">绑定端口</span><span class="sxs-lookup"><span data-stu-id="d88bc-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="d88bc-200">从 BizTalk Server 管理控制台中，右键单击**EAISolution**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="d88bc-201">配置应用程序，在左窗格中，单击**EAIProcess**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="d88bc-202">这是我们创建的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d88bc-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="d88bc-203">在右窗格中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d88bc-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="d88bc-204">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d88bc-204">Use this</span></span>|<span data-ttu-id="d88bc-205">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d88bc-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d88bc-206">**主机**</span><span class="sxs-lookup"><span data-stu-id="d88bc-206">**Host**</span></span>|<span data-ttu-id="d88bc-207">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="d88bc-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d88bc-208">**接收端口**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="d88bc-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="d88bc-209">选择**EAISolutionReceiveReqeustPort**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="d88bc-210">**发送 PortsSend 端口组**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="d88bc-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="d88bc-211">选择**EAISolutionSendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="d88bc-212">**接收端口**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="d88bc-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="d88bc-213">选择**EAISolutionSendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="d88bc-214">单击**确定**保存配置。</span><span class="sxs-lookup"><span data-stu-id="d88bc-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="d88bc-215">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="d88bc-215">To start the application</span></span>  
  
1.  <span data-ttu-id="d88bc-216">从 BizTalk Server 管理控制台中，右键单击**EAISolution**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="d88bc-217">从对话框中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="d88bc-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d88bc-218">内容回顾</span><span class="sxs-lookup"><span data-stu-id="d88bc-218">What did I just do?</span></span>  
 <span data-ttu-id="d88bc-219">在此步骤中，您配置并启动了 EAIApplication 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d88bc-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d88bc-220">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d88bc-220">Next Steps</span></span>  
 <span data-ttu-id="d88bc-221">测试 EAI 解决方案如何处理中的消息[第 3 步： 测试解决方案](../core/step-3-test-the-solution2.md)。</span><span class="sxs-lookup"><span data-stu-id="d88bc-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88bc-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="d88bc-222">See Also</span></span>  
 <span data-ttu-id="d88bc-223">[步骤 1： 部署项目](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="d88bc-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="d88bc-224">步骤 3：测试解决方案</span><span class="sxs-lookup"><span data-stu-id="d88bc-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)