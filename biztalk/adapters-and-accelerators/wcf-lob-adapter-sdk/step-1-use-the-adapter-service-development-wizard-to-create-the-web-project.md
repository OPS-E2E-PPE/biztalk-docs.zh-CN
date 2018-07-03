---
title: 步骤 1： 使用适配器服务开发向导创建 Web 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fb8737f51f9e0b6afe3d61218f69015c1cd5d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984030"
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a><span data-ttu-id="d8848-102">步骤 1： 使用适配器服务开发向导创建 Web 项目</span><span class="sxs-lookup"><span data-stu-id="d8848-102">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>
<span data-ttu-id="d8848-103">![步骤 1，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="d8848-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="d8848-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="d8848-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="d8848-105">在此步骤中，创建使用 Visual Studio 的项目和[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8848-105">In this step, you create a project using Visual Studio and the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="d8848-106">[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]收集有关适配器、 操作和终结点配置的信息，并生成然后部署到 IIS 的 Web 项目。</span><span class="sxs-lookup"><span data-stu-id="d8848-106">The [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] collects information about the adapter, operations, and endpoint configurations, and generates a Web project that can then be deployed to IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d8848-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="d8848-107">Prerequisites</span></span>  
 <span data-ttu-id="d8848-108">必须生成并部署 Echo 示例中所述[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)之前开始学习本教程。</span><span class="sxs-lookup"><span data-stu-id="d8848-108">You must build and deploy the Echo sample described in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) before beginning this tutorial.</span></span>  
  
### <a name="to-start-the-adapter-service-development-wizard"></a><span data-ttu-id="d8848-109">若要启动适配器服务开发向导</span><span class="sxs-lookup"><span data-stu-id="d8848-109">To start the Adapter Service Development Wizard</span></span>  
  
1.  <span data-ttu-id="d8848-110">启动 Visual Studio，然后在**文件**菜单，依次指向**新建**，然后单击**网站**。</span><span class="sxs-lookup"><span data-stu-id="d8848-110">Start Visual Studio and then on the **File** menu, point to **New**, and then click **Web Site**.</span></span>  
  
2.  <span data-ttu-id="d8848-111">在中**新的 Web 站点**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8848-111">In the **New Web Site** dialog box, perform the following actions:</span></span>  
  
    |<span data-ttu-id="d8848-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d8848-112">Use this</span></span>|<span data-ttu-id="d8848-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d8848-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d8848-114">**语言**</span><span class="sxs-lookup"><span data-stu-id="d8848-114">**Language**</span></span>|<span data-ttu-id="d8848-115">单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="d8848-115">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="d8848-116">**模板**</span><span class="sxs-lookup"><span data-stu-id="d8848-116">**Templates**</span></span>|<span data-ttu-id="d8848-117">单击**WCF 适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="d8848-117">Click **WCF Adapter Service**.</span></span>|  
    |<span data-ttu-id="d8848-118">**位置**</span><span class="sxs-lookup"><span data-stu-id="d8848-118">**Location**</span></span>|<span data-ttu-id="d8848-119">选择**文件系统**，然后键入**C:\Tutorials\EchoWeb**作为路径。</span><span class="sxs-lookup"><span data-stu-id="d8848-119">Select **File System**, and then type **C:\Tutorials\EchoWeb** as the path.</span></span>|  
  
3.  <span data-ttu-id="d8848-120">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d8848-120">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="d8848-121">上**欢迎页**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d8848-121">On the **Welcome page**, click **Next**.</span></span>  
  
### <a name="to-select-the-adapter-and-uri"></a><span data-ttu-id="d8848-122">若要选择的适配器和 URI</span><span class="sxs-lookup"><span data-stu-id="d8848-122">To select the adapter and URI</span></span>  
  
