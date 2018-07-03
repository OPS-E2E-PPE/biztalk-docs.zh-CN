---
title: 添加用于 JD Edwards OneWorld 的 BizTalk 适配器 |Microsoft Docs
description: 将 JD Edwards OneWorld 添加到 BizTalk 管理、 创建发送端口、 配置传输属性和 BizTalk Server 中使用 JD Edwards OneWorld 适配器时使用 XMLReceive 和 XMLTransmit 管道
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decababef3ece92c99687a4019b15625b1b4c6b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981390"
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a><span data-ttu-id="5fe0a-103">在 BizTalk 管理中配置 JD Edwards EnterpriseOne 项目</span><span class="sxs-lookup"><span data-stu-id="5fe0a-103">Configure JD Edwards EnterpriseOne artifacts in BizTalk Administration</span></span>
<span data-ttu-id="5fe0a-104">适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含“接收处理程序”文件夹和“发送处理程序”文件夹。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-104">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="5fe0a-105">“发送处理程序”文件夹包含 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-105">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="5fe0a-106">适用于 JD Edwards OneWorld 的 BizTalk 适配器是可以创建的，它在与 BizTalk 服务器相关的进程中运行，而不在隔离的主机进程中运行。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-106">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="5fe0a-107">将适配器添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="5fe0a-107">Add the adapter to BizTalk Administration</span></span> 

1.  <span data-ttu-id="5fe0a-108">打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**.</span><span class="sxs-lookup"><span data-stu-id="5fe0a-108">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
2.  <span data-ttu-id="5fe0a-109">右键单击**适配器**，选择**新建**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
3.  <span data-ttu-id="5fe0a-110">输入适配器的名称。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-110">Enter a name for the adapter.</span></span> <span data-ttu-id="5fe0a-111">例如，输入`JDEOneWorld`。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-111">For example, enter`JDEOneWorld`.</span></span>  
  
4.  <span data-ttu-id="5fe0a-112">选择**JDEOneWorld**从**适配器**列表，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-112">Select **JDEOneWorld** from the **Adapter** list, and select **OK**.</span></span>  

  
### <a name="check-if-the-adapter-is-working"></a><span data-ttu-id="5fe0a-113">检查适配器是否正常工作</span><span class="sxs-lookup"><span data-stu-id="5fe0a-113">Check if the adapter is working</span></span> 
 <span data-ttu-id="5fe0a-114">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以验证适配器工作正常，通过查看**逻辑系统**窗口。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="5fe0a-115">在初始安装时，该窗口为空，因为您还没有建立到服务器系统的连接，也没有建立任何逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-115">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
 
1. <span data-ttu-id="5fe0a-116">在中**BizTalk Server 管理**，展开**平台设置**，展开**适配器**，然后选择**JDEOneWorld**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-116">In **BizTalk Server Administration**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2. <span data-ttu-id="5fe0a-117">在细节窗格中，右键单击**BizTalkServerApplication**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-117">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="5fe0a-118">选择**属性**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-118">Select the **Properties** tab.</span></span>  
  
4. <span data-ttu-id="5fe0a-119">设置 SQL 连接参数。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-119">Set the SQL Connection parameters.</span></span>  
  
   -   <span data-ttu-id="5fe0a-120">**定义 SQL 数据库参数-** SQL Server 名称和数据库都是在安装时设置。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-120">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="5fe0a-121">在这个文本区域，您可以重新定义适用于该适配器的服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-121">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5. <span data-ttu-id="5fe0a-122">选择**关闭**退出**逻辑系统**窗口。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-122">Select **Close** to exit the **Logical System** window.</span></span>  
  
    <span data-ttu-id="5fe0a-123">下一步是使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 添加逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-123">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

## <a name="create-the-send-port"></a><span data-ttu-id="5fe0a-124">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="5fe0a-124">Create the send port</span></span>  
  
1.  <span data-ttu-id="5fe0a-125">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-125">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="5fe0a-126">右键单击**发送端口**，选择**新建**，然后选择**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-126">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5fe0a-127">此外可以使用**静态单向端口**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-127">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="5fe0a-128">在中**发送端口属性**，选择**名称**字段，并输入发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-128">In the **Send Port Properties**, select the **Name** field, and enter a send port name.</span></span> <span data-ttu-id="5fe0a-129">例如，输入**SendToJDE**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-129">For example, enter **SendToJDE**.</span></span>  
  
4.  <span data-ttu-id="5fe0a-130">在中**类型**下拉列表中，选择**JDEOneWorld**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-130">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="5fe0a-131">在中**URI**下拉列表中，选择发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-131">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="5fe0a-132">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-132">Select **OK**.</span></span> 

