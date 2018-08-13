---
title: HTTPRequestResponse |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 81c66f61-d86c-49cf-8d24-21c67c68bc5a
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecea06f7637d7fee46593d412f1570d26b7eaeb1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019522"
---
# <a name="httprequestresponse"></a><span data-ttu-id="7a8f0-102">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="7a8f0-102">HTTPRequestResponse</span></span>
<span data-ttu-id="7a8f0-103">HTTPRequestResponse 示例演示如何使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Internet 服务器应用程序编程接口 (ISAPI) 筛选器允许 ASP.NET 应用程序与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程通信。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-103">The HTTPRequestResponse sample demonstrates how to use the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Internet Server Application Programming Interface (ISAPI) filter to allow an ASP.NET application to communicate with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="7a8f0-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="7a8f0-104">What This Sample Does</span></span>  
 <span data-ttu-id="7a8f0-105">在此示例中，ASP.NET 应用程序将请求提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-105">In this sample, the ASP.NET application submits a request to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI filter.</span></span> <span data-ttu-id="7a8f0-106">然后业务流程使用此消息，并使用异步响应将其返回给 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-106">The orchestration then consumes this message and returns it to the ASP.NET application using a synchronous response.</span></span> <span data-ttu-id="7a8f0-107">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI 筛选器，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程和 ASP.NET 应用程序之间集成。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-107">You achieve the integration between the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration and the ASP.NET application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI filter.</span></span>  

 <span data-ttu-id="7a8f0-108">在本示例中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 ASP.NET 应用程序使用以下一系列步骤来交换采购订单 (PO) 和 PO 回执消息：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-108">In this sample, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and an ASP.NET application exchange purchase order (PO) and PO acknowledgement messages using the following sequence of steps:</span></span>  

1. <span data-ttu-id="7a8f0-109">ASP.NET 应用程序使用 HTTP 请求向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交 XML PO 消息。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-109">An ASP.NET application, using an HTTP request, submits an XML PO message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a8f0-110"> 接收此 XML PO 消息，并构造 XML PO 回执消息，然后以 HTTP 响应的形式向 ASP.NET 应用程序发回此消息。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-110"> receives the XML PO message and constructs an XML PO acknowledgement message, and then sends that message back to the ASP.NET application in the HTTP response.</span></span>  

   <span data-ttu-id="7a8f0-111">ASP.NET 应用程序接收此 XML PO 回执响应，并使用从此响应中提取的状态信息刷新 Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-111">The ASP.NET application receives the XML PO acknowledgement response and refreshes the Web form with status information extracted from the response.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="7a8f0-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="7a8f0-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="7a8f0-113">*\<示例路径\>* \AdaptersUsage\HTTPRequestResponse\\</span><span class="sxs-lookup"><span data-stu-id="7a8f0-113">*\<Samples Path\>* \AdaptersUsage\HTTPRequestResponse\\</span></span>  

 <span data-ttu-id="7a8f0-114">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-114">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                                                                     <span data-ttu-id="7a8f0-115">文件</span><span class="sxs-lookup"><span data-stu-id="7a8f0-115">File(s)</span></span>                                                                                                      |                                                                                             <span data-ttu-id="7a8f0-116">Description</span><span class="sxs-lookup"><span data-stu-id="7a8f0-116">Description</span></span>                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                   <span data-ttu-id="7a8f0-117">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7a8f0-117">Cleanup.bat</span></span>                                                                                                    |  <span data-ttu-id="7a8f0-118">取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-118">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>   |
