---
title: 第 2 步：配置并启动应用程序 1 |Microsoft Docs
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
ms.openlocfilehash: 07fbdba63325f44a803fe4e9c5e83fbd5d31240e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392774"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="7ba09-102">第 2 步：配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="7ba09-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="7ba09-103">![步骤 2 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="7ba09-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="7ba09-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="7ba09-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="7ba09-105">**目标：** 在此步骤中，你可以配置并启动 EAISolution 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ba09-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="7ba09-106">**目的：** 主要是关于绑定配置。</span><span class="sxs-lookup"><span data-stu-id="7ba09-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="7ba09-107">一个绑定和之间创建映射逻辑终结点，如业务流程端口或角色链接，物理终结点，如发送和接收端口或参与方。</span><span class="sxs-lookup"><span data-stu-id="7ba09-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="7ba09-108">这样，BizTalk 业务解决方案的不同组件之间的通信。</span><span class="sxs-lookup"><span data-stu-id="7ba09-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="7ba09-109">可以使用 BizTalk Server 管理控制台来创建绑定。</span><span class="sxs-lookup"><span data-stu-id="7ba09-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7ba09-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="7ba09-110">Prerequisites</span></span>  
 <span data-ttu-id="7ba09-111">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="7ba09-111">Note the following requirements before you begin this step:</span></span>  
  
- <span data-ttu-id="7ba09-112">在开始此步骤之前，必须完成[步骤 1:将项目部署](../core/step-1-deploy-the-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="7ba09-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
- <span data-ttu-id="7ba09-113">您必须作为的成员登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="7ba09-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7ba09-114">过程</span><span class="sxs-lookup"><span data-stu-id="7ba09-114">Procedures</span></span>  
 <span data-ttu-id="7ba09-115">BizTalk 应用程序是一项功能会更加快速、 更轻松地部署、 管理和故障排除 BizTalk Server 业务解决方案的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="7ba09-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="7ba09-116">BizTalk 应用程序是称为"项目，"BizTalk Server 业务解决方案中使用的项的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="7ba09-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="7ba09-117">有关详细信息，请参阅[什么是 BizTalk 应用程序？](../core/what-is-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7ba09-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="7ba09-118">在[步骤 1:将项目部署](../core/step-1-deploy-the-projects.md)，我们配置的应用程序名称为"EAISolution"，然后再部署项目。</span><span class="sxs-lookup"><span data-stu-id="7ba09-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="7ba09-119">因此，EAISolution 应用程序包含业务流程、 两个架构和映射。</span><span class="sxs-lookup"><span data-stu-id="7ba09-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="7ba09-120">若要从 BizTalk Server 管理控制台打开 EAISolution 应用程序</span><span class="sxs-lookup"><span data-stu-id="7ba09-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1. <span data-ttu-id="7ba09-121">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7ba09-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="7ba09-122">在控制台树中的左侧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="7ba09-123">展开**BizTalk 组**，展开**应用程序**，然后单击**EAISolution**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
   <span data-ttu-id="7ba09-124">在 [第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)，我们创建了业务流程。</span><span class="sxs-lookup"><span data-stu-id="7ba09-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="7ba09-125">在业务流程，我们定义了逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="7ba09-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="7ba09-126">在以下过程中，将定义物理端口并将物理端口绑定到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="7ba09-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="7ba09-127">创建 ReceiveRequest 端口</span><span class="sxs-lookup"><span data-stu-id="7ba09-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="7ba09-128">从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="7ba09-129">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-130">Use this</span></span>|<span data-ttu-id="7ba09-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-132">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ba09-132">**Name**</span></span>|<span data-ttu-id="7ba09-133">类型**EAISolutionReceiveRequestPort**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="7ba09-134">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="7ba09-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="7ba09-135">（清除）</span><span class="sxs-lookup"><span data-stu-id="7ba09-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="7ba09-136">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="7ba09-137">从接收位置 1 – 接收位置属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ba09-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-138">Use this</span></span>|<span data-ttu-id="7ba09-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ba09-140">**Name**</span></span>|<span data-ttu-id="7ba09-141">类型**EAISolutionReceiveRequestLocation**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="7ba09-142">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ba09-142">**Type**</span></span>|<span data-ttu-id="7ba09-143">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-143">Select **File**.</span></span>|  
    |<span data-ttu-id="7ba09-144">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="7ba09-144">**Receive handler**</span></span>|<span data-ttu-id="7ba09-145">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="7ba09-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="7ba09-146">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="7ba09-146">**Receive pipeline**</span></span>|<span data-ttu-id="7ba09-147">选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="7ba09-148">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="7ba09-149">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-150">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-150">Use this</span></span>|<span data-ttu-id="7ba09-151">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-152">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="7ba09-152">**Receive folder**</span></span>|<span data-ttu-id="7ba09-153">类型**C:\BTSTutorials\WareHouse\Request**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="7ba09-154">单击**确定**三次。</span><span class="sxs-lookup"><span data-stu-id="7ba09-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="7ba09-155">若要创建 SendDecline 端口</span><span class="sxs-lookup"><span data-stu-id="7ba09-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="7ba09-156">从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="7ba09-157">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-158">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-158">Use this</span></span>|<span data-ttu-id="7ba09-159">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-160">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ba09-160">**Name**</span></span>|<span data-ttu-id="7ba09-161">类型**EAISolutionSendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="7ba09-162">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ba09-162">**Type**</span></span>|<span data-ttu-id="7ba09-163">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-163">Select **File**.</span></span>|  
    |<span data-ttu-id="7ba09-164">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="7ba09-164">**Send handler**</span></span>|<span data-ttu-id="7ba09-165">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="7ba09-166">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="7ba09-166">**Send pipeline**</span></span>|<span data-ttu-id="7ba09-167">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="7ba09-168">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="7ba09-169">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-170">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-170">Use this</span></span>|<span data-ttu-id="7ba09-171">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-172">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="7ba09-172">**Receive folder**</span></span>|<span data-ttu-id="7ba09-173">类型**C:\BTSTutorials\WareHouse\RequestDecline**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="7ba09-174">**文件名**</span><span class="sxs-lookup"><span data-stu-id="7ba09-174">**File name**</span></span>|<span data-ttu-id="7ba09-175">类型**RequestDecline_%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="7ba09-176">单击两次 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="7ba09-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="7ba09-177">若要创建 SendToERP 端口</span><span class="sxs-lookup"><span data-stu-id="7ba09-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="7ba09-178">从 BizTalk Server 管理控制台中下, **EAISolution**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="7ba09-179">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-180">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-180">Use this</span></span>|<span data-ttu-id="7ba09-181">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-182">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ba09-182">**Name**</span></span>|<span data-ttu-id="7ba09-183">类型**EAISolutionSendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="7ba09-184">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ba09-184">**Type**</span></span>|<span data-ttu-id="7ba09-185">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-185">Select **File**.</span></span>|  
    |<span data-ttu-id="7ba09-186">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="7ba09-186">**Send handler**</span></span>|<span data-ttu-id="7ba09-187">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="7ba09-188">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="7ba09-188">**Send pipeline**</span></span>|<span data-ttu-id="7ba09-189">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="7ba09-190">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="7ba09-191">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-192">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-192">Use this</span></span>|<span data-ttu-id="7ba09-193">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-194">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="7ba09-194">**Receive folder**</span></span>|<span data-ttu-id="7ba09-195">类型**C:\BTSTutorials\ERP\Request**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="7ba09-196">**文件名**</span><span class="sxs-lookup"><span data-stu-id="7ba09-196">**File name**</span></span>|<span data-ttu-id="7ba09-197">类型**Request_%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="7ba09-198">单击两次 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="7ba09-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="7ba09-199">若要将端口绑定</span><span class="sxs-lookup"><span data-stu-id="7ba09-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="7ba09-200">从 BizTalk Server 管理控制台中，右键单击**EAISolution**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="7ba09-201">配置应用程序，在左窗格中，单击**EAIProcess**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="7ba09-202">这是我们创建的业务流程。</span><span class="sxs-lookup"><span data-stu-id="7ba09-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="7ba09-203">在右窗格中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7ba09-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="7ba09-204">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7ba09-204">Use this</span></span>|<span data-ttu-id="7ba09-205">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ba09-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7ba09-206">**主机**</span><span class="sxs-lookup"><span data-stu-id="7ba09-206">**Host**</span></span>|<span data-ttu-id="7ba09-207">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="7ba09-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="7ba09-208">**接收端口**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="7ba09-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="7ba09-209">选择**EAISolutionReceiveReqeustPort**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="7ba09-210">**发送 PortsSend 端口组**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="7ba09-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="7ba09-211">选择**EAISolutionSendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="7ba09-212">**接收端口**为**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="7ba09-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="7ba09-213">选择**EAISolutionSendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="7ba09-214">单击**确定**保存配置。</span><span class="sxs-lookup"><span data-stu-id="7ba09-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="7ba09-215">若要启动该应用程序</span><span class="sxs-lookup"><span data-stu-id="7ba09-215">To start the application</span></span>  
  
1.  <span data-ttu-id="7ba09-216">从 BizTalk Server 管理控制台中，右键单击**EAISolution**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="7ba09-217">从对话框中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="7ba09-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="7ba09-218">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="7ba09-218">What did I just do?</span></span>  
 <span data-ttu-id="7ba09-219">在此步骤中，将配置并启动了 EAIApplication 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ba09-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7ba09-220">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7ba09-220">Next Steps</span></span>  
 <span data-ttu-id="7ba09-221">测试 EAI 解决方案如何处理中的消息[步骤 3:测试解决方案](../core/step-3-test-the-solution2.md)。</span><span class="sxs-lookup"><span data-stu-id="7ba09-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba09-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ba09-222">See Also</span></span>  
 <span data-ttu-id="7ba09-223">[步骤 1：将项目部署](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="7ba09-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="7ba09-224">步骤 3：测试解决方案</span><span class="sxs-lookup"><span data-stu-id="7ba09-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)