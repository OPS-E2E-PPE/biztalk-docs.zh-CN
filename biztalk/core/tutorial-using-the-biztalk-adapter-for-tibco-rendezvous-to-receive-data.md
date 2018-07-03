---
title: 教程： 使用 TIBCO Rendezvous 适配器接收 |Microsoft Docs
description: 若要使用 BizTalk Server 中的 TIBCO Rendezvous 的 BizTalk 适配器从 TIBCO 系统接收数据的分步指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 430c559d689ba9b56c28d81d37a1c87f91e14f2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985286"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="dfe39-103">教程：使用适用于 TIBCO Rendezvous 的 BizTalk 适配器来接收数据</span><span class="sxs-lookup"><span data-stu-id="dfe39-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="dfe39-104">您可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收来自 TIBCO 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="dfe39-104">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="dfe39-105">本演练描述了对此进行说明的一个 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="dfe39-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="dfe39-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="dfe39-106">Prerequisites</span></span>  

<span data-ttu-id="dfe39-107">为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dfe39-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

## <a name="about-the-sample"></a><span data-ttu-id="dfe39-108">有关该示例</span><span class="sxs-lookup"><span data-stu-id="dfe39-108">About the sample</span></span> 
- <span data-ttu-id="dfe39-109">本示例使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收来自 TIBCO 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="dfe39-109">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="dfe39-110">业务流程处理消息并使用文件适配器将数据编写为指定文件夹中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="dfe39-110">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  

- <span data-ttu-id="dfe39-111">本示例在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中设计，它使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器以及 BizTalk 业务流程来说明基本功能。</span><span class="sxs-lookup"><span data-stu-id="dfe39-111">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="dfe39-112">本示例假定您知道如何发送来自 TIBCO 的消息以供应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="dfe39-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  