## <a name="configure-the-transport-properties"></a><span data-ttu-id="5fe0a-133">配置传输属性</span><span class="sxs-lookup"><span data-stu-id="5fe0a-133">Configure the transport properties</span></span>
<span data-ttu-id="5fe0a-134">JD Edwards OneWorld 传输属性系统定义用于设计和运行时登录。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-134">The JD Edwards OneWorld Transport Property System Definition is used for design and run-time logon.</span></span> <span data-ttu-id="5fe0a-135">在设计时，将这些凭据设置为浏览 JD Edwards OneWorld 业务函数，并在运行时进行调用。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-135">You set these credentials to browse JD Edwards OneWorld business functions at design time and make calls at run time.</span></span>  
  
 <span data-ttu-id="5fe0a-136">在建立与 JD Edwards OneWorld 的连接后，将参数传递给连接对象（用户、密码、环境）。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-136">When a connection is made to JD Edwards OneWorld, parameters are passed to the connection object (User, Password, Environment).</span></span> <span data-ttu-id="5fe0a-137">它将返回 JD Edwards OneWorld 应用程序业务函数的一个实例。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-137">It returns an instance of the JD Edwards OneWorld aApplication business function.</span></span> <span data-ttu-id="5fe0a-138">通过企业/应用程序服务器名称及服务侦听到的已定义的 TCP/IP 端口可进一步定义这些凭据。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-138">The credentials are further defined by the name of the enterprise/application server, and the defined TCP/IP port on which the service listens.</span></span>  
  
 <span data-ttu-id="5fe0a-139">从名为 jdeinterop.ini 的文件中读取企业服务器名称和端口。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-139">The enterprise server name and port are read from a file that is named jdeinterop.ini.</span></span> <span data-ttu-id="5fe0a-140">这些值必须是系统定义设置中的相同。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-140">These values must be the same as those that are in the System Definition settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fe0a-141">所有条目都要区分大小写。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-141">All entries are case sensitive.</span></span>  
  
### <a name="set-the-properties"></a><span data-ttu-id="5fe0a-142">设置属性</span><span class="sxs-lookup"><span data-stu-id="5fe0a-142">Set the properties</span></span>  
 <span data-ttu-id="5fe0a-143">在中**传输属性**对话框中，你设置特定于服务器系统和你尝试访问的对象的连接和凭据参数。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-143">In the **Transport Properties** dialog box, you set the connection and credential parameters that are specific to the server system and the objects you are trying to access.</span></span>  
  
