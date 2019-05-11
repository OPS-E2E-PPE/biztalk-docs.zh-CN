---
title: 教程：使用 TIBCO Rendezvous 适配器接收 |Microsoft Docs
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
ms.openlocfilehash: ce3d1e3737b56fc8a943d1fdee849a3eb2de5c6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393831"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="16c7c-103">教程：使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收数据</span><span class="sxs-lookup"><span data-stu-id="16c7c-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="16c7c-104">可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器从 TIBCO 系统接收数据。</span><span class="sxs-lookup"><span data-stu-id="16c7c-104">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="16c7c-105">本演练介绍阐释了这一点的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="16c7c-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="16c7c-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="16c7c-106">Prerequisites</span></span>  

<span data-ttu-id="16c7c-107">安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。</span><span class="sxs-lookup"><span data-stu-id="16c7c-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

## <a name="about-the-sample"></a><span data-ttu-id="16c7c-108">有关该示例</span><span class="sxs-lookup"><span data-stu-id="16c7c-108">About the sample</span></span> 
- <span data-ttu-id="16c7c-109">此示例使用用于 TIBCO Rendezvous 的 BizTalk 适配器从 TIBCO 系统接收数据。</span><span class="sxs-lookup"><span data-stu-id="16c7c-109">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="16c7c-110">业务流程处理消息，并使用文件适配器将数据写入为 XML 文件中指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="16c7c-110">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  

