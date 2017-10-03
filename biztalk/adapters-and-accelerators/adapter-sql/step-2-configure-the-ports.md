---
title: "步骤 2： 配置的端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e804da96-26ae-482d-b6e1-67af24d639d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e31746fbbc34e24ab1638cb52c84f99e43a876b5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-the-ports"></a><span data-ttu-id="2d643-102">步骤 2： 配置的端口</span><span class="sxs-lookup"><span data-stu-id="2d643-102">Step 2: Configure the Ports</span></span>
<span data-ttu-id="2d643-103">![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="2d643-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="2d643-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="2d643-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="2d643-105">**目标：**在此步骤中，你将创建中的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2d643-105">**Objective:** In this step, you create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2d643-106">创建用于在业务流程中创建的每个逻辑端口的物理端口。</span><span class="sxs-lookup"><span data-stu-id="2d643-106">You create a physical port for each logical port you created in the orchestration.</span></span> <span data-ttu-id="2d643-107">您将创建以下端口：</span><span class="sxs-lookup"><span data-stu-id="2d643-107">You will create the following ports:</span></span>  
  
-   <span data-ttu-id="2d643-108">单向的 WCF 自定义接收端口来接收到的更改的通知消息**员工**SQL Server 数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="2d643-108">A one-way WCF-Custom receive port to receive notification messages for changes to **Employee** table in a SQL Server database.</span></span>  
  
-   <span data-ttu-id="2d643-109">请求-响应 WCF 自定义发送端口将请求消息发送和接收响应调用**UPDATE_EMPLOYEE**存储过程并在执行插入操作**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="2d643-109">A request-response WCF-Custom send port to send request messages and receive response for invoking the **UPDATE_EMPLOYEE** stored procedure and for performing the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="2d643-110">在业务流程，你可以使用相同的发送端口来执行这两个操作。</span><span class="sxs-lookup"><span data-stu-id="2d643-110">In the orchestration, you used the same send port to perform both the operations.</span></span> <span data-ttu-id="2d643-111">同样，在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您将一个发送端口用于这两种操作。</span><span class="sxs-lookup"><span data-stu-id="2d643-111">Similarly, in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you will use a single send port for both operations.</span></span>  
  
-   <span data-ttu-id="2d643-112">单向发送端口发送插入操作的响应。</span><span class="sxs-lookup"><span data-stu-id="2d643-112">A one-way send port to send the response for the Insert operation.</span></span> <span data-ttu-id="2d643-113">在本教程中，因为你需要告知通过电子邮件，购买部门创建此发送端口作为 SMTP 端口。</span><span class="sxs-lookup"><span data-stu-id="2d643-113">In this tutorial, because you need to inform the Purchases department through an e-mail, you create this send port as an SMTP port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2d643-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="2d643-114">Prerequisites</span></span>  
 <span data-ttu-id="2d643-115">你必须已完成[步骤 1： 部署的业务流程](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md))。</span><span class="sxs-lookup"><span data-stu-id="2d643-115">You must have completed [Step 1: Deploy the Orchestration](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)).</span></span>  
  
### <a name="to-create-a-physical-one-way-receive-port"></a><span data-ttu-id="2d643-116">若要创建物理单向接收端口</span><span class="sxs-lookup"><span data-stu-id="2d643-116">To create a physical one-way receive port</span></span>  
  
1.  <span data-ttu-id="2d643-117">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2d643-117">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="2d643-118">在控制台树中的左侧上，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="2d643-118">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="2d643-119">展开**BizTalk 组**，展开**应用程序**，然后展开**SampleApplication**。</span><span class="sxs-lookup"><span data-stu-id="2d643-119">Expand **BizTalk Group**, expand **Applications**, and expand **SampleApplication**.</span></span> <span data-ttu-id="2d643-120">对于本教程，你可以创建所有端口和 SampleApplication 应用程序中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2d643-120">For this tutorial, you create all the ports and application within the SampleApplication application.</span></span>  
  
