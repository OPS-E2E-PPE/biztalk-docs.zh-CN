---
title: 如何使用 BizTalk WCF 服务发布向导发布服务元数据的 WCF 接收位置的基于内容的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, metadata
ms.assetid: e900b0a0-db17-4db9-a639-54891e02d6d7
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44fb1a5235a3cc86397339099efde18784de6cfc
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752813"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing"></a><span data-ttu-id="0eb99-102">如何使用 BizTalk WCF 服务发布向导为基于内容的路由的 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="0eb99-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location for Content-Based Routing</span></span>
<span data-ttu-id="0eb99-103">你可以使用 BizTalk WCF 服务发布向导创建 WCF 服务，以便为基于内容的路由的现有 WCF 接收位置发布服务元数据。</span><span class="sxs-lookup"><span data-stu-id="0eb99-103">You use the BizTalk WCF Service Publishing Wizard to create a WCF service to publish service metadata for existing WCF receive locations for content-based routing.</span></span>  

> [!NOTE]
>  <span data-ttu-id="0eb99-104">在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="0eb99-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="0eb99-105">BizTalk 项目必须包括要发布为 WCF 服务的架构。</span><span class="sxs-lookup"><span data-stu-id="0eb99-105">The BizTalk projects must include schemas to publish as WCF services.</span></span> <span data-ttu-id="0eb99-106">为 WCF 适配器发布服务元数据之前，还必须使用 BizTalk Server 管理控制台或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带的 BTSTask 命令行工具创建 WCF 接收位置。</span><span class="sxs-lookup"><span data-stu-id="0eb99-106">Before you publish service metadata for the WCF adapters, you must also create the WCF receive locations by using the BizTalk Server Administration console or the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0eb99-107">详细了解如何创建 WCF 接收位置，请参阅中每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb99-107">For more information about how to create a WCF receive location, see the appropriate topic for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  

### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-for-content-based-routing"></a><span data-ttu-id="0eb99-108">为基于内容的路由的现有 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="0eb99-108">To publish service metadata for an existing WCF receive location for content-based routing</span></span>  

1. <span data-ttu-id="0eb99-109">单击**启动**，依次指向**所有程序**，指向 **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** ，然后单击 **BizTalk WCF 服务发布向导** 。</span><span class="sxs-lookup"><span data-stu-id="0eb99-109">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0eb99-110">若要创建和发布 WCF 服务元数据的 BizTalk 业务流程和架构，您可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="0eb99-110">To create and publish WCF service metadata for BizTalk orchestrations and schemas, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="0eb99-111">若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="0eb99-111">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  

2. <span data-ttu-id="0eb99-112">上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-112">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  

