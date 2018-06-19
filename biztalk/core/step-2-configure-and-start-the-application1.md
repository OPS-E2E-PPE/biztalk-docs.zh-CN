---
title: 步骤 2： 配置并启动应用程序 1 |Microsoft 文档
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
ms.openlocfilehash: cc9c3c027126d3a461bf99329b70fda57b9be647
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280005"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="9e26a-102">步骤 2： 配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="9e26a-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="9e26a-103">![步骤 2 / 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="9e26a-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="9e26a-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="9e26a-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="9e26a-105">**目标：** 在此步骤中，可以配置和启动 EAISolution 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e26a-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="9e26a-106">**用途：** 配置主要是指绑定。</span><span class="sxs-lookup"><span data-stu-id="9e26a-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="9e26a-107">绑定可以在逻辑终结点（如业务流程端口或角色链接）与物理终结点（如发送/接收端口或参与方）之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="9e26a-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="9e26a-108">这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="9e26a-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="9e26a-109">使用 BizTalk Server 管理控制台可以创建绑定。</span><span class="sxs-lookup"><span data-stu-id="9e26a-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e26a-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="9e26a-110">Prerequisites</span></span>  
 <span data-ttu-id="9e26a-111">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="9e26a-111">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="9e26a-112">在开始此步骤之前必须完成[步骤 1： 将项目部署](../core/step-1-deploy-the-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="9e26a-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
-   <span data-ttu-id="9e26a-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="9e26a-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9e26a-114">过程</span><span class="sxs-lookup"><span data-stu-id="9e26a-114">Procedures</span></span>  
 <span data-ttu-id="9e26a-115">BizTalk 应用程序是 BizTalk Server 的一项功能，可使你更快、更轻松地对 BizTalk Server 业务解决方案进行部署、管理和故障排除。</span><span class="sxs-lookup"><span data-stu-id="9e26a-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="9e26a-116">BizTalk 应用程序是 BizTalk Server 业务解决方案中使用的项（称为“项目”）的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="9e26a-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="9e26a-117">有关详细信息，请参阅[BizTalk 应用程序是什么？](../core/what-is-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9e26a-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="9e26a-118">在[步骤 1： 将项目部署](../core/step-1-deploy-the-projects.md)，我们配置我们部署项目之前要"EAISolution"的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="9e26a-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="9e26a-119">因此，EAISolution 应用程序中包含一个业务流程、两个架构和一个映射。</span><span class="sxs-lookup"><span data-stu-id="9e26a-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="9e26a-120">从 BizTalk Server 管理控制台打开 EAISolution 应用程序</span><span class="sxs-lookup"><span data-stu-id="9e26a-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="9e26a-121">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e26a-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="9e26a-122">在控制台树中的左侧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="9e26a-123">展开**BizTalk 组**，展开**应用程序**，然后单击**EAISolution**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
 <span data-ttu-id="9e26a-124">在[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)，我们创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="9e26a-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="9e26a-125">在此业务流程中，我们定义了逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="9e26a-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="9e26a-126">在下面的过程中，您将定义物理端口并将物理端口绑定到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="9e26a-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="9e26a-127">创建 ReceiveRequest 端口</span><span class="sxs-lookup"><span data-stu-id="9e26a-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="9e26a-128">从 BizTalk Server 管理控制台，在**EAISolution**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="9e26a-129">在常规选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-130">Use this</span></span>|<span data-ttu-id="9e26a-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-132">**名称**</span><span class="sxs-lookup"><span data-stu-id="9e26a-132">**Name**</span></span>|<span data-ttu-id="9e26a-133">类型**EAISolutionReceiveRequestPort**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="9e26a-134">**启用路由失败消息**</span><span class="sxs-lookup"><span data-stu-id="9e26a-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="9e26a-135">（清除）</span><span class="sxs-lookup"><span data-stu-id="9e26a-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="9e26a-136">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="9e26a-137">从接收位置 1 – 接收位置属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-138">Use this</span></span>|<span data-ttu-id="9e26a-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="9e26a-140">**Name**</span></span>|<span data-ttu-id="9e26a-141">类型**EAISolutionReceiveRequestLocation**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="9e26a-142">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e26a-142">**Type**</span></span>|<span data-ttu-id="9e26a-143">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-143">Select **File**.</span></span>|  
    |<span data-ttu-id="9e26a-144">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="9e26a-144">**Receive handler**</span></span>|<span data-ttu-id="9e26a-145">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="9e26a-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="9e26a-146">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="9e26a-146">**Receive pipeline**</span></span>|<span data-ttu-id="9e26a-147">选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="9e26a-148">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="9e26a-149">从文件传输属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-150">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-150">Use this</span></span>|<span data-ttu-id="9e26a-151">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-152">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="9e26a-152">**Receive folder**</span></span>|<span data-ttu-id="9e26a-153">类型**C:\BTSTutorials\WareHouse\Request**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="9e26a-154">单击**确定**三次。</span><span class="sxs-lookup"><span data-stu-id="9e26a-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="9e26a-155">若要创建 SendDecline 端口</span><span class="sxs-lookup"><span data-stu-id="9e26a-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="9e26a-156">从 BizTalk Server 管理控制台，在**EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="9e26a-157">在“常规”选项卡上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-158">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-158">Use this</span></span>|<span data-ttu-id="9e26a-159">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-160">**名称**</span><span class="sxs-lookup"><span data-stu-id="9e26a-160">**Name**</span></span>|<span data-ttu-id="9e26a-161">类型**EAISolutionSendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="9e26a-162">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e26a-162">**Type**</span></span>|<span data-ttu-id="9e26a-163">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-163">Select **File**.</span></span>|  
    |<span data-ttu-id="9e26a-164">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="9e26a-164">**Send handler**</span></span>|<span data-ttu-id="9e26a-165">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="9e26a-166">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="9e26a-166">**Send pipeline**</span></span>|<span data-ttu-id="9e26a-167">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="9e26a-168">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="9e26a-169">从文件传输属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-170">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-170">Use this</span></span>|<span data-ttu-id="9e26a-171">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-172">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="9e26a-172">**Receive folder**</span></span>|<span data-ttu-id="9e26a-173">类型**C:\BTSTutorials\WareHouse\RequestDecline**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="9e26a-174">**文件名**</span><span class="sxs-lookup"><span data-stu-id="9e26a-174">**File name**</span></span>|<span data-ttu-id="9e26a-175">类型**RequestDecline_%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="9e26a-176">单击两次 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="9e26a-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="9e26a-177">若要创建 SendToERP 端口</span><span class="sxs-lookup"><span data-stu-id="9e26a-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="9e26a-178">从 BizTalk Server 管理控制台，在**EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="9e26a-179">在“常规”选项卡上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-180">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-180">Use this</span></span>|<span data-ttu-id="9e26a-181">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-182">**名称**</span><span class="sxs-lookup"><span data-stu-id="9e26a-182">**Name**</span></span>|<span data-ttu-id="9e26a-183">类型**EAISolutionSendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="9e26a-184">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e26a-184">**Type**</span></span>|<span data-ttu-id="9e26a-185">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-185">Select **File**.</span></span>|  
    |<span data-ttu-id="9e26a-186">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="9e26a-186">**Send handler**</span></span>|<span data-ttu-id="9e26a-187">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="9e26a-188">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="9e26a-188">**Send pipeline**</span></span>|<span data-ttu-id="9e26a-189">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="9e26a-190">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="9e26a-191">从文件传输属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-192">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-192">Use this</span></span>|<span data-ttu-id="9e26a-193">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-194">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="9e26a-194">**Receive folder**</span></span>|<span data-ttu-id="9e26a-195">类型**C:\BTSTutorials\ERP\Request**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="9e26a-196">**文件名**</span><span class="sxs-lookup"><span data-stu-id="9e26a-196">**File name**</span></span>|<span data-ttu-id="9e26a-197">类型**Request_%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="9e26a-198">单击两次 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="9e26a-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="9e26a-199">绑定端口</span><span class="sxs-lookup"><span data-stu-id="9e26a-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="9e26a-200">从 BizTalk Server 管理控制台，右键单击**EAISolution**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="9e26a-201">配置应用程序，在左窗格中，单击**eai 进程**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="9e26a-202">这是我们创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="9e26a-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="9e26a-203">从右窗格中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e26a-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="9e26a-204">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9e26a-204">Use this</span></span>|<span data-ttu-id="9e26a-205">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e26a-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e26a-206">**主机**</span><span class="sxs-lookup"><span data-stu-id="9e26a-206">**Host**</span></span>|<span data-ttu-id="9e26a-207">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="9e26a-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="9e26a-208">**接收端口**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="9e26a-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="9e26a-209">选择**EAISolutionReceiveReqeustPort**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="9e26a-210">**发送 PortsSend 端口组**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="9e26a-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="9e26a-211">选择**EAISolutionSendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="9e26a-212">**接收端口**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="9e26a-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="9e26a-213">选择**EAISolutionSendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="9e26a-214">单击**确定**保存配置。</span><span class="sxs-lookup"><span data-stu-id="9e26a-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="9e26a-215">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="9e26a-215">To start the application</span></span>  
  
1.  <span data-ttu-id="9e26a-216">从 BizTalk Server 管理控制台，右键单击**EAISolution**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="9e26a-217">在对话框中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="9e26a-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9e26a-218">内容回顾</span><span class="sxs-lookup"><span data-stu-id="9e26a-218">What did I just do?</span></span>  
 <span data-ttu-id="9e26a-219">在此步骤中，您配置并启动了 EAIApplication 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e26a-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e26a-220">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9e26a-220">Next Steps</span></span>  
 <span data-ttu-id="9e26a-221">测试 EAI 解决方案如何处理中的消息[步骤 3： 测试解决方案](../core/step-3-test-the-solution2.md)。</span><span class="sxs-lookup"><span data-stu-id="9e26a-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e26a-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e26a-222">See Also</span></span>  
 <span data-ttu-id="9e26a-223">[步骤 1： 部署项目](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="9e26a-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="9e26a-224">步骤 3： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="9e26a-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)