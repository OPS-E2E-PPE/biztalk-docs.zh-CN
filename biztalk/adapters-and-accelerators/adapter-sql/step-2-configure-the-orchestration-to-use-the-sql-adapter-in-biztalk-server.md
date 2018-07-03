---
title: 步骤 2： 使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6293758d9891d86e137d07e9735ce37162d6a96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984022"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a><span data-ttu-id="ae37a-102">步骤 2： 使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程</span><span class="sxs-lookup"><span data-stu-id="ae37a-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>
<span data-ttu-id="ae37a-103">![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="ae37a-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="ae37a-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="ae37a-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="ae37a-105">**目标：** 在此步骤中，执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ae37a-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="ae37a-106">创建 WCF 自定义发送接收端口以发送和接收消息，从 SQL Server 数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae37a-106">Create a WCF-Custom send-receive port to send and receive messages from the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ae37a-107">配置此端口以使用在上一步中创建的映射。</span><span class="sxs-lookup"><span data-stu-id="ae37a-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="ae37a-108">配置业务流程使用 WCF 自定义端口上一步中部署。</span><span class="sxs-lookup"><span data-stu-id="ae37a-108">Configure the orchestration you deployed in the previous step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ae37a-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="ae37a-109">Prerequisites</span></span>  
 <span data-ttu-id="ae37a-110">你应已部署 BizTalk 业务流程，你想要配置 WCF 自定义端口，如中所述[步骤 1： 修改 vPrev BizTalk 项目使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ae37a-110">You should have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port as described in [Step 1: Modify the vPrev BizTalk Project using the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md).</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="ae37a-111">若要创建的 WCF 自定义端口</span><span class="sxs-lookup"><span data-stu-id="ae37a-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="ae37a-112">生成架构上使用 SQL Server 数据库的操作时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ae37a-112">When you generate schema for an operation on the SQL Server database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="ae37a-113">您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。</span><span class="sxs-lookup"><span data-stu-id="ae37a-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="ae37a-114">有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53)。</span><span class="sxs-lookup"><span data-stu-id="ae37a-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53).</span></span>  
  
2. <span data-ttu-id="ae37a-115">导入绑定文件后下, 创建的发送端口**发送端口**文件夹中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae37a-115">After you import the binding file, a send port is created under the **Send Ports** folder in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
3. <span data-ttu-id="ae37a-116">右键单击 WCF 自定义端口，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="ae37a-117">从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="ae37a-118">在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，指定凭据以连接到 SQL Server 数据库，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, specify the credentials to connect to a SQL Server database, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="ae37a-119">从发送端口属性对话框的左窗格中，单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-119">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="ae37a-120">在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**ResponseMap**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-120">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="ae37a-121">![配置入站的映射](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")</span><span class="sxs-lookup"><span data-stu-id="ae37a-121">![Configure inbound map](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")</span></span>  
  
7. <span data-ttu-id="ae37a-122">从发送端口属性对话框的左窗格中，单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-122">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="ae37a-123">在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**RequestMap**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-123">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="ae37a-124">![配置出站映射](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")</span><span class="sxs-lookup"><span data-stu-id="ae37a-124">![Configure outbound map](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")</span></span>  
  
8. <span data-ttu-id="ae37a-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ae37a-125">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="ae37a-126">若要配置的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ae37a-126">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="ae37a-127">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开在其中部署业务流程的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae37a-127">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="ae37a-128">右键单击 BizTalk 应用程序，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="ae37a-128">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="ae37a-129">从左窗格中，单击业务流程配置。</span><span class="sxs-lookup"><span data-stu-id="ae37a-129">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="ae37a-130">在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="ae37a-130">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="ae37a-131">下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae37a-131">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
   1.  <span data-ttu-id="ae37a-132">选择将存放请求消息的文件端口。</span><span class="sxs-lookup"><span data-stu-id="ae37a-132">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="ae37a-133">BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="ae37a-133">The BizTalk orchestration will consume the request message and send it to the SQL Server database.</span></span>  
  
   2.  <span data-ttu-id="ae37a-134">选择 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口。</span><span class="sxs-lookup"><span data-stu-id="ae37a-134">Select the file port where the BizTalk orchestration will drop the response message containing the response from the SQL Server database.</span></span>  
  
   3.  <span data-ttu-id="ae37a-135">选择本主题中前面创建的 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="ae37a-135">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4.  <span data-ttu-id="ae37a-136">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ae37a-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ae37a-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ae37a-137">Next Steps</span></span>  
 <span data-ttu-id="ae37a-138">你现在已经完成迁移到 BizTalk 项目，将消息发送到 SQL Server 数据库使用基于 WCF 的 vPrev BizTalk 项目的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae37a-138">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the SQL Server database using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ae37a-139">您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息以执行插入操作上，SQL Server 数据库中所述[第 3 步： 测试迁移应用程序使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ae37a-139">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the SQL Server database, as described in [Step 3: Test the Migrated Application that uses the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae37a-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae37a-140">See Also</span></span>  
 [<span data-ttu-id="ae37a-141">教程 1： 将 BizTalk 项目迁移到 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ae37a-141">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)