---
title: 如何使用 BizTalk WCF 服务发布向导的 WCF 接收位置发布服务元数据绑定到业务流程端口 |Microsoft Docs
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
ms.openlocfilehash: 7055531629ec3eadded9562d043fb8a31d7fe11e
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752454"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-bound-to-an-orchestration-port"></a><span data-ttu-id="6b1b7-102">如何使用 BizTalk WCF 服务发布向导为已绑定到业务流程端口的 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="6b1b7-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location Bound to an Orchestration Port</span></span>
<span data-ttu-id="6b1b7-103">您可以使用 BizTalk WCF 服务发布向导创建 WCF 服务，以便为已绑定到业务流程端口的现有 WCF 接收位置发布服务元数据。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-103">You use the BizTalk WCF Service Publishing Wizard to create a WCF service to publish service metadata for existing WCF receive locations bound to orchestration ports.</span></span>  

> [!NOTE]
>  <span data-ttu-id="6b1b7-104">在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="6b1b7-105">这些 BizTalk 项目必须包括至少具有一个公用类型修饰符的接收端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-105">The BizTalk projects must include orchestrations having at least one receive port whose type modifier is public.</span></span> <span data-ttu-id="6b1b7-106">发布为 WCF 适配器的服务元数据之前，您还必须创建 WCF 接收位置使用 BizTalk 管理控制台或附带的 BTSTask 命令行工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-106">Before you publish service metadata for the WCF adapters, you must also create the WCF receive locations by using the BizTalk Administration console or the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6b1b7-107">详细了解如何创建 WCF 接收位置，请参阅中每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-107">For more information about how to create a WCF receive location, see the appropriate topic for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  

### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-bound-to-an-orchestration-port"></a><span data-ttu-id="6b1b7-108">为已绑定到业务流程端口的现有 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="6b1b7-108">To publish service metadata for an existing WCF receive location bound to an orchestration port</span></span>  

1. <span data-ttu-id="6b1b7-109">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-110">若要为 BizTalk 业务流程和架构创建并发布 WCF 服务元数据，可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-110">To create and publish WCF serve metadata for BizTalk orchestrations and schemas, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="6b1b7-111">若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-111">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  

2. <span data-ttu-id="6b1b7-112">上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-112">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  

