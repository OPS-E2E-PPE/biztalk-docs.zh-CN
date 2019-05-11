---
title: 步骤 8 （本地）：配置 BizTalk Server 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccff5ca7f7f101eb5b203196449ce1cbb1834b49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258636"
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a><span data-ttu-id="beb20-102">步骤 8 （本地）：配置 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="beb20-102">Step 8 (On Premises): Configure the BizTalk Server Application</span></span>
<span data-ttu-id="beb20-103">上一步中创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程。</span><span class="sxs-lookup"><span data-stu-id="beb20-103">In the previous step you created a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="beb20-104">在此步骤中，将生成、 部署和配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="beb20-104">In this step, you’ll build, deploy, and configure the application.</span></span>  

## <a name="build-and-deploy-the-application"></a><span data-ttu-id="beb20-105">生成和部署应用程序</span><span class="sxs-lookup"><span data-stu-id="beb20-105">Build and deploy the application</span></span>  

1.  <span data-ttu-id="beb20-106">在 Visual Studio 中，右键单击解决方案名称，在解决方案资源管理器，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="beb20-106">In Visual Studio, right-click the solution name in the Solution Explorer, and click **Build**.</span></span>  

2.  <span data-ttu-id="beb20-107">部署过程要求程序集强签名。</span><span class="sxs-lookup"><span data-stu-id="beb20-107">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="beb20-108">必须将项目与一个强名称程序集密钥文件相关联来签名你的程序集。</span><span class="sxs-lookup"><span data-stu-id="beb20-108">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  

    1.  <span data-ttu-id="beb20-109">在解决方案资源管理器中右键单击**OrderProcessingDemo**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="beb20-109">In Solution Explorer, right-click the **OrderProcessingDemo** project, and then click **Properties**.</span></span>  

    2.  <span data-ttu-id="beb20-110">单击**签名**选项卡，然后选择**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="beb20-110">Click the **Signing** tab, and select the **Sign the assembly** checkbox.</span></span>  

    3.  <span data-ttu-id="beb20-111">从下拉列表中**选择强名称密钥文件**框中，选择**\<新建...\>**.</span><span class="sxs-lookup"><span data-stu-id="beb20-111">From the drop-down list in the **Choose a strong name key file** box, select **\<New…\>**.</span></span>  

    4.  <span data-ttu-id="beb20-112">在中**创建强名称密钥**对话框框中，输入密钥文件的名称，例如`OrderProcessingDemo.snk`。</span><span class="sxs-lookup"><span data-stu-id="beb20-112">In the **Create Strong Name Key** dialog box, enter a name for the key file, for example `OrderProcessingDemo.snk`.</span></span> <span data-ttu-id="beb20-113">清除用于保护包含密码的密钥文件复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="beb20-113">Clear the checkbox for protecting the key file with a password, and then click **OK**.</span></span>  

3.  <span data-ttu-id="beb20-114">单击**部署**选项卡上，在右侧的框中**应用程序名称**，类型`OrderProcessingDemo`。</span><span class="sxs-lookup"><span data-stu-id="beb20-114">Click the **Deployment** tab, in the box to the right of **Application Name**, type `OrderProcessingDemo`.</span></span>  

4.  <span data-ttu-id="beb20-115">从下拉列表右侧的框中**重新部署**，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="beb20-115">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  

