---
title: 步骤 8 （在本地）： 配置 BizTalk Server 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa411b7ca828a45aa0d5e58212bb48195c48180f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a><span data-ttu-id="b74f3-102">步骤 8 （在本地）： 配置 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="b74f3-102">Step 8 (On Premises): Configure the BizTalk Server Application</span></span>
<span data-ttu-id="b74f3-103">你在前一个步骤中创建了一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="b74f3-103">In the previous step you created a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="b74f3-104">在本步骤中，你将构建、部署和配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="b74f3-104">In this step, you’ll build, deploy, and configure the application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="b74f3-105">生成并部署应用程序</span><span class="sxs-lookup"><span data-stu-id="b74f3-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="b74f3-106">在 Visual Studio 中，右键单击解决方案名称在解决方案资源管理器，然后单击 **生成**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-106">In Visual Studio, right-click the solution name in the Solution Explorer, and click **Build**.</span></span>  
  
2.  <span data-ttu-id="b74f3-107">部署过程要求程序集是强签名的。</span><span class="sxs-lookup"><span data-stu-id="b74f3-107">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="b74f3-108">必须通过将该项目与一个强名称程序集密钥文件相关联来签名你的程序集。</span><span class="sxs-lookup"><span data-stu-id="b74f3-108">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  
  
    1.  <span data-ttu-id="b74f3-109">在解决方案资源管理器，右键单击 **OrderProcessingDemo** 项目，，然后单击 **属性**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-109">In Solution Explorer, right-click the **OrderProcessingDemo** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="b74f3-110">单击 **签名** 选项卡，然后选择 **对程序集签名** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b74f3-110">Click the **Signing** tab, and select the **Sign the assembly** checkbox.</span></span>  
  
    3.  <span data-ttu-id="b74f3-111">从下拉列表中**选择强名称密钥文件**框中，选择**\<新建...\>**.</span><span class="sxs-lookup"><span data-stu-id="b74f3-111">From the drop-down list in the **Choose a strong name key file** box, select **\<New…\>**.</span></span>  
  
    4.  <span data-ttu-id="b74f3-112">在 **创建强名称密钥** 对话框框中，输入的密钥文件的名称，例如 `OrderProcessingDemo.snk`。</span><span class="sxs-lookup"><span data-stu-id="b74f3-112">In the **Create Strong Name Key** dialog box, enter a name for the key file, for example `OrderProcessingDemo.snk`.</span></span> <span data-ttu-id="b74f3-113">清除保护使用密码的密钥文件的复选框，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-113">Clear the checkbox for protecting the key file with a password, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b74f3-114">单击 **部署** 选项卡上，在右侧的框中 **应用程序名称**, ，类型 `OrderProcessingDemo`。</span><span class="sxs-lookup"><span data-stu-id="b74f3-114">Click the **Deployment** tab, in the box to the right of **Application Name**, type `OrderProcessingDemo`.</span></span>  
  
4.  <span data-ttu-id="b74f3-115">从下拉列表中的右侧的框 **重新部署**, ，选择 **True**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-115">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
5.  <span data-ttu-id="b74f3-116">在解决方案资源管理器，右键单击 **OrderProcessingDemo**, ，然后单击 **部署**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-116">In Solution Explorer, right-click **OrderProcessingDemo**, and then click **Deploy**.</span></span>  <span data-ttu-id="b74f3-117">“输出”窗口应显示：</span><span class="sxs-lookup"><span data-stu-id="b74f3-117">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
## <a name="configure-the-application"></a><span data-ttu-id="b74f3-118">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="b74f3-118">Configure the application</span></span>  
  
1.  <span data-ttu-id="b74f3-119">单击 **启动**, ，指向 **所有程序**, ，指向 **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, ，然后单击 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b74f3-119">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="b74f3-120">在控制台树中的左窗格中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], ，右键单击 **BizTalk 组**, ，然后单击 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-120">In the console tree on the left pane, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="b74f3-121">展开 **BizTalk 组**, ，展开 **应用程序**, ，展开 **OrderProcessingDemo**, ，然后单击 **业务流程**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-121">Expand **BizTalk Group**, expand **Applications**, expand **OrderProcessingDemo**, and then click **Orchestrations**.</span></span> <span data-ttu-id="b74f3-122">你将看到 **OrderProcessingDemo.OrderProcessing** 部署业务流程。</span><span class="sxs-lookup"><span data-stu-id="b74f3-122">You will see that the **OrderProcessingDemo.OrderProcessing** orchestration is deployed.</span></span>  
  
