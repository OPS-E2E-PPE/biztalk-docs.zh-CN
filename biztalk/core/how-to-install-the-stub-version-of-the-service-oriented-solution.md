---
title: 如何安装服务的存根 （stub） 版本面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IIS, installing virtual directories [service solutions]
- service solution tutorial, IIS virtual directories
- service solution tutorial, stub version
- deploying, BAM solutions [service solutions]
- service solution tutorial, solutions [BAM]
- service solution tutorial, service solutions
- SSO, configuring
- IBM WebSphere MQ Client
- service solution tutorial, IBM WebSphere MQ Client
- installing, tutorials
- service solutions, deploying
- service solution tutorial, SSO
- BAM, deploying solutions
- service solution tutorial, building solutions
- service solution tutorial, installing
ms.assetid: 45de7681-4df0-47a4-a02c-509140423a1e
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adaf5cb0117e0d571e0be0ddd42350ce3af2ba80
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010406"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="6b867-102">如何安装面向服务的解决方案的存根版本</span><span class="sxs-lookup"><span data-stu-id="6b867-102">How to Install the Stub Version of the Service Oriented Solution</span></span>
<span data-ttu-id="6b867-103">以下步骤介绍了如何准备计算机以安装面向服务的解决方案的存根版本，以及如何在计算机上安装该解决方案：</span><span class="sxs-lookup"><span data-stu-id="6b867-103">The following steps describe how to prepare your computer before you install the stub version of the service oriented solution, and then how to install the solution on your computer.</span></span>  
  