|                                                                               <span data-ttu-id="7a8f0-119">HTTPRequestResponse.btproj、HTTPRequestResponse.sln</span><span class="sxs-lookup"><span data-stu-id="7a8f0-119">HTTPRequestResponse.btproj, HTTPRequestResponse.sln</span></span>                                                                                |                            <span data-ttu-id="7a8f0-120">提供接收 HTTP 请求、处理 PO 消息并发出响应的 BizTalk 项目的项目和源文件。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-120">Provides project and source files for the BizTalk project that receives the HTTP request, processes the PO message, and issues the response.</span></span>                             |
|                                                                                          <span data-ttu-id="7a8f0-121">HTTPRequestResponseBinding.xml</span><span class="sxs-lookup"><span data-stu-id="7a8f0-121">HTTPRequestResponseBinding.xml</span></span>                                                                                          |                                                                           <span data-ttu-id="7a8f0-122">提供自动设置，如端口绑定。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-122">Provides automated setup such as port binding.</span></span>                                                                            |
|                                                                                             <span data-ttu-id="7a8f0-123">POAck.xsd、POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="7a8f0-123">POAck.xsd, POSchema.xsd</span></span>                                                                                              |                                                            <span data-ttu-id="7a8f0-124">分别提供 PO 回执和 PO .xml 文件的架构。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-124">Provides schemas for the PO acknowledgement and PO .xml files, respectively.</span></span>                                                             |
|                                                                                            <span data-ttu-id="7a8f0-125">POReceiveOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="7a8f0-125">POReceiveOrchestration.odx</span></span>                                                                                            |         <span data-ttu-id="7a8f0-126">提供用于接收 PO、处理 PO 并发出 PO 回执的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-126">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that receives the PO, processes it, and issues the PO acknowledgement.</span></span>          |
|                                                                                                    <span data-ttu-id="7a8f0-127">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="7a8f0-127">Setup.bat</span></span>                                                                                                     |                                                                                 <span data-ttu-id="7a8f0-128">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-128">Builds and initializes this sample.</span></span>                                                                                 |
| <span data-ttu-id="7a8f0-129">\RequestResponse 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-129">In the \RequestResponse folder:</span></span><br /><br /> <span data-ttu-id="7a8f0-130">AssemblyInfo.cs、default.aspx、default.aspx.cs、Global.asax、Global.asax.cs、RequestResponse.csproj、RequestResponse.csproj.webinfo、RequestResponse.sln 和 Web.config</span><span class="sxs-lookup"><span data-stu-id="7a8f0-130">AssemblyInfo.cs, default.aspx, default.aspx.cs, Global.asax, Global.asax.cs, RequestResponse.csproj, RequestResponse.csproj.webinfo, RequestResponse.sln, Web.config</span></span> | <span data-ttu-id="7a8f0-131">包含用作本示例的驱动程序的 ASP.NET 应用程序的组成文件，其中包括项目和解决方案文件、ASPX 文件和 Microsoft Visual C# .NET 源文件等。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-131">Contains files that constitute the ASP.NET application that serves as a driver for this sample, including project and solution files, ASPX files, Microsoft Visual C# .NET source files, and so on.</span></span> |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7a8f0-132">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="7a8f0-132">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7a8f0-133">使用以下过程可以生成并初始化 HTTPRequestResponse 示例。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-133">Use the following procedure to build and initialize the HTTPRequestResponse sample.</span></span>  

#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="7a8f0-134">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="7a8f0-134">To build and initialize this sample</span></span>  

1. <span data-ttu-id="7a8f0-135">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-135">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="7a8f0-136">\<*示例路径*\>\AdaptersUsage\HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="7a8f0-136">\<*Samples Path*\>\AdaptersUsage\HTTPRequestResponse</span></span>  

