---
title: HTTP 适配器 （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e204d1e15ec7483bf2ae2f10db30ffd019651bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332836"
---
# <a name="http-adapter-biztalk-server-sample"></a><span data-ttu-id="fdf97-102">HTTP 适配器 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="fdf97-102">HTTP Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="fdf97-103">HTTP 适配器示例演示如何实现中使用的请求/响应和要求/响应范例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fdf97-103">The HTTP Adapter sample demonstrates how to implement the request/response and solicit/response communication paradigms used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="fdf97-104">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="fdf97-104">Where to Find This Sample</span></span>  
 <span data-ttu-id="fdf97-105">*\<Samples Path\>* \AdaptersDevelopment\HttpAdapter</span><span class="sxs-lookup"><span data-stu-id="fdf97-105">*\<Samples Path\>* \AdaptersDevelopment\HttpAdapter</span></span>\  

 <span data-ttu-id="fdf97-106">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="fdf97-106">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="fdf97-107">文件</span><span class="sxs-lookup"><span data-stu-id="fdf97-107">File(s)</span></span>|<span data-ttu-id="fdf97-108">Description</span><span class="sxs-lookup"><span data-stu-id="fdf97-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdf97-109">\Design-Time\Adapter 管理</span><span class="sxs-lookup"><span data-stu-id="fdf97-109">\Design-Time\Adapter Management</span></span>|<span data-ttu-id="fdf97-110">包含实现此适配器的设计时部分的项目。</span><span class="sxs-lookup"><span data-stu-id="fdf97-110">Contains the project that implements the design time portion of this adapter.</span></span>|  
|<span data-ttu-id="fdf97-111">\Run-Time\HttpReceive</span><span class="sxs-lookup"><span data-stu-id="fdf97-111">\Run-Time\HttpReceive</span></span>|<span data-ttu-id="fdf97-112">包含实现请求/响应适配器通信模式的项目。</span><span class="sxs-lookup"><span data-stu-id="fdf97-112">Contains the project that implements the request/response adapter communication pattern.</span></span> <span data-ttu-id="fdf97-113">这是一个独立的接收器。</span><span class="sxs-lookup"><span data-stu-id="fdf97-113">This is an isolated receiver.</span></span>|  
|<span data-ttu-id="fdf97-114">\Run-Time\HttpSend</span><span class="sxs-lookup"><span data-stu-id="fdf97-114">\Run-Time\HttpSend</span></span>|<span data-ttu-id="fdf97-115">包含实现要求/响应适配器通信模式的项目。</span><span class="sxs-lookup"><span data-stu-id="fdf97-115">Contains the project that implements the solicit/response adapter communication pattern.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="fdf97-116">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="fdf97-116">How to Use This Sample</span></span>  
 <span data-ttu-id="fdf97-117">此示例旨在为您要在开发自定义适配器中使用的框架。</span><span class="sxs-lookup"><span data-stu-id="fdf97-117">This sample is meant as a framework for you to use in developing custom adapters.</span></span> <span data-ttu-id="fdf97-118">在某些情况下 BizTalk Server 可能需要消息传输到特定的自定义应用程序或为其使用的协议不存在的本机适配器。</span><span class="sxs-lookup"><span data-stu-id="fdf97-118">In some cases BizTalk Server may need to transport messages to a specific custom application or use a protocol for which a native adapter that does not exist.</span></span> <span data-ttu-id="fdf97-119">第三方公司编写了适配器，以支持其他协议。</span><span class="sxs-lookup"><span data-stu-id="fdf97-119">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="fdf97-120">您可能想要确定是否有您的协议的适配器在决定编写自定义适配器之前。</span><span class="sxs-lookup"><span data-stu-id="fdf97-120">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="fdf97-121">如果您找不到适配器以支持您的通信要求，可以开发自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="fdf97-121">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  

 <span data-ttu-id="fdf97-122">编写自定义适配器很有挑战性的工作。</span><span class="sxs-lookup"><span data-stu-id="fdf97-122">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="fdf97-123">若要简化此过程，Microsoft 已开发了称作适配器框架的基础。</span><span class="sxs-lookup"><span data-stu-id="fdf97-123">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="fdf97-124">可以将此框架为基础进行开发以及 BizTalk Server SDK 中的示例适配器源代码。</span><span class="sxs-lookup"><span data-stu-id="fdf97-124">You can use this framework as a basis for your development along with sample adapter source code in the BizTalk Server SDK.</span></span>  <span data-ttu-id="fdf97-125">有关自定义适配器和适配器框架的详细信息，请参阅**另请参阅**本文档末尾部分。</span><span class="sxs-lookup"><span data-stu-id="fdf97-125">For more information on custom adapters, and the Adapter Framework, please refer to the **See Also** section at the end of this document.</span></span>  