5.  <span data-ttu-id="beb20-116">在解决方案资源管理器中右键单击**OrderProcessingDemo**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="beb20-116">In Solution Explorer, right-click **OrderProcessingDemo**, and then click **Deploy**.</span></span>  <span data-ttu-id="beb20-117">输出窗口应显示：</span><span class="sxs-lookup"><span data-stu-id="beb20-117">The Output window should display:</span></span>  

    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  

    ```  

## <a name="configure-the-application"></a><span data-ttu-id="beb20-118">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="beb20-118">Configure the application</span></span>  

1. <span data-ttu-id="beb20-119">单击**启动**，依次指向**所有程序**，指向**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="beb20-119">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="beb20-120">在控制台树中的左窗格上，依次展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="beb20-120">In the console tree on the left pane, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  

3. <span data-ttu-id="beb20-121">展开**BizTalk 组**，展开**应用程序**，展开**OrderProcessingDemo**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="beb20-121">Expand **BizTalk Group**, expand **Applications**, expand **OrderProcessingDemo**, and then click **Orchestrations**.</span></span> <span data-ttu-id="beb20-122">你将看到**OrderProcessingDemo.OrderProcessing**部署业务流程。</span><span class="sxs-lookup"><span data-stu-id="beb20-122">You will see that the **OrderProcessingDemo.OrderProcessing** orchestration is deployed.</span></span>  

4. <span data-ttu-id="beb20-123">在业务流程，创建一个逻辑端口 (**ReceiveSO**) 从服务总线队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="beb20-123">In the orchestration, you created a logical port (**ReceiveSO**) to receive messages from the Service Bus Queue.</span></span> <span data-ttu-id="beb20-124">在此步骤中，创建物理接收端口映射到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="beb20-124">In this step, you create a physical receive port to map to the logical port.</span></span>  

   1. <span data-ttu-id="beb20-125">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**OrderProcessingDemo**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="beb20-125">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

   2. <span data-ttu-id="beb20-126">在 **“常规”** 选项卡上，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="beb20-126">On the **General** tab, do the following:</span></span>  


      |                <span data-ttu-id="beb20-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-127">Use this</span></span>                |     <span data-ttu-id="beb20-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-128">To do this</span></span>      |
      |----------------------------------------|---------------------|
      |                <span data-ttu-id="beb20-129">**名称**</span><span class="sxs-lookup"><span data-stu-id="beb20-129">**Name**</span></span>                | <span data-ttu-id="beb20-130">类型**ReceiveSO**。</span><span class="sxs-lookup"><span data-stu-id="beb20-130">Type **ReceiveSO**.</span></span> |
      | <span data-ttu-id="beb20-131">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="beb20-131">**Enable routing for failed messages**</span></span> |       <span data-ttu-id="beb20-132">（清除）</span><span class="sxs-lookup"><span data-stu-id="beb20-132">(clear)</span></span>       |


   3. <span data-ttu-id="beb20-133">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="beb20-133">Click **Receive Locations**, and then click **New**.</span></span>  

   4. <span data-ttu-id="beb20-134">从接收位置 1 – 接收位置属性对话框中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="beb20-134">From Receive Location1 – Receive Location Properties dialog box, do the following:</span></span>  


      |       <span data-ttu-id="beb20-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-135">Use this</span></span>       |              <span data-ttu-id="beb20-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-136">To do this</span></span>              |
      |----------------------|--------------------------------------|
      |       <span data-ttu-id="beb20-137">**名称**</span><span class="sxs-lookup"><span data-stu-id="beb20-137">**Name**</span></span>       |      <span data-ttu-id="beb20-138">类型**ReceiveOrders_SO**。</span><span class="sxs-lookup"><span data-stu-id="beb20-138">Type **ReceiveOrders_SO**.</span></span>      |
      |       <span data-ttu-id="beb20-139">**类型**</span><span class="sxs-lookup"><span data-stu-id="beb20-139">**Type**</span></span>       |       <span data-ttu-id="beb20-140">选择**SB 消息**。</span><span class="sxs-lookup"><span data-stu-id="beb20-140">Select **SB-Messaging**.</span></span>       |
      | <span data-ttu-id="beb20-141">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="beb20-141">**Receive handler**</span></span>  | <span data-ttu-id="beb20-142">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="beb20-142">Select **BizTalkServerApplication**.</span></span> |
      | <span data-ttu-id="beb20-143">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="beb20-143">**Receive pipeline**</span></span> |        <span data-ttu-id="beb20-144">选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="beb20-144">Select **XMLReceive**.</span></span>        |


   5. <span data-ttu-id="beb20-145">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="beb20-145">Click **Configure**.</span></span>  

   6. <span data-ttu-id="beb20-146">SB 消息传输属性对话框中，从上**常规**选项卡上，对于**队列或订阅 URL**，输入**sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span><span class="sxs-lookup"><span data-stu-id="beb20-146">From SB-Messaging Transport Properties dialog box, on the **General** tab, for **Queue or Subscription URL**, enter **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span></span> <span data-ttu-id="beb20-147">在这里， *mynamespace*是服务总线命名空间和*queueordersedi*是你在中创建的服务总线队列[步骤 3 (Azure):创建服务总线队列](../core/step-3-for-azure-create-a-service-bus-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="beb20-147">Here, *mynamespace* is the Service Bus namespace and *queueordersedi* is the Service Bus Queue that you created in [Step 3 (For Azure): Create a Service Bus Queue](../core/step-3-for-azure-create-a-service-bus-queue.md).</span></span>  

   7. <span data-ttu-id="beb20-148">SB 消息传输属性对话框中，从上**身份验证**选项卡上，指定以下值：</span><span class="sxs-lookup"><span data-stu-id="beb20-148">From SB-Messaging Transport Properties dialog box, on the **Authentication** tab, specify the following values:</span></span>  

      |<span data-ttu-id="beb20-149">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-149">Use this</span></span>|<span data-ttu-id="beb20-150">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-150">To do this</span></span>|  
      |--------------|----------------|  
      |<span data-ttu-id="beb20-151">**访问控制服务 STS Uri**</span><span class="sxs-lookup"><span data-stu-id="beb20-151">**Access Control Service STS Uri**</span></span>|<span data-ttu-id="beb20-152">类型 `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span><span class="sxs-lookup"><span data-stu-id="beb20-152">Type `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span></span>|  
      |<span data-ttu-id="beb20-153">**颁发者名称**</span><span class="sxs-lookup"><span data-stu-id="beb20-153">**Issuer name**</span></span>|<span data-ttu-id="beb20-154">指定颁发者名称。</span><span class="sxs-lookup"><span data-stu-id="beb20-154">Specify the issuer name.</span></span> <span data-ttu-id="beb20-155">通常此值设置为`owner`。</span><span class="sxs-lookup"><span data-stu-id="beb20-155">Typically this is set to `owner`.</span></span>|  
      |<span data-ttu-id="beb20-156">**颁发者密钥**</span><span class="sxs-lookup"><span data-stu-id="beb20-156">**Issuer key**</span></span>|<span data-ttu-id="beb20-157">指定的颁发者密钥。</span><span class="sxs-lookup"><span data-stu-id="beb20-157">Specify the issuer key.</span></span>|  

      > [!NOTE]
      >  <span data-ttu-id="beb20-158">你可以获取的值的队列 URL、 ACS URL、 颁发者名称和密钥[Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)。</span><span class="sxs-lookup"><span data-stu-id="beb20-158">You can get the values for the Queue URL, ACS URL, issuer name and key from the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span></span>  

   8. <span data-ttu-id="beb20-159">单击**确定**直到您退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="beb20-159">Click **OK** until you exit all the dialog boxes.</span></span>  

5. <span data-ttu-id="beb20-160">在业务流程，创建一个逻辑端口 (**SendToSQL**) 将消息发送到**SalesOrder**数据库表。</span><span class="sxs-lookup"><span data-stu-id="beb20-160">In the orchestration, you created a logical port (**SendToSQL**) to send messages to the **SalesOrder** database table.</span></span> <span data-ttu-id="beb20-161">在此步骤中，您将创建一个物理发送端口映射到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="beb20-161">In this step, you create a physical send port to map to the logical port.</span></span>  

   1. <span data-ttu-id="beb20-162">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**OrderProcessingDemo**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="beb20-162">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

   2. <span data-ttu-id="beb20-163">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="beb20-163">On the General tab, do the following:</span></span>  


      |     <span data-ttu-id="beb20-164">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-164">Use this</span></span>      |              <span data-ttu-id="beb20-165">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-165">To do this</span></span>              |
      |-------------------|--------------------------------------|
      |     <span data-ttu-id="beb20-166">**名称**</span><span class="sxs-lookup"><span data-stu-id="beb20-166">**Name**</span></span>      |         <span data-ttu-id="beb20-167">类型**SendToSQL**。</span><span class="sxs-lookup"><span data-stu-id="beb20-167">Type **SendToSQL**.</span></span>          |
      |     <span data-ttu-id="beb20-168">**类型**</span><span class="sxs-lookup"><span data-stu-id="beb20-168">**Type**</span></span>      |         <span data-ttu-id="beb20-169">选择**WCF SQL**。</span><span class="sxs-lookup"><span data-stu-id="beb20-169">Select **WCF-SQL**.</span></span>          |
      | <span data-ttu-id="beb20-170">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="beb20-170">**Send handler**</span></span>  | <span data-ttu-id="beb20-171">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="beb20-171">Select **BizTAlkServerApplication**.</span></span> |
      | <span data-ttu-id="beb20-172">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="beb20-172">**Send pipeline**</span></span> |     <span data-ttu-id="beb20-173">选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="beb20-173">Select **PassThruTransmit**.</span></span>     |


   3. <span data-ttu-id="beb20-174">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="beb20-174">Click **Configure**.</span></span>  

   4. <span data-ttu-id="beb20-175">从 WCF SQL 传输属性上**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="beb20-175">From WCF-SQL Transport Properties, on the **General** tab, do the following:</span></span>  


      |     <span data-ttu-id="beb20-176">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-176">Use this</span></span>      |                                                                                                                                                                                    <span data-ttu-id="beb20-177">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-177">To do this</span></span>                                                                                                                                                                                    |
      |-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      | <span data-ttu-id="beb20-178">**地址 (URI)**</span><span class="sxs-lookup"><span data-stu-id="beb20-178">**Address (URI)**</span></span> | <span data-ttu-id="beb20-179">类型**mssql://computername/database_instance_name/databasename**。</span><span class="sxs-lookup"><span data-stu-id="beb20-179">Type **mssql://computername/database_instance_name/databasename**.</span></span> <span data-ttu-id="beb20-180">例如，若要连接到**DemoDB**默认数据库实例下运行的本地计算机上的数据库中，输入 `mssql://.//DemoDB`</span><span class="sxs-lookup"><span data-stu-id="beb20-180">For example, to connect to a **DemoDB** database on the local computer running under the default database instance, enter `mssql://.//DemoDB`</span></span><br /><br /> <span data-ttu-id="beb20-181">有关详细信息，请参阅[创建 SQL Server 连接 URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="beb20-181">For more information, see [Create the SQL Server connection URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span> |
      |    <span data-ttu-id="beb20-182">**操作**</span><span class="sxs-lookup"><span data-stu-id="beb20-182">**Action**</span></span>     |                                                                                                                                                                     <span data-ttu-id="beb20-183">类型**TableOp/Insert/dbo/SalesOrder**。</span><span class="sxs-lookup"><span data-stu-id="beb20-183">Type **TableOp/Insert/dbo/SalesOrder**.</span></span>                                                                                                                                                                      |


   5. <span data-ttu-id="beb20-184">从 WCF SQL 传输属性上**凭据**选项卡上，选择**不使用单一登录**，并指定凭据 （区分大小写） 以连接到 SQL Server 数据库中指定连接字符串。</span><span class="sxs-lookup"><span data-stu-id="beb20-184">From WCF-SQL Transport Properties, on the **Credentials** tab, select **Do not use Single Sign-On**, and specify credentials (case-sensitive) to connect to the SQL Server database you specified in the connection string.</span></span> <span data-ttu-id="beb20-185">如果你想要使用 Windows 身份验证进行连接，将凭据留空。</span><span class="sxs-lookup"><span data-stu-id="beb20-185">If you want to connect using Windows Authentication, leave the credentials blank.</span></span>  

   6. <span data-ttu-id="beb20-186">单击**确定**直到您退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="beb20-186">Click **OK** until you exit all the dialog boxes.</span></span>  

