---
title: 如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, WCF services
- tools, WCF Service Publishing Wizard
- publishing, schemas [WCF services]
- WCF services, schemas
- WCF Service Publishing Wizard
ms.assetid: 3b770fd5-5b7b-493f-9016-d7d58854c5ff
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed13b7f94cf7dea10837295e81063a3f42499c40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398400"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-schemas-as-wcf-services"></a><span data-ttu-id="e323a-102">如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e323a-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Schemas as WCF Services</span></span>
<span data-ttu-id="e323a-103">使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e323a-103">You use the BizTalk WCF Service Publishing Wizard to publish schemas as WCF services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e323a-104">在运行 BizTalk WCF 服务发布向导前必须生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e323a-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="e323a-105">BizTalk 项目必须包括要发布为 WCF 服务的架构。</span><span class="sxs-lookup"><span data-stu-id="e323a-105">The BizTalk projects must include schemas to publish as WCF services.</span></span>  
  
### <a name="to-publish-schemas-as-wcf-servicees"></a><span data-ttu-id="e323a-106">若要将架构发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e323a-106">To publish schemas as WCF servicees</span></span>  
  
1. <span data-ttu-id="e323a-107">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="e323a-107">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e323a-108">若要创建并将 BizTalk 业务流程和架构发布为 WCF 适配器的 WCF 服务，你可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="e323a-108">To create and publish BizTalk orchestrations and schemas as WCF services with the WCF adapters, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="e323a-109">若要将业务流程和架构发布为 Web 服务使用 SOAP 适配器，您可以使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="e323a-109">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  
  
2. <span data-ttu-id="e323a-110">上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e323a-110">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  
  