4.  <span data-ttu-id="2d643-121">请按照下的"部署适配器 for 接收消息从 SQL Server"部分的说明操作[配置使用 WCF 自定义适配器和 SQL 适配器的端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2d643-121">Follow the instructions under the “Deploying Adapters for Receiving Messages from SQL Server” section of [Configure a port using the WCF-custom adapter and SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md).</span></span> <span data-ttu-id="2d643-122">名称为端口**NotifyReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="2d643-122">Name the port as **NotifyReceivePort**.</span></span>  
  
5.  <span data-ttu-id="2d643-123">请确保设置以下的绑定属性，以配置要接收的更改通知的适配器**员工**表。</span><span class="sxs-lookup"><span data-stu-id="2d643-123">Make sure you set the following binding properties to configure the adapter to receive notifications for changes to the **Employee** table.</span></span>  
  
    |<span data-ttu-id="2d643-124">绑定属性</span><span class="sxs-lookup"><span data-stu-id="2d643-124">Binding property</span></span>|<span data-ttu-id="2d643-125">值</span><span class="sxs-lookup"><span data-stu-id="2d643-125">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="2d643-126">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="2d643-126">**InboundOperationType**</span></span>|<span data-ttu-id="2d643-127">将其设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="2d643-127">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="2d643-128">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="2d643-128">**NotificationStatement**</span></span>|<span data-ttu-id="2d643-129">将其设置为：</span><span class="sxs-lookup"><span data-stu-id="2d643-129">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="2d643-130">**注意：**你必须专门的列名称在语句中指定此 Select 语句中所示。</span><span class="sxs-lookup"><span data-stu-id="2d643-130">**Note:** You must specifically specify the column names in the statement as shown in this Select statement.</span></span> <span data-ttu-id="2d643-131">此外，你必须始终指定表名称以及架构名称，例如， `dbo.Employee`。</span><span class="sxs-lookup"><span data-stu-id="2d643-131">Also, you must always specify the table name along with the schema name, for example, `dbo.Employee`.</span></span>|  
    |<span data-ttu-id="2d643-132">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="2d643-132">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="2d643-133">将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="2d643-133">Set this to **True**.</span></span>|  
  
     <span data-ttu-id="2d643-134">有关不同的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2d643-134">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
### <a name="to-create-a-request-response-send-port-for-two-operations"></a><span data-ttu-id="2d643-135">若要创建请求-响应，将发送针对两个操作的端口</span><span class="sxs-lookup"><span data-stu-id="2d643-135">To create a request-response send port for two operations</span></span>  
  
1.  <span data-ttu-id="2d643-136">请按照下的"部署适配器为发送消息到 SQL Server"部分的说明操作[配置使用 WCF 自定义适配器和 SQL 适配器的端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2d643-136">Follow the instructions under the “Deploying Adapters for Sending Messages to SQL Server” section of [Configure a port using the WCF-custom adapter and SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md).</span></span> <span data-ttu-id="2d643-137">名称为端口**SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="2d643-137">Name the port as **SQLOutboundPort**.</span></span>  
  
2.  <span data-ttu-id="2d643-138">因为你将要使用的相同的两个操作发送端口，必须使用动态操作映射来指定该操作的操作。</span><span class="sxs-lookup"><span data-stu-id="2d643-138">Because you are performing two operations using the same send port, you must use dynamic action mapping to specify the action for the operation.</span></span> <span data-ttu-id="2d643-139">在中配置端口时**操作**框中，按以下方式指定操作映射：</span><span class="sxs-lookup"><span data-stu-id="2d643-139">While configuring the port, in the **Action** box, specify the action mapping in the following manner:</span></span>  
  
    ```  
    \<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="UpdateEmp" Action="TypedProcedure/dbo/UPDATE_EMPLOYEE" />  
      <Operation Name="InsertPO" Action="TableOp/Insert/dbo/Purchase_Order" />  
    </BtsActionMapping>  
    ```  
  
     <span data-ttu-id="2d643-140">请注意，业务流程，在中创建两个操作的请求-响应发送端口： **UpdateEmp**和**InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="2d643-140">Note that in the orchestration, you created two operations for the request-response send port: **UpdateEmp** and **InsertPO**.</span></span> <span data-ttu-id="2d643-141">因此，在的物理端口配置你提供的动态操作映射中相同的操作名称。</span><span class="sxs-lookup"><span data-stu-id="2d643-141">So, in the physical port configuration you provide the same operation names in the dynamic action mapping.</span></span> <span data-ttu-id="2d643-142">在上面的摘录中，为操作**UpdateEmp**操作`TypedProcedure/dbo/UPDATE_EMPLOYEE`。</span><span class="sxs-lookup"><span data-stu-id="2d643-142">In the above excerpt, the action for **UpdateEmp** operation is `TypedProcedure/dbo/UPDATE_EMPLOYEE`.</span></span> <span data-ttu-id="2d643-143">同样，为操作**InsertPO**操作`TableOp/Insert/dbo/Purchase_Order`。</span><span class="sxs-lookup"><span data-stu-id="2d643-143">Similarly, the action for **InsertPO** operation is `TableOp/Insert/dbo/Purchase_Order`.</span></span>  
  
3.  <span data-ttu-id="2d643-144">你还必须配置要使用映射器业务流程的将响应消息映射中创建的发送端口**UPDATE_EMPLOYEE**存储插入操作的请求消息的过程**Purchase_顺序**表。</span><span class="sxs-lookup"><span data-stu-id="2d643-144">You must also configure the send port to use the Mapper you created in the orchestration to map the response message of **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation on **Purchase_Order** table.</span></span> <span data-ttu-id="2d643-145">为此：</span><span class="sxs-lookup"><span data-stu-id="2d643-145">To do so:</span></span>  
  
    1.  <span data-ttu-id="2d643-146">右键单击在 SQLOutboundPort[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2d643-146">Right-click the SQLOutboundPort in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="2d643-147">从**SQLOutboundPort-发送端口属性**对话框中，从左窗格中，单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="2d643-147">From the **SQLOutboundPort – Send Port Properties** dialog box, from the left pane, click **Outbound Maps**.</span></span>  
  
    3.  <span data-ttu-id="2d643-148">从右窗格中，在**出站映射**框中，单击下面的单元格中**映射**列，然后从下拉列表中，选择**Transform_1**。</span><span class="sxs-lookup"><span data-stu-id="2d643-148">From the right-pane, in the **Outbound Maps** box, click the cell under the **Map** column, and from the drop-down list, select **Transform_1**.</span></span> <span data-ttu-id="2d643-149">这是你在中 BizTalk 业务流程中创建的映射的名称[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2d643-149">This is the name of the map you created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
         <span data-ttu-id="2d643-150">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2d643-150">Click **OK**.</span></span>  
  
         <span data-ttu-id="2d643-151">![配置出站映射](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")</span><span class="sxs-lookup"><span data-stu-id="2d643-151">![Configure outbound map](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")</span></span>  
  
### <a name="to-create-an-smtp-send-port"></a><span data-ttu-id="2d643-152">若要创建 SMTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="2d643-152">To create an SMTP send port</span></span>  
  
1.  <span data-ttu-id="2d643-153">请按照下的说明操作"如何配置与 SMTP 发送端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台"部分[http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549)。</span><span class="sxs-lookup"><span data-stu-id="2d643-153">Follow the instructions under the “How to Configure an SMTP Send Port with the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console” section at [http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549).</span></span> <span data-ttu-id="2d643-154">名称为端口**EmailResponse**。</span><span class="sxs-lookup"><span data-stu-id="2d643-154">Name the port as **EmailResponse**.</span></span>  
  
2.  <span data-ttu-id="2d643-155">作为的端口配置的一部分，指定为购买部门的电子邮件地址**到**属性。</span><span class="sxs-lookup"><span data-stu-id="2d643-155">As part of the port configuration, specify the e-mail address for the Purchases department for the **To** property.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="2d643-156">内容回顾</span><span class="sxs-lookup"><span data-stu-id="2d643-156">What did I just do?</span></span>  
 <span data-ttu-id="2d643-157">在此步骤中创建 WCF 自定义接收用于从 SQL Server 接收通知的端口，在 SQL Server 上执行操作的 WCF 自定义发送端口和发送响应从 SQL Server 作为电子邮件向购买部门的 SMTP 端口。</span><span class="sxs-lookup"><span data-stu-id="2d643-157">In this step you created a WCF-Custom receive port for receiving notifications from SQL Server, WCF-Custom send port for performing operations on SQL Server, and an SMTP port for sending the response from SQL Server as an e-mail to the Purchases department.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2d643-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2d643-158">Next Steps</span></span>  
 <span data-ttu-id="2d643-159">配置和中所述启动 BizTalk 应用程序，[步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2d643-159">You configure and start the BizTalk application, as described in [Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d643-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d643-160">See Also</span></span>  
 <span data-ttu-id="2d643-161">[步骤 1： 部署的业务流程](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="2d643-161">[Step 1: Deploy the Orchestration](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md) </span></span>  
 <span data-ttu-id="2d643-162">[步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="2d643-162">[Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span></span>  
 [<span data-ttu-id="2d643-163">第 5 课： 部署解决方案</span><span class="sxs-lookup"><span data-stu-id="2d643-163">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)