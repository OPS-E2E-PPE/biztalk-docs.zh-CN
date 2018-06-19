---
title: 如何使用发布向导的 BizTalk WCF 服务发布作为 WCF 服务的业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tools, WCF Service Publishing Wizard
- WCF services, WCF Service Publishing Wizard
- WCF services, orchestrations
- publishing, orchestrations [WCF services]
- orchestrations, WCF services
- WCF Service Publishing Wizard
ms.assetid: db352132-2fe8-4d53-b239-45e5c3525b6c
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e233cfdd0871b55776cdf7cbaa9ee5b2af2724
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973419"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-orchestrations-as-wcf-services"></a><span data-ttu-id="b99a6-102">如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="b99a6-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Orchestrations as WCF Services</span></span>
<span data-ttu-id="b99a6-103">可使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b99a6-103">You use the BizTalk WCF Service Publishing Wizard to publish orchestrations as WCF services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b99a6-104">在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b99a6-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="b99a6-105">这些 BizTalk 项目必须包括至少具有一个公用类型修饰符的接收端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="b99a6-105">The BizTalk projects must include orchestrations having at least one receive port whose type modifier is public.</span></span> <span data-ttu-id="b99a6-106">在创建端口以后，此类型修饰符存在于该业务流程的属性中。</span><span class="sxs-lookup"><span data-stu-id="b99a6-106">This type modifier exists in the properties for the orchestration when the port is created.</span></span>  
  
### <a name="to-publish-an-orchestration-as-a-wcf-service"></a><span data-ttu-id="b99a6-107">将业务流程发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="b99a6-107">To publish an orchestration as a WCF service</span></span>  
  
1.  <span data-ttu-id="b99a6-108">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**BizTalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-108">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-109">若要创建 BizTalk 业务流程和架构并使用 WCF 适配器将其发布为 WCF 服务，可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="b99a6-109">To create and publish BizTalk orchestrations and schemas as WCF services with the WCF adapters, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="b99a6-110">若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="b99a6-110">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  
  
