---
title: 如何使用发布向导的 BizTalk WCF 服务的 WCF 接收位置发布服务元数据绑定到业务流程端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, orchestration ports
- WCF services, metadata
- orchestrations, WCF services
ms.assetid: 04ccce9f-8d18-433a-8299-d06fa155db06
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dce9a66465285dc16f8de804c7a6e99fa7e62a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975043"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-bound-to-an-orchestration-port"></a><span data-ttu-id="6333c-102">如何使用 BizTalk WCF 服务发布向导为已绑定到业务流程端口的 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="6333c-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location Bound to an Orchestration Port</span></span>
<span data-ttu-id="6333c-103">您可以使用 BizTalk WCF 服务发布向导创建 WCF 服务，以便为已绑定到业务流程端口的现有 WCF 接收位置发布服务元数据。</span><span class="sxs-lookup"><span data-stu-id="6333c-103">You use the BizTalk WCF Service Publishing Wizard to create a WCF service to publish service metadata for existing WCF receive locations bound to orchestration ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6333c-104">在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6333c-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="6333c-105">这些 BizTalk 项目必须包括至少具有一个公用类型修饰符的接收端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6333c-105">The BizTalk projects must include orchestrations having at least one receive port whose type modifier is public.</span></span> <span data-ttu-id="6333c-106">在发布服务元数据的 WCF 适配器之前，你还必须创建 WCF 使用 BizTalk 管理控制台或包含的 BTSTask 命令行工具接收位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6333c-106">Before you publish service metadata for the WCF adapters, you must also create the WCF receive locations by using the BizTalk Administration console or the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6333c-107">有关如何创建 WCF 的详细信息接收位置，请参阅中的每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="6333c-107">For more information about how to create a WCF receive location, see the appropriate topic for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-bound-to-an-orchestration-port"></a><span data-ttu-id="6333c-108">为已绑定到业务流程端口的现有 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="6333c-108">To publish service metadata for an existing WCF receive location bound to an orchestration port</span></span>  
  
1.  <span data-ttu-id="6333c-109">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="6333c-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-110">若要为 BizTalk 业务流程和架构创建并发布 WCF 服务元数据，可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="6333c-110">To create and publish WCF serve metadata for BizTalk orchestrations and schemas, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="6333c-111">若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="6333c-111">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  
  