## <a name="building-and-initializing-the-sample-adapter"></a><span data-ttu-id="fdf97-126">生成并初始化示例适配器</span><span class="sxs-lookup"><span data-stu-id="fdf97-126">Building and Initializing the Sample Adapter</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="fdf97-127">如果 BizTalk 安装的是 64 位或修改安装位置，OutboundAssemblyPath、 InboundAssemblyPath、 AdapterMgmtAssemblyPath 需要相应地更改。</span><span class="sxs-lookup"><span data-stu-id="fdf97-127">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  

#### <a name="to-build-and-initialize-the-http-adapter-sample"></a><span data-ttu-id="fdf97-128">若要生成并初始化 HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="fdf97-128">To build and initialize the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="fdf97-129">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="fdf97-129">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="fdf97-130">\<*Samples Path*\>\AdaptersDevelopment\HttpAdapter</span><span class="sxs-lookup"><span data-stu-id="fdf97-130">\<*Samples Path*\>\AdaptersDevelopment\HttpAdapter</span></span>  

2. <span data-ttu-id="fdf97-131">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fdf97-131">Run the file Setup.bat, which performs the following actions:</span></span>  

   -   <span data-ttu-id="fdf97-132">编译 HTTPAdapter 及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="fdf97-132">Compiles the HTTPAdapter and all of its dependencies.</span></span>  

   -   <span data-ttu-id="fdf97-133">创建适配器的接收方端使用的 Internet 信息服务 (IIS) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdf97-133">Creates an Internet Information Services (IIS) application used by the receiver side of the adapter.</span></span>  

   <span data-ttu-id="fdf97-134">在 IIS 7.0 中，必须确保运行此 IIS 应用程序的应用程序池标识是以下组的成员：</span><span class="sxs-lookup"><span data-stu-id="fdf97-134">On IIS 7.0, you must ensure the identity of the application pool running this IIS application is a member of the following groups:</span></span>  

-   <span data-ttu-id="fdf97-135">BizTalk Isolated Host Users 组。</span><span class="sxs-lookup"><span data-stu-id="fdf97-135">BizTalk Isolated Host Users group.</span></span>  

-   <span data-ttu-id="fdf97-136">IIS_WPG 组。</span><span class="sxs-lookup"><span data-stu-id="fdf97-136">IIS_WPG group.</span></span>  

-   <span data-ttu-id="fdf97-137">在 IIS 7.0 上必须迁移应用程序集成.NET 模式下工作。</span><span class="sxs-lookup"><span data-stu-id="fdf97-137">On IIS 7.0, you must migrate the application to work with the Integrated .NET mode.</span></span> <span data-ttu-id="fdf97-138">您可以将迁移应用程序配置，包括的内容\<httpHandlers\>配置部分中的，通过使用以下从命令行窗口 （窗口中必须以管理员身份运行）：</span><span class="sxs-lookup"><span data-stu-id="fdf97-138">You can migrate the application configuration, including the contents of the \<httpHandlers\> configuration section, by using the following from a command line window (the window must be running as Administrator):</span></span>  

    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  

-   <span data-ttu-id="fdf97-139">迁移你的应用程序后，它将运行在经典和集成.NET 模式下，以及在下级平台上。</span><span class="sxs-lookup"><span data-stu-id="fdf97-139">After you migrate your application, it will run in both Classic and Integrated .NET modes, as well as on downlevel platforms.</span></span>  

> [!NOTE]
>  <span data-ttu-id="fdf97-140">在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="fdf97-140">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  

> [!NOTE]
>  <span data-ttu-id="fdf97-141">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="fdf97-141">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="fdf97-142">使用此密钥对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="fdf97-142">Use this key pair to sign the resulting assemblies.</span></span>  

> [!NOTE]
>  <span data-ttu-id="fdf97-143">若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="fdf97-143">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="fdf97-144">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="fdf97-144">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="registering-the-sample-adapter"></a><span data-ttu-id="fdf97-145">注册示例适配器</span><span class="sxs-lookup"><span data-stu-id="fdf97-145">Registering the Sample Adapter</span></span>  