- <span data-ttu-id="16c7c-111">此示例中，在设计[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，说明使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器，BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="16c7c-111">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="16c7c-112">该示例假定您知道如何从应用程序处理的 TIBCO 发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="16c7c-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  

- <span data-ttu-id="16c7c-113">该示例的默认位置是`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`，包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="16c7c-113">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`, and includes the following files:</span></span> 

    |<span data-ttu-id="16c7c-114">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="16c7c-114">**Runtime Project Filename**</span></span>|<span data-ttu-id="16c7c-115">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="16c7c-115">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="16c7c-116">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="16c7c-116">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="16c7c-117">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="16c7c-117">OneWayReceive.sln</span></span>|<span data-ttu-id="16c7c-118">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="16c7c-118">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="16c7c-119">PureMessage.xsd，</span><span class="sxs-lookup"><span data-stu-id="16c7c-119">PureMessage.xsd,</span></span>|<span data-ttu-id="16c7c-120">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="16c7c-120">Schema file for the application.</span></span>|  
    |<span data-ttu-id="16c7c-121">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="16c7c-121">TIBCORvOWR.odx</span></span>|<span data-ttu-id="16c7c-122">使用应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="16c7c-122">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="16c7c-123">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="16c7c-123">TIBCORv.snk</span></span>|<span data-ttu-id="16c7c-124">强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="16c7c-124">The strong naming key file.</span></span>|  


## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="16c7c-125">第 1 步：将适配器添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="16c7c-125">Step 1: Add the adapter to BizTalk Administration</span></span>

1.  <span data-ttu-id="16c7c-126">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-126">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3.  <span data-ttu-id="16c7c-127">右键单击**适配器**，然后指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="16c7c-127">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="16c7c-128">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-128">to display the **Adapter Properties** dialog.</span></span>  

4.  <span data-ttu-id="16c7c-129">输入一个值**名称**字段，例如**TIBCO Rendezvous**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-129">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  

5.  <span data-ttu-id="16c7c-130">选择**tibco （) Rendezvous(r)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-130">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

## <a name="step-2-create-a-receive-port"></a><span data-ttu-id="16c7c-131">第 2 步：创建接收端口</span><span class="sxs-lookup"><span data-stu-id="16c7c-131">Step 2: Create a Receive Port</span></span>  

1.  <span data-ttu-id="16c7c-132">在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-132">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="16c7c-133">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...** 以显示**接收端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-133">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  

3.  <span data-ttu-id="16c7c-134">输入一个值**名称**字段，例如**TIBCORvOneWayRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-134">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  

## <a name="step-3-create-a-receive-location"></a><span data-ttu-id="16c7c-135">步骤 3：创建接收位置</span><span class="sxs-lookup"><span data-stu-id="16c7c-135">Step 3: Create a Receive Location</span></span>  

1. <span data-ttu-id="16c7c-136">右键单击新接收端口，然后单击**新建**，**接收位置...**</span><span class="sxs-lookup"><span data-stu-id="16c7c-136">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="16c7c-137">若要显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-137">to display the **Receive Location Properties** dialog.</span></span>  

2. <span data-ttu-id="16c7c-138">输入一个值**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="16c7c-138">Enter a value for the **Name** field.</span></span> <span data-ttu-id="16c7c-139">例如，输入**TIBCORvOneWayRL**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-139">For example, enter **TIBCORvOneWayRL**.</span></span>  

3. <span data-ttu-id="16c7c-140">从中可用的适配器列表中选择 TIBCO Rendezvous 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-140">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="16c7c-141">此值是在中创建 TIBCO 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="16c7c-141">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

4. <span data-ttu-id="16c7c-142">输入一个值**RendezvousSubjectName**下**AdapterRequiredProperties**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-142">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  

5. <span data-ttu-id="16c7c-143">输入值**认证的侦听程序属性**:</span><span class="sxs-lookup"><span data-stu-id="16c7c-143">Enter values for the **Certified Listener Properties**:</span></span>  


   |   <span data-ttu-id="16c7c-144">**属性**</span><span class="sxs-lookup"><span data-stu-id="16c7c-144">**Property**</span></span>   |                                                                         <span data-ttu-id="16c7c-145">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="16c7c-145">**Value**</span></span>                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="16c7c-146">分类帐文件名称</span><span class="sxs-lookup"><span data-stu-id="16c7c-146">Ledger file name</span></span> |                                             <span data-ttu-id="16c7c-147">要用于持久性认证的消息传递的分类帐文件名称。</span><span class="sxs-lookup"><span data-stu-id="16c7c-147">Ledger file name to use for persistent certified message delivery.</span></span>                                             |
   |  <span data-ttu-id="16c7c-148">可重复使用名称</span><span class="sxs-lookup"><span data-stu-id="16c7c-148">Reusable name</span></span>   | <span data-ttu-id="16c7c-149">若要使用认证的消息传递的可重用通信名称。</span><span class="sxs-lookup"><span data-stu-id="16c7c-149">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="16c7c-150">名称必须是唯一的而在网络上的所有认证的消息通信名称。</span><span class="sxs-lookup"><span data-stu-id="16c7c-150">The name must be unique among all certified message correspondent names on the network.</span></span> |


6. <span data-ttu-id="16c7c-151">输入值**凭据**:</span><span class="sxs-lookup"><span data-stu-id="16c7c-151">Enter values for the **Credentials**:</span></span>  


   | <span data-ttu-id="16c7c-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="16c7c-152">**Property**</span></span> |                   <span data-ttu-id="16c7c-153">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="16c7c-153">**Value**</span></span>                    |
   |--------------|------------------------------------------------|
   |   <span data-ttu-id="16c7c-154">Password</span><span class="sxs-lookup"><span data-stu-id="16c7c-154">Password</span></span>   | <span data-ttu-id="16c7c-155">TIBCO Rendezvous 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="16c7c-155">The password for the TIBCO Rendezvous server.</span></span>  |
   |  <span data-ttu-id="16c7c-156">“用户名”</span><span class="sxs-lookup"><span data-stu-id="16c7c-156">User name</span></span>   | <span data-ttu-id="16c7c-157">TIBCO Rendezvous 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="16c7c-157">The user name for the TIBCO Rendezvous server.</span></span> |


7. <span data-ttu-id="16c7c-158">输入值**RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="16c7c-158">Enter values for the **RendezvousTransport**:</span></span>  

   |<span data-ttu-id="16c7c-159">**属性**</span><span class="sxs-lookup"><span data-stu-id="16c7c-159">**Property**</span></span>|<span data-ttu-id="16c7c-160">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="16c7c-160">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="16c7c-161">后台程序</span><span class="sxs-lookup"><span data-stu-id="16c7c-161">Daemon</span></span>|<span data-ttu-id="16c7c-162">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="16c7c-162">Rendezvous Transport Daemon parameter.</span></span>|  
   |<span data-ttu-id="16c7c-163">网络</span><span class="sxs-lookup"><span data-stu-id="16c7c-163">Network</span></span>|<span data-ttu-id="16c7c-164">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="16c7c-164">Rendezvous Transport Network parameter.</span></span>|  
   |<span data-ttu-id="16c7c-165">服务</span><span class="sxs-lookup"><span data-stu-id="16c7c-165">Service</span></span>|<span data-ttu-id="16c7c-166">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="16c7c-166">Rendezvous Transport Service parameter.</span></span>|  

    <span data-ttu-id="16c7c-167">有关属性的详细信息，请参阅[创建接收项目](../core/creating-tibco-rendezvous-receive-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="16c7c-167">For more information about the properties, see [Create Receive artifacts](../core/creating-tibco-rendezvous-receive-handlers.md).</span></span>  

8. <span data-ttu-id="16c7c-168">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="16c7c-168">Click **OK**.</span></span>  

9. <span data-ttu-id="16c7c-169">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-169">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

10. <span data-ttu-id="16c7c-170">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-170">Right-click the receive location and click **Enable**.</span></span>  

## <a name="step-4-create-a-one-way-send-port"></a><span data-ttu-id="16c7c-171">步骤 4：创建一个单向发送端口</span><span class="sxs-lookup"><span data-stu-id="16c7c-171">Step 4: Create a one-way send port</span></span>  

1. <span data-ttu-id="16c7c-172">创建发送端口，例如 C:\FilesOut 要使用的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="16c7c-172">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  

2. <span data-ttu-id="16c7c-173">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-173">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

3. <span data-ttu-id="16c7c-174">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口...**</span><span class="sxs-lookup"><span data-stu-id="16c7c-174">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="16c7c-175">若要显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-175">to display the **Send Port Properties** dialog.</span></span>  

4. <span data-ttu-id="16c7c-176">输入一个值**名称**字段，例如**TIBCORvOneWayFileSP**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-176">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  

5. <span data-ttu-id="16c7c-177">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-177">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

6. <span data-ttu-id="16c7c-178">有关**目标文件夹**属性中，输入前面创建的文件夹的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-178">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  

7. <span data-ttu-id="16c7c-179">选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-179">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="16c7c-180">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="16c7c-180">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

## <a name="step-5-build-and-deploy-the-project"></a><span data-ttu-id="16c7c-181">步骤 5：生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="16c7c-181">Step 5: Build and deploy the project</span></span>  

1. <span data-ttu-id="16c7c-182">右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**属性**以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="16c7c-182">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="16c7c-183">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="16c7c-183">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="16c7c-184">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="16c7c-184">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  

4. <span data-ttu-id="16c7c-185">右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="16c7c-185">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

## <a name="step-6-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="16c7c-186">步骤 6：绑定、 登记，并启动业务流程</span><span class="sxs-lookup"><span data-stu-id="16c7c-186">Step 6: Bind, Enlist, and start the orchestration</span></span>  

1. <span data-ttu-id="16c7c-187">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="16c7c-187">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="16c7c-188">单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="16c7c-188">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="16c7c-189">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="16c7c-189">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="16c7c-190">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="16c7c-190">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="16c7c-191">指定适当的值的绑定选项，例如：</span><span class="sxs-lookup"><span data-stu-id="16c7c-191">Specify the appropriate values for the binding options, for example:</span></span>  


   | <span data-ttu-id="16c7c-192">**参数**</span><span class="sxs-lookup"><span data-stu-id="16c7c-192">**Parameter**</span></span> |        <span data-ttu-id="16c7c-193">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="16c7c-193">**Value**</span></span>         |
   |---------------|--------------------------|
   |     <span data-ttu-id="16c7c-194">主机</span><span class="sxs-lookup"><span data-stu-id="16c7c-194">Host</span></span>      | <span data-ttu-id="16c7c-195">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="16c7c-195">BizTalkServerApplication</span></span> |
   |   <span data-ttu-id="16c7c-196">SendPort</span><span class="sxs-lookup"><span data-stu-id="16c7c-196">SendPort</span></span>    |   <span data-ttu-id="16c7c-197">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="16c7c-197">TIBCORvOneWayFileSP</span></span>    |
   |  <span data-ttu-id="16c7c-198">ReceivePort</span><span class="sxs-lookup"><span data-stu-id="16c7c-198">ReceivePort</span></span>  |     <span data-ttu-id="16c7c-199">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="16c7c-199">TIBCORvOneWayRP</span></span>      |


6. <span data-ttu-id="16c7c-200">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="16c7c-200">Click **OK**.</span></span>  

7. <span data-ttu-id="16c7c-201">右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="16c7c-201">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  

## <a name="step-7-confirm-the-application-receives-a-message"></a><span data-ttu-id="16c7c-202">步骤 7：确认应用程序收到一条消息</span><span class="sxs-lookup"><span data-stu-id="16c7c-202">Step 7: Confirm the application receives a message</span></span>  

- <span data-ttu-id="16c7c-203">打开文件发送端口配置为发送到计算机并验证已生成输出文档的文件夹。</span><span class="sxs-lookup"><span data-stu-id="16c7c-203">Open the folder that the file send port is configured to send to, and verify that an output document was generated.</span></span>  

  <span data-ttu-id="16c7c-204">如果成功处理的文档实例，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="16c7c-204">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="16c7c-205">TIBCO Rendezvous 适配器从 TIBCO 系统接收消息，并将其发布到 MessageBox 作为 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="16c7c-205">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="16c7c-206">业务流程订阅此发布的消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="16c7c-206">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="16c7c-207">业务流程实例将消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="16c7c-207">The orchestration instance publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="16c7c-208">File 发送端口订阅此消息，以便 BizTalk 向文件适配器发送的消息。</span><span class="sxs-lookup"><span data-stu-id="16c7c-208">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  

5.  <span data-ttu-id="16c7c-209">文件适配器写入包含结果集限于指定的输出文件夹的消息。</span><span class="sxs-lookup"><span data-stu-id="16c7c-209">The File adapter writes the message containing the result set to the designated output folder.</span></span>  

## <a name="see-also"></a><span data-ttu-id="16c7c-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="16c7c-210">See Also</span></span>  
 <span data-ttu-id="16c7c-211">[教程：使用用于 TIBCO Rendezvous 的 BizTalk 适配器发送数据](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="16c7c-211">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="16c7c-212">[教程：使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="16c7c-212">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="16c7c-213">入门</span><span class="sxs-lookup"><span data-stu-id="16c7c-213">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)