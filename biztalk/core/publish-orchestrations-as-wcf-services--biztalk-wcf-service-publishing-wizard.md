---
title: 如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务 |Microsoft Docs
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
ms.openlocfilehash: c2e3edfb54f9864b0c5d17ed455d96df7e15b9ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398408"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-orchestrations-as-wcf-services"></a><span data-ttu-id="215b9-102">如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="215b9-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Orchestrations as WCF Services</span></span>
<span data-ttu-id="215b9-103">使用 BizTalk WCF 服务发布向导将业务流程作为 WCF 服务发布。</span><span class="sxs-lookup"><span data-stu-id="215b9-103">You use the BizTalk WCF Service Publishing Wizard to publish orchestrations as WCF services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="215b9-104">在运行 BizTalk WCF 服务发布向导前必须生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="215b9-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="215b9-105">BizTalk 项目必须包括至少具有一个接收的端口的类型修饰符是公共的业务流程。</span><span class="sxs-lookup"><span data-stu-id="215b9-105">The BizTalk projects must include orchestrations having at least one receive port whose type modifier is public.</span></span> <span data-ttu-id="215b9-106">创建端口时，此类型修饰符存在业务流程的属性中。</span><span class="sxs-lookup"><span data-stu-id="215b9-106">This type modifier exists in the properties for the orchestration when the port is created.</span></span>  
  
### <a name="to-publish-an-orchestration-as-a-wcf-service"></a><span data-ttu-id="215b9-107">若要将业务流程作为 WCF 服务发布</span><span class="sxs-lookup"><span data-stu-id="215b9-107">To publish an orchestration as a WCF service</span></span>  
  
1. <span data-ttu-id="215b9-108">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**BizTalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="215b9-108">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="215b9-109">若要创建并将 BizTalk 业务流程和架构发布为 WCF 适配器的 WCF 服务，你可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="215b9-109">To create and publish BizTalk orchestrations and schemas as WCF services with the WCF adapters, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="215b9-110">若要将业务流程和架构发布为 Web 服务使用 SOAP 适配器，您可以使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="215b9-110">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  
  
2. <span data-ttu-id="215b9-111">上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-111">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  
  