2. <span data-ttu-id="7a8f0-137">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-137">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="7a8f0-138">编译并配置用于驱动本示例的 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-138">Compiles and configures the ASP.NET application used to drive this sample.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="7a8f0-139">在创建应用程序池在 IIS 管理器，设置**DefaultAppPool**到.NET Framework 版本 **.Net Framework v4.0**。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-139">While creating application pool in IIS Manager, set the **DefaultAppPool** .NET Framework version to **.Net Framework v4.0**.</span></span>  

   - <span data-ttu-id="7a8f0-140">编译并部署本示例中使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-140">Compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration used in this sample.</span></span>  

   - <span data-ttu-id="7a8f0-141">编译并部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-141">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="7a8f0-142">创建并绑定必要的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 端口。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-142">Creates and binds the necessary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ports.</span></span>  

   - <span data-ttu-id="7a8f0-143">启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-143">Starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

     > [!IMPORTANT]
     >  <span data-ttu-id="7a8f0-144">必须更改实现 Web 应用程序 (Default.aspx.cs) 的示例代码，使其反映您的环境：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-144">You must change the sample code that implements the Web application (Default.aspx.cs) to reflect your environment:</span></span>  
     >   
     >  <span data-ttu-id="7a8f0-145">http://\<*服务器名称*\>/\<*虚拟 dir*\>/BTSHTTPReceive.dll 其中`<servername>`是 Web 的名称您要发布到，服务器和`<`*虚拟 dir* `>`是此文件所在的位置的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-145">http://\<*server name*\>/\<*virtual dir*\>/BTSHTTPReceive.dll where `<servername>` is the name of the Web server you are posting to, and `<`*virtual dir*`>` is the virtual directory where this file resides.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="7a8f0-146">在尝试运行本示例之前，应确认在生成和初始化过程中 BizTalk 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-146">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="7a8f0-147">如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-147">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="7a8f0-148">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-148">Use this key pair to sign the resulting assemblies.</span></span> <span data-ttu-id="7a8f0-149">同时，在尝试生成该项目之前，您还必须从 RequestResponse.csproj 文件中手动删除对 default.aspx.resx 和 Global.asax.resx 的引用。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-149">You must also manually remove the references to default.aspx.resx and Global.asax.resx from the file RequestResponse.csproj before attempting to build that project.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="7a8f0-150">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="7a8f0-151">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="7a8f0-152">必须配置和启用 IIS 以便使用 HTTP 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-152">You must configure and enable IIS to use the HTTP receive adapter.</span></span> <span data-ttu-id="7a8f0-153">有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-153">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  

3. <span data-ttu-id="7a8f0-154">setup.bat 文件将本示例的虚拟目录配置为在与默认网站相关联的 IIS 应用程序池中运行。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-154">The setup.bat file configures the virtual directory for this sample to run in the IIS application pool associated with the default web site.</span></span>  <span data-ttu-id="7a8f0-155">若要配置本示例中的用户上下文中运行的虚拟目录**BizTalk Isolated Host Users**并**IIS_IURS**用户组，应配置要运行在新的虚拟目录IIS 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-155">To configure the virtual directory for this sample to run under the context of a user in the **BizTalk Isolated Host Users** and **IIS_IURS** user groups, you should configure the virtual directory to run in a new IIS application pool.</span></span> <span data-ttu-id="7a8f0-156">通过完成以下步骤，可将虚拟目录配置为在新的 IIS 应用程序池中运行：</span><span class="sxs-lookup"><span data-stu-id="7a8f0-156">Configure the virtual directory to run in a new IIS application pool by completing the following steps:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7a8f0-157">如果已经为另一个 SDK 示例创建了新的应用程序池，可继续进行下面的最后一步。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-157">If you have already created a new application pool for another SDK sample then you can proceed to the last step below.</span></span>  

   1.  <span data-ttu-id="7a8f0-158">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="7a8f0-158">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

   2.  <span data-ttu-id="7a8f0-159">在中**Internet 信息服务 (IIS) 管理器**，导航到**应用程序池**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-159">In the **Internet Information Services (IIS) Manager**, navigate to the **Application Pools** folder.</span></span>  

   3.  <span data-ttu-id="7a8f0-160">右键单击**应用程序池**文件夹，然后单击**新建**，**应用程序池...**</span><span class="sxs-lookup"><span data-stu-id="7a8f0-160">Right-click the **Application Pools** folder and click **New**, **Application Pool...**</span></span>  

   4.  <span data-ttu-id="7a8f0-161">输入的名称**应用程序池 ID:** 如 BizTalkSDKSamples，确认**对新应用程序池使用默认设置**选项已选中，然后单击**确定**到创建新的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-161">Enter a name for the **Application Pool ID:** such as BizTalkSDKSamples, verify that the **Use default settings for new application pool** option is selected and click **OK** to create the new application pool.</span></span>  

   5.  <span data-ttu-id="7a8f0-162">右键单击新的应用程序池，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-162">Right-click the new application pool and then click **Properties**.</span></span>  

   6.  <span data-ttu-id="7a8f0-163">单击**标识**选项卡的属性对话框并更改用于成员的用户运行此应用程序池标识**BizTalk Isolated Host Users**用户组。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-163">Click the **Identity** tab of the properties dialog box and change the identity under which this application pool runs to a user that is a member of the **BizTalk Isolated Host Users** user group.</span></span>  <span data-ttu-id="7a8f0-164">此用户还应是本地组成员的**IIS_IURS**用户组。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-164">This user should also be a member of the local **IIS_IURS** user group.</span></span>  

   7.  <span data-ttu-id="7a8f0-165">将本 SDK 示例的虚拟目录配置为在新应用程序池下运行。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-165">Configure the virtual directory for this SDK sample to run under the new application pool.</span></span> <span data-ttu-id="7a8f0-166">**应用程序池**设置位于**虚拟目录**选项卡的虚拟目录属性对话框。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-166">The **Application pool** setting is available on the **Virtual Directory** tab of the Virtual Directory properties dialog box.</span></span> <span data-ttu-id="7a8f0-167">为本示例创建的虚拟目录为 HttpRequestResponseSample。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-167">The virtual directory created for this sample is HttpRequestResponseSample.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="7a8f0-168">运行本示例</span><span class="sxs-lookup"><span data-stu-id="7a8f0-168">Running This Sample</span></span>  
 <span data-ttu-id="7a8f0-169">使用以下过程运行 HTTPRequestResponse 示例。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-169">Use the following procedure to run the HTTPRequestResponse sample.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="7a8f0-170">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="7a8f0-170">To run this sample</span></span>  