#### <a name="to-register-the-http-adapter-sample"></a><span data-ttu-id="fdf97-146">若要注册 HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="fdf97-146">To register the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="fdf97-147">在 Windows 资源管理器，导航到安装驱动器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后导航到\<示例路径\>\AdaptersDevelopment\HTTPAdapter。</span><span class="sxs-lookup"><span data-stu-id="fdf97-147">In Windows Explorer, navigate to the installation drive for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then navigate to \<Samples Path\>\AdaptersDevelopment\HTTPAdapter.</span></span>  

2. <span data-ttu-id="fdf97-148">若要将示例适配器添加到注册表中，双击**HTTP.NET.reg**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-148">To add the sample adapter to the registry, double-click **HTTP.NET.reg**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="fdf97-149">HTTP.NET.reg 包含硬编码路径[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装目录。</span><span class="sxs-lookup"><span data-stu-id="fdf97-149">HTTP.NET.reg includes hard-coded paths to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation directory.</span></span> <span data-ttu-id="fdf97-150">如果未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的默认位置或者升级你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从以前版本的安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则必须修改文件 HTTP.NET.reg 使用相应的路径。</span><span class="sxs-lookup"><span data-stu-id="fdf97-150">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the default location or if you upgraded your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from a previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must modify the file HTTP.NET.reg with the appropriate paths.</span></span> <span data-ttu-id="fdf97-151">更新相关联的"揙 OutboundAssemblyPath"和"AdapterMgmtAssemblyPath"值，使其指向正确的位置的指定文件的路径。</span><span class="sxs-lookup"><span data-stu-id="fdf97-151">Update the paths associated with the "OutboundAssemblyPath" and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="fdf97-152">如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为 hkey_classes_root\wow6432node\clsid \ 中**HTTP.NET.reg**注册表文件。</span><span class="sxs-lookup"><span data-stu-id="fdf97-152">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **HTTP.NET.reg** registry file.</span></span>  

3. <span data-ttu-id="fdf97-153">在中**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-153">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  

4. <span data-ttu-id="fdf97-154">若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-154">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  

## <a name="installing-the-sample-adapter"></a><span data-ttu-id="fdf97-155">安装示例适配器</span><span class="sxs-lookup"><span data-stu-id="fdf97-155">Installing the Sample Adapter</span></span>  

#### <a name="to-install-the-http-adapter-sample"></a><span data-ttu-id="fdf97-156">若要安装 HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="fdf97-156">To install the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="fdf97-157">单击**启动**菜单中，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-157">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="fdf97-158">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]树，然后展开**BizTalk 组**树，然后展开**平台设置**树。</span><span class="sxs-lookup"><span data-stu-id="fdf97-158">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] tree, then expand the **BizTalk Group** tree, then expand the **Platform Settings** tree.</span></span>  

3. <span data-ttu-id="fdf97-159">右键单击**适配器**，单击**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-159">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

4. <span data-ttu-id="fdf97-160">在中**适配器属性**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="fdf97-160">In the **Adapter Properties** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="fdf97-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fdf97-161">Use this</span></span>   |                  <span data-ttu-id="fdf97-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fdf97-162">To do this</span></span>                  |
   |-------------|----------------------------------------------|
   |    <span data-ttu-id="fdf97-163">“属性”</span><span class="sxs-lookup"><span data-stu-id="fdf97-163">Name</span></span>     |              <span data-ttu-id="fdf97-164">类型**HTTP.NET**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-164">Type **HTTP.NET**.</span></span>              |
   |   <span data-ttu-id="fdf97-165">适配器</span><span class="sxs-lookup"><span data-stu-id="fdf97-165">Adapter</span></span>   | <span data-ttu-id="fdf97-166">选择**HTTP.NET**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="fdf97-166">Select **HTTP.NET** from the drop-down list.</span></span> |
   | <span data-ttu-id="fdf97-167">Description</span><span class="sxs-lookup"><span data-stu-id="fdf97-167">Description</span></span> |      <span data-ttu-id="fdf97-168">类型**示例 HTTP.NET 适配器**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-168">Type **Sample HTTP.NET Adapter**.</span></span>       |


5. <span data-ttu-id="fdf97-169">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="fdf97-169">Click **OK**.</span></span>  

6. <span data-ttu-id="fdf97-170">此时，适配器将显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。</span><span class="sxs-lookup"><span data-stu-id="fdf97-170">The adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  

## <a name="stopping-and-restarting-the-host-instance"></a><span data-ttu-id="fdf97-171">停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="fdf97-171">Stopping and Restarting the Host Instance</span></span>  

