---
title: 步骤 2： 使用 Siebel 适配器在 BizTalk Server 管理控制台中配置业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f779c9b347c43fb9bd2a6dcdbdb3c33ac8ad09c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009126"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a><span data-ttu-id="e5fba-102">步骤 2： 使用 Siebel 适配器在 BizTalk Server 管理控制台中配置业务流程</span><span class="sxs-lookup"><span data-stu-id="e5fba-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console with the Siebel adapter</span></span>
<span data-ttu-id="e5fba-103">![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="e5fba-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="e5fba-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="e5fba-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="e5fba-105">**目标：** 在此步骤中，执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e5fba-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="e5fba-106">创建 WCF 自定义发送接收端口以发送和接收消息从 Siebel 系统使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5fba-106">Create a WCF-Custom send-receive port to send and receive messages from the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="e5fba-107">配置此端口以使用在上一步中创建的映射。</span><span class="sxs-lookup"><span data-stu-id="e5fba-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="e5fba-108">配置业务流程中使用 WCF 自定义端口的最后一步部署。</span><span class="sxs-lookup"><span data-stu-id="e5fba-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="e5fba-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="e5fba-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="e5fba-110">你必须部署你想要配置 WCF 自定义端口的 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="e5fba-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="e5fba-111">若要创建的 WCF 自定义端口</span><span class="sxs-lookup"><span data-stu-id="e5fba-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="e5fba-112">生成对 Siebel 系统使用的操作的架构时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e5fba-112">When you generate schema for an operation on the Siebel system using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="e5fba-113">您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。</span><span class="sxs-lookup"><span data-stu-id="e5fba-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="e5fba-114">有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)。</span><span class="sxs-lookup"><span data-stu-id="e5fba-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372).</span></span>  
  
2. <span data-ttu-id="e5fba-115">导入绑定文件后下, 创建的发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e5fba-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="e5fba-116">右键单击 WCF 自定义端口，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="e5fba-117">从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="e5fba-118">在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，并指定要连接到 Siebel 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="e5fba-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and specify the credentials to connect to a Siebel system.</span></span>  
  
6. <span data-ttu-id="e5fba-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e5fba-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="e5fba-120">从发送端口属性对话框的左窗格中，单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="e5fba-121">在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**ResponseMap**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="e5fba-122">![配置入站的映射](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")</span><span class="sxs-lookup"><span data-stu-id="e5fba-122">![Configure inbound map](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")</span></span>  
  
8. <span data-ttu-id="e5fba-123">从发送端口属性对话框的左窗格中，单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="e5fba-124">在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**RequestMap**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="e5fba-125">![配置出站映射](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")</span><span class="sxs-lookup"><span data-stu-id="e5fba-125">![Configure outbound map](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")</span></span>  
  
9. <span data-ttu-id="e5fba-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e5fba-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="e5fba-127">若要配置的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="e5fba-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="e5fba-128">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5fba-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="e5fba-129">右键单击 BizTalk 应用程序，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="e5fba-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="e5fba-130">从左窗格中，单击业务流程配置。</span><span class="sxs-lookup"><span data-stu-id="e5fba-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="e5fba-131">在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="e5fba-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="e5fba-132">下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。</span><span class="sxs-lookup"><span data-stu-id="e5fba-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="e5fba-133">选择将存放请求消息的文件端口。</span><span class="sxs-lookup"><span data-stu-id="e5fba-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="e5fba-134">BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e5fba-134">The BizTalk orchestration will consume the request message and send it to the Siebel system.</span></span>  
  
   2. <span data-ttu-id="e5fba-135">选择 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口。</span><span class="sxs-lookup"><span data-stu-id="e5fba-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Siebel system.</span></span>  
  
   3. <span data-ttu-id="e5fba-136">选择本主题中前面创建的 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="e5fba-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="e5fba-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e5fba-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="e5fba-138">有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360)。</span><span class="sxs-lookup"><span data-stu-id="e5fba-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e5fba-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5fba-139">Next Steps</span></span>  
 <span data-ttu-id="e5fba-140">你现在已经完成迁移到 BizTalk 项目，将消息发送到使用基于 WCF 的 Siebel 系统 vPrev BizTalk 项目的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5fba-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="e5fba-141">您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息调用帐户业务组件上的插入操作，如中所述[第 3 步： 测试迁移应用程序使用 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="e5fba-141">You must now test the migrated BizTalk application by sending a request message to invoke the Insert operation on the Account business component, as described in [Step 3: Test the Migrated Application with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fba-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5fba-142">See Also</span></span>  
 [<span data-ttu-id="e5fba-143">教程 2： 迁移中 Siebel 的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="e5fba-143">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)