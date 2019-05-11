---
title: 教程：使用 TIBCO Rendezvous 适配器发送 |Microsoft Docs
description: 若要使用 BizTalk Server 中的 TIBCO Rendezvous 的 BizTalk 适配器将数据发送到 TIBCO 系统的分步指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b883f6ec3529a7a0a1acce538f2d878210d7c01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393816"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="0a536-103">教程：使用用于 TIBCO Rendezvous 的 BizTalk 适配器发送数据</span><span class="sxs-lookup"><span data-stu-id="0a536-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="0a536-104">用于 TIBCO Rendezvous 的 BizTalk 适配器可用于将数据发送到 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="0a536-104">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="0a536-105">本演练介绍阐释了这一点的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="0a536-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0a536-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="0a536-106">Prerequisites</span></span>  

- <span data-ttu-id="0a536-107">安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。</span><span class="sxs-lookup"><span data-stu-id="0a536-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

- <span data-ttu-id="0a536-108">此示例使用包含消息上下文属性的 DLL:Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span><span class="sxs-lookup"><span data-stu-id="0a536-108">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="0a536-109">您可能需要更新对此库的解决方案的引用。</span><span class="sxs-lookup"><span data-stu-id="0a536-109">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="0a536-110">有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="0a536-110">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  

## <a name="about-the-sample"></a><span data-ttu-id="0a536-111">有关该示例</span><span class="sxs-lookup"><span data-stu-id="0a536-111">About the sample</span></span> 

- <span data-ttu-id="0a536-112">此示例提取文件文件夹中的 XML 文件，将该文件发送到业务流程，然后使用用于 TIBCO Rendezvous 的 BizTalk 适配器在 TIBCO 系统中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="0a536-112">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  