1.  <span data-ttu-id="d8848-123">上**选择操作来生成服务协定**页上，选择**echoAdapterBindingV2**从**选择绑定**下拉列表，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d8848-123">On the **Choose the operations to generate a service contract** page, select **echoAdapterBindingV2** from the **Select a binding** drop-down list, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="d8848-124">上**安全**选项卡**配置适配器**对话框中，将**客户端凭据类型**到**用户名**，然后设置**用户名凭据**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d8848-124">On the **Security** tab of the **Configure Adapter** dialog box, set **Client Credential type** to **Username**, and then set the **User name credentials** as follows:</span></span>  
  
    |<span data-ttu-id="d8848-125">“属性”</span><span class="sxs-lookup"><span data-stu-id="d8848-125">Property</span></span>|<span data-ttu-id="d8848-126">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d8848-126">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d8848-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="d8848-127">**User name**</span></span>|<span data-ttu-id="d8848-128">username</span><span class="sxs-lookup"><span data-stu-id="d8848-128">username</span></span>|  
    |<span data-ttu-id="d8848-129">**密码**</span><span class="sxs-lookup"><span data-stu-id="d8848-129">**Password**</span></span>|<span data-ttu-id="d8848-130">password</span><span class="sxs-lookup"><span data-stu-id="d8848-130">password</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d8848-131">用户名和密码在此处输入只能使用在向导中，执行步骤时连接到该适配器，而不会保留在向导完成后。</span><span class="sxs-lookup"><span data-stu-id="d8848-131">The user name and password entered here are only used to connect to the adapter while performing the steps in the wizard, and are not preserved after the wizard completes.</span></span>  
  
3.  <span data-ttu-id="d8848-132">单击**URI 属性**选项卡，然后按如下所示设置属性：</span><span class="sxs-lookup"><span data-stu-id="d8848-132">Click the **URI Properties** tab, and then set the properties as follows:</span></span>  
  
    |<span data-ttu-id="d8848-133">“属性”</span><span class="sxs-lookup"><span data-stu-id="d8848-133">Property</span></span>|<span data-ttu-id="d8848-134">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d8848-134">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d8848-135">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="d8848-135">**Application**</span></span>|<span data-ttu-id="d8848-136">LobApplication</span><span class="sxs-lookup"><span data-stu-id="d8848-136">LobApplication</span></span>|  
    |<span data-ttu-id="d8848-137">**EnableAuthentication**</span><span class="sxs-lookup"><span data-stu-id="d8848-137">**EnableAuthentication**</span></span>|<span data-ttu-id="d8848-138">True</span><span class="sxs-lookup"><span data-stu-id="d8848-138">True</span></span>|  
    |<span data-ttu-id="d8848-139">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d8848-139">**Hostname**</span></span>|<span data-ttu-id="d8848-140">lobhostname</span><span class="sxs-lookup"><span data-stu-id="d8848-140">lobhostname</span></span>|  
    |<span data-ttu-id="d8848-141">**EchoInUpperCase**</span><span class="sxs-lookup"><span data-stu-id="d8848-141">**EchoInUpperCase**</span></span>|<span data-ttu-id="d8848-142">False</span><span class="sxs-lookup"><span data-stu-id="d8848-142">False</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d8848-143">此处选择的 URI 属性将用于创建\<**客户端**\>\<**终结点**\> web.config 文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="d8848-143">The URI properties selected here will be used to create the \<**client**\>\<**endpoint**\> elements in the web.config file.</span></span>  
  
4.  <span data-ttu-id="d8848-144">单击**绑定属性**选项卡。请注意默认值，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8848-144">Click the **Binding Properties** tab. Note the default values, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8848-145">绑定值将用于生成\<**绑定**\>\<**echoAdapterBindingV2** \> web.config 文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="d8848-145">The binding values will be used to generate the \<**bindings**\>\<**echoAdapterBindingV2**\> elements in the web.config file.</span></span>  
  
### <a name="to-select-the-contract-and-operations"></a><span data-ttu-id="d8848-146">若要选择约定和操作</span><span class="sxs-lookup"><span data-stu-id="d8848-146">To select the contract and operations</span></span>  
  
1.  <span data-ttu-id="d8848-147">上**选择操作来生成服务协定**页上，单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="d8848-147">On the **Choose the operations to generate a service contract** page, click **Connect**.</span></span>  
  
2.  <span data-ttu-id="d8848-148">在中**选择一个类别**树中，选择**主类别**。</span><span class="sxs-lookup"><span data-stu-id="d8848-148">In the **Select a category** tree, select **Main Category**.</span></span> <span data-ttu-id="d8848-149">这将填充**可用类别和操作**列表。</span><span class="sxs-lookup"><span data-stu-id="d8848-149">This populates the **Available categories and operations** list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8848-150">您还可以输入搜索词**类别中的搜索**字段以查找包含搜索词的任何操作。</span><span class="sxs-lookup"><span data-stu-id="d8848-150">You can also enter a search term in the **Search in category** field to find any operations that contain the search term.</span></span>  
  