- <span data-ttu-id="dfe39-113">该示例的默认位置是`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`，包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="dfe39-113">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`, and includes the following files:</span></span> 

    |<span data-ttu-id="dfe39-114">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="dfe39-114">**Runtime Project Filename**</span></span>|<span data-ttu-id="dfe39-115">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="dfe39-115">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="dfe39-116">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="dfe39-116">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="dfe39-117">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="dfe39-117">OneWayReceive.sln</span></span>|<span data-ttu-id="dfe39-118">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="dfe39-118">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="dfe39-119">PureMessage.xsd，</span><span class="sxs-lookup"><span data-stu-id="dfe39-119">PureMessage.xsd,</span></span>|<span data-ttu-id="dfe39-120">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="dfe39-120">Schema file for the application.</span></span>|  
    |<span data-ttu-id="dfe39-121">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="dfe39-121">TIBCORvOWR.odx</span></span>|<span data-ttu-id="dfe39-122">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="dfe39-122">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="dfe39-123">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="dfe39-123">TIBCORv.snk</span></span>|<span data-ttu-id="dfe39-124">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="dfe39-124">The strong naming key file.</span></span>|  


## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="dfe39-125">步骤 1： 将适配器添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="dfe39-125">Step 1: Add the adapter to BizTalk Administration</span></span>

1.  <span data-ttu-id="dfe39-126">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-126">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3.  <span data-ttu-id="dfe39-127">右键单击**适配器**，然后指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="dfe39-127">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="dfe39-128">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-128">to display the **Adapter Properties** dialog.</span></span>  

4.  <span data-ttu-id="dfe39-129">输入一个值**名称**字段，例如**TIBCO Rendezvous**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-129">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  

5.  <span data-ttu-id="dfe39-130">选择**tibco （) Rendezvous(r)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-130">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

## <a name="step-2-create-a-receive-port"></a><span data-ttu-id="dfe39-131">步骤 2： 创建接收端口</span><span class="sxs-lookup"><span data-stu-id="dfe39-131">Step 2: Create a Receive Port</span></span>  

1.  <span data-ttu-id="dfe39-132">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-132">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="dfe39-133">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...** 以显示**接收端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-133">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  

3.  <span data-ttu-id="dfe39-134">输入一个值**名称**字段，例如**TIBCORvOneWayRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-134">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  

## <a name="step-3-create-a-receive-location"></a><span data-ttu-id="dfe39-135">步骤 3： 创建接收位置</span><span class="sxs-lookup"><span data-stu-id="dfe39-135">Step 3: Create a Receive Location</span></span>  

1. <span data-ttu-id="dfe39-136">右键单击新接收端口，然后单击**新建**，**接收位置...**</span><span class="sxs-lookup"><span data-stu-id="dfe39-136">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="dfe39-137">若要显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-137">to display the **Receive Location Properties** dialog.</span></span>  

2. <span data-ttu-id="dfe39-138">输入一个值**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="dfe39-138">Enter a value for the **Name** field.</span></span> <span data-ttu-id="dfe39-139">例如，输入**TIBCORvOneWayRL**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-139">For example, enter **TIBCORvOneWayRL**.</span></span>  

3. <span data-ttu-id="dfe39-140">从中可用的适配器列表中选择 TIBCO Rendezvous 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-140">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="dfe39-141">该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO 适配器时指定的名称。</span><span class="sxs-lookup"><span data-stu-id="dfe39-141">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

4. <span data-ttu-id="dfe39-142">输入一个值**RendezvousSubjectName**下**AdapterRequiredProperties**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-142">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  

5. <span data-ttu-id="dfe39-143">输入值**认证的侦听程序属性**:</span><span class="sxs-lookup"><span data-stu-id="dfe39-143">Enter values for the **Certified Listener Properties**:</span></span>  


   |   <span data-ttu-id="dfe39-144">**属性**</span><span class="sxs-lookup"><span data-stu-id="dfe39-144">**Property**</span></span>   |                                                                         <span data-ttu-id="dfe39-145">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="dfe39-145">**Value**</span></span>                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="dfe39-146">分类帐文件名称</span><span class="sxs-lookup"><span data-stu-id="dfe39-146">Ledger file name</span></span> |                                             <span data-ttu-id="dfe39-147">用于持久性认证消息传递的分类帐文件名。</span><span class="sxs-lookup"><span data-stu-id="dfe39-147">Ledger file name to use for persistent certified message delivery.</span></span>                                             |
   |  <span data-ttu-id="dfe39-148">可重复使用的名称</span><span class="sxs-lookup"><span data-stu-id="dfe39-148">Reusable name</span></span>   | <span data-ttu-id="dfe39-149">用于已验证消息传递的可重用的通信名称。</span><span class="sxs-lookup"><span data-stu-id="dfe39-149">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="dfe39-150">在网络上所有已验证消息通信名称中，该名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dfe39-150">The name must be unique among all certified message correspondent names on the network.</span></span> |


6. <span data-ttu-id="dfe39-151">输入值**凭据**:</span><span class="sxs-lookup"><span data-stu-id="dfe39-151">Enter values for the **Credentials**:</span></span>  


   | <span data-ttu-id="dfe39-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="dfe39-152">**Property**</span></span> |                   <span data-ttu-id="dfe39-153">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="dfe39-153">**Value**</span></span>                    |
   |--------------|------------------------------------------------|
   |   <span data-ttu-id="dfe39-154">Password</span><span class="sxs-lookup"><span data-stu-id="dfe39-154">Password</span></span>   | <span data-ttu-id="dfe39-155">TIBCO Rendezvous 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="dfe39-155">The password for the TIBCO Rendezvous server.</span></span>  |
   |  <span data-ttu-id="dfe39-156">“用户名”</span><span class="sxs-lookup"><span data-stu-id="dfe39-156">User name</span></span>   | <span data-ttu-id="dfe39-157">TIBCO Rendezvous 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="dfe39-157">The user name for the TIBCO Rendezvous server.</span></span> |


7. <span data-ttu-id="dfe39-158">输入值**RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="dfe39-158">Enter values for the **RendezvousTransport**:</span></span>  

   |<span data-ttu-id="dfe39-159">**属性**</span><span class="sxs-lookup"><span data-stu-id="dfe39-159">**Property**</span></span>|<span data-ttu-id="dfe39-160">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="dfe39-160">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="dfe39-161">后台程序</span><span class="sxs-lookup"><span data-stu-id="dfe39-161">Daemon</span></span>|<span data-ttu-id="dfe39-162">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="dfe39-162">Rendezvous Transport Daemon parameter.</span></span>|  
   |<span data-ttu-id="dfe39-163">网络</span><span class="sxs-lookup"><span data-stu-id="dfe39-163">Network</span></span>|<span data-ttu-id="dfe39-164">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="dfe39-164">Rendezvous Transport Network parameter.</span></span>|  
   |<span data-ttu-id="dfe39-165">服务</span><span class="sxs-lookup"><span data-stu-id="dfe39-165">Service</span></span>|<span data-ttu-id="dfe39-166">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="dfe39-166">Rendezvous Transport Service parameter.</span></span>|  

    <span data-ttu-id="dfe39-167">有关属性的详细信息，请参阅[创建接收项目](../core/creating-tibco-rendezvous-receive-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="dfe39-167">For more information about the properties, see [Create Receive artifacts](../core/creating-tibco-rendezvous-receive-handlers.md).</span></span>  

8. <span data-ttu-id="dfe39-168">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="dfe39-168">Click **OK**.</span></span>  

9. <span data-ttu-id="dfe39-169">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-169">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

10. <span data-ttu-id="dfe39-170">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-170">Right-click the receive location and click **Enable**.</span></span>  

## <a name="step-4-create-a-one-way-send-port"></a><span data-ttu-id="dfe39-171">步骤 4： 创建单向发送端口</span><span class="sxs-lookup"><span data-stu-id="dfe39-171">Step 4: Create a one-way send port</span></span>  

1. <span data-ttu-id="dfe39-172">创建发送端口要使用的目标文件夹，例如 C:\FilesOut。</span><span class="sxs-lookup"><span data-stu-id="dfe39-172">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  

2. <span data-ttu-id="dfe39-173">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-173">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

3. <span data-ttu-id="dfe39-174">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口...**</span><span class="sxs-lookup"><span data-stu-id="dfe39-174">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="dfe39-175">若要显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-175">to display the **Send Port Properties** dialog.</span></span>  

4. <span data-ttu-id="dfe39-176">输入一个值**名称**字段，例如**TIBCORvOneWayFileSP**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-176">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  

5. <span data-ttu-id="dfe39-177">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-177">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

6. <span data-ttu-id="dfe39-178">有关**目标文件夹**属性中，输入前面创建的文件夹的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-178">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  

7. <span data-ttu-id="dfe39-179">选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-179">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="dfe39-180">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="dfe39-180">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

## <a name="step-5-build-and-deploy-the-project"></a><span data-ttu-id="dfe39-181">步骤 5： 生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="dfe39-181">Step 5: Build and deploy the project</span></span>  

1. <span data-ttu-id="dfe39-182">右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**属性**以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="dfe39-182">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="dfe39-183">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="dfe39-183">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="dfe39-184">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="dfe39-184">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  

4. <span data-ttu-id="dfe39-185">右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="dfe39-185">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

## <a name="step-6-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="dfe39-186">步骤 6： 将绑定、 登记，并启动业务流程</span><span class="sxs-lookup"><span data-stu-id="dfe39-186">Step 6: Bind, Enlist, and start the orchestration</span></span>  

1. <span data-ttu-id="dfe39-187">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="dfe39-187">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="dfe39-188">单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="dfe39-188">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="dfe39-189">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="dfe39-189">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="dfe39-190">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="dfe39-190">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="dfe39-191">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="dfe39-191">Specify the appropriate values for the binding options, for example:</span></span>  


   | <span data-ttu-id="dfe39-192">**参数**</span><span class="sxs-lookup"><span data-stu-id="dfe39-192">**Parameter**</span></span> |        <span data-ttu-id="dfe39-193">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="dfe39-193">**Value**</span></span>         |
   |---------------|--------------------------|
   |     <span data-ttu-id="dfe39-194">主机</span><span class="sxs-lookup"><span data-stu-id="dfe39-194">Host</span></span>      | <span data-ttu-id="dfe39-195">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="dfe39-195">BizTalkServerApplication</span></span> |
   |   <span data-ttu-id="dfe39-196">发送端口</span><span class="sxs-lookup"><span data-stu-id="dfe39-196">SendPort</span></span>    |   <span data-ttu-id="dfe39-197">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="dfe39-197">TIBCORvOneWayFileSP</span></span>    |
   |  <span data-ttu-id="dfe39-198">接收端口</span><span class="sxs-lookup"><span data-stu-id="dfe39-198">ReceivePort</span></span>  |     <span data-ttu-id="dfe39-199">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="dfe39-199">TIBCORvOneWayRP</span></span>      |


6. <span data-ttu-id="dfe39-200">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="dfe39-200">Click **OK**.</span></span>  

7. <span data-ttu-id="dfe39-201">右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="dfe39-201">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  

## <a name="step-7-confirm-the-application-receives-a-message"></a><span data-ttu-id="dfe39-202">步骤 7： 确认应用程序收到一条消息</span><span class="sxs-lookup"><span data-stu-id="dfe39-202">Step 7: Confirm the application receives a message</span></span>  

- <span data-ttu-id="dfe39-203">打开文件发送端口配置为发送到计算机并验证已生成输出文档的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dfe39-203">Open the folder that the file send port is configured to send to, and verify that an output document was generated.</span></span>  

  <span data-ttu-id="dfe39-204">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="dfe39-204">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="dfe39-205">TIBCO Rendezvous 适配器接收来自 TIBCO 系统的消息并将其作为 BizTalk 消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="dfe39-205">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="dfe39-206">业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="dfe39-206">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="dfe39-207">业务流程实例将此消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="dfe39-207">The orchestration instance publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="dfe39-208">文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。</span><span class="sxs-lookup"><span data-stu-id="dfe39-208">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  

5.  <span data-ttu-id="dfe39-209">文件适配器将包含结果集的消息写入到指定的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="dfe39-209">The File adapter writes the message containing the result set to the designated output folder.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dfe39-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfe39-210">See Also</span></span>  
 <span data-ttu-id="dfe39-211">[教程： 使用用于 TIBCO Rendezvous 的 BizTalk 适配器发送数据](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="dfe39-211">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="dfe39-212">[教程： 使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="dfe39-212">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="dfe39-213">入门</span><span class="sxs-lookup"><span data-stu-id="dfe39-213">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)