1.  <span data-ttu-id="7a8f0-171">在 Internet Explorer 中，导航到 http://localhost/RequestResponse/ 。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-171">In Internet Explorer, navigate to http://localhost/RequestResponse/.</span></span>  

2.  <span data-ttu-id="7a8f0-172">填写 Web 窗体中所需的字段，再单击**下订单**提交你的订单。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-172">Complete the necessary fields in the Web form, and then click **Place Order** to submit your order.</span></span>  

3.  <span data-ttu-id="7a8f0-173">查看 Web 窗体在收到响应后进行刷新时的订单状态。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-173">Observe the status of your order when the Web form refreshes after receiving a response.</span></span>  

## <a name="comments"></a><span data-ttu-id="7a8f0-174">注释</span><span class="sxs-lookup"><span data-stu-id="7a8f0-174">Comments</span></span>  
 <span data-ttu-id="7a8f0-175">**BTSHTTPReceiveISAPI**配置此示例中使用的扩展，以在单台计算机默认安装中工作。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-175">The **BTSHTTPReceiveISAPI** extension used in this sample is configured to work on a single computer default installation.</span></span> <span data-ttu-id="7a8f0-176">若要扩展其他配置，此示例，请参阅[HTTP 适配器](../core/http-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-176">To extend this sample for additional configurations, see [HTTP Adapter](../core/http-adapter.md).</span></span>  

 <span data-ttu-id="7a8f0-177">您可以将本示例扩展为通常通过 Web 窗体或 HTTP 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交数据所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-177">You can extend this sample to applications that are required to submit data to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] through a Web form, or through HTTP in general.</span></span> <span data-ttu-id="7a8f0-178">通过扩展本示例的 ASP.NET 应用程序部分，您可以在向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交数据之前查询更多信息并执行其他预处理。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-178">By extending the ASP.NET application portion of this sample, you can query for more information and perform other preprocessing before submitting the data to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="see-also"></a><span data-ttu-id="7a8f0-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a8f0-179">See Also</span></span>  
 [<span data-ttu-id="7a8f0-180">HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="7a8f0-180">HTTP Adapter Samples</span></span>](../core/http-adapter-samples.md)