6. <span data-ttu-id="beb20-187">在业务流程，创建一个逻辑端口 (**SendToFile**) 将消息发送到共享的文件位置。</span><span class="sxs-lookup"><span data-stu-id="beb20-187">In the orchestration, you created a logical port (**SendToFile**) to send messages to a shared file location.</span></span> <span data-ttu-id="beb20-188">在此步骤中，您将创建一个物理发送端口映射到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="beb20-188">In this step, you create a physical send port to map to the logical port.</span></span>  

   1. <span data-ttu-id="beb20-189">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**OrderProcessingDemo**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="beb20-189">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

   2. <span data-ttu-id="beb20-190">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="beb20-190">On the General tab, do the following:</span></span>  


      |     <span data-ttu-id="beb20-191">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-191">Use this</span></span>      |              <span data-ttu-id="beb20-192">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-192">To do this</span></span>              |
      |-------------------|--------------------------------------|
      |     <span data-ttu-id="beb20-193">**名称**</span><span class="sxs-lookup"><span data-stu-id="beb20-193">**Name**</span></span>      |         <span data-ttu-id="beb20-194">类型**SendToFile**。</span><span class="sxs-lookup"><span data-stu-id="beb20-194">Type **SendToFile**.</span></span>         |
      |     <span data-ttu-id="beb20-195">**类型**</span><span class="sxs-lookup"><span data-stu-id="beb20-195">**Type**</span></span>      |           <span data-ttu-id="beb20-196">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="beb20-196">Select **File**.</span></span>           |
      | <span data-ttu-id="beb20-197">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="beb20-197">**Send handler**</span></span>  | <span data-ttu-id="beb20-198">选择**BizTAlkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="beb20-198">Select **BizTAlkServerApplication**.</span></span> |
      | <span data-ttu-id="beb20-199">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="beb20-199">**Send pipeline**</span></span> |       <span data-ttu-id="beb20-200">选择**XML 传输**。</span><span class="sxs-lookup"><span data-stu-id="beb20-200">Select **XML Transmit**.</span></span>       |


   3. <span data-ttu-id="beb20-201">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="beb20-201">Click **Configure**.</span></span>  

   4. <span data-ttu-id="beb20-202">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="beb20-202">From File Transport Properties, do the following:</span></span>  


      |      <span data-ttu-id="beb20-203">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-203">Use this</span></span>      |                        <span data-ttu-id="beb20-204">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-204">To do this</span></span>                        |
      |--------------------|----------------------------------------------------------|
      | <span data-ttu-id="beb20-205">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="beb20-205">**Receive folder**</span></span> | <span data-ttu-id="beb20-206">指定你想要发送消息的位置。</span><span class="sxs-lookup"><span data-stu-id="beb20-206">Specify the location where you want to send the message.</span></span> |
      |   <span data-ttu-id="beb20-207">**文件名**</span><span class="sxs-lookup"><span data-stu-id="beb20-207">**File name**</span></span>    |               <span data-ttu-id="beb20-208">保留 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="beb20-208">Retain **%MessageID%.xml**.</span></span>                |


   5. <span data-ttu-id="beb20-209">单击**确定**直到您退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="beb20-209">Click **OK** until you exit all the dialog boxes.</span></span>  

