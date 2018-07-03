---
title: 步骤 3： 创建应用程序定义文件 |Microsoft Docs
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
ms.openlocfilehash: e7a5e2919a4cfed649342fda82435211b059206d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988214"
---
# <a name="step-3-create-an-application-definition-file"></a><span data-ttu-id="83c7d-102">步骤 3： 创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="83c7d-102">Step 3: Create an Application Definition File</span></span>
<span data-ttu-id="83c7d-103">![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="83c7d-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="83c7d-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="83c7d-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="83c7d-105">Microsoft Office SharePoint Server 中的业务数据目录功能公开，并将业务线 (LOB) 应用程序中的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="83c7d-105">The Business Data Catalog feature in Microsoft Office SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="83c7d-106">若要将此数据合并到您的门户网站，必须生成可以使用 Microsoft Office SharePoint Server 应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="83c7d-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="83c7d-107">在此步骤中使用 Business Data Catalog Definition Editor 工具，适用于 Microsoft Office SharePoint Server 2007 SDK，为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="83c7d-107">In this step you use the Business Data Catalog Definition Editor tool, available with the Microsoft Office SharePoint Server 2007 SDK, to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="83c7d-108">此定义文件描述 Echo 适配器的 EchoGreetings 方法，并将在后续步骤中用于启用 SharePoint 与适配器进行通信。</span><span class="sxs-lookup"><span data-stu-id="83c7d-108">This definition file describes the EchoGreetings method of the Echo adapter, and will be used in later steps to enable SharePoint to communicate with the adapter.</span></span>  
  
 <span data-ttu-id="83c7d-109">要创建的 Microsoft Office SharePoint Server 应用程序的用途是允许您调用 Echo 适配器的 EchoGreetings 方法并使用 SharePoint Web 部件将响应返回。</span><span class="sxs-lookup"><span data-stu-id="83c7d-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to allow you to invoke the EchoGreetings method of the Echo adapter and return the response using a SharePoint Web Part.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83c7d-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="83c7d-110">Prerequisites</span></span>  
 <span data-ttu-id="83c7d-111">您应当已完成[步骤 2： 将 Web 项目部署](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)。</span><span class="sxs-lookup"><span data-stu-id="83c7d-111">You should have completed [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md).</span></span> <span data-ttu-id="83c7d-112">您还必须访问到 Business Data Catalog Definition Editor，作为 Microsoft Office SharePoint Server 2007 SDK 的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="83c7d-112">You must also have access to the Business Data Catalog Definition Editor, which is installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="83c7d-113">你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="83c7d-113">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="83c7d-114">创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="83c7d-114">Creating an Application Definition File</span></span>  
 <span data-ttu-id="83c7d-115">本主题提供创建在 IIS 中承载的 WCF 适配器与连接的 SharePoint 业务数据目录应用程序定义文件的分步说明。</span><span class="sxs-lookup"><span data-stu-id="83c7d-115">This topic provides step-by-step instructions to create an application definition file for connecting the SharePoint Business Data Catalog with the WCF adapter hosted in IIS.</span></span>  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a><span data-ttu-id="83c7d-116">若要连接到 WCF 适配器服务并创建实体</span><span class="sxs-lookup"><span data-stu-id="83c7d-116">To connect to the WCF adapter service and create entities</span></span>  
  
1.  <span data-ttu-id="83c7d-117">从**开始菜单**，依次指向**所有程序**，然后单击**Microsoft Business Data Catalog Definition Editor**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-117">From the **Start menu**, point to **All Programs**, and then click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="83c7d-118">在工具栏上，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-118">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="83c7d-119">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-119">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="83c7d-120">在中**URL**框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="83c7d-120">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="83c7d-121">该 URL 必须采用以下格式： `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span><span class="sxs-lookup"><span data-stu-id="83c7d-121">The URL must be in the following format: `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span></span>  
  
5.  <span data-ttu-id="83c7d-122">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-122">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="83c7d-123">若要查看可用的操作，请单击**添加 Web 方法**选项卡。您应看到 EchoGreetings 方法。</span><span class="sxs-lookup"><span data-stu-id="83c7d-123">To see the available operations, click the **Add Web Method** tab. You should see the EchoGreetings method.</span></span> <span data-ttu-id="83c7d-124">将方法拖至设计图面。</span><span class="sxs-lookup"><span data-stu-id="83c7d-124">Drag the method to the Design Surface.</span></span>  
  
7.  <span data-ttu-id="83c7d-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="83c7d-125">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="83c7d-126">在中**输入 LOB 系统的名称**对话框中键入名称**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="83c7d-126">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="83c7d-127">对于此示例中，输入**EchoWSLOB**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-127">For this example, enter **EchoWSLOB**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="83c7d-128">展开**EchoWSLob**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-128">Expand the **EchoWSLob** node, and then expand the **Entities** node.</span></span> <span data-ttu-id="83c7d-129">选择**Entity0**并在属性窗格中键入**EchoGreetings**的值作为**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="83c7d-129">Select **Entity0** and in the Properties pane type **EchoGreetings** as the value for the **Name** property.</span></span>  
  
     <span data-ttu-id="83c7d-130">![实体名称](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span><span class="sxs-lookup"><span data-stu-id="83c7d-130">![Entity Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span></span>  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a><span data-ttu-id="83c7d-131">该方法为指定的用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="83c7d-131">Specify User Name and Password Headers for the Method</span></span>  
 <span data-ttu-id="83c7d-132">在调用 WCF 适配器时，可能需要提供用户凭据将传递到 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="83c7d-132">When calling a WCF adapter, you may have to provide user credentials that will be passed to the LOB system.</span></span> <span data-ttu-id="83c7d-133">在中[步骤 1： 使用适配器服务开发向导创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)，配置 Echo 适配器需要的 MyUserHeader 和 MyPassHeader 字段中提供的用户名和密码信息。</span><span class="sxs-lookup"><span data-stu-id="83c7d-133">In [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md), you configured the Echo adapter to require that user name and password information be provided in the MyUserHeader and MyPassHeader fields.</span></span> <span data-ttu-id="83c7d-134">现在必须使用此应用程序定义文件的相同字段名称。</span><span class="sxs-lookup"><span data-stu-id="83c7d-134">You must now use the same field names for this application definition file.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="83c7d-135">若要指定用户名称和密码标头</span><span class="sxs-lookup"><span data-stu-id="83c7d-135">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="83c7d-136">在元数据对象窗格中，展开**EchoGreetings**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-136">In the Metadata Objects pane, expand the **EchoGreetings** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="83c7d-137">单击**EchoGreetings**节点，然后在属性窗格中，单击旁边的省略号 **（...）** 按钮**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-137">Click the **EchoGreetings** node and, in the Properties pane, click the ellipsis **(…)** button in the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="83c7d-138">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在**名称**字段的属性窗格中，键入**HttpHeaderUserName**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-138">In the PropertyView Collection Editor window, click **Add**, and in the **Name** field of the Property pane, type  **HttpHeaderUserName**.</span></span>  
  
     <span data-ttu-id="83c7d-139">![指定用户名标题字段](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span><span class="sxs-lookup"><span data-stu-id="83c7d-139">![Specify Username Header Fields](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span></span>  
  
4.  <span data-ttu-id="83c7d-140">在中**PropertyValue**字段中，键入**MyUserHeader**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-140">In the **PropertyValue**field, type **MyUserHeader**.</span></span>  
  
5.  <span data-ttu-id="83c7d-141">单击**外**，然后在属性窗格中键入**HttpHeaderPassword**对于名称字段中，然后键入**MyPassHeader**为**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-141">Click **Add**, and in the Property pane type **HttpHeaderPassword** for the Name field, then type **MyPassHeader** for the **PropertyValue** field.</span></span>  
  
6.  <span data-ttu-id="83c7d-142">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="83c7d-142">Click **OK**.</span></span>  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a><span data-ttu-id="83c7d-143">设置了单一登录连接到 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="83c7d-143">Set up Single Sign-On for Connecting to the Echo Adapter</span></span>  
 <span data-ttu-id="83c7d-144">SharePoint 使用从单一登录信息的 MyUserHeader 和 MyPassHeader 使用身份验证的值填充。</span><span class="sxs-lookup"><span data-stu-id="83c7d-144">SharePoint uses information from Single Sign-On to populate the MyUserHeader and MyPassHeader with authentication values.</span></span> <span data-ttu-id="83c7d-145">若要链接到单一登录此应用程序定义文件，必须提供 SecondarySsoApplicationId。</span><span class="sxs-lookup"><span data-stu-id="83c7d-145">To link this application definition file to Single Sign-On, you must provide a SecondarySsoApplicationId.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="83c7d-146">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="83c7d-146">To set the SecondarySsoApplicationId property</span></span>  
  
1. <span data-ttu-id="83c7d-147">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-147">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Instances** node.</span></span>  
  
2. <span data-ttu-id="83c7d-148">单击**EchoWSLOB_Instance**，然后在属性窗格中，单击省略号<strong>（...）</strong>按钮**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-148">Click **EchoWSLOB_Instance**, and in the Properties pane, click the ellipsis <strong>(…)</strong>button in the **Properties** field.</span></span>  
  
3. <span data-ttu-id="83c7d-149">在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**SecondarySsoApplicationId**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-149">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="83c7d-150">在中**PropertyValue**字段中，键入**EchoSSO**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-150">In the **PropertyValue** field, type **EchoSSO**.</span></span>  
  
    <span data-ttu-id="83c7d-151">![设置 SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span><span class="sxs-lookup"><span data-stu-id="83c7d-151">![Set the SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span></span>  
  
5. <span data-ttu-id="83c7d-152">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="83c7d-152">Click **OK**.</span></span>  
  
## <a name="create-input-filters-and-default-values"></a><span data-ttu-id="83c7d-153">创建输入筛选器和默认值</span><span class="sxs-lookup"><span data-stu-id="83c7d-153">Create Input Filters and Default Values</span></span>  
 <span data-ttu-id="83c7d-154">应用程序定义文件必须能够接受用户输入可以传递给 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="83c7d-154">The application definition file must be able to  accept user input that can be passed to a Web service.</span></span> <span data-ttu-id="83c7d-155">若要实现此目的，必须执行以下一组任务：</span><span class="sxs-lookup"><span data-stu-id="83c7d-155">To accomplish this, you must perform the following set of tasks:</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a><span data-ttu-id="83c7d-156">若要创建筛选器，并将其映射到问候语参数</span><span class="sxs-lookup"><span data-stu-id="83c7d-156">To create a filter, and map it to the greeting parameter</span></span>  
  
1.  <span data-ttu-id="83c7d-157">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-157">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="83c7d-158">展开**EchoGreetings**方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-158">Expand the **EchoGreetings** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
3.  <span data-ttu-id="83c7d-159">在属性窗格中，键入**问候**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-159">In the Properties pane, type **Greeting** in the **Name** field.</span></span>  
  
     <span data-ttu-id="83c7d-160">![设置筛选器名称](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span><span class="sxs-lookup"><span data-stu-id="83c7d-160">![Set the Filter Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span></span>  
  
4.  <span data-ttu-id="83c7d-161">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点</span><span class="sxs-lookup"><span data-stu-id="83c7d-161">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node</span></span>  
  
5.  <span data-ttu-id="83c7d-162">展开**EchoGreetings**方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-162">Expand the **EchoGreetings** method, and then expand the **Parameters** node.</span></span>  
  
6.  <span data-ttu-id="83c7d-163">展开**问候**节点，然后展开第二个**问候**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-163">Expand the **greeting** node, and then expand the second **greeting** node.</span></span>  
  
7.  <span data-ttu-id="83c7d-164">单击**greetingText**节点，然后在属性窗格中，选择**问候**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="83c7d-164">Click the **greetingText** node, and in the Properties pane, select **Greeting** from the **FilterDescriptor** list.</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a><span data-ttu-id="83c7d-165">若要创建 Finder 方法实例 EchoGreetings 方法</span><span class="sxs-lookup"><span data-stu-id="83c7d-165">To create a Finder method instance for the EchoGreetings method</span></span>  
  
1.  <span data-ttu-id="83c7d-166">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-166">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="83c7d-167">展开**EchoGreetings**方法中，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="83c7d-167">Expand the **EchoGreetings** method, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
3.  <span data-ttu-id="83c7d-168">在创建方法实例窗口中，单击**Finder**有关**方法实例类型**，然后选择**返回**为**返回 TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="83c7d-168">In the Create Method Instance window, click **Finder** for **Method Instance Type**, and then select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="83c7d-169">![创建方法实例](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span><span class="sxs-lookup"><span data-stu-id="83c7d-169">![Create the Method Instance](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span></span>  
  
4.  <span data-ttu-id="83c7d-170">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="83c7d-170">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="83c7d-171">在属性窗格中，键入**EchoGreetings_Instance**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-171">In the Properties pane, type **EchoGreetings_Instance** in the **Name** field.</span></span>  
  
#### <a name="to-set-default-parameters"></a><span data-ttu-id="83c7d-172">若要设置默认参数</span><span class="sxs-lookup"><span data-stu-id="83c7d-172">To set default parameters</span></span>  
  
1.  <span data-ttu-id="83c7d-173">在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-173">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="83c7d-174">展开**EchoGreetings**方法，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-174">Expand the **EchoGreetings** method, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="83c7d-175">选择**EchoGreetings_Instance**方法实例，并在属性窗格中，单击省略号按钮 （...） 在**DefaultValues**字段。</span><span class="sxs-lookup"><span data-stu-id="83c7d-175">Select the **EchoGreetings_Instance** method instance, and in the Properties pane, click the ellipsis button (…) in the **DefaultValues** field.</span></span>  
  
4.  <span data-ttu-id="83c7d-176">在编辑窗口中，展开**问候**节点，然后展开第二个**问候**节点。</span><span class="sxs-lookup"><span data-stu-id="83c7d-176">In the Edit window, expand the **greeting** node, and then expand the second **greeting** node.</span></span> <span data-ttu-id="83c7d-177">展开**名称**节点，直到完全显示树状结构。</span><span class="sxs-lookup"><span data-stu-id="83c7d-177">Expand the **name** node, until the tree structure is fully displayed.</span></span>  
  
5.  <span data-ttu-id="83c7d-178">在编辑窗口中，设置字段值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83c7d-178">In the Edit window, set the field values as follows:</span></span>  
  
    |<span data-ttu-id="83c7d-179">将此项设置</span><span class="sxs-lookup"><span data-stu-id="83c7d-179">Set this</span></span>|<span data-ttu-id="83c7d-180">与此</span><span class="sxs-lookup"><span data-stu-id="83c7d-180">To this</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="83c7d-181">**id**</span><span class="sxs-lookup"><span data-stu-id="83c7d-181">**id**</span></span>|<span data-ttu-id="83c7d-182">GUID 值，例如 27829ed4 583a-40 c 4 ad87 fb8cdd9dc98d。</span><span class="sxs-lookup"><span data-stu-id="83c7d-182">A GUID value, for example 27829ed4-583a-40c4-ad87-fb8cdd9dc98d.</span></span>|  
    |<span data-ttu-id="83c7d-183">**sentDateTime**</span><span class="sxs-lookup"><span data-stu-id="83c7d-183">**sentDateTime**</span></span>|<span data-ttu-id="83c7d-184">当前日期和时间，例如 05/15/08 上午 9:12 点</span><span class="sxs-lookup"><span data-stu-id="83c7d-184">The current date and time, for example 05/15/08 9:12 AM</span></span>|  
    |<span data-ttu-id="83c7d-185">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="83c7d-185">**firstName**</span></span>|<span data-ttu-id="83c7d-186">第一个</span><span class="sxs-lookup"><span data-stu-id="83c7d-186">First</span></span>|  
    |<span data-ttu-id="83c7d-187">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="83c7d-187">**middleName**</span></span>|<span data-ttu-id="83c7d-188">Middle</span><span class="sxs-lookup"><span data-stu-id="83c7d-188">Middle</span></span>|  
    |<span data-ttu-id="83c7d-189">**姓氏**</span><span class="sxs-lookup"><span data-stu-id="83c7d-189">**lastName**</span></span>|<span data-ttu-id="83c7d-190">上一次</span><span class="sxs-lookup"><span data-stu-id="83c7d-190">Last</span></span>|  
  
     <span data-ttu-id="83c7d-191">![默认参数](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span><span class="sxs-lookup"><span data-stu-id="83c7d-191">![Default Parameters](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span></span>  
  
6.  <span data-ttu-id="83c7d-192">单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-192">Click **Close**.</span></span>  
  
### <a name="to-export-the-application-definition-file"></a><span data-ttu-id="83c7d-193">若要导出的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="83c7d-193">To export the application definition file</span></span>  
  
1.  <span data-ttu-id="83c7d-194">在元数据对象窗格中，右键单击**EchoWSLOB**节点，并单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="83c7d-194">In the Metadata Objects pane, right-click the **EchoWSLOB** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="83c7d-195">将文件另存 EchoWS.xml。</span><span class="sxs-lookup"><span data-stu-id="83c7d-195">Save the file as EchoWS.xml.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="83c7d-196">内容回顾</span><span class="sxs-lookup"><span data-stu-id="83c7d-196">What did I just do?</span></span>  
 <span data-ttu-id="83c7d-197">Business Data Catalog Definition Editor 工具具有用于创建可以导入到 Microsoft Office SharePoint Server 2007，以便与您在 IIS 中承载的适配器的连接应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="83c7d-197">You have used the Business Data Catalog Definition Editor tool to create an application definition file that can be imported into Microsoft Office SharePoint Server 2007 to enable connectivity with your adapter that is hosted in IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="83c7d-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="83c7d-198">Next Steps</span></span>  
 <span data-ttu-id="83c7d-199">现在，您必须创建 SharePoint 应用程序根据在此步骤中创建的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="83c7d-199">You must now create a SharePoint application based on the application definition file created in this step.</span></span> <span data-ttu-id="83c7d-200">请参阅[步骤 4： 创建 Sharepoint 应用程序以访问适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="83c7d-200">See [Step 4: Create a Sharepoint Application to Access the Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c7d-201">请参阅</span><span class="sxs-lookup"><span data-stu-id="83c7d-201">See Also</span></span>  
 [<span data-ttu-id="83c7d-202">教程 3：在 IIS 中托管 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="83c7d-202">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)