2.  <span data-ttu-id="b99a6-111">上**BizTalk WCF 服务发布向导欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-111">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="b99a6-112">上**WCF 服务类型**页上，选择**服务终结点**选项可将 WCF 服务发布上 BizTalk 程序集中选择 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="b99a6-112">On the **WCF Service Type** page, select **Service endpoint** option to publish the WCF services on selected BizTalk orchestrations in a BizTalk assembly.</span></span>  
  
     <span data-ttu-id="b99a6-113">![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span><span class="sxs-lookup"><span data-stu-id="b99a6-113">![WCF Service Type page](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span></span>  
  
4.  <span data-ttu-id="b99a6-114">上**WCF 服务类型**页上，选择**启用元数据终结点**复选框以指示是否隔离的 WCF 接收由 Internet 信息服务 (IIS) 承载的位置发布服务元数据有关使用 HTTP/GET 请求检索。</span><span class="sxs-lookup"><span data-stu-id="b99a6-114">On the **WCF Service Type** page, select **Enable metadata endpoint** check-box to indicate whether the isolated WCF receive location hosted by Internet Information Services (IIS) publish service metadata for retrieval using an HTTP/GET request.</span></span> <span data-ttu-id="b99a6-115">通过启用此复选框，则向导将生成 Web.config 其中**httpGetEnabled**属性 **\<serviceMetadata\>** 元素设置为**true**.</span><span class="sxs-lookup"><span data-stu-id="b99a6-115">By enabling this check-box, the wizard generates Web.config where the **httpGetEnabled** attribute of the **\<serviceMetadata\>** element is set to **true**.</span></span> <span data-ttu-id="b99a6-116">您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="b99a6-116">You can use a metadata import tool (such as SvcUtil.exe) to generate the client code required to call this service in the development environment.</span></span> <span data-ttu-id="b99a6-117">从该处发布元数据的地址为终结点地址加上 **？ wsdl**查询字符串。</span><span class="sxs-lookup"><span data-stu-id="b99a6-117">The address at which the metadata is published is the endpoint address plus a **?wsdl** query string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-118">为了避免无意中泄漏可能的敏感服务元数据，建议在生产环境中禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="b99a6-118">To prevent unintentional disclosure of potentially sensitive service metadata, it is recommended to disable this behavior on the production environment.</span></span> <span data-ttu-id="b99a6-119">这可通过将 httpgetenabled 设置为 false 完成，或删除 MEX 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="b99a6-119">This can be done by setting httpgetenabled to false, or deleting the MEX virtual directory.</span></span>  
  
5.  <span data-ttu-id="b99a6-120">上**WCF 服务类型**页上，在**适配器名称 （传输类型）** 下拉列表中，选择 WCF 服务发布使用独立的 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="b99a6-120">On the **WCF Service Type** page, in the **Adapter name (Transport type)** drop-down list, select the isolated WCF adapter with which the WCF services are published.</span></span> <span data-ttu-id="b99a6-121">可以选择以下任意适配器：</span><span class="sxs-lookup"><span data-stu-id="b99a6-121">You can select any of the following adapters:</span></span>  
  
    -   <span data-ttu-id="b99a6-122">**WCF BasicHttp。**</span><span class="sxs-lookup"><span data-stu-id="b99a6-122">**WCF-BasicHttp.**</span></span> <span data-ttu-id="b99a6-123">WCF-BasicHttp 适配器可与符合 WS-I Basic Profile 1.1 的 Web Services（如基于 ASMX 的服务）进行通信。</span><span class="sxs-lookup"><span data-stu-id="b99a6-123">The WCF-BasicHttp adapter can communicate with WS-I Basic Profile 1.1-conformant Web services like ASMX-based services.</span></span>  
  
    -   <span data-ttu-id="b99a6-124">**WCF WSHttp。**</span><span class="sxs-lookup"><span data-stu-id="b99a6-124">**WCF-WSHttp.**</span></span> <span data-ttu-id="b99a6-125">WCF-WSHttp 适配器可通过 HTTP 和 HTTPS 上的 WS-\* 标准与服务通信。</span><span class="sxs-lookup"><span data-stu-id="b99a6-125">The WCF-WSHttp adapter can communicate with a service through the WS-\* standards over HTTP and HTTPS.</span></span>  
  
    -   <span data-ttu-id="b99a6-126">**WCF CustomIsolated。**</span><span class="sxs-lookup"><span data-stu-id="b99a6-126">**WCF-CustomIsolated.**</span></span> <span data-ttu-id="b99a6-127">WCF-CustomIsolated 适配器支持通过 HTTP 传输使用 Windows Communication Foundation (WCF) 扩展性功能。</span><span class="sxs-lookup"><span data-stu-id="b99a6-127">The WCF-CustomIsolated adapter enables the use of Windows Communication Foundation (WCF) extensibility features over the HTTP transport.</span></span>  
  
6.  <span data-ttu-id="b99a6-128">上**WCF 服务类型**页上，选择**以下应用程序中的创建 BizTalk 接收位置**复选框以创建接收端口和对应于每个生成的.svc 文件的位置在中选择的 WCF 适配器**适配器名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="b99a6-128">On the **WCF Service Type** page, select the **Create BizTalk receive locations in the following application** check-box to create the receive ports and locations corresponding to each generated .svc file for the WCF adapter that you selected in the **Adapter name** drop-down list.</span></span> <span data-ttu-id="b99a6-129">如果接收位置已经存在，则不会替换它。</span><span class="sxs-lookup"><span data-stu-id="b99a6-129">If a receive location already exists, it is not replaced.</span></span> <span data-ttu-id="b99a6-130">选择此选项后，选择应用程序中生成的接收端口和位置**BizTalk 应用程序名称**下拉列表，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-130">After selecting this option, choose the application where the receive ports and locations will be generated in the **BizTalk application name** drop-down list, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="b99a6-131">上**创建 WCF 服务**页上，选择**作为 WCF 服务发布 BizTalk 业务流程**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-131">On the **Create WCF Service** page, select **Publish BizTalk orchestrations as WCF service**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b99a6-132">![创建 WCF 服务页](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span><span class="sxs-lookup"><span data-stu-id="b99a6-132">![Create WCF Service page](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span></span>  
  
8.  <span data-ttu-id="b99a6-133">上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含业务流程的程序集以发布，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-133">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** text box, type the name of the BizTalk assembly file or click **Browse** to browse to the assembly containing the orchestration(s) to publish, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-134">在选择 BizTalk 程序集文件前, 先将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或安装到全局程序集缓存 (GAC 中) 的依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="b99a6-134">Before choosing a BizTalk assembly file, copy all of the dependent assemblies into the same folder with the BizTalk assembly or install the dependent assemblies to the global assembly cache (GAC).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-135">如果 BizTalk 程序集文件安装到 GAC 中，请确保在 GAC 的程序集，已更新与程序集将在中选择**BizTalk 程序集**对话框。</span><span class="sxs-lookup"><span data-stu-id="b99a6-135">If you installed the BizTalk assembly file into the GAC, make sure that the assembly in the GAC has been updated with the assembly that you will select in the **BizTalk Assembly** dialog box.</span></span> <span data-ttu-id="b99a6-136">如果位于 GAC 中的程序集具有相同的完全限定的名，BizTalk WCF 服务发布向导将使用而不是所选的 GAC 中的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="b99a6-136">If the assembly in the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-137">路径长度超过 260 个字符时，可能会出现错误消息，指示路径太长。</span><span class="sxs-lookup"><span data-stu-id="b99a6-137">Paths over 260 characters long may cause an error message that the path is too long.</span></span>  
  
     <span data-ttu-id="b99a6-138">![BizTalk 程序集页](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span><span class="sxs-lookup"><span data-stu-id="b99a6-138">![BizTalk Assembly page](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span></span>  
  
9. <span data-ttu-id="b99a6-139">上**业务流程和端口**页上，单击加号 （+） 展开每个程序集和业务流程的树节点。</span><span class="sxs-lookup"><span data-stu-id="b99a6-139">On the **Orchestrations and Ports** page, expand the tree nodes for each assembly and orchestration by clicking the plus sign (+).</span></span> <span data-ttu-id="b99a6-140">选择业务流程和端口通过选择相应的树节点复选框来发布。</span><span class="sxs-lookup"><span data-stu-id="b99a6-140">Select orchestrations and ports to publish by selecting the corresponding tree node check boxes.</span></span> <span data-ttu-id="b99a6-141">如果你想要创建一个 WCF 服务 （.svc 文件） 的所有而不是一个 WCF 服务，每个所选的接收端口接收端口，请选择**合并到单个 WCF 服务的所有所选的端口**选项，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-141">If you want to create one WCF service (.svc file) for all of the selected receive ports instead of one WCF service for each receive port, select the **Merge all selected ports into a single WCF service** option, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-142">将所有选定端口合并到单个 WCF 服务后，所有选定端口都具有相同的端口类型，并且端口中的操作名称都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b99a6-142">When you merge all selected ports into a single WCF service, all of the selected ports have the same port type, and the operation names in the ports are unique.</span></span>  
  
     <span data-ttu-id="b99a6-143">![操作和端口页面](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span><span class="sxs-lookup"><span data-stu-id="b99a6-143">![Operations and Ports page](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span></span>  
  
10. <span data-ttu-id="b99a6-144">上**WCF 服务属性**页上，在**的 WCF 服务的 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-144">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b99a6-145">![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="b99a6-145">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  
  
11. <span data-ttu-id="b99a6-146">上**WCF 服务位置**页上，在**位置**文本框中，键入中生成的 WCF 服务的 Web 目录名称。</span><span class="sxs-lookup"><span data-stu-id="b99a6-146">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="b99a6-147">你可以接受默认位置 (http://localhost/ <*BizTalk 程序集名称*>)，键入用于中的 WCF 服务的位置**位置**文本框中或单击**浏览**并选择 Web 目录。</span><span class="sxs-lookup"><span data-stu-id="b99a6-147">You can accept the default location (http://localhost/<*BizTalk Assembly Name*>), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="b99a6-148">选择以下任何选项：</span><span class="sxs-lookup"><span data-stu-id="b99a6-148">Select any of the following options:</span></span>  
  
    -   <span data-ttu-id="b99a6-149">**覆盖现有项目。**</span><span class="sxs-lookup"><span data-stu-id="b99a6-149">**Overwrite existing project.**</span></span> <span data-ttu-id="b99a6-150">仅当 Web 目录已存在时，此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="b99a6-150">This option is only available if the Web directory already exists.</span></span> <span data-ttu-id="b99a6-151">仅当选择了此选项时，您才能够发布到同一位置。</span><span class="sxs-lookup"><span data-stu-id="b99a6-151">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="b99a6-152">否则，必须输入不同的项目位置。</span><span class="sxs-lookup"><span data-stu-id="b99a6-152">Otherwise, you must enter a different project location.</span></span>  
  
    -   <span data-ttu-id="b99a6-153">**允许匿名访问 WCF 服务。**</span><span class="sxs-lookup"><span data-stu-id="b99a6-153">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="b99a6-154">此选项会为已创建的虚拟目录添加匿名访问权限。</span><span class="sxs-lookup"><span data-stu-id="b99a6-154">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="b99a6-155">默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b99a6-155">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  
  
     <span data-ttu-id="b99a6-156">在完成此页，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b99a6-156">When you finish this page, click **Next**.</span></span>  
  
     <span data-ttu-id="b99a6-157">![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="b99a6-157">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-158">项目位置可位于其他服务器上。</span><span class="sxs-lookup"><span data-stu-id="b99a6-158">The project location can exist on a different server.</span></span> <span data-ttu-id="b99a6-159">若要将 WCF 服务发布到不同的服务器，键入项目名称，作为 http://&lt*servername*>/<*WCF 服务位置*>。</span><span class="sxs-lookup"><span data-stu-id="b99a6-159">To publish the WCF services to a different server, type the project name as http://<*servername*>/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-160">项目位置可位于非默认网站上。</span><span class="sxs-lookup"><span data-stu-id="b99a6-160">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="b99a6-161">发布到非默认网站时，请在该 URL 中包括网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="b99a6-161">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="b99a6-162">例如，http://&lt*servername*>: 8080 / <*WCF 服务位置*>。</span><span class="sxs-lookup"><span data-stu-id="b99a6-162">For example, http://<*servername*>:8080/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-163">在使用向导创建接收位置时，向导会使用默认值创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="b99a6-163">When using the wizard to create receive locations, the wizard creates the receive locations using the default values.</span></span> <span data-ttu-id="b99a6-164">接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。</span><span class="sxs-lookup"><span data-stu-id="b99a6-164">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** pipeline.</span></span> <span data-ttu-id="b99a6-165">如果通过已发布的 WCF 服务接收的消息需要任何特殊的管道处理 （例如，验证、 相关/属性提升或入站/出站映射），则应将接收管道设置为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或到自定义管道，使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b99a6-165">If messages received through the published WCF services require any special pipeline processing (for example, validation, correlation/property promotion, or inbound/outbound maps) then you should set the receive pipeline to **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, or to a custom pipeline, using the BizTalk Server Administration console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b99a6-166">如果你决定不使用**发布作为 WCF 服务的业务流程**选项在上访问此页上之后,**创建 WCF 服务**页上，你可能会看到， **Web 服务描述**的服务和方法名称从之前选择的 BizTalk 程序集的显示更改发布选项。</span><span class="sxs-lookup"><span data-stu-id="b99a6-166">If you decide not to use the **Publishing orchestration as WCF service** option after you reach this page, on the **Create WCF Service** page, you may see that the **Web service description** displays the service and method names from the BizTalk assembly that you selected before you changed the publishing option.</span></span> <span data-ttu-id="b99a6-167">这是因为更改发布方法时不会清除内存中的 Web 服务说明。</span><span class="sxs-lookup"><span data-stu-id="b99a6-167">This is because the in-memory Web service description is not cleared when the publishing method is changed.</span></span>  
  
12. <span data-ttu-id="b99a6-168">上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="b99a6-168">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  
  
13. <span data-ttu-id="b99a6-169">单击**创建**创建 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b99a6-169">Click **Create** to create the WCF services.</span></span>  
  
14. <span data-ttu-id="b99a6-170">单击**完成**完成 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="b99a6-170">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  
  
15. <span data-ttu-id="b99a6-171">使用 BizTalk WCF 服务发布向导发布 WCF 服务之后，必须对其进行正确配置。</span><span class="sxs-lookup"><span data-stu-id="b99a6-171">After publishing WCF services with the BizTalk WCF Service Publishing Wizard, you must configure them properly.</span></span> <span data-ttu-id="b99a6-172">有关如何配置独立的 WCF 接收适配器，请参阅[如何通过 BizTalk WCF 服务发布向导配置 WCF 服务发布](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="b99a6-172">For information about how to configure the isolated WCF receive adapter, see [How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b99a6-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b99a6-173">See Also</span></span>  
 <span data-ttu-id="b99a6-174">[如何配置与 BizTalk WCF 服务发布向导发布的 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="b99a6-174">[How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span></span>  
 <span data-ttu-id="b99a6-175">[演练： 使用 WCF BasicHttp 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b99a6-175">[Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span></span>  
 [<span data-ttu-id="b99a6-176">如何使用发布向导的 BizTalk WCF 服务发布作为 WCF 服务的架构</span><span class="sxs-lookup"><span data-stu-id="b99a6-176">How to Use the BizTalk WCF Service Publishing Wizard to Publish Schemas as WCF Services</span></span>](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)