2.  <span data-ttu-id="6333c-112">上**BizTalk WCF 服务发布向导欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6333c-112">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="6333c-113">上**WCF 服务类型**页上，选择**元数据仅终结点 (MEX)** 选项可将发布为提供 WCF 服务元数据的 WCF 服务接收将在下一步中选择的位置。</span><span class="sxs-lookup"><span data-stu-id="6333c-113">On the **WCF Service Type** page, select the **Metdata only endpoint (MEX)** option to publish the WCF services to provide service metadata for the WCF receive location that you will select in the next step.</span></span>  
  
     <span data-ttu-id="6333c-114">![WCF 服务类型页](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span><span class="sxs-lookup"><span data-stu-id="6333c-114">![WCF Service Type page](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span></span>  
  
4.  <span data-ttu-id="6333c-115">上**WCF 服务类型**页上，在**发布元数据接收位置**下拉列表中，选择 WCF 接收位置以发布服务元数据，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="6333c-115">On the **WCF Service Type** page, in the **Publish metadata for receive location** drop-down list, select a WCF receive location to publish service metadata for, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="6333c-116">上**创建 WCF 服务**页上，选择**作为 WCF 服务发布 BizTalk 业务流程**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6333c-116">On the **Create WCF Service** page, select **Publish BizTalk orchestrations as WCF service**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="6333c-117">![创建 WCF 服务页](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span><span class="sxs-lookup"><span data-stu-id="6333c-117">![Create WCF Service page](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span></span>  
  
6.  <span data-ttu-id="6333c-118">上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含业务流程的程序集以发布服务元数据，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6333c-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** text box, type the name of the BizTalk assembly file or click **Browse** to browse to the assembly containing the orchestration(s) to publish service metadata for, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-119">在选择 BizTalk 程序集文件之前, 将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或安装到全局程序集缓存 (GAC 中) 的依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="6333c-119">Before selecting a BizTalk assembly file, copy all of the dependent assemblies into the same folder with the BizTalk assembly or install the dependent assemblies to the global assembly cache (GAC).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-120">如果 BizTalk 程序集文件安装到 GAC 中，请确保在 GAC 的程序集，已更新与程序集将在中选择**BizTalk 程序集**对话框。</span><span class="sxs-lookup"><span data-stu-id="6333c-120">If you installed the BizTalk assembly file into the GAC, make sure that the assembly in the GAC has been updated with the assembly that you will select in the **BizTalk Assembly** dialog box.</span></span> <span data-ttu-id="6333c-121">如果位于 GAC 中的程序集具有相同的完全限定的名，BizTalk WCF 服务发布向导将使用而不是所选的 GAC 中的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="6333c-121">If the assembly in the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-122">路径长度超过 260 个字符时，可能会出现错误消息，指示路径太长。</span><span class="sxs-lookup"><span data-stu-id="6333c-122">Paths over 260 characters long may cause an error message that the path is too long.</span></span>  
  
     <span data-ttu-id="6333c-123">![BizTalk 程序集页](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span><span class="sxs-lookup"><span data-stu-id="6333c-123">![BizTalk Assembly page](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span></span>  
  
7.  <span data-ttu-id="6333c-124">上**业务流程和端口**页上，单击加号 （+） 展开每个程序集和业务流程的树节点。</span><span class="sxs-lookup"><span data-stu-id="6333c-124">On the **Orchestrations and Ports** page, expand the tree nodes for each assembly and orchestration by clicking the plus sign (+).</span></span> <span data-ttu-id="6333c-125">选中相应树节点的复选框以选择要为其发布元数据的业务流程和端口。</span><span class="sxs-lookup"><span data-stu-id="6333c-125">Select orchestrations and ports to publish metadata for by selecting the corresponding tree node check boxes.</span></span> <span data-ttu-id="6333c-126">如果你想要创建一个 WCF 服务 （.svc 文件） 的所有而不是一个 WCF 服务，每个所选的接收端口接收端口，请选择**合并到单个 WCF 服务的所有所选的端口**选项，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6333c-126">If you want to create one WCF service (.svc file) for all of the selected receive ports instead of one WCF service for each receive port, select the **Merge all selected ports into a single WCF service** option, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-127">将所有选定端口合并到单个 WCF 服务后，所有选定端口都具有相同的端口类型，并且端口中的操作名称都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6333c-127">When you merge all selected ports into a single WCF service, all of the selected ports have the same port type, and the operation names in the ports are unique.</span></span>  
  
     <span data-ttu-id="6333c-128">![操作和端口页面](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span><span class="sxs-lookup"><span data-stu-id="6333c-128">![Operations and Ports page](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span></span>  
  
8.  <span data-ttu-id="6333c-129">上**WCF 服务属性**页上，在**的 WCF 服务的 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6333c-129">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  
  
     <span data-ttu-id="6333c-130">![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="6333c-130">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  
  
9. <span data-ttu-id="6333c-131">上**WCF 服务位置**页上，在**位置**文本框中，键入中生成的 WCF 服务的 Web 目录名称。</span><span class="sxs-lookup"><span data-stu-id="6333c-131">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="6333c-132">你可以接受默认位置 (http://localhost/ <*BizTalk 程序集名称*>)，键入用于中的 WCF 服务的位置**位置**文本框中或单击**浏览**并选择 Web 目录。</span><span class="sxs-lookup"><span data-stu-id="6333c-132">You can accept the default location (http://localhost/<*BizTalk Assembly Name*>), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="6333c-133">选择以下任何选项：</span><span class="sxs-lookup"><span data-stu-id="6333c-133">Select any of the following options:</span></span>  
  
    -   <span data-ttu-id="6333c-134">**覆盖现有项目。**</span><span class="sxs-lookup"><span data-stu-id="6333c-134">**Overwrite existing project.**</span></span> <span data-ttu-id="6333c-135">此选项是 Web 目录已存在时才可用。</span><span class="sxs-lookup"><span data-stu-id="6333c-135">This option is available only if the Web directory already exists.</span></span> <span data-ttu-id="6333c-136">仅当选择了此选项时，您才能够发布到同一位置。</span><span class="sxs-lookup"><span data-stu-id="6333c-136">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="6333c-137">否则，必须输入不同的项目位置。</span><span class="sxs-lookup"><span data-stu-id="6333c-137">Otherwise, you must enter a different project location.</span></span>  
  
    -   <span data-ttu-id="6333c-138">**允许匿名访问 WCF 服务。**</span><span class="sxs-lookup"><span data-stu-id="6333c-138">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="6333c-139">此选项会为已创建的虚拟目录添加匿名访问权限。</span><span class="sxs-lookup"><span data-stu-id="6333c-139">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="6333c-140">默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6333c-140">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  
  
     <span data-ttu-id="6333c-141">在完成此页，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6333c-141">When you finish this page, click **Next**.</span></span>  
  
     <span data-ttu-id="6333c-142">![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="6333c-142">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-143">项目位置可位于其他服务器上。</span><span class="sxs-lookup"><span data-stu-id="6333c-143">The project location can exist on a different server.</span></span> <span data-ttu-id="6333c-144">若要将 WCF 服务发布到不同的服务器，键入项目名称，作为 http://&lt*servername*>/<*WCF 服务位置*>。</span><span class="sxs-lookup"><span data-stu-id="6333c-144">To publish the WCF services to a different server, type the project name as http://<*servername*>/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-145">项目位置可位于非默认网站上。</span><span class="sxs-lookup"><span data-stu-id="6333c-145">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="6333c-146">发布到非默认网站时，请在该 URL 中包括网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="6333c-146">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="6333c-147">例如，http://&lt*servername*>: 8080 / <*WCF 服务位置*>。</span><span class="sxs-lookup"><span data-stu-id="6333c-147">For example, http://<*servername*>:8080/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-148">向导将创建 Web 应用程序的 App_DataTemp 文件夹中的 BindingInfo.xml 文件管道中使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="6333c-148">The BindingInfo.xml file that the wizard creates in the App_DataTemp folder of the Web application uses the default values for the pipelines.</span></span> <span data-ttu-id="6333c-149">接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.XMLReceive**管道，而默认值为发送管道**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**管道。</span><span class="sxs-lookup"><span data-stu-id="6333c-149">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.XMLReceive** pipeline, and the default value for the send pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** pipeline.</span></span>  
  
10. <span data-ttu-id="6333c-150">上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="6333c-150">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  
  
11. <span data-ttu-id="6333c-151">单击**创建**创建 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6333c-151">Click **Create** to create the WCF services.</span></span>  
  
12. <span data-ttu-id="6333c-152">单击**完成**完成 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="6333c-152">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  
  
### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a><span data-ttu-id="6333c-153">为发布服务元数据配置 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="6333c-153">To configure the Web application for publishing service metadata</span></span>  
  
1.  <span data-ttu-id="6333c-154">为 BizTalk WCF 服务发布向导创建的 Web 应用程序启用 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="6333c-154">Enable ASP.NET for the Web application that the BizTalk WCF Service Publishing Wizard created.</span></span> <span data-ttu-id="6333c-155">有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="6333c-155">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-156">如果使用的是 Windows Server 2008 或 Windows Vista，则必须将应用程序池的标识帐户添加到 BizTalk Server Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="6333c-156">If you are using Windows Server 2008 or Windows Vista, you must add the Identity Account of the Application Pool to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6333c-157">将相应帐户添加到 BizTalk Server Administrators 组之后，需要重新启动 IIS 服务以使设置生效。</span><span class="sxs-lookup"><span data-stu-id="6333c-157">After you add the appropriate account to the BizTalk Server Administrators group, you need to restart the IIS service fro the setting to take effect.</span></span>  
  
2.  <span data-ttu-id="6333c-158">打开命令提示符，请转到 BizTalk WCF 服务发布向导中为 %SystemDrive%\InetPub 而创建的 WCF 服务的文件夹\\，然后打开 Web.config 文件使用记事本。</span><span class="sxs-lookup"><span data-stu-id="6333c-158">Open a command prompt, go to the folder where the BizTalk WCF Service Publishing Wizard created the WCF services in %SystemDrive%\InetPub\\, and then open the Web.config file using Notepad.</span></span>  
  
3.  <span data-ttu-id="6333c-159">在记事本中，添加以下代码行内的 **\<system.web\>** 元素：</span><span class="sxs-lookup"><span data-stu-id="6333c-159">In Notepad, add the following line inside the **\<system.web\>** element:</span></span>  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6333c-160">此设置是可选的，用于向已发布的 WCF 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6333c-160">This setting is optional and it grants the ASP.NET application hosting the published WCF service access to any resource that is subject to operating system security.</span></span> <span data-ttu-id="6333c-161">如果在已发布的 WCF 服务所在的计算机上安装并运行了 Windows SharePoint Services，则这是 WCF 所必需的信任级别。</span><span class="sxs-lookup"><span data-stu-id="6333c-161">This is the trust level that WCF requires when you have Windows SharePoint Services installed and running on the same machine with the published WCF services.</span></span>  
  
4.  <span data-ttu-id="6333c-162">在 Internet Explorer 中，在**地址**框中，键入使用格式 http:// 的 WCF 服务的 URL*主机 [: 端口]*/*apppath* /*wcfservicename.svc*若要测试已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6333c-162">In Internet Explorer, in the **Address** box, type the URL for the WCF service using the format http://*host[:port]*/*apppath*/*wcfservicename.svc* to test the published WCF service.</span></span> <span data-ttu-id="6333c-163">以下表所述的参数。</span><span class="sxs-lookup"><span data-stu-id="6333c-163">The parameters are described in the following table.</span></span>  
  
    |<span data-ttu-id="6333c-164">参数</span><span class="sxs-lookup"><span data-stu-id="6333c-164">Parameter</span></span>|<span data-ttu-id="6333c-165">值</span><span class="sxs-lookup"><span data-stu-id="6333c-165">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="6333c-166">*主机 [: 端口]*</span><span class="sxs-lookup"><span data-stu-id="6333c-166">*host[:port]*</span></span>|<span data-ttu-id="6333c-167">在其中部署了你的 WCF 服务的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="6333c-167">The name of the computer where you have deployed your WCF service.</span></span> <span data-ttu-id="6333c-168">此服务器名称后面可跟冒号和端口号。</span><span class="sxs-lookup"><span data-stu-id="6333c-168">A colon and the port number can follow this server name.</span></span>|  
    |<span data-ttu-id="6333c-169">*apppath*</span><span class="sxs-lookup"><span data-stu-id="6333c-169">*apppath*</span></span>|<span data-ttu-id="6333c-170">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="6333c-170">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="6333c-171">*wcfservicename.svc*</span><span class="sxs-lookup"><span data-stu-id="6333c-171">*wcfservicename.svc*</span></span>|<span data-ttu-id="6333c-172">WCF 服务 .svc 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6333c-172">The name of the WCF service .svc file.</span></span>|  
  
5.  <span data-ttu-id="6333c-173">为了避免无意中泄漏可能敏感的服务元数据，我们建议执行下列任务以在生产环境中禁止此行为：</span><span class="sxs-lookup"><span data-stu-id="6333c-173">To prevent unintentional disclosure of potentially sensitive service metadata, we recommend that you disable this behavior in the production environment by performing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="6333c-174">在记事本中，打开 BizTalk WCF 服务发布向导中为 %SystemDrive%\InetPub 而创建的 WCF 服务的文件夹中的 Web.config\\。</span><span class="sxs-lookup"><span data-stu-id="6333c-174">In Notepad, open Web.config in the folder where the BizTalk WCF Service Publishing Wizard created the WCF service in %SystemDrive%\InetPub\\.</span></span>  
  
    2.  <span data-ttu-id="6333c-175">在记事本中，设置**httpGetEnabled**属性中 **\<serviceMetadata\>** 元素为 false，如下所示的以下行：</span><span class="sxs-lookup"><span data-stu-id="6333c-175">In Notepad, set the  the **httpGetEnabled** attribute in the  **\<serviceMetadata\>** element to false as in the following line:</span></span>  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="6333c-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6333c-176">See Also</span></span>  
 <span data-ttu-id="6333c-177">[如何使用发布向导的 BizTalk WCF 服务的 WCF 接收位置用于基于内容的路由发布服务元数据](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md) </span><span class="sxs-lookup"><span data-stu-id="6333c-177">[How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location for Content-Based Routing](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md) </span></span>  
 [<span data-ttu-id="6333c-178">演练：通过 WCF-NetMsmq 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="6333c-178">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)