4.  <span data-ttu-id="b74f3-123">在业务流程，你已创建的逻辑端口 (**ReceiveSO**) 从 Service Bus 队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="b74f3-123">In the orchestration, you created a logical port (**ReceiveSO**) to receive messages from the Service Bus Queue.</span></span> <span data-ttu-id="b74f3-124">在此步骤中，将创建一个映射到逻辑端口的物理接收端口。</span><span class="sxs-lookup"><span data-stu-id="b74f3-124">In this step, you create a physical receive port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="b74f3-125">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，在 **OrderProcessingDemo** 节点，右键单击 **接收端口**, ，指向 **新建**, ，然后单击 **单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-125">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
    2.  <span data-ttu-id="b74f3-126">在 **“常规”** 选项卡上，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b74f3-126">On the **General** tab, do the following:</span></span>  
  
        |<span data-ttu-id="b74f3-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-127">Use this</span></span>|<span data-ttu-id="b74f3-128">動作</span><span class="sxs-lookup"><span data-stu-id="b74f3-128">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-129">**名称**</span><span class="sxs-lookup"><span data-stu-id="b74f3-129">**Name**</span></span>|<span data-ttu-id="b74f3-130">类型 **ReceiveSO**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-130">Type **ReceiveSO**.</span></span>|  
        |<span data-ttu-id="b74f3-131">**启用路由失败消息**</span><span class="sxs-lookup"><span data-stu-id="b74f3-131">**Enable routing for failed messages**</span></span>|<span data-ttu-id="b74f3-132">（清除）</span><span class="sxs-lookup"><span data-stu-id="b74f3-132">(clear)</span></span>|  
  
    3.  <span data-ttu-id="b74f3-133">单击 **接收位置**, ，然后单击 **新建**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-133">Click **Receive Locations**, and then click **New**.</span></span>  
  
    4.  <span data-ttu-id="b74f3-134">从“接收位置 1 – 接收位置属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b74f3-134">From Receive Location1 – Receive Location Properties dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="b74f3-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-135">Use this</span></span>|<span data-ttu-id="b74f3-136">動作</span><span class="sxs-lookup"><span data-stu-id="b74f3-136">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-137">**名称**</span><span class="sxs-lookup"><span data-stu-id="b74f3-137">**Name**</span></span>|<span data-ttu-id="b74f3-138">类型 **ReceiveOrders_SO**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-138">Type **ReceiveOrders_SO**.</span></span>|  
        |<span data-ttu-id="b74f3-139">**类型**</span><span class="sxs-lookup"><span data-stu-id="b74f3-139">**Type**</span></span>|<span data-ttu-id="b74f3-140">选择 **SB 消息**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-140">Select **SB-Messaging**.</span></span>|  
        |<span data-ttu-id="b74f3-141">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="b74f3-141">**Receive handler**</span></span>|<span data-ttu-id="b74f3-142">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="b74f3-142">Select **BizTalkServerApplication**.</span></span>|  
        |<span data-ttu-id="b74f3-143">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="b74f3-143">**Receive pipeline**</span></span>|<span data-ttu-id="b74f3-144">选择 **XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-144">Select **XMLReceive**.</span></span>|  
  
    5.  <span data-ttu-id="b74f3-145">单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-145">Click **Configure**.</span></span>  
  
    6.  <span data-ttu-id="b74f3-146">SB 消息传输属性对话框中，从上 **常规** 选项卡上，为 **队列或订阅 URL**, ，输入 **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-146">From SB-Messaging Transport Properties dialog box, on the **General** tab, for **Queue or Subscription URL**, enter **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span></span> <span data-ttu-id="b74f3-147">在这里， *mynamespace*是服务总线命名空间和*queueordersedi*是你在中创建的服务总线队列[(为 Azure) 的步骤 3︰ 创建 Service Bus 队列](../core/step-3-for-azure-create-a-service-bus-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="b74f3-147">Here, *mynamespace* is the Service Bus namespace and *queueordersedi* is the Service Bus Queue that you created in [Step 3 (For Azure): Create a Service Bus Queue](../core/step-3-for-azure-create-a-service-bus-queue.md).</span></span>  
  
    7.  <span data-ttu-id="b74f3-148">SB 消息传输属性对话框中，从上 **身份验证** 选项卡上，指定以下值︰</span><span class="sxs-lookup"><span data-stu-id="b74f3-148">From SB-Messaging Transport Properties dialog box, on the **Authentication** tab, specify the following values:</span></span>  
  
        |<span data-ttu-id="b74f3-149">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-149">Use this</span></span>|<span data-ttu-id="b74f3-150">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b74f3-150">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-151">**访问控制服务 STS Uri**</span><span class="sxs-lookup"><span data-stu-id="b74f3-151">**Access Control Service STS Uri**</span></span>|<span data-ttu-id="b74f3-152">类型 `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span><span class="sxs-lookup"><span data-stu-id="b74f3-152">Type `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span></span>|  
        |<span data-ttu-id="b74f3-153">**颁发者名称**</span><span class="sxs-lookup"><span data-stu-id="b74f3-153">**Issuer name**</span></span>|<span data-ttu-id="b74f3-154">指定发布者名称。</span><span class="sxs-lookup"><span data-stu-id="b74f3-154">Specify the issuer name.</span></span> <span data-ttu-id="b74f3-155">通常这设置为 `owner`。</span><span class="sxs-lookup"><span data-stu-id="b74f3-155">Typically this is set to `owner`.</span></span>|  
        |<span data-ttu-id="b74f3-156">**颁发者密钥**</span><span class="sxs-lookup"><span data-stu-id="b74f3-156">**Issuer key**</span></span>|<span data-ttu-id="b74f3-157">指定发布者密钥。</span><span class="sxs-lookup"><span data-stu-id="b74f3-157">Specify the issuer key.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="b74f3-158">你可以获取的值为队列 URL，ACS URL 颁发者名称和密钥从 [Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)。</span><span class="sxs-lookup"><span data-stu-id="b74f3-158">You can get the values for the Queue URL, ACS URL, issuer name and key from the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span></span>  
  
    8.  <span data-ttu-id="b74f3-159">单击 **确定** 直到退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="b74f3-159">Click **OK** until you exit all the dialog boxes.</span></span>  
  