-   [<span data-ttu-id="6b867-104">准备计算机以安装服务面向解决方案的存根 （stub） 版本</span><span class="sxs-lookup"><span data-stu-id="6b867-104">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="6b867-105">安装 Windows 的 IBM WebSphere MQ 客户端</span><span class="sxs-lookup"><span data-stu-id="6b867-105">Install the IBM WebSphere MQ Client for Windows</span></span>](#step3)  
  
-   [<span data-ttu-id="6b867-106">为服务面向解决方案在 IIS 中创建的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6b867-106">Create the virtual directories in IIS for the Service Oriented Solution</span></span>](#step5)  
  
-   [<span data-ttu-id="6b867-107">生成面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="6b867-107">Build the Service Oriented Solution</span></span>](#step7)  
  
-   [<span data-ttu-id="6b867-108">SSO 数据库中创建的企业单一登录 (SSO) 条目和值</span><span class="sxs-lookup"><span data-stu-id="6b867-108">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>](#step9)  
  
-   [<span data-ttu-id="6b867-109">部署服务面向解决方案的 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="6b867-109">Deploy the BAM definition for the Service Oriented Solution</span></span>](#step11)  
  
-   [<span data-ttu-id="6b867-110">部署面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="6b867-110">Deploy the Service Oriented Solution</span></span>](#step13)  
  
##  <a name="step1"></a><span data-ttu-id="6b867-111">准备计算机以安装服务面向解决方案的存根 （stub） 版本</span><span class="sxs-lookup"><span data-stu-id="6b867-111">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="6b867-112">准备计算机以安装面向服务的解决方案的存根版本</span><span class="sxs-lookup"><span data-stu-id="6b867-112">To prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="6b867-113">请确保**Default Web Site**配置为使用 ASP.NET 2.X。</span><span class="sxs-lookup"><span data-stu-id="6b867-113">Make sure that the **Default Web Site** is configured to use ASP.NET 2.X.</span></span>  
  
    1.  <span data-ttu-id="6b867-114">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="6b867-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    2.  <span data-ttu-id="6b867-115">在**Internet Information Services (IIS) Manager**，计算机名称，展开**站点**，展开**Default Web Site**，展开**aspnet_client**，展开**system_web**。</span><span class="sxs-lookup"><span data-stu-id="6b867-115">In the **Internet Information Services (IIS) Manager**, the machine name, expand  **Sites**, expand **Default Web Site**, expand **aspnet_client**, expand **system_web**.</span></span>  
  
    3.  <span data-ttu-id="6b867-116">确保子文件夹为 2.X。</span><span class="sxs-lookup"><span data-stu-id="6b867-116">Make sure that the sub-folder is 2.X.</span></span>  
  
2.  <span data-ttu-id="6b867-117">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**服务**。</span><span class="sxs-lookup"><span data-stu-id="6b867-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="6b867-118">使用**服务**控制台中，请确保以下服务正在运行：</span><span class="sxs-lookup"><span data-stu-id="6b867-118">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="6b867-119">**World Wide Web 发布**</span><span class="sxs-lookup"><span data-stu-id="6b867-119">**World Wide Web Publishing**</span></span>  
  
3.  <span data-ttu-id="6b867-120">单击**启动**，指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，并将到本地管理员组的 BizTalk 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="6b867-120">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
4.  <span data-ttu-id="6b867-121">如果你安装 Windows SharePoint Services，排除 （根） 的**Default Web Site**从，如下所示 Windows SharePoint Services 管理 Paths： 单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="6b867-121">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="6b867-122">下**虚拟服务器配置**，选择**配置虚拟服务器设置**。</span><span class="sxs-lookup"><span data-stu-id="6b867-122">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="6b867-123">上**虚拟服务器列表**页上，单击**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="6b867-123">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="6b867-124">上**虚拟服务器设置**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="6b867-124">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="6b867-125">在**包含的路径**部分**定义托管路径**页上，选择**根**，然后单击**删除所选的路径**。</span><span class="sxs-lookup"><span data-stu-id="6b867-125">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="6b867-126">在命令提示符下，执行 IISReset。</span><span class="sxs-lookup"><span data-stu-id="6b867-126">At a command prompt, perform an IISReset.</span></span>  
  
5.  <span data-ttu-id="6b867-127">从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="6b867-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
6.  <span data-ttu-id="6b867-128">打开命令提示符，键入以下命令，然后按 Enter 以设置 %BTSSolutionsPath% 环境。</span><span class="sxs-lookup"><span data-stu-id="6b867-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment.</span></span> <span data-ttu-id="6b867-129">然后，退出命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6b867-129">Then, exit the command prompt.</span></span>  
  
    -   <span data-ttu-id="6b867-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="6b867-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6b867-131">如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。</span><span class="sxs-lookup"><span data-stu-id="6b867-131">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6b867-132">有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)。</span><span class="sxs-lookup"><span data-stu-id="6b867-132">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="6b867-133">安装 Windows 的 IBM WebSphere MQ 客户端</span><span class="sxs-lookup"><span data-stu-id="6b867-133">Install the IBM WebSphere MQ Client for Windows</span></span>  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a><span data-ttu-id="6b867-134">安装 IBM WebSphere MQ Client for Windows</span><span class="sxs-lookup"><span data-stu-id="6b867-134">To install the IBM WebSphere MQ Client for Windows</span></span>  
  
1.  <span data-ttu-id="6b867-135">下载最新版本的 IBM WebSphere MQ Client for Windows。</span><span class="sxs-lookup"><span data-stu-id="6b867-135">Download the latest version of IBM WebSphere MQ Client for Windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-136">即使解决方案的存根版本不需要 IBM WebSphere Server，客户端应用程序仍然会引用由 IBM WebSphere MQ Client for Windows 提供的 amqmdnet.dll 文件，因此必须安装它。</span><span class="sxs-lookup"><span data-stu-id="6b867-136">Even if the stub version of the solution doesn't require IBM WebSphere Server, the client application references the amqmdnet.dll file provided by IBM WebSphere MQ Client for Windows, so you must install it.</span></span> <span data-ttu-id="6b867-137">存根版本的客户端实际上不会调用该 DLL 中的 API。</span><span class="sxs-lookup"><span data-stu-id="6b867-137">The client of the stub version does not actually call an API in the DLL.</span></span> <span data-ttu-id="6b867-138">只有在编译和运行客户端应用程序时才需要该 DLL。</span><span class="sxs-lookup"><span data-stu-id="6b867-138">It is required only for compiling and running the client application.</span></span> <span data-ttu-id="6b867-139">你可以从 IBM 网站下载 IBM WebSphere MQ Client for Windows。</span><span class="sxs-lookup"><span data-stu-id="6b867-139">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
2.  <span data-ttu-id="6b867-140">安装 IBM WebSphere MQ Client for Windows。</span><span class="sxs-lookup"><span data-stu-id="6b867-140">Install IBM WebSphere MQ Client for Windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-141">不需要配置 IBM WebSphere MQ Client for Windows。</span><span class="sxs-lookup"><span data-stu-id="6b867-141">You don't need to configure IBM WebSphere MQ Client for Windows.</span></span> <span data-ttu-id="6b867-142">请保留所有默认设置。</span><span class="sxs-lookup"><span data-stu-id="6b867-142">Keep all of the default settings.</span></span>  
  
3.  <span data-ttu-id="6b867-143">将用于 .NET 程序集的 WebSphere MQ 类添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="6b867-143">Add WebSphere MQ classes for the .NET assembly to the global assembly cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="6b867-144">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，导航到目录\<IBM MQSeries 安装目录\>\bin。</span><span class="sxs-lookup"><span data-stu-id="6b867-144">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, navigate to the directory \<IBM MQSeries Installation Directory\>\bin.</span></span>  
  
    2.  <span data-ttu-id="6b867-145">运行以下命令（请确保 gacutil.exe 位于该路径环境下）：</span><span class="sxs-lookup"><span data-stu-id="6b867-145">Run the following command (make sure gacutil.exe is in the path environment):</span></span>  
  
         `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a><span data-ttu-id="6b867-146">为服务面向解决方案在 IIS 中创建的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6b867-146">Create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a><span data-ttu-id="6b867-147">在 IIS 中为面向服务的解决方案创建虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6b867-147">To create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="6b867-148">在**Internet Information Services (IIS) Manager**，右键单击**应用程序池**，选择**添加应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="6b867-148">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **Add Application Pool**.</span></span>  
  
     <span data-ttu-id="6b867-149">上**添加应用程序池**对话框中，键入`SSOStubAppPool`中**名称**文本中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6b867-149">On the **Add Application Pool** dialog box, type `SSOStubAppPool` in the **Name** text box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6b867-150">面向服务的解决方案使用的虚拟目录包括：业务流程的存根版本的已发布 Web Services、存根 SAP Web Services、存根付款跟踪程序 Web Services 和存根挂起事务 Web Services。</span><span class="sxs-lookup"><span data-stu-id="6b867-150">The virtual directories that service-oriented solution uses include the published Web service for the stub version of orchestrations, the stub SAP Web service, the stub Payment Tracker Web service, and the stub Pending Transaction Web service.</span></span>  
  
2.  <span data-ttu-id="6b867-151">在**Internet Information Services (IIS) Manager**，右键单击你刚的应用程序池创建，，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="6b867-151">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="6b867-152">单击右侧的列中**标识**属性，然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="6b867-152">Click in the column to the right of the **Identity** property, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="6b867-153">在**应用程序池标识**对话框中，选择**自定义帐户**选项，并依次**设置**。</span><span class="sxs-lookup"><span data-stu-id="6b867-153">In the **Application Pool Identity** dialog box, select the **Custom Account** option, and then click **Set**.</span></span>  
  
5.  <span data-ttu-id="6b867-154">在**设置凭据**对话框中，指定用户名和密码，确认密码，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6b867-154">In the **Set Credentials** dialog box, specify a username and password, confirm the password, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-155">此用户必须有权执行业务流程代理 Web Services，并且必须添加到 BizTalk Server Administrators、SSO Administrators 或 SSO Affiliated Administrators 组中。</span><span class="sxs-lookup"><span data-stu-id="6b867-155">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
6.  <span data-ttu-id="6b867-156">单击**确定**关闭**应用程序池标识**对话框。</span><span class="sxs-lookup"><span data-stu-id="6b867-156">Click **OK** to close the **Application Pool Identity** dialog box.</span></span>  
  
7.  <span data-ttu-id="6b867-157">单击“确定”  关闭“高级设置”  对话框。</span><span class="sxs-lookup"><span data-stu-id="6b867-157">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
8.  <span data-ttu-id="6b867-158">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="6b867-158">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
    1.  <span data-ttu-id="6b867-159">使用**虚拟目录创建向导**，为代理的适配器版本的 Web 服务创建以下虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="6b867-159">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="6b867-160">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span><span class="sxs-lookup"><span data-stu-id="6b867-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span></span>  
  
         <span data-ttu-id="6b867-161">路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span><span class="sxs-lookup"><span data-stu-id="6b867-161">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span></span>  
  
         <span data-ttu-id="6b867-162">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="6b867-162">Access Permissions = Read, Run scripts</span></span>  
  
    2.  <span data-ttu-id="6b867-163">使用**虚拟目录创建向导**，为代理的适配器版本的 Web 服务创建以下虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="6b867-163">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="6b867-164">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="6b867-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
         <span data-ttu-id="6b867-165">路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="6b867-165">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
         <span data-ttu-id="6b867-166">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="6b867-166">Access Permissions = Read, Run scripts</span></span>  
  
    3.  <span data-ttu-id="6b867-167">使用**虚拟目录创建向导**，为代理的适配器版本的 Web 服务创建以下虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="6b867-167">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="6b867-168">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="6b867-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
         <span data-ttu-id="6b867-169">路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="6b867-169">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
         <span data-ttu-id="6b867-170">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="6b867-170">Access Permissions = Read, Run scripts</span></span>  
  
    4.  <span data-ttu-id="6b867-171">使用**虚拟目录创建向导**，为代理的适配器版本的 Web 服务创建以下虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="6b867-171">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="6b867-172">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span><span class="sxs-lookup"><span data-stu-id="6b867-172">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span></span>  
  
         <span data-ttu-id="6b867-173">路径 = \<BizTalk 安装目录\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span><span class="sxs-lookup"><span data-stu-id="6b867-173">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span></span>  
  
         <span data-ttu-id="6b867-174">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="6b867-174">Access Permissions = Read, Run scripts</span></span>  
  
9. <span data-ttu-id="6b867-175">在**Internet Information Services (IIS) Manager**，展开**网站，** 展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b867-175">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="6b867-176">上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚创建。</span><span class="sxs-lookup"><span data-stu-id="6b867-176">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="6b867-177">单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证启用**，然后清除其他**身份验证访问**复选框。</span><span class="sxs-lookup"><span data-stu-id="6b867-177">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="6b867-178">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="6b867-178">Click **OK** to exit.</span></span>  
  
10. <span data-ttu-id="6b867-179">在**Internet Information Services (IIS) Manager**，展开**网站，** 展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b867-179">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="6b867-180">上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚创建。</span><span class="sxs-lookup"><span data-stu-id="6b867-180">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="6b867-181">单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**.</span><span class="sxs-lookup"><span data-stu-id="6b867-181">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="6b867-182">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="6b867-182">Click **OK** to exit.</span></span>  
  
11. <span data-ttu-id="6b867-183">在**Internet Information Services (IIS) Manager**，展开**网站，** 展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b867-183">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="6b867-184">上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚创建。</span><span class="sxs-lookup"><span data-stu-id="6b867-184">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="6b867-185">单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**.</span><span class="sxs-lookup"><span data-stu-id="6b867-185">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="6b867-186">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="6b867-186">Click **OK** to exit.</span></span>  
  
12. <span data-ttu-id="6b867-187">在**Internet Information Services (IIS) Manager**，展开**网站，** 展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b867-187">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="6b867-188">上**虚拟目录**选项卡上，设置**应用程序池**到**SSOStubAppPool**你刚创建。</span><span class="sxs-lookup"><span data-stu-id="6b867-188">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="6b867-189">单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**.</span><span class="sxs-lookup"><span data-stu-id="6b867-189">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="6b867-190">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="6b867-190">Click **OK** to exit.</span></span>  
  
##  <a name="step7"></a><span data-ttu-id="6b867-191">生成面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="6b867-191">Build the Service Oriented Solution</span></span>  
  
#### <a name="to-build-the-service-oriented-solution"></a><span data-ttu-id="6b867-192">若要生成服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="6b867-192">To build the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="6b867-193">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="6b867-193">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-194">在文件中 **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs**和 **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**，将替换为 a1054514fc67bded 17f20caea2afcc8c 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="6b867-194">In the files **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs** and **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**, replace all the instances of 17f20caea2afcc8c with a1054514fc67bded.</span></span>  
  
2.  <span data-ttu-id="6b867-195">在“Visual Studio 命令提示”下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln 文件夹，然后运行以下命令以生成面向服务的解决方案的存根版本。</span><span class="sxs-lookup"><span data-stu-id="6b867-195">At the Visual Studio Command Prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln folder, and then run the following command to build the stub version of service-oriented solution.</span></span>  
  
    -   `SetupBTSSoln.bat`  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-196">在下面列出的文件中，将 17f20caea2afcc8c 所有的实例替换为当前公钥标记。</span><span class="sxs-lookup"><span data-stu-id="6b867-196">In the files listed below, replace all the instances of 17f20caea2afcc8c with the current public key token.</span></span>  
    >   
    >  -   <span data-ttu-id="6b867-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="6b867-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="6b867-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="6b867-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="6b867-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="6b867-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="6b867-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span><span class="sxs-lookup"><span data-stu-id="6b867-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span></span>  
    > -   <span data-ttu-id="6b867-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span><span class="sxs-lookup"><span data-stu-id="6b867-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span></span>  
    > -   <span data-ttu-id="6b867-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="6b867-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span></span>  
  
##  <a name="step9"></a><span data-ttu-id="6b867-203">SSO 数据库中创建的企业单一登录 (SSO) 条目和值</span><span class="sxs-lookup"><span data-stu-id="6b867-203">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a><span data-ttu-id="6b867-204">在 SSO 数据库中创建企业单一登录 (SSO) 条目和值</span><span class="sxs-lookup"><span data-stu-id="6b867-204">To create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
1.  <span data-ttu-id="6b867-205">打开命令提示符，将当前目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts，然后运行以下命令以设置 Enterprise Single Sign-On 文件夹的 PATH 环境：</span><span class="sxs-lookup"><span data-stu-id="6b867-205">Open a command prompt, change the current directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts, and then run the following command to set the PATH environment for the Enterprise Single Sign-On folder.</span></span>  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  <span data-ttu-id="6b867-206">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，使用记事本打开 ConfigStoreApp.xml，然后查看该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="6b867-206">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open ConfigStoreApp.xml using Notepad, and then review the contents of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-207">此文件定义了该方案在 SSO 中用于存储配置参数的配置存储应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b867-207">This file defines the configuration store application in SSO that the scenario uses to store configuration parameters.</span></span> <span data-ttu-id="6b867-208">一些配置参数包括**超时**用于与 SAP 通信 （对于所有三个版本） 的值。</span><span class="sxs-lookup"><span data-stu-id="6b867-208">Some of the configuration parameters include the **Timeout** value used to communicate with SAP (for all three versions).</span></span> <span data-ttu-id="6b867-209">不需要更改此文件。</span><span class="sxs-lookup"><span data-stu-id="6b867-209">No changes to this file are necessary.</span></span>  
  
3.  <span data-ttu-id="6b867-210">在命令提示符下，运行以下命令以创建 SSO 配置存储应用程序：</span><span class="sxs-lookup"><span data-stu-id="6b867-210">At the command prompt, run the following command to create the SSO configuration store application.</span></span>  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  <span data-ttu-id="6b867-211">在命令提示符下，使用记事本打开 SetConfigValuesInSSO.cmd，然后查看该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="6b867-211">At the command prompt, open SetConfigValuesInSSO.cmd using Notepad, and then review the contents of the file</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b867-212">此命令文件在 SSO 数据库中设置的配置参数的值。</span><span class="sxs-lookup"><span data-stu-id="6b867-212">This command file sets the values of the configuration parameters in the SSO database.</span></span> <span data-ttu-id="6b867-213">该命令文件的开头包含几个设置局部变量值的 set 语句。</span><span class="sxs-lookup"><span data-stu-id="6b867-213">It contains several set statements that set the values in local variables in the beginning of the command file.</span></span> <span data-ttu-id="6b867-214">**SAPAdapterTimeout**， **PendingTransactionsAdapterTimeout**，和**PaymentTrackingAdapterTimeout**存根 （stub） 和适配器版本中使用值。</span><span class="sxs-lookup"><span data-stu-id="6b867-214">The **SAPAdapterTimeout**, **PendingTransactionsAdapterTimeout**, and **PaymentTrackingAdapterTimeout** values are used in the stub and adapter version.</span></span> <span data-ttu-id="6b867-215">其余的值用于内联版本。</span><span class="sxs-lookup"><span data-stu-id="6b867-215">The remaining values are used in the inline version.</span></span> <span data-ttu-id="6b867-216">对于存根版本不需要更改此文件。</span><span class="sxs-lookup"><span data-stu-id="6b867-216">No changes to this file are necessary for stub version.</span></span>  
  
5.  <span data-ttu-id="6b867-217">在命令提示符处，键入`SetConfigValuesInSSO.cmd`，然后按 ENTER 来 SSO 配置存储应用程序中存储的值。</span><span class="sxs-lookup"><span data-stu-id="6b867-217">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER to store the values in the SSO configuration store application.</span></span>  
  
6.  <span data-ttu-id="6b867-218">在命令提示符下，运行以下命令以在 SSO 中启用票证：</span><span class="sxs-lookup"><span data-stu-id="6b867-218">At the command prompt, run the following command to enable tickets in SSO:</span></span>  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a><span data-ttu-id="6b867-219">部署服务面向解决方案的 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="6b867-219">Deploy the BAM definition for the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a><span data-ttu-id="6b867-220">若要部署服务面向解决方案的 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="6b867-220">To deploy the BAM definition for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="6b867-221">在命令提示符下，键入以下命令，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="6b867-221">At a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="6b867-222">此命令将设置用于查找 BAM 实用工具的路径：</span><span class="sxs-lookup"><span data-stu-id="6b867-222">This sets the path to find the BAM utility:</span></span>  
  
    -   <span data-ttu-id="6b867-223">集 PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span><span class="sxs-lookup"><span data-stu-id="6b867-223">SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span></span>  
  
2.  <span data-ttu-id="6b867-224">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM 文件夹，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="6b867-224">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM folder, and type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  <span data-ttu-id="6b867-225">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="6b867-225">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
##  <a name="step13"></a><span data-ttu-id="6b867-226">部署面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="6b867-226">Deploy the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-service-oriented-solution"></a><span data-ttu-id="6b867-227">若要部署服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="6b867-227">To deploy the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="6b867-228">打开命令提示符，并将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6b867-228">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="6b867-229">修改**DeployStubBinding.cmd**通过将替换为"发布"的"debug"和"开发"的所有实例的文件。</span><span class="sxs-lookup"><span data-stu-id="6b867-229">Modify the **DeployStubBinding.cmd** file by replacing all the instances of “debug” and “development” with “release”.</span></span>  
  
3.  <span data-ttu-id="6b867-230">打开命令提示符，并将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6b867-230">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span> <span data-ttu-id="6b867-231">键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="6b867-231">Type the following command, and then press ENTER:</span></span>  
  
    -   `DeployStubBinding.cmd`  
  
4.  <span data-ttu-id="6b867-232">在命令提示符下，运行以下命令以启动用于存根版本的业务流程：</span><span class="sxs-lookup"><span data-stu-id="6b867-232">At the command prompt, run the following command to start the orchestrations for the stub version</span></span>  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a><span data-ttu-id="6b867-233">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b867-233">Next Steps</span></span>  
 <span data-ttu-id="6b867-234">测试面向服务的解决方案的存根 （stub） 版本中的工作方式[如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="6b867-234">You test how the stub version of the service-oriented solution works in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b867-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b867-235">See Also</span></span>  
 <span data-ttu-id="6b867-236">[在安装之前面向服务解决方案](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6b867-236">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="6b867-237">[如何安装内联和服务的适配器版本面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6b867-237">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="6b867-238">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="6b867-238">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)