#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a><span data-ttu-id="fdf97-172">若要停止并重新启动 HTTP 适配器示例的主机实例</span><span class="sxs-lookup"><span data-stu-id="fdf97-172">To stop and restart the host instance for the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="fdf97-173">单击**启动**菜单中，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fdf97-173">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and select [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="fdf97-174">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]树，然后展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-174">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] tree, then expand **Platform Settings**, and click **Host Instances**.</span></span>  

3. <span data-ttu-id="fdf97-175">在结果窗格中，右键单击主机实例 （通常情况下，计算机名称），然后依次**停止**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-175">In the results pane, right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  

    <span data-ttu-id="fdf97-176">主机实例的状态将变为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-176">The status of the host instance changes to **Stopped**.</span></span>  

4. <span data-ttu-id="fdf97-177">在结果窗格中，右键单击该主机实例，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-177">In the results pane, right-click the host instance, and then click **Start**.</span></span>  

   <span data-ttu-id="fdf97-178">现在，HTTP.NET 适配器已准备好应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="fdf97-178">The HTTP.NET adapter is now ready to be used by your application.</span></span> <span data-ttu-id="fdf97-179">配置适配器的格式时**虚拟目录**传输属性的形式： /httpreceive/httpreceive.aspx?optionalQueryString。</span><span class="sxs-lookup"><span data-stu-id="fdf97-179">When configuring the adapter, the format for the **Virtual Directory** transport property is of the form: /httpreceive/httpreceive.aspx?optionalQueryString.</span></span>  

## <a name="comments"></a><span data-ttu-id="fdf97-180">注释</span><span class="sxs-lookup"><span data-stu-id="fdf97-180">Comments</span></span>  
 <span data-ttu-id="fdf97-181">建立的 HTTP.NET 适配器中提供的 BaseAdapter 类用法 *\<示例路径\>* \AdaptersDevelopment\BaseAdapter\v1.0...2\\。</span><span class="sxs-lookup"><span data-stu-id="fdf97-181">The HTTP.NET adapter makes use of the BaseAdapter classes provided in *\<Samples Path\>* \AdaptersDevelopment\BaseAdapter\v1.0..2\\.</span></span> <span data-ttu-id="fdf97-182">BaseAdapter 项目中提供的类旨在加快适配器的开发速度。</span><span class="sxs-lookup"><span data-stu-id="fdf97-182">The classes provided in the BaseAdapter project are intended to accelerate adapter development.</span></span> <span data-ttu-id="fdf97-183">请参考有关提供的类的详细信息的 BaseAdapter 代码注释。</span><span class="sxs-lookup"><span data-stu-id="fdf97-183">Refer to the BaseAdapter code comments for details about the classes provided.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fdf97-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdf97-184">See Also</span></span>  
 <span data-ttu-id="fdf97-185">[注册适配器](../core/registering-an-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-185">[Registering an Adapter](../core/registering-an-adapter.md) </span></span>  
 <span data-ttu-id="fdf97-186">[适配器示例-用法](../core/adapter-samples-usage.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-186">[Adapter Samples - Usage](../core/adapter-samples-usage.md) </span></span>  
 <span data-ttu-id="fdf97-187">[开发自定义适配器](../core/developing-custom-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-187">[Developing Custom Adapters](../core/developing-custom-adapters.md) </span></span>  
 <span data-ttu-id="fdf97-188">[适配器框架是什么？](../core/what-is-the-adapter-framework.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-188">[What Is the Adapter Framework?](../core/what-is-the-adapter-framework.md) </span></span>  
 <span data-ttu-id="fdf97-189">[使用适配器框架工具](../core/using-the-adapter-framework-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-189">[Using the Adapter Framework Tools](../core/using-the-adapter-framework-tools.md) </span></span>  
 <span data-ttu-id="fdf97-190">[开发接收适配器](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-190">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="fdf97-191">[开发发送适配器](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-191">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="fdf97-192">[如何部署自定义适配器](../core/how-to-deploy-a-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-192">[How to Deploy a Custom Adapter](../core/how-to-deploy-a-custom-adapter.md) </span></span>  
 <span data-ttu-id="fdf97-193">[设计您的适配器的提示](../core/tips-for-designing-your-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fdf97-193">[Tips for Designing Your Adapter](../core/tips-for-designing-your-adapter.md) </span></span>  
 [<span data-ttu-id="fdf97-194">适配器设计时配置</span><span class="sxs-lookup"><span data-stu-id="fdf97-194">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)