5.  <span data-ttu-id="b74f3-160">在业务流程，你已创建的逻辑端口 (**SendToSQL**) 将消息发送到 **SalesOrder** 数据库表。</span><span class="sxs-lookup"><span data-stu-id="b74f3-160">In the orchestration, you created a logical port (**SendToSQL**) to send messages to the **SalesOrder** database table.</span></span> <span data-ttu-id="b74f3-161">在此步骤中，将创建一个映射到逻辑端口的物理发送端口。</span><span class="sxs-lookup"><span data-stu-id="b74f3-161">In this step, you create a physical send port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="b74f3-162">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，在 **OrderProcessingDemo** 节点，右键单击 **发送端口**, ，指向 **新建**, ，然后单击 **静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-162">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="b74f3-163">在“常规”选项卡上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b74f3-163">On the General tab, do the following:</span></span>  
  
        |<span data-ttu-id="b74f3-164">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-164">Use this</span></span>|<span data-ttu-id="b74f3-165">動作</span><span class="sxs-lookup"><span data-stu-id="b74f3-165">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-166">**名称**</span><span class="sxs-lookup"><span data-stu-id="b74f3-166">**Name**</span></span>|<span data-ttu-id="b74f3-167">类型 **SendToSQL**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-167">Type **SendToSQL**.</span></span>|  
        |<span data-ttu-id="b74f3-168">**类型**</span><span class="sxs-lookup"><span data-stu-id="b74f3-168">**Type**</span></span>|<span data-ttu-id="b74f3-169">选择 **WCF SQL**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-169">Select **WCF-SQL**.</span></span>|  
        |<span data-ttu-id="b74f3-170">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="b74f3-170">**Send handler**</span></span>|<span data-ttu-id="b74f3-171">选择 **BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-171">Select **BizTAlkServerApplication**.</span></span>|  
        |<span data-ttu-id="b74f3-172">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="b74f3-172">**Send pipeline**</span></span>|<span data-ttu-id="b74f3-173">选择 **PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-173">Select **PassThruTransmit**.</span></span>|  
  
    3.  <span data-ttu-id="b74f3-174">单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-174">Click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="b74f3-175">从 WCF SQL 传输属性上 **常规** 选项卡上，执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="b74f3-175">From WCF-SQL Transport Properties, on the **General** tab, do the following:</span></span>  
  
        |<span data-ttu-id="b74f3-176">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-176">Use this</span></span>|<span data-ttu-id="b74f3-177">動作</span><span class="sxs-lookup"><span data-stu-id="b74f3-177">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-178">**地址 (URI)**</span><span class="sxs-lookup"><span data-stu-id="b74f3-178">**Address (URI)**</span></span>|<span data-ttu-id="b74f3-179">类型 **mssql://computername/database_instance_name/databasename**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-179">Type **mssql://computername/database_instance_name/databasename**.</span></span> <span data-ttu-id="b74f3-180">例如，若要连接到 **DemoDB** 数据库默认数据库实例下运行的本地计算机上，输入 `mssql://.//DemoDB`</span><span class="sxs-lookup"><span data-stu-id="b74f3-180">For example, to connect to a **DemoDB** database on the local computer running under the default database instance, enter `mssql://.//DemoDB`</span></span><br /><br /> <span data-ttu-id="b74f3-181">有关详细信息，请参阅[创建 SQL Server 连接 URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b74f3-181">For more information, see [Create the SQL Server connection URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>|  
        |<span data-ttu-id="b74f3-182">**操作**</span><span class="sxs-lookup"><span data-stu-id="b74f3-182">**Action**</span></span>|<span data-ttu-id="b74f3-183">类型 **TableOp/Insert/dbo/SalesOrder**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-183">Type **TableOp/Insert/dbo/SalesOrder**.</span></span>|  
  
    5.  <span data-ttu-id="b74f3-184">从 WCF SQL 传输属性上 **凭据** 选项卡上，选择 **不使用单一登录**, ，并指定 （区分大小写） 的凭据以连接到连接字符串中指定的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="b74f3-184">From WCF-SQL Transport Properties, on the **Credentials** tab, select **Do not use Single Sign-On**, and specify credentials (case-sensitive) to connect to the SQL Server database you specified in the connection string.</span></span> <span data-ttu-id="b74f3-185">如果要使用 Windows 身份验证进行连接，请将凭据留空。</span><span class="sxs-lookup"><span data-stu-id="b74f3-185">If you want to connect using Windows Authentication, leave the credentials blank.</span></span>  
  
    6.  <span data-ttu-id="b74f3-186">单击 **确定** 直到退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="b74f3-186">Click **OK** until you exit all the dialog boxes.</span></span>  
  
