---
title: "教程： 使用 TIBCO 会合适配器发送 |Microsoft 文档"
description: "分步指南，以用于 BizTalk 适配器 TIBCO 会合 BizTalk Server 中将数据发送到 TIBCO 系统"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08987e92465358276df7936f39cfa7c449c0503
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="1bf0a-103">教程：使用 TIBCO Rendezvous 的 BizTalk 适配器以发送数据</span><span class="sxs-lookup"><span data-stu-id="1bf0a-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="1bf0a-104">您可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器向 TIBCO 系统发送数据。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-104">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="1bf0a-105">本演练描述了对此进行说明的一个 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1bf0a-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="1bf0a-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="1bf0a-107">为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
-   <span data-ttu-id="1bf0a-108">此示例使用包含消息上下文属性的 DLL: Microsoft.BizTalk.Adapters.TibRV.Properties.dll。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-108">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="1bf0a-109">您可能需要更新解决方案对此库的引用。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-109">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="1bf0a-110">有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-110">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  
  
## <a name="about-the-sample"></a><span data-ttu-id="1bf0a-111">有关该示例</span><span class="sxs-lookup"><span data-stu-id="1bf0a-111">About the sample</span></span> 

- <span data-ttu-id="1bf0a-112">该示例从一个文件夹选取一个 XML 文件，将该文件发送到业务流程，然后使用用于 TIBCO Rendezvous 的 BizTalk 适配器在 TIBCO 系统中创建一个记录。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-112">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  
  
- <span data-ttu-id="1bf0a-113">本示例是在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中设计的，它通过 BizTalk 业务流程中使用用于 TIBCO Rendezvous 的 BizTalk 适配器介绍了一些基本功能。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-113">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  
  