3. <span data-ttu-id="0eb99-113">上**WCF 服务类型**页上，选择**元数据仅终结点 (MEX)** 选项来发布 WCF 服务以提供服务元数据为 WCF 接收位置将在下一步中选择。</span><span class="sxs-lookup"><span data-stu-id="0eb99-113">On the **WCF Service Type** page, select the **Metdata only endpoint (MEX)** option to publish the WCF services to provide service metadata for the WCF receive location that you will select in the next step.</span></span>  

    <span data-ttu-id="0eb99-114">![WCF 服务类型页](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span><span class="sxs-lookup"><span data-stu-id="0eb99-114">![WCF Service Type page](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span></span>  

4. <span data-ttu-id="0eb99-115">上**WCF 服务类型**页上，在**接收位置发布元数据用于**下拉列表中，选择 WCF 接收位置发布服务元数据，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="0eb99-115">On the **WCF Service Type** page, in the **Publish metadata for receive location** drop-down list, select a WCF receive location to publish service metadata for, and then click **Next**.</span></span>  

5. <span data-ttu-id="0eb99-116">上**创建 WCF 服务**页上，选择**将架构发布为 WCF 服务**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-116">On the **Create WCF Service** page, select **Publish schemas as WCF service**, and then click **Next**.</span></span>  

    <span data-ttu-id="0eb99-117">![创建 WCF 服务页](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")</span><span class="sxs-lookup"><span data-stu-id="0eb99-117">![Create WCF Service page](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")</span></span>  

6. <span data-ttu-id="0eb99-118">上**WCF 服务**页上，选择要发布服务元数据的 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="0eb99-118">On the **WCF Service** page, define the WCF service contract(s) to publish service metadata for.</span></span> <span data-ttu-id="0eb99-119">使用中的树**Web 服务说明**对话框可以添加、 删除、 重命名和编辑要发布的 WCF 服务的 Web 服务说明节点。</span><span class="sxs-lookup"><span data-stu-id="0eb99-119">You use the tree in the **Web service description** dialog box to add, remove, rename, and edit the Web service description nodes for the WCF services to publish.</span></span> <span data-ttu-id="0eb99-120">**信息**对话框提供了有关所选节点的信息，并显示当前节点或任何子节点中的任何错误：</span><span class="sxs-lookup"><span data-stu-id="0eb99-120">The **Information** dialog box provides information about the selected node and displays any errors in the current node or any subnodes:</span></span>  

   -   <span data-ttu-id="0eb99-121">树的根节点（Web Services 说明）描述了要发布的 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="0eb99-121">The root node to the tree (Web service description) describes the WCF service contracts to publish.</span></span> <span data-ttu-id="0eb99-122">虚拟目录名称使用该根节点作为默认名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-122">The virtual directory name uses the root node as the default name.</span></span> <span data-ttu-id="0eb99-123">您可以修改要通过选择发布的 WCF 服务的 Web 服务说明名称**重命名 web 服务说明**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-123">You can modify the Web service description name for the WCF services to publish by selecting **Rename web service description**.</span></span>  

        <span data-ttu-id="0eb99-124">![WCF 服务页](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")</span><span class="sxs-lookup"><span data-stu-id="0eb99-124">![WCF Service page](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")</span></span>  

   -   <span data-ttu-id="0eb99-125">Web 方法节点， **Operation1**，默认服务节点， **Service1**，默认情况下所示**Web 服务说明**对话框可用于请求-响应接收位置。</span><span class="sxs-lookup"><span data-stu-id="0eb99-125">The Web method node, **Operation1**, of the default service node, **Service1**, shown by default in the **Web service description** dialog box can be used for a request-response receive location.</span></span> <span data-ttu-id="0eb99-126">如果选择了一个单向 WCF 接收位置，用于此服务约定中，右键单击默认的 Web 方法节点，单击**删除 web 方法**，然后按如下所示创建一个单向 Web 方法： 右键单击默认服务节点，点向**添加 web 方法**，然后单击**单向**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-126">If you selected a one-way WCF receive location for this service contract, right-click the default Web method node, click **Delete web method**, and then create a one-way Web method as follows: Right-click the default service node, point to **Add web method**, and then click **One-Way**.</span></span>  

   -   <span data-ttu-id="0eb99-127">若要添加新的 WCF 服务，右键单击 Web 服务说明的名称，然后依次**添加 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-127">To add a new WCF service, right-click the Web service description name, and then click **Add web service**.</span></span> <span data-ttu-id="0eb99-128">这会创建一个不带有任何 WCF 操作的新 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="0eb99-128">This creates a new WCF service without any WCF operations.</span></span> <span data-ttu-id="0eb99-129">若要修改 WCF 服务的名称，请右键单击 WCF 服务节点，单击**重命名 web 服务**，然后按 ENTER 以接受新名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-129">To modify the name of the WCF service, right-click the WCF service node, click **Rename web service**, and then press ENTER to accept the new name.</span></span>  

   -   <span data-ttu-id="0eb99-130">若要添加新的 WCF 操作，请右键单击 WCF 服务节点，指向**添加 Web 方法**，然后单击**单向**（对于请求 WCF 操作） 或**请求-响应**(为请求-响应 WCF 操作）。</span><span class="sxs-lookup"><span data-stu-id="0eb99-130">To add a new WCF operation, right-click the WCF service node, point to **Add Web Method**, and then click **One-way** (for a request WCF operation) or **Request-response** (for a request-response WCF operation).</span></span>  

   -   <span data-ttu-id="0eb99-131">若要设置的请求和响应架构类型，请右键单击**请求**或**响应**节点，，然后单击**选择架构类型**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-131">To set the request and response schema types, right-click the **Request** or **Response** node, and then click **Select schema type**.</span></span> <span data-ttu-id="0eb99-132">在中**请求消息类型**框中，键入包含文档架构中的程序集名称**BizTalk 程序集文件**文本框中或单击**浏览**搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="0eb99-132">In the **Request Message Type** dialog box, type the name of the assembly containing the document schema in the **BizTalk assembly file** text box or click **Browse** to search for the assembly.</span></span> <span data-ttu-id="0eb99-133">**可用架构类型**列表视图中显示的架构的每个根元素。</span><span class="sxs-lookup"><span data-stu-id="0eb99-133">The **Available schema types** list view displays each root element of the schema.</span></span> <span data-ttu-id="0eb99-134">选择要作为请求或响应架构类型添加的根节点。</span><span class="sxs-lookup"><span data-stu-id="0eb99-134">Select a root node to add as the request or response schema type.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="0eb99-135">如果在全局程序集缓存 (GAC) 中安装 BizTalk 程序集文件，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**请求消息类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="0eb99-135">If you installed the BizTalk assembly file into the global assembly cache (GAC), make sure that the assembly in the GAC has been updated with the assembly that you will select in the **Request Message Type** dialog box.</span></span> <span data-ttu-id="0eb99-136">如果 GAC 中的程序集具有相同的完全限定名，则 BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是您选择的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="0eb99-136">If the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  

        <span data-ttu-id="0eb99-137">![请求消息类型页](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")</span><span class="sxs-lookup"><span data-stu-id="0eb99-137">![Request Message Type page](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")</span></span>  

   -   <span data-ttu-id="0eb99-138">您可以重命名**请求**并**响应**节点而不会影响生成的代码。</span><span class="sxs-lookup"><span data-stu-id="0eb99-138">You can rename the **Request** and **Response** nodes without affecting the generated code.</span></span> <span data-ttu-id="0eb99-139">在定义了架构之后，可以重命名部分元素，这会修改 WCF 操作的参数名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-139">After defining your schemas, you can rename the part elements, which modifies the WCF operation parameter name.</span></span> <span data-ttu-id="0eb99-140">通过查看要发布的 WCF 服务的服务元数据，可以看到发生的更改。</span><span class="sxs-lookup"><span data-stu-id="0eb99-140">You can see the changes by viewing the service metadata for the WCF services to publish.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0eb99-141">在重命名任何 Web Services 说明节点时，不能使用空格。</span><span class="sxs-lookup"><span data-stu-id="0eb99-141">You cannot use spaces when renaming any of the Web service description nodes.</span></span>  

7. <span data-ttu-id="0eb99-142">单击**下一步**继续执行向导。</span><span class="sxs-lookup"><span data-stu-id="0eb99-142">Click **Next** to continue the wizard.</span></span>  

8. <span data-ttu-id="0eb99-143">上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-143">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  

    <span data-ttu-id="0eb99-144">![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="0eb99-144">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  

9. <span data-ttu-id="0eb99-145">上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-145">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="0eb99-146">您可以接受默认位置 (`http://localhost/<Web service description name>`)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。</span><span class="sxs-lookup"><span data-stu-id="0eb99-146">You can accept the default location (`http://localhost/<Web service description name>`), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="0eb99-147">选择以下任何选项：</span><span class="sxs-lookup"><span data-stu-id="0eb99-147">Select any of the following options:</span></span>  

   - <span data-ttu-id="0eb99-148">**覆盖现有项目。**</span><span class="sxs-lookup"><span data-stu-id="0eb99-148">**Overwrite existing project.**</span></span> <span data-ttu-id="0eb99-149">此选项才可用，仅当 Web 目录已存在。</span><span class="sxs-lookup"><span data-stu-id="0eb99-149">This option is available only if the Web directory already exists.</span></span> <span data-ttu-id="0eb99-150">仅当选择了此选项时，您才能够发布到同一位置。</span><span class="sxs-lookup"><span data-stu-id="0eb99-150">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="0eb99-151">否则，必须输入不同的项目位置。</span><span class="sxs-lookup"><span data-stu-id="0eb99-151">Otherwise, you must enter a different project location.</span></span>  

   - <span data-ttu-id="0eb99-152">**允许匿名访问 WCF 服务。**</span><span class="sxs-lookup"><span data-stu-id="0eb99-152">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="0eb99-153">此选项会为已创建的虚拟目录添加匿名访问权限。</span><span class="sxs-lookup"><span data-stu-id="0eb99-153">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="0eb99-154">默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0eb99-154">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  

     <span data-ttu-id="0eb99-155">在完成此页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0eb99-155">When you finish this page, click **Next**.</span></span>  

     <span data-ttu-id="0eb99-156">![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="0eb99-156">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="0eb99-157">项目位置可位于其他服务器上。</span><span class="sxs-lookup"><span data-stu-id="0eb99-157">The project location can exist on a different server.</span></span> <span data-ttu-id="0eb99-158">若要将 WCF 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<WCF service location>`。</span><span class="sxs-lookup"><span data-stu-id="0eb99-158">To publish the WCF services to a different server, type the project name as `http://<servername>/<WCF service location>`.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="0eb99-159">项目位置可位于非默认网站上。</span><span class="sxs-lookup"><span data-stu-id="0eb99-159">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="0eb99-160">发布到非默认网站时，请在该 URL 中包括网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="0eb99-160">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="0eb99-161">例如 `http://<servername>:8080/<WCF service location>` 。</span><span class="sxs-lookup"><span data-stu-id="0eb99-161">For example, `http://<servername>:8080/<WCF service location>`.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="0eb99-162">向导在 Web 应用程序的 \App_Data\Temp 文件夹中创建的 BindingInfo.xml 文件使用管道的默认值。</span><span class="sxs-lookup"><span data-stu-id="0eb99-162">The BindingInfo.xml file that the wizard creates in the \App_Data\Temp folder of the Web application uses the default values for the pipelines.</span></span> <span data-ttu-id="0eb99-163">接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.XMLReceive**管道和默认值为发送管道**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**管道。</span><span class="sxs-lookup"><span data-stu-id="0eb99-163">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.XMLReceive** pipeline, and the default value for the send pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** pipeline.</span></span>  

10. <span data-ttu-id="0eb99-164">上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="0eb99-164">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  

11. <span data-ttu-id="0eb99-165">单击**创建**创建 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="0eb99-165">Click **Create** to create the WCF services.</span></span>  

12. <span data-ttu-id="0eb99-166">单击**完成**完成 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="0eb99-166">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  

### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a><span data-ttu-id="0eb99-167">为发布服务元数据配置 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="0eb99-167">To configure the Web application for publishing service metadata</span></span>  

1. <span data-ttu-id="0eb99-168">为 BizTalk WCF 服务发布向导创建的 Web 应用程序启用 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="0eb99-168">Enable ASP.NET for the Web application that the BizTalk WCF Service Publishing Wizard created.</span></span> <span data-ttu-id="0eb99-169">有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb99-169">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0eb99-170">如果您使用的是其他版本的 Windows 操作系统，则必须将应用程序池的标识帐户添加到 BizTalk Server Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="0eb99-170">If you are using another version of the Windows operating system, you must add the Identity Account of the Application Pool to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0eb99-171">将相应的帐户添加到 BizTalk Server Administrators 组后，需要重新启动 IIS 服务，设置才能生效。</span><span class="sxs-lookup"><span data-stu-id="0eb99-171">After you add the appropriate account to the BizTalk Server Administrators group, you need to restart the IIS service for the setting to take effect.</span></span>  

2. <span data-ttu-id="0eb99-172">打开命令提示符，请转到 BizTalk WCF 服务发布向导创建 WCF 服务中 %SystemDrive%\InetPub 所在的文件夹\\，然后打开 Web.config 文件使用记事本。</span><span class="sxs-lookup"><span data-stu-id="0eb99-172">Open a command prompt, go to the folder where the BizTalk WCF Service Publishing Wizard created the WCF services in %SystemDrive%\InetPub\\, and then open the Web.config file using Notepad.</span></span>  

3. <span data-ttu-id="0eb99-173">在记事本中，添加以下行 **\<system.web\>** 元素：</span><span class="sxs-lookup"><span data-stu-id="0eb99-173">In Notepad, add the following line inside the **\<system.web\>** element:</span></span>  

   ```  
   <trust level="Full" originUrl="" />  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="0eb99-174">此设置是可选的，用于向已发布的 WCF 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0eb99-174">This setting is optional and it grants the ASP.NET application hosting the published WCF service access to any resource that is subject to operating system security.</span></span> <span data-ttu-id="0eb99-175">如果在已发布的 WCF 服务所在的计算机上安装并运行了 Windows SharePoint Services，则这是 WCF 所必需的信任级别。</span><span class="sxs-lookup"><span data-stu-id="0eb99-175">This is the trust level that WCF requires when you have Windows SharePoint Services installed and running on the same machine with the published WCF services.</span></span>  

4. <span data-ttu-id="0eb99-176">在 Internet Explorer 中，在**地址**框中，键入格式为 的 WCF 服务 URL http://<em>主机 [: 端口]</em>/*apppath* /*wcfservicename.svc*以测试已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="0eb99-176">In Internet Explorer, in the **Address** box, type the URL for the WCF service using the format http://<em>host[:port]</em>/*apppath*/*wcfservicename.svc* to test the published WCF service.</span></span> <span data-ttu-id="0eb99-177">介绍了下表的参数。</span><span class="sxs-lookup"><span data-stu-id="0eb99-177">The parameters are described in the following table.</span></span>  


   |      <span data-ttu-id="0eb99-178">参数</span><span class="sxs-lookup"><span data-stu-id="0eb99-178">Parameter</span></span>       |                                                            <span data-ttu-id="0eb99-179">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="0eb99-179">Value</span></span>                                                            |
   |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
   |    <span data-ttu-id="0eb99-180">*主机 [: 端口]*</span><span class="sxs-lookup"><span data-stu-id="0eb99-180">*host[:port]*</span></span>     | <span data-ttu-id="0eb99-181">在其中部署了你的 WCF 服务的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-181">The name of the computer where you have deployed your WCF service.</span></span> <span data-ttu-id="0eb99-182">此服务器名称后面可跟冒号和端口号。</span><span class="sxs-lookup"><span data-stu-id="0eb99-182">A colon and the port number can follow this server name.</span></span> |
   |      <span data-ttu-id="0eb99-183">*apppath*</span><span class="sxs-lookup"><span data-stu-id="0eb99-183">*apppath*</span></span>       |                              <span data-ttu-id="0eb99-184">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-184">The name of your virtual directory and the Web application path.</span></span>                               |
   | <span data-ttu-id="0eb99-185">*wcfservicename.svc*</span><span class="sxs-lookup"><span data-stu-id="0eb99-185">*wcfservicename.svc*</span></span> |                                           <span data-ttu-id="0eb99-186">WCF 服务 .svc 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="0eb99-186">The name of the WCF service .svc file.</span></span>                                            |


5. <span data-ttu-id="0eb99-187">为了避免无意中泄漏可能敏感的服务元数据，我们建议执行下列任务以在生产环境中禁止此行为：</span><span class="sxs-lookup"><span data-stu-id="0eb99-187">To prevent unintentional disclosure of potentially sensitive service metadata, we recommend that you disable this behavior in the production environment by performing the following tasks:</span></span>  

   1.  <span data-ttu-id="0eb99-188">在记事本中，打开 BizTalk WCF 服务发布向导创建 WCF 服务中 %SystemDrive%\InetPub 所在的文件夹中的 Web.config\\。</span><span class="sxs-lookup"><span data-stu-id="0eb99-188">In Notepad, open Web.config in the folder where the BizTalk WCF Service Publishing Wizard created the WCF service in %SystemDrive%\InetPub\\.</span></span>  

   2.  <span data-ttu-id="0eb99-189">在记事本中，设置 **httpGetEnabled** 属性中 **\<serviceMetadata\>** 元素为 false，如以下行：</span><span class="sxs-lookup"><span data-stu-id="0eb99-189">In Notepad, set the **httpGetEnabled** attribute in the  **\<serviceMetadata\>** element to false as following line:</span></span>  

       ```  
       <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
       ```  

## <a name="see-also"></a><span data-ttu-id="0eb99-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eb99-190">See Also</span></span>  
 <span data-ttu-id="0eb99-191">[如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="0eb99-191">[How to Use the BizTalk WCF Service Publishing Wizard to Publish Schemas as WCF Services](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md) </span></span>  
 [<span data-ttu-id="0eb99-192">演练：通过 WCF-NetMsmq 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="0eb99-192">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)