3. <span data-ttu-id="e323a-111">上**WCF 服务类型**页上，选择**服务终结点**上发布的 WCF 服务中选择选项，BizTalk 业务流程的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="e323a-111">On the **WCF Service Type** page, select the **Service endpoint** option to publish the WCF services on selected BizTalk orchestrations in a BizTalk assembly.</span></span>  
  
    <span data-ttu-id="e323a-112">![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span><span class="sxs-lookup"><span data-stu-id="e323a-112">![WCF Service Type page](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span></span>  
  
4. <span data-ttu-id="e323a-113">上**WCF 服务类型**页上，选中或清除**启用元数据终结点**复选框以指示独立的 WCF 接收位置由 Internet 信息服务 (IIS) 承载是否将发布使用 HTTP/GET 请求进行检索服务元数据。</span><span class="sxs-lookup"><span data-stu-id="e323a-113">On the **WCF Service Type** page, select or clear the **Enable metadata endpoint** check box to indicate whether the isolated WCF receive location hosted by Internet Information Services (IIS) will publish service metadata for retrieval using an HTTP/GET request.</span></span>  
  
    <span data-ttu-id="e323a-114">选中此复选框后，向导生成的 Web.config 文件中的**httpGetEnabled**的属性 **\<serviceMetadata\>** 元素设置为 **，则返回 true**。</span><span class="sxs-lookup"><span data-stu-id="e323a-114">When this check box is selected, the wizard generates a Web.config file  in which the **httpGetEnabled** attribute of the **\<serviceMetadata\>** element is set to **true**.</span></span> <span data-ttu-id="e323a-115">您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="e323a-115">You can use a metadata import tool (such as SvcUtil.exe) to generate the client code required to call this service in the development environment.</span></span> <span data-ttu-id="e323a-116">发布元数据的地址为终结点地址加上 **？ wsdl**查询字符串。</span><span class="sxs-lookup"><span data-stu-id="e323a-116">The address at which the metadata is published is the endpoint address plus a **?wsdl** query string.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e323a-117">若要防止无意中泄漏可能敏感的服务元数据，我们建议禁用此行为在生产环境中。</span><span class="sxs-lookup"><span data-stu-id="e323a-117">To prevent unintentional disclosure of potentially sensitive service metadata, we recommend that you disable this behavior in the production environment.</span></span> <span data-ttu-id="e323a-118">这可以通过将 httpgetenabled 设置为 false，或删除 MEX 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e323a-118">This can be done by setting httpgetenabled to false, or deleting the MEX virtual directory.</span></span>  
  
5. <span data-ttu-id="e323a-119">上**WCF 服务类型**页上，在**适配器名称 （传输类型）** 下拉列表中，选择的 WCF 服务发布使用独立的 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="e323a-119">On the **WCF Service Type** page, in the **Adapter name (Transport type)** drop-down list, select the isolated WCF adapter with which the WCF services are published.</span></span> <span data-ttu-id="e323a-120">您可以选择任何以下适配器：</span><span class="sxs-lookup"><span data-stu-id="e323a-120">You can select any of the following adapters:</span></span>  
  
   -   <span data-ttu-id="e323a-121">**WCF-BasicHttp.**</span><span class="sxs-lookup"><span data-stu-id="e323a-121">**WCF-BasicHttp.**</span></span> <span data-ttu-id="e323a-122">Wcf-basichttp 适配器能够与 WS-基本配置文件 1.1 的 web 服务与基于 ASMX 的服务一样。</span><span class="sxs-lookup"><span data-stu-id="e323a-122">The WCF-BasicHttp adapter can communicate with WS-I Basic Profile 1.1-conformant Web services like ASMX-based services.</span></span>  
  
   -   <span data-ttu-id="e323a-123">**WCF-WSHttp.**</span><span class="sxs-lookup"><span data-stu-id="e323a-123">**WCF-WSHttp.**</span></span> <span data-ttu-id="e323a-124">Wcf-wshttp 适配器能够与服务的 WS-\* 标准通过 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="e323a-124">The WCF-WSHttp adapter can communicate with a service through the WS-\* standards over HTTP and HTTPS.</span></span>  
  
   -   <span data-ttu-id="e323a-125">**WCF CustomIsolated。**</span><span class="sxs-lookup"><span data-stu-id="e323a-125">**WCF-CustomIsolated.**</span></span> <span data-ttu-id="e323a-126">Wcf-customisolated 适配器支持通过 HTTP 传输使用 Windows Communication Foundation (WCF) 扩展性功能。</span><span class="sxs-lookup"><span data-stu-id="e323a-126">The WCF-CustomIsolated adapter enables the use of Windows Communication Foundation (WCF) extensibility features over the HTTP transport.</span></span>  
  
6. <span data-ttu-id="e323a-127">上**WCF 服务类型**页上，选择**以下应用程序中的创建 BizTalk 接收位置**复选框以创建接收端口和对应于每个生成的.svc 文件的位置在中选择的 WCF 适配器**适配器名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e323a-127">On the **WCF Service Type** page, select the **Create BizTalk receive locations in the following application** check box to create the receive ports and locations corresponding to each generated .svc file for the WCF adapter that you selected in the **Adapter name** drop-down list.</span></span> <span data-ttu-id="e323a-128">如果接收位置已存在，则不会替换它。</span><span class="sxs-lookup"><span data-stu-id="e323a-128">If a receive location already exists, it is not replaced.</span></span> <span data-ttu-id="e323a-129">选择此选项后，选择应用程序中生成接收端口和位置**BizTalk 应用程序名称**下拉列表，再单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e323a-129">After selecting this option, choose the application where the receive ports and locations will be generated in the **BizTalk application name** drop-down list, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="e323a-130">上**创建 WCF 服务**页上，选择**将架构发布为 WCF 服务**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e323a-130">On the **Create WCF Service** page, select **Publish schemas as WCF service**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="e323a-131">![创建 WCF 服务页](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")</span><span class="sxs-lookup"><span data-stu-id="e323a-131">![Create WCF Service page](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")</span></span>  
  
8. <span data-ttu-id="e323a-132">上**WCF 服务**页上，选择要发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e323a-132">On the **WCF Service** page, define the WCF service(s) to publish.</span></span> <span data-ttu-id="e323a-133">使用中的树**Web 服务说明**对话框可以添加、 删除、 重命名和编辑要发布的 WCF 服务的 Web 服务说明节点。</span><span class="sxs-lookup"><span data-stu-id="e323a-133">Use the tree in the **Web service description** dialog box to add, remove, rename, and edit the Web service description nodes for the WCF services to publish.</span></span> <span data-ttu-id="e323a-134">**信息**对话框提供了有关所选节点的信息，并显示当前节点或子节点中的任何错误：</span><span class="sxs-lookup"><span data-stu-id="e323a-134">The **Information** dialog box provides information about the selected node and displays any errors in the current node or subnodes:</span></span>  
  
   -   <span data-ttu-id="e323a-135">（Web 服务说明） 的树的根节点描述了要发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e323a-135">The root node to the tree (Web service description) describes the WCF services to publish.</span></span> <span data-ttu-id="e323a-136">虚拟目录名称使用的根节点作为默认名称。</span><span class="sxs-lookup"><span data-stu-id="e323a-136">The virtual directory name uses the root node as the default name.</span></span> <span data-ttu-id="e323a-137">您可以修改要通过选择发布的 WCF 服务的 Web 服务说明名称**重命名 web 服务说明**。</span><span class="sxs-lookup"><span data-stu-id="e323a-137">You can modify the Web service description name for the WCF services to publish by selecting **Rename web service description**.</span></span>  
  
        <span data-ttu-id="e323a-138">![WCF 服务页](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")</span><span class="sxs-lookup"><span data-stu-id="e323a-138">![WCF Service page](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")</span></span>  
  
   -   <span data-ttu-id="e323a-139">Web 方法节点， **Operation1**，默认服务节点， **Service1**，默认情况下所示**Web 服务说明**对话框可用于请求-响应接收位置。</span><span class="sxs-lookup"><span data-stu-id="e323a-139">The Web method node, **Operation1**, of the default service node, **Service1**, shown by default in the **Web service description** dialog box can be used for a request-response receive location.</span></span> <span data-ttu-id="e323a-140">如果你打算发布一个单向 WCF 接收位置，用于此服务说明，右键单击默认的 Web 方法节点，单击**删除 web 方法**，然后创建一个单向 Web 方法，如下所示：右键单击默认服务节点，指向**添加 web 方法**，然后单击**单向**。</span><span class="sxs-lookup"><span data-stu-id="e323a-140">If you plan to publish a one-way WCF receive location for this service description, right-click the default Web method node, click **Delete web method**, and then create a one-way Web method as follows: Right-click the default service node, point to **Add web method**, and then click **One-Way**.</span></span>  
  
   -   <span data-ttu-id="e323a-141">若要添加新的 WCF 服务，右键单击 Web 服务说明的名称，然后依次**添加 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="e323a-141">To add a new WCF service, right-click the Web service description name, and then click **Add web service**.</span></span> <span data-ttu-id="e323a-142">这将创建一个新的 WCF 服务，而无需任何 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="e323a-142">This creates a new WCF service without any WCF operations.</span></span> <span data-ttu-id="e323a-143">若要修改 WCF 服务的名称，请右键单击 WCF 服务节点，单击**重命名 web 服务**，然后按 ENTER 以接受新名称。</span><span class="sxs-lookup"><span data-stu-id="e323a-143">To modify the name of the WCF service, right-click the WCF service node, click **Rename web service**, and then press ENTER to accept the new name.</span></span>  
  
   -   <span data-ttu-id="e323a-144">若要添加新的 WCF 操作，请右键单击 WCF 服务节点，指向**添加 Web 方法**，然后单击**单向**（对于请求 WCF 操作） 或**请求-响应**(为请求-响应 WCF 操作）。</span><span class="sxs-lookup"><span data-stu-id="e323a-144">To add a new WCF operation, right-click the WCF service node, point to **Add Web Method**, and then click **One-way** (for a request WCF operation) or **Request-response** (for a request-response WCF operation).</span></span>  
  
   -   <span data-ttu-id="e323a-145">若要设置的请求和响应架构类型，请右键单击**请求**或**响应**节点，，然后单击**选择架构类型**。</span><span class="sxs-lookup"><span data-stu-id="e323a-145">To set the request and response schema types, right-click the **Request** or **Response** node, and then click **Select schema type**.</span></span> <span data-ttu-id="e323a-146">在中**请求消息类型**框中，键入包含文档架构中的程序集名称**BizTalk 程序集文件**文本框中或单击**浏览**搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="e323a-146">In the **Request Message Type** dialog box, type the name of the assembly containing the document schema in the **BizTalk assembly file**text box or click **Browse** to search for the assembly.</span></span> <span data-ttu-id="e323a-147">**可用架构类型**列表视图中显示的架构的每个根元素。</span><span class="sxs-lookup"><span data-stu-id="e323a-147">The **Available schema types** list view displays each root element of the schema.</span></span> <span data-ttu-id="e323a-148">选择要添加为请求或响应架构类型的根节点。</span><span class="sxs-lookup"><span data-stu-id="e323a-148">Select a root node to add as the request or response schema type.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="e323a-149">如果在全局程序集缓存 (GAC) 中安装 BizTalk 程序集文件，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**请求消息类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="e323a-149">If you installed the BizTalk assembly file into the global assembly cache (GAC), make sure that the assembly in the GAC has been updated with the assembly that you will select in the **Request Message Type** dialog box.</span></span> <span data-ttu-id="e323a-150">如果 GAC 具有相同的完全限定的名称，BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是所选的一个。</span><span class="sxs-lookup"><span data-stu-id="e323a-150">If the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  
  
        <span data-ttu-id="e323a-151">![请求消息类型页](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")</span><span class="sxs-lookup"><span data-stu-id="e323a-151">![Request Message Type page](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")</span></span>  
  
   -   <span data-ttu-id="e323a-152">您可以重命名**请求**并**响应**节点而不会影响生成的代码。</span><span class="sxs-lookup"><span data-stu-id="e323a-152">You can rename the **Request** and **Response** nodes without affecting the generated code.</span></span> <span data-ttu-id="e323a-153">在之后定义了架构，您可以重命名部分元素中，这会修改 WCF 操作参数名称。</span><span class="sxs-lookup"><span data-stu-id="e323a-153">After defining your schemas, you can rename the part elements, which modifies the WCF operation parameter name.</span></span> <span data-ttu-id="e323a-154">通过查看要发布的 WCF 服务的服务元数据，可以看到所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e323a-154">You can see the changes by viewing the service metadata for the WCF services to publish.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="e323a-155">重命名任何 Web 服务说明节点时，不能使用空格。</span><span class="sxs-lookup"><span data-stu-id="e323a-155">You cannot use spaces when renaming any of the Web service description nodes.</span></span>  
  
9. <span data-ttu-id="e323a-156">单击**下一步**继续执行向导。</span><span class="sxs-lookup"><span data-stu-id="e323a-156">Click **Next** to continue the wizard.</span></span>  
  
10. <span data-ttu-id="e323a-157">上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e323a-157">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  
  
     <span data-ttu-id="e323a-158">![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="e323a-158">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  
  
11. <span data-ttu-id="e323a-159">上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。</span><span class="sxs-lookup"><span data-stu-id="e323a-159">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="e323a-160">您可以接受默认位置 (`http://localhost/<Web service description name>`)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。</span><span class="sxs-lookup"><span data-stu-id="e323a-160">You can accept the default location (`http://localhost/<Web service description name>`), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="e323a-161">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e323a-161">Select any of the following options:</span></span>  
  
    - <span data-ttu-id="e323a-162">**覆盖现有项目。**</span><span class="sxs-lookup"><span data-stu-id="e323a-162">**Overwrite existing project.**</span></span> <span data-ttu-id="e323a-163">此选项才可用，仅当 Web 目录已存在。</span><span class="sxs-lookup"><span data-stu-id="e323a-163">This option is available only if the Web directory already exists.</span></span> <span data-ttu-id="e323a-164">你将能够发布到相同位置，才选择此选项。</span><span class="sxs-lookup"><span data-stu-id="e323a-164">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="e323a-165">否则，必须输入不同的项目位置。</span><span class="sxs-lookup"><span data-stu-id="e323a-165">Otherwise, you must enter a different project location.</span></span>  
  
    - <span data-ttu-id="e323a-166">**允许匿名访问 WCF 服务。**</span><span class="sxs-lookup"><span data-stu-id="e323a-166">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="e323a-167">此选项将添加到创建的虚拟目录的匿名访问。</span><span class="sxs-lookup"><span data-stu-id="e323a-167">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="e323a-168">默认情况下，虚拟目录的访问权限从继承其父虚拟目录或 Web 站点 （如果它是顶级虚拟目录）。</span><span class="sxs-lookup"><span data-stu-id="e323a-168">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  
  
      <span data-ttu-id="e323a-169">在完成此页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e323a-169">When you finish this page, click **Next**.</span></span>  
  
      <span data-ttu-id="e323a-170">![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="e323a-170">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e323a-171">项目位置可位于其他服务器上。</span><span class="sxs-lookup"><span data-stu-id="e323a-171">The project location can exist on a different server.</span></span> <span data-ttu-id="e323a-172">若要将 WCF 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<WCF service location>`。</span><span class="sxs-lookup"><span data-stu-id="e323a-172">To publish the WCF services to a different server, type the project name as `http://<servername>/<WCF service location>`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e323a-173">项目位置可位于非默认网站上。</span><span class="sxs-lookup"><span data-stu-id="e323a-173">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="e323a-174">发布到非默认网站时，请在该 URL 中包括网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="e323a-174">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="e323a-175">例如，`http://<servername>:8080/<WCF service location>`。</span><span class="sxs-lookup"><span data-stu-id="e323a-175">For example, `http://<servername>:8080/<WCF service location>`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e323a-176">在使用向导创建接收位置时，向导会使用默认值创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="e323a-176">When using the wizard to create receive locations, the wizard creates the receive locations using the default values.</span></span> <span data-ttu-id="e323a-177">接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。</span><span class="sxs-lookup"><span data-stu-id="e323a-177">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** pipeline.</span></span> <span data-ttu-id="e323a-178">如果通过已发布的 WCF 服务接收的消息需要任何特殊的管道处理 （例如，验证、 关联/属性升级或入站/出站映射），则应将接收管道设置为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或通过使用 BizTalk 管理控制台中自定义管道。</span><span class="sxs-lookup"><span data-stu-id="e323a-178">If messages received through the published WCF services require any special pipeline processing (for example, validation, correlation/property promotion, or inbound/outbound maps) then you should set the receive pipeline to **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, or to a custom pipeline by using the BizTalk Administration console.</span></span>  
  
12. <span data-ttu-id="e323a-179">上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="e323a-179">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  
  
13. <span data-ttu-id="e323a-180">单击**创建**创建 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e323a-180">Click **Create** to create the WCF services.</span></span>  
  
14. <span data-ttu-id="e323a-181">单击**完成**完成 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="e323a-181">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  
  
15. <span data-ttu-id="e323a-182">发布 WCF 服务使用 BizTalk WCF 服务发布向导之后, 必须正确配置它们。</span><span class="sxs-lookup"><span data-stu-id="e323a-182">After publishing WCF services with the BizTalk WCF Service Publishing Wizard, you must configure them properly.</span></span> <span data-ttu-id="e323a-183">有关如何配置独立的 WCF 接收适配器，请参阅[如何使用 BizTalk WCF 服务发布向导配置 WCF 服务发布](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="e323a-183">For information about how to configure the isolated WCF receive adapter, see [How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e323a-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="e323a-184">See Also</span></span>  
 <span data-ttu-id="e323a-185">[如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e323a-185">[How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span></span>  
 <span data-ttu-id="e323a-186">[演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e323a-186">[Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span></span>  
 [<span data-ttu-id="e323a-187">如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e323a-187">How to Use the BizTalk WCF Service Publishing Wizard to Publish Orchestrations as WCF Services</span></span>](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)