3. <span data-ttu-id="215b9-112">上**WCF 服务类型**页上，选择**服务终结点**上发布的 WCF 服务中选择选项，BizTalk 业务流程的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="215b9-112">On the **WCF Service Type** page, select **Service endpoint** option to publish the WCF services on selected BizTalk orchestrations in a BizTalk assembly.</span></span>  
  
    <span data-ttu-id="215b9-113">![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span><span class="sxs-lookup"><span data-stu-id="215b9-113">![WCF Service Type page](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span></span>  
  
4. <span data-ttu-id="215b9-114">上**WCF 服务类型**页上，选择**启用元数据终结点**复选框，指示是否独立的 WCF 接收位置由 Internet 信息服务 (IIS) 承载发布服务元数据使用 HTTP/GET 请求检索。</span><span class="sxs-lookup"><span data-stu-id="215b9-114">On the **WCF Service Type** page, select **Enable metadata endpoint** check-box to indicate whether the isolated WCF receive location hosted by Internet Information Services (IIS) publish service metadata for retrieval using an HTTP/GET request.</span></span> <span data-ttu-id="215b9-115">通过启用此复选框，向导生成的 Web.config 其中**httpGetEnabled**的属性 **\<serviceMetadata\>** 元素设置为 **，则返回 true**.</span><span class="sxs-lookup"><span data-stu-id="215b9-115">By enabling this check-box, the wizard generates Web.config where the **httpGetEnabled** attribute of the **\<serviceMetadata\>** element is set to **true**.</span></span> <span data-ttu-id="215b9-116">您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="215b9-116">You can use a metadata import tool (such as SvcUtil.exe) to generate the client code required to call this service in the development environment.</span></span> <span data-ttu-id="215b9-117">发布元数据的地址为终结点地址加上 **？ wsdl**查询字符串。</span><span class="sxs-lookup"><span data-stu-id="215b9-117">The address at which the metadata is published is the endpoint address plus a **?wsdl** query string.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="215b9-118">为了避免无意中泄漏可能的敏感服务元数据，建议在生产环境中禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="215b9-118">To prevent unintentional disclosure of potentially sensitive service metadata, it is recommended to disable this behavior on the production environment.</span></span> <span data-ttu-id="215b9-119">这可以通过将 httpgetenabled 设置为 false，或删除 MEX 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="215b9-119">This can be done by setting httpgetenabled to false, or deleting the MEX virtual directory.</span></span>  
  
5. <span data-ttu-id="215b9-120">上**WCF 服务类型**页上，在**适配器名称 （传输类型）** 下拉列表中，选择的 WCF 服务发布使用独立的 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="215b9-120">On the **WCF Service Type** page, in the **Adapter name (Transport type)** drop-down list, select the isolated WCF adapter with which the WCF services are published.</span></span> <span data-ttu-id="215b9-121">您可以选择任何以下适配器：</span><span class="sxs-lookup"><span data-stu-id="215b9-121">You can select any of the following adapters:</span></span>  
  
   -   <span data-ttu-id="215b9-122">**WCF-BasicHttp.**</span><span class="sxs-lookup"><span data-stu-id="215b9-122">**WCF-BasicHttp.**</span></span> <span data-ttu-id="215b9-123">Wcf-basichttp 适配器能够与 WS-基本配置文件 1.1 的 web 服务与基于 ASMX 的服务一样。</span><span class="sxs-lookup"><span data-stu-id="215b9-123">The WCF-BasicHttp adapter can communicate with WS-I Basic Profile 1.1-conformant Web services like ASMX-based services.</span></span>  
  
   -   <span data-ttu-id="215b9-124">**WCF-WSHttp.**</span><span class="sxs-lookup"><span data-stu-id="215b9-124">**WCF-WSHttp.**</span></span> <span data-ttu-id="215b9-125">Wcf-wshttp 适配器能够与服务的 WS-\* 标准通过 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="215b9-125">The WCF-WSHttp adapter can communicate with a service through the WS-\* standards over HTTP and HTTPS.</span></span>  
  
   -   <span data-ttu-id="215b9-126">**WCF CustomIsolated。**</span><span class="sxs-lookup"><span data-stu-id="215b9-126">**WCF-CustomIsolated.**</span></span> <span data-ttu-id="215b9-127">Wcf-customisolated 适配器支持通过 HTTP 传输使用 Windows Communication Foundation (WCF) 扩展性功能。</span><span class="sxs-lookup"><span data-stu-id="215b9-127">The WCF-CustomIsolated adapter enables the use of Windows Communication Foundation (WCF) extensibility features over the HTTP transport.</span></span>  
  
6. <span data-ttu-id="215b9-128">上**WCF 服务类型**页上，选择**以下应用程序中的创建 BizTalk 接收位置**复选框以创建接收端口和对应于每个生成的.svc 文件的位置在中选择的 WCF 适配器**适配器名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="215b9-128">On the **WCF Service Type** page, select the **Create BizTalk receive locations in the following application** check-box to create the receive ports and locations corresponding to each generated .svc file for the WCF adapter that you selected in the **Adapter name** drop-down list.</span></span> <span data-ttu-id="215b9-129">如果接收位置已存在，则不会替换它。</span><span class="sxs-lookup"><span data-stu-id="215b9-129">If a receive location already exists, it is not replaced.</span></span> <span data-ttu-id="215b9-130">选择此选项后，选择应用程序中生成接收端口和位置**BizTalk 应用程序名称**下拉列表，再单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-130">After selecting this option, choose the application where the receive ports and locations will be generated in the **BizTalk application name** drop-down list, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="215b9-131">上**创建 WCF 服务**页上，选择**BizTalk 业务流程发布为 WCF 服务**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-131">On the **Create WCF Service** page, select **Publish BizTalk orchestrations as WCF service**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="215b9-132">![创建 WCF 服务页](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span><span class="sxs-lookup"><span data-stu-id="215b9-132">![Create WCF Service page](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span></span>  
  
8. <span data-ttu-id="215b9-133">上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含业务流程的程序集以发布，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-133">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** text box, type the name of the BizTalk assembly file or click **Browse** to browse to the assembly containing the orchestration(s) to publish, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="215b9-134">之前选择 BizTalk 程序集文件，将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或依赖程序集安装到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="215b9-134">Before choosing a BizTalk assembly file, copy all of the dependent assemblies into the same folder with the BizTalk assembly or install the dependent assemblies to the global assembly cache (GAC).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="215b9-135">如果 BizTalk 程序集文件安装到 GAC 中时，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**BizTalk 程序集**对话框。</span><span class="sxs-lookup"><span data-stu-id="215b9-135">If you installed the BizTalk assembly file into the GAC, make sure that the assembly in the GAC has been updated with the assembly that you will select in the **BizTalk Assembly** dialog box.</span></span> <span data-ttu-id="215b9-136">如果 GAC 中的程序集具有相同的完全限定的名称，BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是所选。</span><span class="sxs-lookup"><span data-stu-id="215b9-136">If the assembly in the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="215b9-137">路径长度超过 260 个字符可能会导致错误消息的路径太长。</span><span class="sxs-lookup"><span data-stu-id="215b9-137">Paths over 260 characters long may cause an error message that the path is too long.</span></span>  
  
    <span data-ttu-id="215b9-138">![BizTalk 程序集页面](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span><span class="sxs-lookup"><span data-stu-id="215b9-138">![BizTalk Assembly page](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span></span>  
  
9. <span data-ttu-id="215b9-139">上**业务流程和端口**页上，单击加号 （+） 展开每个程序集和业务流程的树节点。</span><span class="sxs-lookup"><span data-stu-id="215b9-139">On the **Orchestrations and Ports** page, expand the tree nodes for each assembly and orchestration by clicking the plus sign (+).</span></span> <span data-ttu-id="215b9-140">选择业务流程和端口发布通过选中相应树节点复选框。</span><span class="sxs-lookup"><span data-stu-id="215b9-140">Select orchestrations and ports to publish by selecting the corresponding tree node check boxes.</span></span> <span data-ttu-id="215b9-141">如果你想要创建一个 WCF 服务 （.svc 文件） 的所有选定的接收端口，而不是一个 WCF 服务，每个接收端口，请选择**所有选定的端口合并为单个 WCF 服务**选项，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-141">If you want to create one WCF service (.svc file) for all of the selected receive ports instead of one WCF service for each receive port, select the **Merge all selected ports into a single WCF service** option, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="215b9-142">您将所有选定的端口合并为单个 WCF 服务时，所有选定端口都具有相同的端口类型，并且端口中的操作名称都是唯一。</span><span class="sxs-lookup"><span data-stu-id="215b9-142">When you merge all selected ports into a single WCF service, all of the selected ports have the same port type, and the operation names in the ports are unique.</span></span>  
  
     <span data-ttu-id="215b9-143">![操作和端口页](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span><span class="sxs-lookup"><span data-stu-id="215b9-143">![Operations and Ports page](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span></span>  
  
10. <span data-ttu-id="215b9-144">上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-144">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  
  
     <span data-ttu-id="215b9-145">![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="215b9-145">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  
  
11. <span data-ttu-id="215b9-146">上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。</span><span class="sxs-lookup"><span data-stu-id="215b9-146">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="215b9-147">您可以接受默认位置 (`http://localhost/<BizTalk Assembly Name>`)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。</span><span class="sxs-lookup"><span data-stu-id="215b9-147">You can accept the default location (`http://localhost/<BizTalk Assembly Name>`), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="215b9-148">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="215b9-148">Select any of the following options:</span></span>  
  
    - <span data-ttu-id="215b9-149">**覆盖现有项目。**</span><span class="sxs-lookup"><span data-stu-id="215b9-149">**Overwrite existing project.**</span></span> <span data-ttu-id="215b9-150">此选项才可用的 Web 目录已存在。</span><span class="sxs-lookup"><span data-stu-id="215b9-150">This option is only available if the Web directory already exists.</span></span> <span data-ttu-id="215b9-151">你将能够发布到相同位置，才选择此选项。</span><span class="sxs-lookup"><span data-stu-id="215b9-151">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="215b9-152">否则，必须输入不同的项目位置。</span><span class="sxs-lookup"><span data-stu-id="215b9-152">Otherwise, you must enter a different project location.</span></span>  
  
    - <span data-ttu-id="215b9-153">**允许匿名访问 WCF 服务。**</span><span class="sxs-lookup"><span data-stu-id="215b9-153">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="215b9-154">此选项将添加到创建的虚拟目录的匿名访问。</span><span class="sxs-lookup"><span data-stu-id="215b9-154">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="215b9-155">默认情况下，虚拟目录的访问权限从继承其父虚拟目录或 Web 站点 （如果它是顶级虚拟目录）。</span><span class="sxs-lookup"><span data-stu-id="215b9-155">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  
  
      <span data-ttu-id="215b9-156">在完成此页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="215b9-156">When you finish this page, click **Next**.</span></span>  
  
      <span data-ttu-id="215b9-157">![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="215b9-157">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="215b9-158">项目位置可位于其他服务器上。</span><span class="sxs-lookup"><span data-stu-id="215b9-158">The project location can exist on a different server.</span></span> <span data-ttu-id="215b9-159">若要将 WCF 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<WCF service location>`。</span><span class="sxs-lookup"><span data-stu-id="215b9-159">To publish the WCF services to a different server, type the project name as `http://<servername>/<WCF service location>`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="215b9-160">项目位置可位于非默认网站上。</span><span class="sxs-lookup"><span data-stu-id="215b9-160">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="215b9-161">发布到非默认网站时，请在该 URL 中包括网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="215b9-161">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="215b9-162">例如，`http://<servername>:8080/<WCF service location>`。</span><span class="sxs-lookup"><span data-stu-id="215b9-162">For example, `http://<servername>:8080/<WCF service location>`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="215b9-163">在使用向导创建接收位置时，向导会使用默认值创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="215b9-163">When using the wizard to create receive locations, the wizard creates the receive locations using the default values.</span></span> <span data-ttu-id="215b9-164">接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。</span><span class="sxs-lookup"><span data-stu-id="215b9-164">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** pipeline.</span></span> <span data-ttu-id="215b9-165">如果通过已发布的 WCF 服务接收的消息需要任何特殊的管道处理 （例如，验证、 关联/属性升级或入站/出站映射），则应将接收管道设置为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或到自定义管道，使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="215b9-165">If messages received through the published WCF services require any special pipeline processing (for example, validation, correlation/property promotion, or inbound/outbound maps) then you should set the receive pipeline to **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, or to a custom pipeline, using the BizTalk Server Administration console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="215b9-166">如果你决定不使用**业务流程发布为 WCF 服务**选项在上访问此页上之后,**创建 WCF 服务**页上，你可能会看到， **Web 服务说明**服务和方法名称从之前你所选择的 BizTalk 程序集的显示更改发布选项。</span><span class="sxs-lookup"><span data-stu-id="215b9-166">If you decide not to use the **Publishing orchestration as WCF service** option after you reach this page, on the **Create WCF Service** page, you may see that the **Web service description** displays the service and method names from the BizTalk assembly that you selected before you changed the publishing option.</span></span> <span data-ttu-id="215b9-167">这是因为更改发布方法时不会清除内存中 Web 服务说明。</span><span class="sxs-lookup"><span data-stu-id="215b9-167">This is because the in-memory Web service description is not cleared when the publishing method is changed.</span></span>  
  
12. <span data-ttu-id="215b9-168">上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="215b9-168">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  
  
13. <span data-ttu-id="215b9-169">单击**创建**创建 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="215b9-169">Click **Create** to create the WCF services.</span></span>  
  
14. <span data-ttu-id="215b9-170">单击**完成**完成 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="215b9-170">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  
  
15. <span data-ttu-id="215b9-171">发布 WCF 服务使用 BizTalk WCF 服务发布向导之后, 必须正确配置它们。</span><span class="sxs-lookup"><span data-stu-id="215b9-171">After publishing WCF services with the BizTalk WCF Service Publishing Wizard, you must configure them properly.</span></span> <span data-ttu-id="215b9-172">有关如何配置独立的 WCF 接收适配器，请参阅[如何使用 BizTalk WCF 服务发布向导配置 WCF 服务发布](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="215b9-172">For information about how to configure the isolated WCF receive adapter, see [How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="215b9-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="215b9-173">See Also</span></span>  
 <span data-ttu-id="215b9-174">[如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="215b9-174">[How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span></span>  
 <span data-ttu-id="215b9-175">[演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="215b9-175">[Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span></span>  
 [<span data-ttu-id="215b9-176">如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="215b9-176">How to Use the BizTalk WCF Service Publishing Wizard to Publish Schemas as WCF Services</span></span>](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)