3. <span data-ttu-id="6b1b7-113">上**WCF 服务类型**页上，选择**元数据仅终结点 (MEX)** 选项来发布 WCF 服务以提供服务元数据为 WCF 接收位置将在下一步中选择。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-113">On the **WCF Service Type** page, select the **Metdata only endpoint (MEX)** option to publish the WCF services to provide service metadata for the WCF receive location that you will select in the next step.</span></span>  

    <span data-ttu-id="6b1b7-114">![WCF 服务类型页](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span><span class="sxs-lookup"><span data-stu-id="6b1b7-114">![WCF Service Type page](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span></span>  

4. <span data-ttu-id="6b1b7-115">上**WCF 服务类型**页上，在**接收位置发布元数据用于**下拉列表中，选择 WCF 接收位置发布服务元数据，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-115">On the **WCF Service Type** page, in the **Publish metadata for receive location** drop-down list, select a WCF receive location to publish service metadata for, and then click **Next**.</span></span>  

5. <span data-ttu-id="6b1b7-116">上**创建 WCF 服务**页上，选择**BizTalk 业务流程发布为 WCF 服务**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-116">On the **Create WCF Service** page, select **Publish BizTalk orchestrations as WCF service**, and then click **Next**.</span></span>  

    <span data-ttu-id="6b1b7-117">![创建 WCF 服务页](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span><span class="sxs-lookup"><span data-stu-id="6b1b7-117">![Create WCF Service page](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span></span>  

6. <span data-ttu-id="6b1b7-118">上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含业务流程的程序集以发布服务元数据，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** text box, type the name of the BizTalk assembly file or click **Browse** to browse to the assembly containing the orchestration(s) to publish service metadata for, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-119">之前选择 BizTalk 程序集文件，将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或依赖程序集安装到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-119">Before selecting a BizTalk assembly file, copy all of the dependent assemblies into the same folder with the BizTalk assembly or install the dependent assemblies to the global assembly cache (GAC).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-120">如果 BizTalk 程序集文件安装到 GAC 中时，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**BizTalk 程序集**对话框。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-120">If you installed the BizTalk assembly file into the GAC, make sure that the assembly in the GAC has been updated with the assembly that you will select in the **BizTalk Assembly** dialog box.</span></span> <span data-ttu-id="6b1b7-121">如果 GAC 中的程序集具有相同的完全限定的名称，BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是所选。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-121">If the assembly in the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-122">路径长度超过 260 个字符时，可能会出现错误消息，指示路径太长。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-122">Paths over 260 characters long may cause an error message that the path is too long.</span></span>  

    <span data-ttu-id="6b1b7-123">![BizTalk 程序集页面](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span><span class="sxs-lookup"><span data-stu-id="6b1b7-123">![BizTalk Assembly page](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span></span>  

7. <span data-ttu-id="6b1b7-124">上**业务流程和端口**页上，单击加号 （+） 展开每个程序集和业务流程的树节点。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-124">On the **Orchestrations and Ports** page, expand the tree nodes for each assembly and orchestration by clicking the plus sign (+).</span></span> <span data-ttu-id="6b1b7-125">选中相应树节点的复选框以选择要为其发布元数据的业务流程和端口。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-125">Select orchestrations and ports to publish metadata for by selecting the corresponding tree node check boxes.</span></span> <span data-ttu-id="6b1b7-126">如果你想要创建一个 WCF 服务 （.svc 文件） 的所有选定的接收端口，而不是一个 WCF 服务，每个接收端口，请选择**所有选定的端口合并为单个 WCF 服务**选项，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-126">If you want to create one WCF service (.svc file) for all of the selected receive ports instead of one WCF service for each receive port, select the **Merge all selected ports into a single WCF service** option, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-127">将所有选定端口合并到单个 WCF 服务后，所有选定端口都具有相同的端口类型，并且端口中的操作名称都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-127">When you merge all selected ports into a single WCF service, all of the selected ports have the same port type, and the operation names in the ports are unique.</span></span>  

    <span data-ttu-id="6b1b7-128">![操作和端口页](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span><span class="sxs-lookup"><span data-stu-id="6b1b7-128">![Operations and Ports page](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span></span>  

8. <span data-ttu-id="6b1b7-129">上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-129">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  

    <span data-ttu-id="6b1b7-130">![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="6b1b7-130">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  

9. <span data-ttu-id="6b1b7-131">上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-131">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="6b1b7-132">您可以接受默认位置 (`http://localhost/<BizTalk Assembly Name>`)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-132">You can accept the default location (`http://localhost/<BizTalk Assembly Name>`), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="6b1b7-133">选择以下任何选项：</span><span class="sxs-lookup"><span data-stu-id="6b1b7-133">Select any of the following options:</span></span>  

   - <span data-ttu-id="6b1b7-134">**覆盖现有项目。**</span><span class="sxs-lookup"><span data-stu-id="6b1b7-134">**Overwrite existing project.**</span></span> <span data-ttu-id="6b1b7-135">此选项才可用，仅当 Web 目录已存在。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-135">This option is available only if the Web directory already exists.</span></span> <span data-ttu-id="6b1b7-136">仅当选择了此选项时，您才能够发布到同一位置。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-136">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="6b1b7-137">否则，必须输入不同的项目位置。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-137">Otherwise, you must enter a different project location.</span></span>  

   - <span data-ttu-id="6b1b7-138">**允许匿名访问 WCF 服务。**</span><span class="sxs-lookup"><span data-stu-id="6b1b7-138">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="6b1b7-139">此选项会为已创建的虚拟目录添加匿名访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-139">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="6b1b7-140">默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-140">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  

     <span data-ttu-id="6b1b7-141">在完成此页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-141">When you finish this page, click **Next**.</span></span>  

     <span data-ttu-id="6b1b7-142">![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="6b1b7-142">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="6b1b7-143">项目位置可位于其他服务器上。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-143">The project location can exist on a different server.</span></span> <span data-ttu-id="6b1b7-144">若要将 WCF 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<WCF service location>`。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-144">To publish the WCF services to a different server, type the project name as `http://<servername>/<WCF service location>`.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="6b1b7-145">项目位置可位于非默认网站上。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-145">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="6b1b7-146">发布到非默认网站时，请在该 URL 中包括网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-146">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="6b1b7-147">例如 `http://<servername>:8080/<WCF service location>` 。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-147">For example, `http://<servername>:8080/<WCF service location>`.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="6b1b7-148">该向导创建 Web 应用程序的 App_DataTemp 文件夹中的 BindingInfo.xml 文件对管道使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-148">The BindingInfo.xml file that the wizard creates in the App_DataTemp folder of the Web application uses the default values for the pipelines.</span></span> <span data-ttu-id="6b1b7-149">接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.XMLReceive**管道和默认值为发送管道**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**管道。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-149">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.XMLReceive** pipeline, and the default value for the send pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** pipeline.</span></span>  

10. <span data-ttu-id="6b1b7-150">上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-150">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  

11. <span data-ttu-id="6b1b7-151">单击**创建**创建 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-151">Click **Create** to create the WCF services.</span></span>  

12. <span data-ttu-id="6b1b7-152">单击**完成**完成 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-152">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  

### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a><span data-ttu-id="6b1b7-153">为发布服务元数据配置 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="6b1b7-153">To configure the Web application for publishing service metadata</span></span>  

1. <span data-ttu-id="6b1b7-154">为 BizTalk WCF 服务发布向导创建的 Web 应用程序启用 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-154">Enable ASP.NET for the Web application that the BizTalk WCF Service Publishing Wizard created.</span></span> <span data-ttu-id="6b1b7-155">有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-155">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-156">如果使用的是 Windows Server 2008 或 Windows Vista，则必须将应用程序池的标识帐户添加到 BizTalk Server Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-156">If you are using Windows Server 2008 or Windows Vista, you must add the Identity Account of the Application Pool to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6b1b7-157">将相应帐户添加到 BizTalk Server Administrators 组之后，需要重新启动 IIS 服务以使设置生效。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-157">After you add the appropriate account to the BizTalk Server Administrators group, you need to restart the IIS service fro the setting to take effect.</span></span>  

2. <span data-ttu-id="6b1b7-158">打开命令提示符，请转到 BizTalk WCF 服务发布向导创建 WCF 服务中 %SystemDrive%\InetPub 所在的文件夹\\，然后打开 Web.config 文件使用记事本。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-158">Open a command prompt, go to the folder where the BizTalk WCF Service Publishing Wizard created the WCF services in %SystemDrive%\InetPub\\, and then open the Web.config file using Notepad.</span></span>  

3. <span data-ttu-id="6b1b7-159">在记事本中，添加以下行 **\<system.web\>** 元素：</span><span class="sxs-lookup"><span data-stu-id="6b1b7-159">In Notepad, add the following line inside the **\<system.web\>** element:</span></span>  

   ```  
   <trust level="Full" originUrl="" />  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="6b1b7-160">此设置是可选的，用于向已发布的 WCF 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-160">This setting is optional and it grants the ASP.NET application hosting the published WCF service access to any resource that is subject to operating system security.</span></span> <span data-ttu-id="6b1b7-161">如果在已发布的 WCF 服务所在的计算机上安装并运行了 Windows SharePoint Services，则这是 WCF 所必需的信任级别。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-161">This is the trust level that WCF requires when you have Windows SharePoint Services installed and running on the same machine with the published WCF services.</span></span>  

4. <span data-ttu-id="6b1b7-162">在 Internet Explorer 中，在**地址**框中，键入格式为 的 WCF 服务 URL http://<em>主机 [: 端口]</em>/*apppath* /*wcfservicename.svc*以测试已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-162">In Internet Explorer, in the **Address** box, type the URL for the WCF service using the format http://<em>host[:port]</em>/*apppath*/*wcfservicename.svc* to test the published WCF service.</span></span> <span data-ttu-id="6b1b7-163">介绍了下表的参数。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-163">The parameters are described in the following table.</span></span>  


   |      <span data-ttu-id="6b1b7-164">参数</span><span class="sxs-lookup"><span data-stu-id="6b1b7-164">Parameter</span></span>       |                                                            <span data-ttu-id="6b1b7-165">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="6b1b7-165">Value</span></span>                                                            |
   |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
   |    <span data-ttu-id="6b1b7-166">*主机 [: 端口]*</span><span class="sxs-lookup"><span data-stu-id="6b1b7-166">*host[:port]*</span></span>     | <span data-ttu-id="6b1b7-167">在其中部署了你的 WCF 服务的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-167">The name of the computer where you have deployed your WCF service.</span></span> <span data-ttu-id="6b1b7-168">此服务器名称后面可跟冒号和端口号。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-168">A colon and the port number can follow this server name.</span></span> |
   |      <span data-ttu-id="6b1b7-169">*apppath*</span><span class="sxs-lookup"><span data-stu-id="6b1b7-169">*apppath*</span></span>       |                              <span data-ttu-id="6b1b7-170">虚拟目录和 Web 应用程序路径的名称。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-170">The name of your virtual directory and the Web application path.</span></span>                               |
   | <span data-ttu-id="6b1b7-171">*wcfservicename.svc*</span><span class="sxs-lookup"><span data-stu-id="6b1b7-171">*wcfservicename.svc*</span></span> |                                           <span data-ttu-id="6b1b7-172">WCF 服务 .svc 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-172">The name of the WCF service .svc file.</span></span>                                            |


5. <span data-ttu-id="6b1b7-173">为了避免无意中泄漏可能敏感的服务元数据，我们建议执行下列任务以在生产环境中禁止此行为：</span><span class="sxs-lookup"><span data-stu-id="6b1b7-173">To prevent unintentional disclosure of potentially sensitive service metadata, we recommend that you disable this behavior in the production environment by performing the following tasks:</span></span>  

   1.  <span data-ttu-id="6b1b7-174">在记事本中，打开 BizTalk WCF 服务发布向导创建 WCF 服务中 %SystemDrive%\InetPub 所在的文件夹中的 Web.config\\。</span><span class="sxs-lookup"><span data-stu-id="6b1b7-174">In Notepad, open Web.config in the folder where the BizTalk WCF Service Publishing Wizard created the WCF service in %SystemDrive%\InetPub\\.</span></span>  

   2.  <span data-ttu-id="6b1b7-175">在记事本中，设置**httpGetEnabled**属性中 **\<serviceMetadata\>** 元素为 false，如以下行中所示：</span><span class="sxs-lookup"><span data-stu-id="6b1b7-175">In Notepad, set the **httpGetEnabled** attribute in the  **\<serviceMetadata\>** element to false as in the following line:</span></span>  

       ```  
       <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
       ```  

## <a name="see-also"></a><span data-ttu-id="6b1b7-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b1b7-176">See Also</span></span>  
 <span data-ttu-id="6b1b7-177">[如何使用 BizTalk WCF 服务发布向导发布服务元数据的 WCF 接收位置的基于内容的路由](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md) </span><span class="sxs-lookup"><span data-stu-id="6b1b7-177">[How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location for Content-Based Routing](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md) </span></span>  
 [<span data-ttu-id="6b1b7-178">演练：通过 WCF-NetMsmq 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="6b1b7-178">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)