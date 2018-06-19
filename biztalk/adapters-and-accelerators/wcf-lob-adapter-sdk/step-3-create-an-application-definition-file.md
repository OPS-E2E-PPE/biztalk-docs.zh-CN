---
title: 步骤 3： 创建应用程序定义文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 843fafdb-571e-4da4-ad04-7dc7f23e03ac
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce22a63e8267c36c1306974caa0faa5f9aa6be4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227005"
---
# <a name="step-3-create-an-application-definition-file"></a><span data-ttu-id="f134b-102">步骤 3： 创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="f134b-102">Step 3: Create an Application Definition File</span></span>
<span data-ttu-id="f134b-103">![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="f134b-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="f134b-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="f134b-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="f134b-105">Microsoft Office SharePoint Server 中的业务数据目录功能公开，并将业务线 (LOB) 应用程序中的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="f134b-105">The Business Data Catalog feature in Microsoft Office SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="f134b-106">若要将此数据合并到您的门户网站，必须在生成应用程序定义文件，可以使用 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="f134b-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="f134b-107">在此步骤中使用业务数据目录定义编辑器工具，适用于 Microsoft Office SharePoint Server 2007 SDK，为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="f134b-107">In this step you use the Business Data Catalog Definition Editor tool, available with the Microsoft Office SharePoint Server 2007 SDK, to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="f134b-108">此定义文件描述 Echo 适配器，EchoGreetings 方法，并且将在后续步骤中用于启用 SharePoint 与适配器进行通信。</span><span class="sxs-lookup"><span data-stu-id="f134b-108">This definition file describes the EchoGreetings method of the Echo adapter, and will be used in later steps to enable SharePoint to communicate with the adapter.</span></span>  
  
 <span data-ttu-id="f134b-109">要创建 Microsoft Office SharePoint Server 应用程序的目的是允许你调用 Echo 适配器 EchoGreetings 方法并返回使用 SharePoint Web 部件的响应。</span><span class="sxs-lookup"><span data-stu-id="f134b-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to allow you to invoke the EchoGreetings method of the Echo adapter and return the response using a SharePoint Web Part.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f134b-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="f134b-110">Prerequisites</span></span>  
 <span data-ttu-id="f134b-111">你应该已完成[步骤 2： 将 Web 项目部署](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)。</span><span class="sxs-lookup"><span data-stu-id="f134b-111">You should have completed [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md).</span></span> <span data-ttu-id="f134b-112">你必须可以访问到业务数据目录定义编辑器中，作为 Microsoft Office SharePoint Server 2007 SDK 的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="f134b-112">You must also have access to the Business Data Catalog Definition Editor, which is installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="f134b-113">你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="f134b-113">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="f134b-114">创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="f134b-114">Creating an Application Definition File</span></span>  
 <span data-ttu-id="f134b-115">本主题提供用于创建应用程序定义文件用于连接 SharePoint 业务数据目录与在 IIS 中承载的 WCF 适配器分步说明。</span><span class="sxs-lookup"><span data-stu-id="f134b-115">This topic provides step-by-step instructions to create an application definition file for connecting the SharePoint Business Data Catalog with the WCF adapter hosted in IIS.</span></span>  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a><span data-ttu-id="f134b-116">若要连接到 WCF 适配器服务并创建实体</span><span class="sxs-lookup"><span data-stu-id="f134b-116">To connect to the WCF adapter service and create entities</span></span>  
  
1.  <span data-ttu-id="f134b-117">从**开始菜单**，指向**所有程序**，然后单击**Microsoft 业务数据目录定义编辑器**。</span><span class="sxs-lookup"><span data-stu-id="f134b-117">From the **Start menu**, point to **All Programs**, and then click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="f134b-118">在工具栏上，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="f134b-118">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="f134b-119">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="f134b-119">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="f134b-120">在**URL**框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="f134b-120">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="f134b-121">该 URL 必须采用以下格式：`https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span><span class="sxs-lookup"><span data-stu-id="f134b-121">The URL must be in the following format: `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span></span>  
  
5.  <span data-ttu-id="f134b-122">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="f134b-122">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="f134b-123">若要查看可用操作，请单击**添加 Web 方法**选项卡。你应看到 EchoGreetings 方法。</span><span class="sxs-lookup"><span data-stu-id="f134b-123">To see the available operations, click the **Add Web Method** tab. You should see the EchoGreetings method.</span></span> <span data-ttu-id="f134b-124">将方法拖到设计图面。</span><span class="sxs-lookup"><span data-stu-id="f134b-124">Drag the method to the Design Surface.</span></span>  
  
7.  <span data-ttu-id="f134b-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f134b-125">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f134b-126">在**输入 LOB 系统的名称**对话框中，键入一个名称中**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="f134b-126">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="f134b-127">对于此示例中，输入**EchoWSLOB**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f134b-127">For this example, enter **EchoWSLOB**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="f134b-128">展开**EchoWSLob**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-128">Expand the **EchoWSLob** node, and then expand the **Entities** node.</span></span> <span data-ttu-id="f134b-129">选择**Entity0** ，在属性窗格中键入**EchoGreetings**的值作为**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="f134b-129">Select **Entity0** and in the Properties pane type **EchoGreetings** as the value for the **Name** property.</span></span>  
  
     <span data-ttu-id="f134b-130">![实体名称](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span><span class="sxs-lookup"><span data-stu-id="f134b-130">![Entity Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span></span>  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a><span data-ttu-id="f134b-131">为方法中指定用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="f134b-131">Specify User Name and Password Headers for the Method</span></span>  
 <span data-ttu-id="f134b-132">在调用 WCF 适配器时，你可能需要提供用户凭据将传递到 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="f134b-132">When calling a WCF adapter, you may have to provide user credentials that will be passed to the LOB system.</span></span> <span data-ttu-id="f134b-133">在[步骤 1： 使用适配器服务开发向导来创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)，你将回显适配器配置为要求的 MyUserHeader 和 MyPassHeader 字段提供用户名和密码信息。</span><span class="sxs-lookup"><span data-stu-id="f134b-133">In [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md), you configured the Echo adapter to require that user name and password information be provided in the MyUserHeader and MyPassHeader fields.</span></span> <span data-ttu-id="f134b-134">你现在必须使用此应用程序定义文件相同的字段名称。</span><span class="sxs-lookup"><span data-stu-id="f134b-134">You must now use the same field names for this application definition file.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="f134b-135">若要指定用户名称和密码标头</span><span class="sxs-lookup"><span data-stu-id="f134b-135">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="f134b-136">在元数据对象窗格中，展开**EchoGreetings**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-136">In the Metadata Objects pane, expand the **EchoGreetings** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f134b-137">单击**EchoGreetings**节点，然后在属性窗格中，单击省略号 **（...）** 按钮**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-137">Click the **EchoGreetings** node and, in the Properties pane, click the ellipsis **(…)** button in the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="f134b-138">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在**名称**字段的属性窗格中，类型**HttpHeaderUserName**。</span><span class="sxs-lookup"><span data-stu-id="f134b-138">In the PropertyView Collection Editor window, click **Add**, and in the **Name** field of the Property pane, type  **HttpHeaderUserName**.</span></span>  
  
     <span data-ttu-id="f134b-139">![指定用户名标头字段](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span><span class="sxs-lookup"><span data-stu-id="f134b-139">![Specify Username Header Fields](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span></span>  
  
4.  <span data-ttu-id="f134b-140">在**PropertyValue**字段中，键入**MyUserHeader**。</span><span class="sxs-lookup"><span data-stu-id="f134b-140">In the **PropertyValue**field, type **MyUserHeader**.</span></span>  
  
5.  <span data-ttu-id="f134b-141">单击**添加**，在属性窗格中键入**HttpHeaderPassword**对于名称字段中，然后键入**MyPassHeader**为**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-141">Click **Add**, and in the Property pane type **HttpHeaderPassword** for the Name field, then type **MyPassHeader** for the **PropertyValue** field.</span></span>  
  
6.  <span data-ttu-id="f134b-142">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f134b-142">Click **OK**.</span></span>  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a><span data-ttu-id="f134b-143">为连接到 Echo 适配器向上上单一登录设置</span><span class="sxs-lookup"><span data-stu-id="f134b-143">Set up Single Sign-On for Connecting to the Echo Adapter</span></span>  
 <span data-ttu-id="f134b-144">SharePoint 使用从单一登录的信息来填充的 MyUserHeader 和 MyPassHeader 身份验证值。</span><span class="sxs-lookup"><span data-stu-id="f134b-144">SharePoint uses information from Single Sign-On to populate the MyUserHeader and MyPassHeader with authentication values.</span></span> <span data-ttu-id="f134b-145">若要链接到单一登录此应用程序定义文件，你必须提供 SecondarySsoApplicationId。</span><span class="sxs-lookup"><span data-stu-id="f134b-145">To link this application definition file to Single Sign-On, you must provide a SecondarySsoApplicationId.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="f134b-146">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="f134b-146">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="f134b-147">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-147">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="f134b-148">单击**EchoWSLOB_Instance**，在属性窗格中，单击省略号 **（...）** 按钮**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-148">Click **EchoWSLOB_Instance**, and in the Properties pane, click the ellipsis **(…)** button in the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="f134b-149">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-149">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="f134b-150">在**PropertyValue**字段中，键入**EchoSSO**。</span><span class="sxs-lookup"><span data-stu-id="f134b-150">In the **PropertyValue** field, type **EchoSSO**.</span></span>  
  
     <span data-ttu-id="f134b-151">![设置 SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span><span class="sxs-lookup"><span data-stu-id="f134b-151">![Set the SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span></span>  
  
5.  <span data-ttu-id="f134b-152">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f134b-152">Click **OK**.</span></span>  
  
## <a name="create-input-filters-and-default-values"></a><span data-ttu-id="f134b-153">创建输入筛选器和默认值</span><span class="sxs-lookup"><span data-stu-id="f134b-153">Create Input Filters and Default Values</span></span>  
 <span data-ttu-id="f134b-154">应用程序定义文件必须能够接受用户输入可以传递给 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="f134b-154">The application definition file must be able to  accept user input that can be passed to a Web service.</span></span> <span data-ttu-id="f134b-155">若要完成此操作，必须执行以下一组任务：</span><span class="sxs-lookup"><span data-stu-id="f134b-155">To accomplish this, you must perform the following set of tasks:</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a><span data-ttu-id="f134b-156">创建筛选器，并将其映射到问候语参数</span><span class="sxs-lookup"><span data-stu-id="f134b-156">To create a filter, and map it to the greeting parameter</span></span>  
  
1.  <span data-ttu-id="f134b-157">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-157">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f134b-158">展开**EchoGreetings**方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f134b-158">Expand the **EchoGreetings** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
3.  <span data-ttu-id="f134b-159">在属性窗格中，键入**问候**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-159">In the Properties pane, type **Greeting** in the **Name** field.</span></span>  
  
     <span data-ttu-id="f134b-160">![设置筛选器名称](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span><span class="sxs-lookup"><span data-stu-id="f134b-160">![Set the Filter Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span></span>  
  
4.  <span data-ttu-id="f134b-161">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点</span><span class="sxs-lookup"><span data-stu-id="f134b-161">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node</span></span>  
  
5.  <span data-ttu-id="f134b-162">展开**EchoGreetings**方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-162">Expand the **EchoGreetings** method, and then expand the **Parameters** node.</span></span>  
  
6.  <span data-ttu-id="f134b-163">展开**问候**节点，然后展开第二个**问候**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-163">Expand the **greeting** node, and then expand the second **greeting** node.</span></span>  
  
7.  <span data-ttu-id="f134b-164">单击**greetingText**节点，然后在属性窗格中，选择**问候**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="f134b-164">Click the **greetingText** node, and in the Properties pane, select **Greeting** from the **FilterDescriptor** list.</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a><span data-ttu-id="f134b-165">若要创建 EchoGreetings 方法的 Finder 方法实例</span><span class="sxs-lookup"><span data-stu-id="f134b-165">To create a Finder method instance for the EchoGreetings method</span></span>  
  
1.  <span data-ttu-id="f134b-166">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-166">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f134b-167">展开**EchoGreetings**方法中，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="f134b-167">Expand the **EchoGreetings** method, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
3.  <span data-ttu-id="f134b-168">在创建方法实例窗口中，单击**Finder**为**方法实例类型**，然后选择**返回**为**返回 TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="f134b-168">In the Create Method Instance window, click **Finder** for **Method Instance Type**, and then select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="f134b-169">![创建方法实例](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span><span class="sxs-lookup"><span data-stu-id="f134b-169">![Create the Method Instance](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span></span>  
  
4.  <span data-ttu-id="f134b-170">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f134b-170">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f134b-171">在属性窗格中，键入**EchoGreetings_Instance**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-171">In the Properties pane, type **EchoGreetings_Instance** in the **Name** field.</span></span>  
  
#### <a name="to-set-default-parameters"></a><span data-ttu-id="f134b-172">若要设置默认参数</span><span class="sxs-lookup"><span data-stu-id="f134b-172">To set default parameters</span></span>  
  
1.  <span data-ttu-id="f134b-173">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-173">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f134b-174">展开**EchoGreetings**方法，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-174">Expand the **EchoGreetings** method, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="f134b-175">选择**EchoGreetings_Instance**方法实例，并在属性窗格中，单击中的省略号按钮 （…） **DefaultValues**字段。</span><span class="sxs-lookup"><span data-stu-id="f134b-175">Select the **EchoGreetings_Instance** method instance, and in the Properties pane, click the ellipsis button (…) in the **DefaultValues** field.</span></span>  
  
4.  <span data-ttu-id="f134b-176">在编辑窗口中，展开**问候**节点，然后展开第二个**问候**节点。</span><span class="sxs-lookup"><span data-stu-id="f134b-176">In the Edit window, expand the **greeting** node, and then expand the second **greeting** node.</span></span> <span data-ttu-id="f134b-177">展开**名称**节点，直到完全显示树状结构。</span><span class="sxs-lookup"><span data-stu-id="f134b-177">Expand the **name** node, until the tree structure is fully displayed.</span></span>  
  
5.  <span data-ttu-id="f134b-178">在编辑窗口中，设置字段值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f134b-178">In the Edit window, set the field values as follows:</span></span>  
  
    |<span data-ttu-id="f134b-179">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="f134b-179">Set this</span></span>|<span data-ttu-id="f134b-180">至此</span><span class="sxs-lookup"><span data-stu-id="f134b-180">To this</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="f134b-181">**id**</span><span class="sxs-lookup"><span data-stu-id="f134b-181">**id**</span></span>|<span data-ttu-id="f134b-182">GUID 值，例如 27829ed4-583a-40 c 4 ad87 fb8cdd9dc98d。</span><span class="sxs-lookup"><span data-stu-id="f134b-182">A GUID value, for example 27829ed4-583a-40c4-ad87-fb8cdd9dc98d.</span></span>|  
    |<span data-ttu-id="f134b-183">**sentDateTime**</span><span class="sxs-lookup"><span data-stu-id="f134b-183">**sentDateTime**</span></span>|<span data-ttu-id="f134b-184">当前日期和时间，例如 05/15/08 上午 9:12</span><span class="sxs-lookup"><span data-stu-id="f134b-184">The current date and time, for example 05/15/08 9:12 AM</span></span>|  
    |<span data-ttu-id="f134b-185">**firstName**</span><span class="sxs-lookup"><span data-stu-id="f134b-185">**firstName**</span></span>|<span data-ttu-id="f134b-186">第一个</span><span class="sxs-lookup"><span data-stu-id="f134b-186">First</span></span>|  
    |<span data-ttu-id="f134b-187">**middleName**</span><span class="sxs-lookup"><span data-stu-id="f134b-187">**middleName**</span></span>|<span data-ttu-id="f134b-188">Middle</span><span class="sxs-lookup"><span data-stu-id="f134b-188">Middle</span></span>|  
    |<span data-ttu-id="f134b-189">**lastName**</span><span class="sxs-lookup"><span data-stu-id="f134b-189">**lastName**</span></span>|<span data-ttu-id="f134b-190">上一次</span><span class="sxs-lookup"><span data-stu-id="f134b-190">Last</span></span>|  
  
     <span data-ttu-id="f134b-191">![默认参数](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span><span class="sxs-lookup"><span data-stu-id="f134b-191">![Default Parameters](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span></span>  
  
6.  <span data-ttu-id="f134b-192">单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="f134b-192">Click **Close**.</span></span>  
  
### <a name="to-export-the-application-definition-file"></a><span data-ttu-id="f134b-193">若要导出的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="f134b-193">To export the application definition file</span></span>  
  
1.  <span data-ttu-id="f134b-194">在元数据对象窗格中，右键单击**EchoWSLOB**节点，，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="f134b-194">In the Metadata Objects pane, right-click the **EchoWSLOB** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="f134b-195">将文件保存为 EchoWS.xml。</span><span class="sxs-lookup"><span data-stu-id="f134b-195">Save the file as EchoWS.xml.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="f134b-196">内容回顾</span><span class="sxs-lookup"><span data-stu-id="f134b-196">What did I just do?</span></span>  
 <span data-ttu-id="f134b-197">你已使用业务数据目录定义编辑器工具创建的应用程序定义文件，可以导入到 Microsoft Office SharePoint Server 2007，以启用与你在 IIS 中承载的适配器的连接。</span><span class="sxs-lookup"><span data-stu-id="f134b-197">You have used the Business Data Catalog Definition Editor tool to create an application definition file that can be imported into Microsoft Office SharePoint Server 2007 to enable connectivity with your adapter that is hosted in IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f134b-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f134b-198">Next Steps</span></span>  
 <span data-ttu-id="f134b-199">你现在必须创建 SharePoint 应用程序根据在此步骤中创建的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="f134b-199">You must now create a SharePoint application based on the application definition file created in this step.</span></span> <span data-ttu-id="f134b-200">请参阅[步骤 4： 创建 Sharepoint 应用程序访问适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="f134b-200">See [Step 4: Create a Sharepoint Application to Access the Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f134b-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f134b-201">See Also</span></span>  
 [<span data-ttu-id="f134b-202">教程 3： 承载在 IIS 中的 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="f134b-202">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)