6.  <span data-ttu-id="b74f3-187">在业务流程，你已创建的逻辑端口 (**SendToFile**) 将消息发送到共享的文件位置。</span><span class="sxs-lookup"><span data-stu-id="b74f3-187">In the orchestration, you created a logical port (**SendToFile**) to send messages to a shared file location.</span></span> <span data-ttu-id="b74f3-188">在此步骤中，将创建一个映射到逻辑端口的物理发送端口。</span><span class="sxs-lookup"><span data-stu-id="b74f3-188">In this step, you create a physical send port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="b74f3-189">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，在 **OrderProcessingDemo** 节点，右键单击 **发送端口**, ，指向 **新建**, ，然后单击 **静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-189">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="b74f3-190">在“常规”选项卡上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b74f3-190">On the General tab, do the following:</span></span>  
  
        |<span data-ttu-id="b74f3-191">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-191">Use this</span></span>|<span data-ttu-id="b74f3-192">動作</span><span class="sxs-lookup"><span data-stu-id="b74f3-192">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-193">**名称**</span><span class="sxs-lookup"><span data-stu-id="b74f3-193">**Name**</span></span>|<span data-ttu-id="b74f3-194">类型 **SendToFile**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-194">Type **SendToFile**.</span></span>|  
        |<span data-ttu-id="b74f3-195">**类型**</span><span class="sxs-lookup"><span data-stu-id="b74f3-195">**Type**</span></span>|<span data-ttu-id="b74f3-196">选择 **文件**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-196">Select **File**.</span></span>|  
        |<span data-ttu-id="b74f3-197">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="b74f3-197">**Send handler**</span></span>|<span data-ttu-id="b74f3-198">选择 **BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-198">Select **BizTAlkServerApplication**.</span></span>|  
        |<span data-ttu-id="b74f3-199">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="b74f3-199">**Send pipeline**</span></span>|<span data-ttu-id="b74f3-200">选择 **XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-200">Select **XML Transmit**.</span></span>|  
  
    3.  <span data-ttu-id="b74f3-201">单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-201">Click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="b74f3-202">从文件传输属性，请执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="b74f3-202">From File Transport Properties, do the following:</span></span>  
  
        |<span data-ttu-id="b74f3-203">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-203">Use this</span></span>|<span data-ttu-id="b74f3-204">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b74f3-204">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-205">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="b74f3-205">**Receive folder**</span></span>|<span data-ttu-id="b74f3-206">指定要向其发送消息的位置。</span><span class="sxs-lookup"><span data-stu-id="b74f3-206">Specify the location where you want to send the message.</span></span>|  
        |<span data-ttu-id="b74f3-207">**文件名**</span><span class="sxs-lookup"><span data-stu-id="b74f3-207">**File name**</span></span>|<span data-ttu-id="b74f3-208">保留 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-208">Retain **%MessageID%.xml**.</span></span>|  
  
    5.  <span data-ttu-id="b74f3-209">单击 **确定** 直到退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="b74f3-209">Click **OK** until you exit all the dialog boxes.</span></span>  
  
