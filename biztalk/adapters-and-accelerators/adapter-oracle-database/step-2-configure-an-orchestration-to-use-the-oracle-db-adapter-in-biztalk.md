---
title: 步骤 2： 配置业务流程在 BizTalk Server 管理控制台中使用 Oracle 数据库适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 598b4ab0-ff22-4dfa-aa9c-774c60c90227
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0a8b8035b27babeacd6e5ade8c2cc40c8af2d75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007862"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a><span data-ttu-id="1d782-102">步骤 2： 配置业务流程在 BizTalk Server 管理控制台中使用 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="1d782-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter</span></span>
<span data-ttu-id="1d782-103">![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="1d782-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="1d782-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="1d782-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="1d782-105">**目标：** 在此步骤中，执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1d782-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="1d782-106">创建 WCF 自定义发送接收端口以发送和接收消息从 Oracle 数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1d782-106">Create a WCF-Custom send-receive port to send and receive messages from the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="1d782-107">配置此端口以使用在上一步中创建的映射。</span><span class="sxs-lookup"><span data-stu-id="1d782-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="1d782-108">配置业务流程中使用 WCF 自定义端口的最后一步部署。</span><span class="sxs-lookup"><span data-stu-id="1d782-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="1d782-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="1d782-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="1d782-110">你必须部署你想要配置 WCF 自定义端口的 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="1d782-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="1d782-111">若要创建的 WCF 自定义端口</span><span class="sxs-lookup"><span data-stu-id="1d782-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="1d782-112">生成对 Oracle 数据库使用的操作的架构时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="1d782-112">When you generate schema for an operation on the Oracle database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="1d782-113">您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d782-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="1d782-114">有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f)。</span><span class="sxs-lookup"><span data-stu-id="1d782-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f).</span></span>  
  
2. <span data-ttu-id="1d782-115">导入绑定文件后下, 创建的发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1d782-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="1d782-116">右键单击 WCF 自定义端口，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1d782-116">Right-click the WCF-Custom port and click **Properties**.</span></span>  
  
4. <span data-ttu-id="1d782-117">从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1d782-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="1d782-118">在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后指定用于连接到 Oracle 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="1d782-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an Oracle database.</span></span>  
  
6. <span data-ttu-id="1d782-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1d782-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="1d782-120">从发送端口属性对话框的左窗格中，单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="1d782-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="1d782-121">在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**ResponseMap**。</span><span class="sxs-lookup"><span data-stu-id="1d782-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="1d782-122">![配置入站的映射](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span><span class="sxs-lookup"><span data-stu-id="1d782-122">![Configure inbound map](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span></span>  
  
8. <span data-ttu-id="1d782-123">从发送端口属性对话框的左窗格中，单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="1d782-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="1d782-124">在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**RequestMap**。</span><span class="sxs-lookup"><span data-stu-id="1d782-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="1d782-125">![配置出站映射](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span><span class="sxs-lookup"><span data-stu-id="1d782-125">![Configure outbound map](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span></span>  
  
9. <span data-ttu-id="1d782-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1d782-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="1d782-127">若要配置的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1d782-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="1d782-128">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d782-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="1d782-129">右键单击 BizTalk 应用程序，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="1d782-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="1d782-130">从左窗格中，单击业务流程配置。</span><span class="sxs-lookup"><span data-stu-id="1d782-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="1d782-131">在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="1d782-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="1d782-132">下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。</span><span class="sxs-lookup"><span data-stu-id="1d782-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="1d782-133">选择将存放请求消息的文件端口。</span><span class="sxs-lookup"><span data-stu-id="1d782-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="1d782-134">BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="1d782-134">The BizTalk orchestration will consume the request message and send it to the Oracle database.</span></span>  
  
   2. <span data-ttu-id="1d782-135">选择 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的文件端口。</span><span class="sxs-lookup"><span data-stu-id="1d782-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Oracle database.</span></span>  
  
   3. <span data-ttu-id="1d782-136">选择本主题中前面创建的 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="1d782-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="1d782-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1d782-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="1d782-138">有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkID=196961 ](http://go.microsoft.com/fwlink/?LinkID=196961)。</span><span class="sxs-lookup"><span data-stu-id="1d782-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1d782-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1d782-139">Next Steps</span></span>  
 <span data-ttu-id="1d782-140">你现在已经完成迁移到 BizTalk 项目，将消息发送到使用基于 WCF 的 Oracle 数据库 vPrev BizTalk 项目的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1d782-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="1d782-141">您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息以执行插入操作上，对 Oracle 数据库中所述[第 3 步： 测试已迁移应用程序到 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1d782-141">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the Oracle database, as described in [Step 3: Test the migrated application to Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d782-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d782-142">See Also</span></span>  
 <span data-ttu-id="1d782-143">[教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d782-143">[Tutorial: Migrating BizTalk Projects](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span></span>