- <span data-ttu-id="1bf0a-114">此示例的默认位置是`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`，并包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="1bf0a-114">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`, and includes the following files:</span></span> 
    
    |<span data-ttu-id="1bf0a-115">**运行时项目文件名**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-115">**Runtime Project Filename**</span></span>|<span data-ttu-id="1bf0a-116">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-116">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="1bf0a-117">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="1bf0a-117">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="1bf0a-118">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="1bf0a-118">OneWaySend.sln</span></span>|<span data-ttu-id="1bf0a-119">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-119">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="1bf0a-120">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="1bf0a-120">Schema.xsd</span></span><br /><br /> <span data-ttu-id="1bf0a-121">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1bf0a-121">PropertySchema.xsd</span></span>|<span data-ttu-id="1bf0a-122">应用程序的架构和属性架构文件。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-122">Schema and property schema files for the application.</span></span>|  
    |<span data-ttu-id="1bf0a-123">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="1bf0a-123">Orchestration.odx</span></span>|<span data-ttu-id="1bf0a-124">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-124">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="1bf0a-125">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="1bf0a-125">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="1bf0a-126">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-126">The strong naming key file.</span></span>|  
  
## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="1bf0a-127">步骤 1： 将适配器添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="1bf0a-127">Step 1: Add the adapter to BizTalk Administration</span></span>
  
1.  <span data-ttu-id="1bf0a-128">在**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-128">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="1bf0a-129">右键单击**适配器**和指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-129">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="1bf0a-130">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-130">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="1bf0a-131">输入一个值**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-131">Enter a value for the **Name** field.</span></span> <span data-ttu-id="1bf0a-132">例如，输入**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-132">For example, enter **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="1bf0a-133">选择**TIBCO(r) Rendezvous(r)**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-133">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
## <a name="step-2-create-a-send-port"></a><span data-ttu-id="1bf0a-134">步骤 2： 创建发送端口</span><span class="sxs-lookup"><span data-stu-id="1bf0a-134">Step 2: Create a Send Port</span></span>  
  
1.  <span data-ttu-id="1bf0a-135">在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-135">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="1bf0a-136">右键单击**发送端口**和指向**新建**，**静态单向发送端口...**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-136">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="1bf0a-137">若要显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-137">to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="1bf0a-138">输入一个值**名称**字段，例如**TIBCORndOneWaySP**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-138">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="1bf0a-139">从中的可用适配器的列表中选择 TIBCO 会合适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-139">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bf0a-140">此值是 TIBCO 企业消息系统适配器在创建时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-140">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5.  <span data-ttu-id="1bf0a-141">输入值**认证发件人属性**:</span><span class="sxs-lookup"><span data-stu-id="1bf0a-141">Enter values for the **Certified Sender Properties**:</span></span>  
  
    |<span data-ttu-id="1bf0a-142">**属性**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-142">**Property**</span></span>|<span data-ttu-id="1bf0a-143">**值**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-143">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="1bf0a-144">分类帐文件名称</span><span class="sxs-lookup"><span data-stu-id="1bf0a-144">Ledger file name</span></span>|<span data-ttu-id="1bf0a-145">用于持久性认证消息传递的分类帐文件名。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-145">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="1bf0a-146">可重复使用的名称</span><span class="sxs-lookup"><span data-stu-id="1bf0a-146">Reusable name</span></span>|<span data-ttu-id="1bf0a-147">用于已验证消息传递的可重用的通信名称。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-147">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="1bf0a-148">在网络上所有已验证消息通信名称中，该名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-148">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="1bf0a-149">输入值**凭据**:</span><span class="sxs-lookup"><span data-stu-id="1bf0a-149">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="1bf0a-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-150">**Property**</span></span>|<span data-ttu-id="1bf0a-151">**值**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-151">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="1bf0a-152">密码</span><span class="sxs-lookup"><span data-stu-id="1bf0a-152">Password</span></span>|<span data-ttu-id="1bf0a-153">TIBCO Rendezvous 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-153">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="1bf0a-154">用户名</span><span class="sxs-lookup"><span data-stu-id="1bf0a-154">User name</span></span>|<span data-ttu-id="1bf0a-155">TIBCO Rendezvous 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-155">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="1bf0a-156">输入值**RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="1bf0a-156">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="1bf0a-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-157">**Property**</span></span>|<span data-ttu-id="1bf0a-158">**值**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-158">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="1bf0a-159">后台程序</span><span class="sxs-lookup"><span data-stu-id="1bf0a-159">Daemon</span></span>|<span data-ttu-id="1bf0a-160">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-160">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="1bf0a-161">Network</span><span class="sxs-lookup"><span data-stu-id="1bf0a-161">Network</span></span>|<span data-ttu-id="1bf0a-162">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-162">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="1bf0a-163">服务</span><span class="sxs-lookup"><span data-stu-id="1bf0a-163">Service</span></span>|<span data-ttu-id="1bf0a-164">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-164">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="1bf0a-165">有关属性的详细信息，请参阅[创建发送项目](../core/creating-tibco-rendezvous-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-165">For more information about the properties, see [Create the send artifacts](../core/creating-tibco-rendezvous-send-handlers.md).</span></span>  
  
8.  <span data-ttu-id="1bf0a-166">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-166">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1bf0a-167">选择**XML 传输**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-167">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
10. <span data-ttu-id="1bf0a-168">右键单击发送端口，然后单击**启动**登记和启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-168">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
## <a name="step-3-create-a-receive-port"></a><span data-ttu-id="1bf0a-169">步骤 3： 创建接收端口</span><span class="sxs-lookup"><span data-stu-id="1bf0a-169">Step 3: Create a receive port</span></span>  
  
1.  <span data-ttu-id="1bf0a-170">在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-170">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="1bf0a-171">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...**以显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-171">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="1bf0a-172">输入一个值**名称**字段，例如**TIBCORndOneWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-172">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  
  
## <a name="step-4-create-a-receive-location"></a><span data-ttu-id="1bf0a-173">步骤 4： 创建接收位置</span><span class="sxs-lookup"><span data-stu-id="1bf0a-173">Step 4: Create a receive location</span></span>  
  
1.  <span data-ttu-id="1bf0a-174">为要监视的文件接收位置创建文件夹，例如 C:\Filesource。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-174">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="1bf0a-175">右键单击新的接收端口，然后单击**新建**，**接收位置...**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-175">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="1bf0a-176">若要显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-176">to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="1bf0a-177">输入一个值**名称**字段，例如**TIBCORndOneWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="1bf0a-178">选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-178">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="1bf0a-179">输入以前为创建的文件夹的位置**接收文件夹**属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-179">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="1bf0a-180">选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-180">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="1bf0a-181">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-181">Right-click the receive location and click **Enable**.</span></span>  
  
## <a name="step-5-generate-a-document-instance-from-the-schema"></a><span data-ttu-id="1bf0a-182">步骤 5： 从架构生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="1bf0a-182">Step 5: Generate a document instance from the schema</span></span>  
  
1.  <span data-ttu-id="1bf0a-183">在 Visual Studio 中，右击 Schema.xsd 在解决方案资源管理器，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-183">In Visual Studio,right-click Schema.xsd in Solution Explorer, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1bf0a-184">在属性窗口中，单击以选中**输出实例文件名**选项下**常规**部分。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-184">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  
  
3.  <span data-ttu-id="1bf0a-185">单击省略号按钮 （…） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-185">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
4.  <span data-ttu-id="1bf0a-186">指定的文件夹和输出文件实例的名称，例如**C:\instance.xml**单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-186">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bf0a-187">请勿指定为此处的文件接收位置指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-187">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
5.  <span data-ttu-id="1bf0a-188">右击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**在指定的位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-188">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
## <a name="step-6-update-the-generated-document-instance"></a><span data-ttu-id="1bf0a-189">步骤 6： 更新生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="1bf0a-189">Step 6: Update the generated document instance</span></span>  
  
1.  <span data-ttu-id="1bf0a-190">在文本编辑器 （记事本工作原理），打开生成的文档实例并编辑文档实例，来确保数据将 TIBCO 系统中生成的唯一记录的内容。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-190">Open the generated document instance in a text editor(Notepad works), and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="1bf0a-191">例如，以下代码演示数据文件的第一部分：</span><span class="sxs-lookup"><span data-stu-id="1bf0a-191">For example, the follow code shows the first part of the data file:</span></span>  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  <span data-ttu-id="1bf0a-192">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-192">Save the modified document instance.</span></span>  
  
## <a name="step-7-build-and-deploy-the-project"></a><span data-ttu-id="1bf0a-193">步骤 7： 生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="1bf0a-193">Step 7: Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="1bf0a-194">右键单击**OneWaySend**项目在解决方案资源管理器，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-194">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="1bf0a-195">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-195">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="1bf0a-196">输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-196">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="1bf0a-197">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-197">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
## <a name="step-8-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="1bf0a-198">步骤 8： 绑定，登记，并开始业务流程</span><span class="sxs-lookup"><span data-stu-id="1bf0a-198">Step 8: Bind, enlist, and start the orchestration</span></span>  
  
1.  <span data-ttu-id="1bf0a-199">在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-199">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="1bf0a-200">单击**刷新**中 MMC 工具栏或按按钮**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-200">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="1bf0a-201">双击要显示的业务流程**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-201">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="1bf0a-202">单击**绑定**显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-202">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="1bf0a-203">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="1bf0a-203">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="1bf0a-204">**参数**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-204">**Parameter**</span></span>|<span data-ttu-id="1bf0a-205">**值**</span><span class="sxs-lookup"><span data-stu-id="1bf0a-205">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="1bf0a-206">主机</span><span class="sxs-lookup"><span data-stu-id="1bf0a-206">Host</span></span>|<span data-ttu-id="1bf0a-207">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="1bf0a-207">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="1bf0a-208">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="1bf0a-208">FileReceivePort</span></span>|<span data-ttu-id="1bf0a-209">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="1bf0a-209">TIBCORndOneWayFileRP</span></span>|  
    |<span data-ttu-id="1bf0a-210">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="1bf0a-210">TibcoRendezvousSend</span></span>|<span data-ttu-id="1bf0a-211">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="1bf0a-211">TIBCORndOneWaySP</span></span>|  
  
6.  <span data-ttu-id="1bf0a-212">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-212">Click OK.</span></span>  
  
7. <span data-ttu-id="1bf0a-213">右键单击业务流程，然后单击**启动**登记和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-213">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  
  
## <a name="step-9-drop-a-document-and-check-the-tibco-system"></a><span data-ttu-id="1bf0a-214">步骤 9： 删除一个文档，并检查 TIBCO 系统</span><span class="sxs-lookup"><span data-stu-id="1bf0a-214">Step 9: Drop a document, and check the TIBCO system</span></span>
  
-   <span data-ttu-id="1bf0a-215">将早期创建的文档实例复制到应用程序监视的文件接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-215">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  
  
-   <span data-ttu-id="1bf0a-216">使用 TIBCO Web 界面验证是否已从 XML 文件中的数据创建记录。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-216">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  
  

<span data-ttu-id="1bf0a-217">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="1bf0a-217">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="1bf0a-218">文件适配器从文件夹中检索文件，并作为 BizTalk 消息将其发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-218">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="1bf0a-219">业务流程订阅此发布消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将该消息发送到该业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-219">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="1bf0a-220">业务流程实例使用业务流程中指定的逻辑处理该消息，并将该消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-220">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="1bf0a-221">TIBCO 发送端口订阅此发布消息，以便 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-221">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  
  
5.  <span data-ttu-id="1bf0a-222">发送端口将消息传给用于 TIBCO Rendezvous 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-222">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
6.  <span data-ttu-id="1bf0a-223">用于 TIBCO Rendezvous 的 BizTalk 适配器将消息发送给 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="1bf0a-223">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf0a-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bf0a-224">See Also</span></span>  
 <span data-ttu-id="1bf0a-225">[教程： 使用 TIBCO 会合的 BizTalk 适配器来接收数据](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="1bf0a-225">[Tutorial: Use the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="1bf0a-226">[教程： 使用 Microsoft BizTalk Adapter for TIBCO 会合](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="1bf0a-226">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="1bf0a-227">入门</span><span class="sxs-lookup"><span data-stu-id="1bf0a-227">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)