- <span data-ttu-id="0a536-113">此示例中，在设计[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，说明使用用于 TIBCO Rendezvous 的 BizTalk 适配器，BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="0a536-113">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  

- <span data-ttu-id="0a536-114">该示例的默认位置是`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`，包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="0a536-114">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`, and includes the following files:</span></span> 

    |<span data-ttu-id="0a536-115">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="0a536-115">**Runtime Project Filename**</span></span>|<span data-ttu-id="0a536-116">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="0a536-116">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="0a536-117">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="0a536-117">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="0a536-118">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="0a536-118">OneWaySend.sln</span></span>|<span data-ttu-id="0a536-119">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="0a536-119">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="0a536-120">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="0a536-120">Schema.xsd</span></span><br /><br /> <span data-ttu-id="0a536-121">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="0a536-121">PropertySchema.xsd</span></span>|<span data-ttu-id="0a536-122">应用程序的架构和属性架构文件。</span><span class="sxs-lookup"><span data-stu-id="0a536-122">Schema and property schema files for the application.</span></span>|  
    |<span data-ttu-id="0a536-123">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="0a536-123">Orchestration.odx</span></span>|<span data-ttu-id="0a536-124">使用应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a536-124">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="0a536-125">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="0a536-125">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="0a536-126">强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="0a536-126">The strong naming key file.</span></span>|  

## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="0a536-127">第 1 步：将适配器添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="0a536-127">Step 1: Add the adapter to BizTalk Administration</span></span>

1.  <span data-ttu-id="0a536-128">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="0a536-128">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3.  <span data-ttu-id="0a536-129">右键单击**适配器**，然后指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="0a536-129">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="0a536-130">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-130">to display the **Adapter Properties** dialog.</span></span>  

4.  <span data-ttu-id="0a536-131">输入一个值**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="0a536-131">Enter a value for the **Name** field.</span></span> <span data-ttu-id="0a536-132">例如，输入**TIBCO Rendezvous**。</span><span class="sxs-lookup"><span data-stu-id="0a536-132">For example, enter **TIBCO Rendezvous**.</span></span>  

5.  <span data-ttu-id="0a536-133">选择**tibco （) Rendezvous(r)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a536-133">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

## <a name="step-2-create-a-send-port"></a><span data-ttu-id="0a536-134">第 2 步：创建发送端口</span><span class="sxs-lookup"><span data-stu-id="0a536-134">Step 2: Create a Send Port</span></span>  

1. <span data-ttu-id="0a536-135">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="0a536-135">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="0a536-136">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口...**</span><span class="sxs-lookup"><span data-stu-id="0a536-136">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="0a536-137">若要显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-137">to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="0a536-138">输入一个值**名称**字段，例如**TIBCORndOneWaySP**。</span><span class="sxs-lookup"><span data-stu-id="0a536-138">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  

4. <span data-ttu-id="0a536-139">从中可用的适配器列表中选择 TIBCO Rendezvous 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-139">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0a536-140">此值是在中创建 TIBCO Enterprise Message System 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0a536-140">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

5. <span data-ttu-id="0a536-141">输入值**已认证发送方属性**:</span><span class="sxs-lookup"><span data-stu-id="0a536-141">Enter values for the **Certified Sender Properties**:</span></span>  


   |   <span data-ttu-id="0a536-142">**属性**</span><span class="sxs-lookup"><span data-stu-id="0a536-142">**Property**</span></span>   |                                                                         <span data-ttu-id="0a536-143">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="0a536-143">**Value**</span></span>                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="0a536-144">分类帐文件名称</span><span class="sxs-lookup"><span data-stu-id="0a536-144">Ledger file name</span></span> |                                             <span data-ttu-id="0a536-145">要用于持久性认证的消息传递的分类帐文件名称。</span><span class="sxs-lookup"><span data-stu-id="0a536-145">Ledger file name to use for persistent certified message delivery.</span></span>                                             |
   |  <span data-ttu-id="0a536-146">可重复使用名称</span><span class="sxs-lookup"><span data-stu-id="0a536-146">Reusable name</span></span>   | <span data-ttu-id="0a536-147">若要使用认证的消息传递的可重用通信名称。</span><span class="sxs-lookup"><span data-stu-id="0a536-147">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="0a536-148">名称必须是唯一的而在网络上的所有认证的消息通信名称。</span><span class="sxs-lookup"><span data-stu-id="0a536-148">The name must be unique among all certified message correspondent names on the network.</span></span> |


6. <span data-ttu-id="0a536-149">输入值**凭据**:</span><span class="sxs-lookup"><span data-stu-id="0a536-149">Enter values for the **Credentials**:</span></span>  


   | <span data-ttu-id="0a536-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="0a536-150">**Property**</span></span> |                   <span data-ttu-id="0a536-151">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="0a536-151">**Value**</span></span>                    |
   |--------------|------------------------------------------------|
   |   <span data-ttu-id="0a536-152">Password</span><span class="sxs-lookup"><span data-stu-id="0a536-152">Password</span></span>   | <span data-ttu-id="0a536-153">TIBCO Rendezvous 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="0a536-153">The password for the TIBCO Rendezvous server.</span></span>  |
   |  <span data-ttu-id="0a536-154">“用户名”</span><span class="sxs-lookup"><span data-stu-id="0a536-154">User name</span></span>   | <span data-ttu-id="0a536-155">TIBCO Rendezvous 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="0a536-155">The user name for the TIBCO Rendezvous server.</span></span> |


7. <span data-ttu-id="0a536-156">输入值**RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="0a536-156">Enter values for the **RendezvousTransport**:</span></span>  

   |<span data-ttu-id="0a536-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="0a536-157">**Property**</span></span>|<span data-ttu-id="0a536-158">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="0a536-158">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="0a536-159">后台程序</span><span class="sxs-lookup"><span data-stu-id="0a536-159">Daemon</span></span>|<span data-ttu-id="0a536-160">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="0a536-160">Rendezvous Transport Daemon parameter.</span></span>|  
   |<span data-ttu-id="0a536-161">网络</span><span class="sxs-lookup"><span data-stu-id="0a536-161">Network</span></span>|<span data-ttu-id="0a536-162">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="0a536-162">Rendezvous Transport Network parameter.</span></span>|  
   |<span data-ttu-id="0a536-163">服务</span><span class="sxs-lookup"><span data-stu-id="0a536-163">Service</span></span>|<span data-ttu-id="0a536-164">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="0a536-164">Rendezvous Transport Service parameter.</span></span>|  

    <span data-ttu-id="0a536-165">有关属性的详细信息，请参阅[创建发送项目](../core/creating-tibco-rendezvous-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="0a536-165">For more information about the properties, see [Create the send artifacts](../core/creating-tibco-rendezvous-send-handlers.md).</span></span>  

8. <span data-ttu-id="0a536-166">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0a536-166">Click **OK**.</span></span>  

9. <span data-ttu-id="0a536-167">选择**XML 传输**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a536-167">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

10. <span data-ttu-id="0a536-168">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="0a536-168">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

## <a name="step-3-create-a-receive-port"></a><span data-ttu-id="0a536-169">步骤 3：创建接收端口</span><span class="sxs-lookup"><span data-stu-id="0a536-169">Step 3: Create a receive port</span></span>  

1.  <span data-ttu-id="0a536-170">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="0a536-170">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="0a536-171">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...** 显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-171">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  

3.  <span data-ttu-id="0a536-172">输入一个值**名称**字段，例如**TIBCORndOneWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a536-172">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  

## <a name="step-4-create-a-receive-location"></a><span data-ttu-id="0a536-173">步骤 4：创建接收位置</span><span class="sxs-lookup"><span data-stu-id="0a536-173">Step 4: Create a receive location</span></span>  

1.  <span data-ttu-id="0a536-174">创建一个文件夹，文件接收位置监视，例如 C:\Filesource。</span><span class="sxs-lookup"><span data-stu-id="0a536-174">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="0a536-175">右键单击新接收端口，然后单击**新建**，**接收位置...**</span><span class="sxs-lookup"><span data-stu-id="0a536-175">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="0a536-176">若要显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-176">to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="0a536-177">输入一个值**名称**字段，例如**TIBCORndOneWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="0a536-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="0a536-178">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-178">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="0a536-179">输入您为前面创建的文件夹的位置**接收文件夹**属性，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a536-179">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="0a536-180">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a536-180">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="0a536-181">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="0a536-181">Right-click the receive location and click **Enable**.</span></span>  

## <a name="step-5-generate-a-document-instance-from-the-schema"></a><span data-ttu-id="0a536-182">步骤 5：从架构生成文档实例</span><span class="sxs-lookup"><span data-stu-id="0a536-182">Step 5: Generate a document instance from the schema</span></span>  

1.  <span data-ttu-id="0a536-183">在 Visual Studio 中，右键单击 Schema.xsd 在解决方案资源管理器中的，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0a536-183">In Visual Studio,right-click Schema.xsd in Solution Explorer, and click **Properties**.</span></span>  

2.  <span data-ttu-id="0a536-184">在属性窗口中，单击以选中**输出实例文件名**下**常规**部分。</span><span class="sxs-lookup"><span data-stu-id="0a536-184">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  

3.  <span data-ttu-id="0a536-185">单击省略号按钮 （...） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-185">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

4.  <span data-ttu-id="0a536-186">指定的文件夹和输出文件实例名称，例如**C:\instance.xml**然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="0a536-186">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="0a536-187">未指定为 file 接收位置在此处指定的文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="0a536-187">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

5.  <span data-ttu-id="0a536-188">右键单击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**以在指定位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="0a536-188">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

## <a name="step-6-update-the-generated-document-instance"></a><span data-ttu-id="0a536-189">步骤 6：更新生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="0a536-189">Step 6: Update the generated document instance</span></span>  

1.  <span data-ttu-id="0a536-190">在文本编辑器 （记事本的工作原理），打开生成的文档实例，并编辑文档实例，以确保数据将在 TIBCO 系统中生成唯一的记录的内容。</span><span class="sxs-lookup"><span data-stu-id="0a536-190">Open the generated document instance in a text editor(Notepad works), and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="0a536-191">例如，下面的代码显示了数据文件的第一部分：</span><span class="sxs-lookup"><span data-stu-id="0a536-191">For example, the follow code shows the first part of the data file:</span></span>  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  <span data-ttu-id="0a536-192">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="0a536-192">Save the modified document instance.</span></span>  

## <a name="step-7-build-and-deploy-the-project"></a><span data-ttu-id="0a536-193">步骤 7：生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="0a536-193">Step 7: Build and deploy the project</span></span>  

1. <span data-ttu-id="0a536-194">右键单击**OneWaySend**项目在解决方案资源管理器，然后单击**属性**以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="0a536-194">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="0a536-195">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0a536-195">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="0a536-196">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="0a536-196">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="0a536-197">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="0a536-197">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

## <a name="step-8-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="0a536-198">步骤 8：将绑定、 登记和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="0a536-198">Step 8: Bind, enlist, and start the orchestration</span></span>  

1. <span data-ttu-id="0a536-199">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="0a536-199">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="0a536-200">单击**刷新**按钮在 MMC 工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="0a536-200">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="0a536-201">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a536-201">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="0a536-202">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="0a536-202">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="0a536-203">指定适当的值的绑定选项，例如：</span><span class="sxs-lookup"><span data-stu-id="0a536-203">Specify the appropriate values for the binding options, for example:</span></span>  


   |    <span data-ttu-id="0a536-204">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a536-204">**Parameter**</span></span>    |        <span data-ttu-id="0a536-205">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="0a536-205">**Value**</span></span>         |
   |---------------------|--------------------------|
   |        <span data-ttu-id="0a536-206">主机</span><span class="sxs-lookup"><span data-stu-id="0a536-206">Host</span></span>         | <span data-ttu-id="0a536-207">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="0a536-207">BizTalkServerApplication</span></span> |
   |   <span data-ttu-id="0a536-208">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="0a536-208">FileReceivePort</span></span>   |   <span data-ttu-id="0a536-209">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="0a536-209">TIBCORndOneWayFileRP</span></span>   |
   | <span data-ttu-id="0a536-210">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="0a536-210">TibcoRendezvousSend</span></span> |     <span data-ttu-id="0a536-211">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="0a536-211">TIBCORndOneWaySP</span></span>     |


6. <span data-ttu-id="0a536-212">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="0a536-212">Click OK.</span></span>  

7. <span data-ttu-id="0a536-213">右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a536-213">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  

## <a name="step-9-drop-a-document-and-check-the-tibco-system"></a><span data-ttu-id="0a536-214">步骤 9：删除一个文档，并检查 TIBCO 系统</span><span class="sxs-lookup"><span data-stu-id="0a536-214">Step 9: Drop a document, and check the TIBCO system</span></span>

-   <span data-ttu-id="0a536-215">复制到文件之前创建的文档实例接收文件夹应用程序监视器。</span><span class="sxs-lookup"><span data-stu-id="0a536-215">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  

-   <span data-ttu-id="0a536-216">使用 TIBCO web 界面验证记录已创建从 XML 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="0a536-216">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  


<span data-ttu-id="0a536-217">如果成功处理的文档实例，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="0a536-217">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="0a536-218">文件适配器从文件夹中检索该文件，并将其发布到 MessageBox 作为 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="0a536-218">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="0a536-219">业务流程订阅此发布的消息，以便 BizTalk 消息引擎将激活业务流程的实例并将消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="0a536-219">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="0a536-220">业务流程实例处理使用业务流程中指定的逻辑消息，并将消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="0a536-220">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="0a536-221">TIBCO 发送端口订阅此发布消息，因此 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。</span><span class="sxs-lookup"><span data-stu-id="0a536-221">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  

5.  <span data-ttu-id="0a536-222">发送端口将消息传 TIBCO Rendezvous 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="0a536-222">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  

6.  <span data-ttu-id="0a536-223">用于 TIBCO Rendezvous 的 BizTalk 适配器将消息发送到 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="0a536-223">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0a536-224">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a536-224">See Also</span></span>  
 <span data-ttu-id="0a536-225">[教程：使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收数据](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="0a536-225">[Tutorial: Use the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="0a536-226">[教程：使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="0a536-226">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="0a536-227">入门</span><span class="sxs-lookup"><span data-stu-id="0a536-227">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)