7.  <span data-ttu-id="b74f3-210">现在，你必须将物理端口和逻辑端口绑定在一起以配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="b74f3-210">You must now bind the physical and logical ports together to configure the application.</span></span>  
  
    1.  <span data-ttu-id="b74f3-211">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击 **OrderProcessingDemo**, ，然后单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-211">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Configure**.</span></span>  
  
    2.  <span data-ttu-id="b74f3-212">配置应用程序，在左窗格中，单击 **OrderProcessing**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-212">From Configure Application, in the left pane, click **OrderProcessing**.</span></span>  
  
    3.  <span data-ttu-id="b74f3-213">使用下表中值配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="b74f3-213">Use the values in the following table to configure the application.</span></span>  
  
        |<span data-ttu-id="b74f3-214">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b74f3-214">Use this</span></span>|<span data-ttu-id="b74f3-215">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b74f3-215">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b74f3-216">有关 **主机**</span><span class="sxs-lookup"><span data-stu-id="b74f3-216">For **Host**</span></span>|<span data-ttu-id="b74f3-217">选择 **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="b74f3-217">Select **BizTalkServerApplication**</span></span>|  
        |<span data-ttu-id="b74f3-218">为逻辑端口 **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="b74f3-218">For logical port **ReceiveSO**</span></span>|<span data-ttu-id="b74f3-219">选择物理端口 **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="b74f3-219">Select physical port **ReceiveSO**</span></span>|  
        |<span data-ttu-id="b74f3-220">为逻辑端口 **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="b74f3-220">For logical port **SendToSQL**</span></span>|<span data-ttu-id="b74f3-221">选择物理端口 **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="b74f3-221">Select physical port **SendToSQL**</span></span>|  
        |<span data-ttu-id="b74f3-222">为逻辑端口 **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="b74f3-222">For logical port **SendToFile**</span></span>|<span data-ttu-id="b74f3-223">选择物理端口 **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="b74f3-223">Select physical port **SendToFile**</span></span>|  
  
    4.  <span data-ttu-id="b74f3-224">单击 **确定** 保存配置。</span><span class="sxs-lookup"><span data-stu-id="b74f3-224">Click **OK** to save the configuration.</span></span>  
  
## <a name="start-the-application"></a><span data-ttu-id="b74f3-225">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="b74f3-225">Start the application</span></span>  
  
1.  <span data-ttu-id="b74f3-226">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击 **OrderProcessingDemo**, ，然后单击 **启动**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-226">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="b74f3-227">在对话框中，单击 **启动**。</span><span class="sxs-lookup"><span data-stu-id="b74f3-227">From the dialog, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74f3-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b74f3-228">See Also</span></span>  
 [<span data-ttu-id="b74f3-229">教程 4︰ 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="b74f3-229">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)