1.  <span data-ttu-id="5fe0a-144">提供凭据。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-144">Provide credentials.</span></span> <span data-ttu-id="5fe0a-145">您可以使用以下方法之一访问 JD Edwards OneWorld 系统：</span><span class="sxs-lookup"><span data-stu-id="5fe0a-145">You can access the JD Edwards OneWorld system using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="5fe0a-146">登录凭据 （密码、 用户名）： 如果使用此方法，请转到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-146">Logon credentials (Password, User name): If you use this method, go to step 5.</span></span>  
  
    -   <span data-ttu-id="5fe0a-147">单一登录。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-147">Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="5fe0a-148">若要使用单一登录 (SSO)，选择**是**中**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-148">To use Single Sign-On (SSO), select **Yes** in the **Use SSO**.</span></span>  
  
     <span data-ttu-id="5fe0a-149">有关如何设置 SSO 的详细信息，请参阅[适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0a-149">For more information about how to set up SSO, see [Security in the adapter](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span></span>  
  
3.  <span data-ttu-id="5fe0a-150">在列表中选择一个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-150">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="5fe0a-151">企业单一登录工具创建的关联应用程序代表诸如 JD Edwards OneWorld 之类的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-151">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as JD Edwards OneWorld.</span></span> <span data-ttu-id="5fe0a-152">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-152">Microsoft BizTalk Adapter for JD Edwards OneWorld uses the credentials of an application user.</span></span> <span data-ttu-id="5fe0a-153">这些凭据是从服务器系统的 SSO 凭据数据库中为指定关联应用程序检索的。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-153">These credentials are retrieved from the SSO Credentials database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="5fe0a-154">凭据是启动 BizTalk Server 项目的应用程序用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-154">The credentials are those of the application user who launched the BizTalk Server project.</span></span>  
  
     <span data-ttu-id="5fe0a-155">有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-155">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
4.  <span data-ttu-id="5fe0a-156">展开**JD Edwards OneWorld 系统**节点并输入所需的所有信息以连接到 JD Edwards OneWorld 服务器。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-156">Expand the **JD Edwards OneWorld system** node and enter all required information for connection to the JD Edwards OneWorld server.</span></span>  
  
     <span data-ttu-id="5fe0a-157">![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")</span><span class="sxs-lookup"><span data-stu-id="5fe0a-157">![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")</span></span>  
  
     <span data-ttu-id="5fe0a-158">设置连接参数后，您可以浏览 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-158">After you set the connection parameters, you can browse a JD Edwards OneWorld system.</span></span> <span data-ttu-id="5fe0a-159">有关详细信息，请参阅[导入到 BizTalk Server 项目 JD Edwards OneWorld 架构](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-159">For more information, see [Importing JD Edwards OneWorld Schemas into BizTalk Server Projects](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).</span></span>  
  
5.  <span data-ttu-id="5fe0a-160">输入一个值，表示在调用，例如 200 数**最大并发调用**如有必要。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-160">Enter a value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="5fe0a-161">`Max Concurrent Calls`参数可以优化您的配置。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-161">The `Max Concurrent Calls` parameter lets you optimize your configuration.</span></span> <span data-ttu-id="5fe0a-162">在吞吐量超过了后端处理能力的情况下，可以使用此参数激活消息重载保护。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-162">You use this parameter in instances where the throughput exceeds back-end processing capabilities, to activate message-overload protection.</span></span> <span data-ttu-id="5fe0a-163">默认值为 -1，表示调用不受限制。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-163">The default is -1, which means that the calls are unlimited.</span></span>  
  
     <span data-ttu-id="5fe0a-164">在 BizTalk Server 将消息提交到传输适配器后，首先会从该适配器收到一个批。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-164">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter.</span></span> <span data-ttu-id="5fe0a-165">它调用批上的 `TransmitMessage` 以传输每个消息。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-165">It invokes `TransmitMessage` on the batch to transmit each message.</span></span> <span data-ttu-id="5fe0a-166">完成上述操作后，BizTalk Server 对批调用 `Done`，然后适配器开始将消息传输到后端。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-166">When done, BizTalk Server invokes `Done` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="5fe0a-167">如果在调用 `Done` 前，BizTalk Server 获得了多个批，这可能就永远不会发生。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-167">If BizTalk Server obtains multiple batches before invoking `Done`, it might never occur.</span></span> <span data-ttu-id="5fe0a-168">通过设置批中的最大消息数量，可以控制传输到后端的消息。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-168">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span>  
  
     <span data-ttu-id="5fe0a-169">更改此参数后，所做更改会在一分钟内生效；BizTalk Server 必须检索 SQL 数据库中保存的对适配器配置的更改。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-169">Changing this parameter takes effect within one minute; BizTalk Server must retrieve the changes to the adapter configuration saved in the SQL database.</span></span>  
  
6.  <span data-ttu-id="5fe0a-170">选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-170">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="5fe0a-171">例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-171">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5fe0a-172">browsingagent.exe 在退出当前浏览会话之前不会进行刷新。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-172">The browsingagent.exe does not refresh until you exit the current browsing session.</span></span> <span data-ttu-id="5fe0a-173">例如，你必须退出**生成的添加项**浏览会话并重新进入以便更新 browsingagent.exe。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-173">For example, you must exit the **Add generated item** browsing session and reenter to update the browsingagent.exe.</span></span>  
  
7.  <span data-ttu-id="5fe0a-174">提供所需的所有信息后，单击**Apply**，然后单击**确定**接受连接信息。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-174">After providing all required information, click **Apply**, and then click **OK** to accept the connection information.</span></span>  
  
     <span data-ttu-id="5fe0a-175">您必须为用于 JD Edwards OneWorld 的 BizTalk 适配器设置连接参数才能访问 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-175">You must set connection parameters for BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld.</span></span>  
  
### <a name="adapter-required-properties"></a><span data-ttu-id="5fe0a-176">所需的适配器属性</span><span class="sxs-lookup"><span data-stu-id="5fe0a-176">Adapter required properties</span></span>  
 <span data-ttu-id="5fe0a-177">如果没有在控制面板中设置全局环境变量，则可以在此部分中执行这项工作。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-177">If you did not set global environment variables in Control Panel, you can do so in this section.</span></span>  
  
|<span data-ttu-id="5fe0a-178">参数</span><span class="sxs-lookup"><span data-stu-id="5fe0a-178">Parameter</span></span>|<span data-ttu-id="5fe0a-179">Description</span><span class="sxs-lookup"><span data-stu-id="5fe0a-179">Description</span></span>|  
|---------------|-----------------|  
|`Host`|<span data-ttu-id="5fe0a-180">键入主机服务器计算机名称的名称 (例如， `actsvr1`); 或的计算机的 IP 地址 (例如， `123.456.0.789`)。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-180">Type the name of the host server computer name (for example, `actsvr1`); or the IP address of the computer (for example, `123.456.0.789`).</span></span>|  
|<span data-ttu-id="5fe0a-181">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="5fe0a-181">JAVA_HOME</span></span>|<span data-ttu-id="5fe0a-182">键入 JDK 安装的完整路径。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-182">Type the complete path of your JDK installation.</span></span>|  
|<span data-ttu-id="5fe0a-183">JDE Edwards 环境</span><span class="sxs-lookup"><span data-stu-id="5fe0a-183">JDE Edwards Environment</span></span>|<span data-ttu-id="5fe0a-184">例如，JD Edwards OneWorld 中键入环境名称`DV7333`。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-184">Type the name of an environment in JD Edwards OneWorld, for example, `DV7333`.</span></span><br /><br /> <span data-ttu-id="5fe0a-185">DV7333 是开发环境的公用名，PY7333 是原型环境的公用名，PD7333 是生产环境的公用名。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-185">DV7333 is a common name for the development environment, PY7333 is common for the prototype environment, and PD7333 is common for the production environment.</span></span>|  
|<span data-ttu-id="5fe0a-186">JDEdwards JAR 文件</span><span class="sxs-lookup"><span data-stu-id="5fe0a-186">JDEdwards JAR Files</span></span>|<span data-ttu-id="5fe0a-187">输入每个 JAR 文件的完整路径和文件名称：</span><span class="sxs-lookup"><span data-stu-id="5fe0a-187">Enter the complete path and file name for each JAR file:</span></span><br /><br /> <span data-ttu-id="5fe0a-188">-Connector.jar</span><span class="sxs-lookup"><span data-stu-id="5fe0a-188">-   Connector.jar</span></span><br /><span data-ttu-id="5fe0a-189">-Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="5fe0a-189">-   Kernel.jar</span></span><br /><span data-ttu-id="5fe0a-190">-JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="5fe0a-190">-   JDEJAccess.jar</span></span><br /><span data-ttu-id="5fe0a-191">-JDEActionalInterop.jar</span><span class="sxs-lookup"><span data-stu-id="5fe0a-191">-   JDEActionalInterop.jar</span></span><br /><br /> <span data-ttu-id="5fe0a-192">每个 jar 文件必须用分号 (;) 分隔，中间不留空格。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-192">Each jar file must be separated with a semi-colon (;) and no space.</span></span> <span data-ttu-id="5fe0a-193">例如：</span><span class="sxs-lookup"><span data-stu-id="5fe0a-193">For example:</span></span><br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|<span data-ttu-id="5fe0a-194">Password</span><span class="sxs-lookup"><span data-stu-id="5fe0a-194">Password</span></span>|<span data-ttu-id="5fe0a-195">键入指定用户的密码。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-195">Type the password of the specified user.</span></span>|  
|<span data-ttu-id="5fe0a-196">端口</span><span class="sxs-lookup"><span data-stu-id="5fe0a-196">Port</span></span>|<span data-ttu-id="5fe0a-197">键入将要交换数据的端口号 (例如， `6009`)。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-197">Type the port number that will exchange data (for example, `6009`).</span></span>|  
|<span data-ttu-id="5fe0a-198">用户名</span><span class="sxs-lookup"><span data-stu-id="5fe0a-198">User Name</span></span>|<span data-ttu-id="5fe0a-199">键入将用于登录 JD Edwards OneWorld 系统的 JD Edwards OneWorld 用户名。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-199">Type a JD Edwards OneWorld user name that will be used to log on to the JD Edwards OneWorld system.</span></span>|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a><span data-ttu-id="5fe0a-200">使用 XMLTransmit 和 XMLReceive 管道</span><span class="sxs-lookup"><span data-stu-id="5fe0a-200">Use the XMLTransmit and XMLReceive pipelines</span></span>
<span data-ttu-id="5fe0a-201">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器要求你选择 XMLTransmit 和 XMLReceive 的发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-201">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines.</span></span>  
  
1.  <span data-ttu-id="5fe0a-202">在中**BizTalk Server 管理**，展开**应用程序**，然后展开你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-202">In **BizTalk Server Administration**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="5fe0a-203">选择**发送端口**，右键单击您的发送端口，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-203">Select **Send Ports**, right-click your send port, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5fe0a-204">在中**发送端口属性**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5fe0a-204">In the **Send Ports Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="5fe0a-205">选择发送管道从**发送管道**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-205">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="5fe0a-206">选择从接收管道**接收管道**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-206">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
4.  <span data-ttu-id="5fe0a-207">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="5fe0a-207">Select **OK**.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="5fe0a-208">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5fe0a-208">Next steps</span></span>
[<span data-ttu-id="5fe0a-209">将适配器架构导入到 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5fe0a-209">Import adapter schemas into Visual Studio</span></span>](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="5fe0a-210">使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="5fe0a-210">Use Message Context Properties</span></span>](using-message-context-properties2.md)