3.  <span data-ttu-id="d8848-151">在中**可用类别和操作**列表中，选择**EchoGreetings**然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d8848-151">In the **Available categories and operations** list, select **EchoGreetings** and click **Add**.</span></span> <span data-ttu-id="d8848-152">此选项会移动到的 EchoGreetings 操作**添加的类别和操作**列表。</span><span class="sxs-lookup"><span data-stu-id="d8848-152">This moves the EchoGreetings operation to the **Added categories and operations** list.</span></span> <span data-ttu-id="d8848-153">此处选择的操作将向客户端应用程序可以通过由向导生成的客户端代理代码公开。</span><span class="sxs-lookup"><span data-stu-id="d8848-153">The operations selected here will be exposed to client applications through the client proxy code generated by the wizard.</span></span>  
  
     <span data-ttu-id="d8848-154">![选择约定和操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span><span class="sxs-lookup"><span data-stu-id="d8848-154">![Select Contract and Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")</span></span>  
  
4.  <span data-ttu-id="d8848-155">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="d8848-155">Click **Next**.</span></span>  
  
### <a name="to-configure-service-and-endpoint-behavior"></a><span data-ttu-id="d8848-156">若要配置服务和终结点行为</span><span class="sxs-lookup"><span data-stu-id="d8848-156">To configure service and endpoint behavior</span></span>  
  
1.  <span data-ttu-id="d8848-157">上**配置服务和终结点行为**页上，输入以下值：**服务行为配置**:</span><span class="sxs-lookup"><span data-stu-id="d8848-157">On the **Configure service and endpoint behaviors** page, enter the following values for **Service Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="d8848-158">“属性”</span><span class="sxs-lookup"><span data-stu-id="d8848-158">Property</span></span>|<span data-ttu-id="d8848-159">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d8848-159">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d8848-160">**EnableMetadataExchange**</span><span class="sxs-lookup"><span data-stu-id="d8848-160">**EnableMetadataExchange**</span></span>|<span data-ttu-id="d8848-161">True</span><span class="sxs-lookup"><span data-stu-id="d8848-161">True</span></span>|  
    |<span data-ttu-id="d8848-162">**IncludeExceptionDetailsinFault**</span><span class="sxs-lookup"><span data-stu-id="d8848-162">**IncludeExceptionDetailsinFault**</span></span>|<span data-ttu-id="d8848-163">True</span><span class="sxs-lookup"><span data-stu-id="d8848-163">True</span></span>|  
    |<span data-ttu-id="d8848-164">**名称**</span><span class="sxs-lookup"><span data-stu-id="d8848-164">**Name**</span></span>|<span data-ttu-id="d8848-165">customServiceBehavior</span><span class="sxs-lookup"><span data-stu-id="d8848-165">customServiceBehavior</span></span>|  
    |<span data-ttu-id="d8848-166">**UseServiceCertificate**</span><span class="sxs-lookup"><span data-stu-id="d8848-166">**UseServiceCertificate**</span></span>|<span data-ttu-id="d8848-167">False</span><span class="sxs-lookup"><span data-stu-id="d8848-167">False</span></span>|  
  
     <span data-ttu-id="d8848-168">使用这些值来填充\< **serviceBehaviors**\>。</span><span class="sxs-lookup"><span data-stu-id="d8848-168">These values are used to populate the \<**serviceBehaviors**\>.</span></span>  
  
2.  <span data-ttu-id="d8848-169">输入以下值：**终结点行为配置**:</span><span class="sxs-lookup"><span data-stu-id="d8848-169">Enter the following values for **Endpoint Behavior Configuration**:</span></span>  
  
    |<span data-ttu-id="d8848-170">“属性”</span><span class="sxs-lookup"><span data-stu-id="d8848-170">Property</span></span>|<span data-ttu-id="d8848-171">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d8848-171">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="d8848-172">**名称**</span><span class="sxs-lookup"><span data-stu-id="d8848-172">**Name**</span></span>|<span data-ttu-id="d8848-173">customEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="d8848-173">customEndpointBehavior</span></span>|  
    |<span data-ttu-id="d8848-174">**AuthenticationType**</span><span class="sxs-lookup"><span data-stu-id="d8848-174">**AuthenticationType**</span></span>|<span data-ttu-id="d8848-175">**HTTPUsernamePassword**</span><span class="sxs-lookup"><span data-stu-id="d8848-175">**HTTPUsernamePassword**</span></span>|  
    |<span data-ttu-id="d8848-176">**UsernameHeader**</span><span class="sxs-lookup"><span data-stu-id="d8848-176">**UsernameHeader**</span></span>|<span data-ttu-id="d8848-177">MyUserHeader</span><span class="sxs-lookup"><span data-stu-id="d8848-177">MyUserHeader</span></span>|  
    |<span data-ttu-id="d8848-178">**PasswordHeader**</span><span class="sxs-lookup"><span data-stu-id="d8848-178">**PasswordHeader**</span></span>|<span data-ttu-id="d8848-179">MyPassHeader</span><span class="sxs-lookup"><span data-stu-id="d8848-179">MyPassHeader</span></span>|  
  
     <span data-ttu-id="d8848-180">这些值用于指定**adapterSecurityBridgeType**中 <**endpointBehaviors** web.confg 中的元素。</span><span class="sxs-lookup"><span data-stu-id="d8848-180">These values will be used to specify the **adapterSecurityBridgeType** in the <**endpointBehaviors** element in web.confg.</span></span>  
  
     <span data-ttu-id="d8848-181">![终结点配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span><span class="sxs-lookup"><span data-stu-id="d8848-181">![Endpoint Configuration](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")</span></span>  
  
3.  <span data-ttu-id="d8848-182">单击 **“下一步”**</span><span class="sxs-lookup"><span data-stu-id="d8848-182">Click **Next**</span></span>  
  
### <a name="to-configure-the-binding"></a><span data-ttu-id="d8848-183">若要配置的绑定</span><span class="sxs-lookup"><span data-stu-id="d8848-183">To configure the binding</span></span>  
  
1. <span data-ttu-id="d8848-184">上**配置服务终结点绑定和地址**页上，选择**BindingConfiguration**中的条目**配置地址和协定绑定**，和然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="d8848-184">On the **Configure the service endpoint binding and address** page, select the **BindingConfiguration** entry in **Configure the address and binding for the contract**, and then click the ellipsis (**…**) button.</span></span>  
  
2. <span data-ttu-id="d8848-185">在中**自定义绑定**对话框中，将**模式**到**TransportWithMessageCredential**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8848-185">In the **Customize Binding** dialog box, set **Mode** to **TransportWithMessageCredential**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="d8848-186">单击**Apply**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d8848-186">Click **Apply**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="d8848-187">上**摘要**页上，查看的约定和操作为此项目中，选择，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="d8848-187">On the **Summary** page, review the contracts and operations selected for this project, and then click **Finish**.</span></span> <span data-ttu-id="d8848-188">您将看到 EchoWeb 解决方案，其中包含创建的项目文件 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8848-188">You will be presented with the EchoWeb solution, which contains the project files created by the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d8848-189">内容回顾</span><span class="sxs-lookup"><span data-stu-id="d8848-189">What did I just do?</span></span>  
 <span data-ttu-id="d8848-190">在此步骤中，您使用[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]生成 Web 项目，在发布到 IIS 中，将在开发 Echo 适配器的主机[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)在 IIS 进程。</span><span class="sxs-lookup"><span data-stu-id="d8848-190">In this step, you used the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] to generate a Web project that, when published to IIS, will host the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) in the IIS process.</span></span> <span data-ttu-id="d8848-191">生成的 Web 项目允许 Web 服务和 WCF 客户端访问所选的操作。</span><span class="sxs-lookup"><span data-stu-id="d8848-191">The resulting Web project allows Web Services and WCF clients to access the selected operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d8848-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d8848-192">Next Steps</span></span>  
 <span data-ttu-id="d8848-193">要生成并部署 Web 项目，请转到[步骤 2： 将 Web 项目部署](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span><span class="sxs-lookup"><span data-stu-id="d8848-193">To build and deploy the Web project, proceed to [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8848-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8848-194">See Also</span></span>  
 [<span data-ttu-id="d8848-195">教程 1：开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="d8848-195">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)