7. <span data-ttu-id="beb20-210">现在必须将绑定在一起以配置应用程序的物理和逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="beb20-210">You must now bind the physical and logical ports together to configure the application.</span></span>  

   1. <span data-ttu-id="beb20-211">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**OrderProcessingDemo**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="beb20-211">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Configure**.</span></span>  

   2. <span data-ttu-id="beb20-212">配置应用程序，在左窗格中，单击**OrderProcessing**。</span><span class="sxs-lookup"><span data-stu-id="beb20-212">From Configure Application, in the left pane, click **OrderProcessing**.</span></span>  

   3. <span data-ttu-id="beb20-213">使用下表中的值配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="beb20-213">Use the values in the following table to configure the application.</span></span>  


      |            <span data-ttu-id="beb20-214">使用此选项</span><span class="sxs-lookup"><span data-stu-id="beb20-214">Use this</span></span>             |             <span data-ttu-id="beb20-215">执行的操作</span><span class="sxs-lookup"><span data-stu-id="beb20-215">To do this</span></span>              |
      |---------------------------------|-------------------------------------|
      |          <span data-ttu-id="beb20-216">有关**主机**</span><span class="sxs-lookup"><span data-stu-id="beb20-216">For **Host**</span></span>           | <span data-ttu-id="beb20-217">Select **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="beb20-217">Select **BizTalkServerApplication**</span></span> |
      | <span data-ttu-id="beb20-218">对于逻辑端口**ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="beb20-218">For logical port **ReceiveSO**</span></span>  | <span data-ttu-id="beb20-219">选择物理端口**ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="beb20-219">Select physical port **ReceiveSO**</span></span>  |
      | <span data-ttu-id="beb20-220">对于逻辑端口**SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="beb20-220">For logical port **SendToSQL**</span></span>  | <span data-ttu-id="beb20-221">选择物理端口**SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="beb20-221">Select physical port **SendToSQL**</span></span>  |
      | <span data-ttu-id="beb20-222">对于逻辑端口**SendToFile**</span><span class="sxs-lookup"><span data-stu-id="beb20-222">For logical port **SendToFile**</span></span> | <span data-ttu-id="beb20-223">选择物理端口**SendToFile**</span><span class="sxs-lookup"><span data-stu-id="beb20-223">Select physical port **SendToFile**</span></span> |


   4. <span data-ttu-id="beb20-224">单击**确定**保存配置。</span><span class="sxs-lookup"><span data-stu-id="beb20-224">Click **OK** to save the configuration.</span></span>  

## <a name="start-the-application"></a><span data-ttu-id="beb20-225">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="beb20-225">Start the application</span></span>  

1. <span data-ttu-id="beb20-226">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**OrderProcessingDemo**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="beb20-226">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Start**.</span></span>  

2. <span data-ttu-id="beb20-227">从对话框中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="beb20-227">From the dialog, click **Start**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="beb20-228">请参阅</span><span class="sxs-lookup"><span data-stu-id="beb20-228">See Also</span></span>  
 [<span data-ttu-id="beb20-229">教程 4：创建混合应用程序使用 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="beb20-229">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)