---
title: 如何安装业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: 61
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb067c206018996bc48641bcd8211921b0294dd
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752518"
---
# <a name="how-to-install-the-business-process-management-solution"></a><span data-ttu-id="2696e-102">如何安装业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="2696e-102">How to Install the Business Process Management Solution</span></span>
<span data-ttu-id="2696e-103">以下步骤介绍如何为安装业务流程管理 (BPM) 解决方案准备计算机，以及如何在此计算机上安装该解决方案：</span><span class="sxs-lookup"><span data-stu-id="2696e-103">The following steps describe how to prepare the computer for installing the Business Process Management (BPM) solution, and how to install the solution on this computer.</span></span>  
  
-   [<span data-ttu-id="2696e-104">准备用于安装业务流程管理解决方案的计算机</span><span class="sxs-lookup"><span data-stu-id="2696e-104">Prepare the computer for installing the Business Process Management Solution</span></span>](#step1)  
  
     <span data-ttu-id="2696e-105">在准备步骤中，需要创建将由接收和发送端口使用的文件夹、队列和 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="2696e-105">In the preparation step, you create the folders, queues, and SQL database that will be used by the receive and send ports.</span></span> <span data-ttu-id="2696e-106">还要为客户端应用程序、CSRWebApp 和 OrderBroker 代理 Web Services 创建两个虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="2696e-106">You also create the two virtual directories for the client application, CSRWebApp, and the OrderBroker proxy Web Service.</span></span>  
  
-   [<span data-ttu-id="2696e-107">配置用于安装业务流程管理解决方案的计算机</span><span class="sxs-lookup"><span data-stu-id="2696e-107">Configure the computer for installing the Business Process Management Solution</span></span>](#step3)  
  
-   [<span data-ttu-id="2696e-108">安装业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="2696e-108">Install the Business Process Management Solution</span></span>](#step5)  
  
> [!NOTE]
>  <span data-ttu-id="2696e-109">您将运行一些批处理文件以部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="2696e-109">You will run some batch files to deploy the solution.</span></span> <span data-ttu-id="2696e-110">建议将批处理文件的输出重定向到文本文件，以检验脚本是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="2696e-110">We recommend that you redirect the output of the batch files to a text file to verify that the script completed successfully.</span></span>  
  
##  <a name="step1"></a> <span data-ttu-id="2696e-111">准备用于安装业务流程管理解决方案的计算机</span><span class="sxs-lookup"><span data-stu-id="2696e-111">Prepare the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="2696e-112">若要准备用于安装业务流程管理解决方案的计算机</span><span class="sxs-lookup"><span data-stu-id="2696e-112">To prepare the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="2696e-113">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**服务**。</span><span class="sxs-lookup"><span data-stu-id="2696e-113">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="2696e-114">使用**Services**控制台中，请确保以下服务正在运行：</span><span class="sxs-lookup"><span data-stu-id="2696e-114">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="2696e-115">**FTP 发布**</span><span class="sxs-lookup"><span data-stu-id="2696e-115">**FTP Publishing**</span></span>  
  
    -   <span data-ttu-id="2696e-116">**消息队列**</span><span class="sxs-lookup"><span data-stu-id="2696e-116">**Message Queuing**</span></span>  
  
    -   <span data-ttu-id="2696e-117">**World Wide Web 发布**</span><span class="sxs-lookup"><span data-stu-id="2696e-117">**World Wide Web Publishing**</span></span>  
  
2.  <span data-ttu-id="2696e-118">单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，以及如何将到本地管理员组的 BizTalk 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="2696e-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="2696e-119">如果您安装了 Windows SharePoint Services，排除了 （根） 的**Default Web Site** ，如下所示 Windows SharePoint Services 管理路径中： 单击**启动**，指向**所有程序**，依次指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="2696e-119">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="2696e-120">下**虚拟服务器配置**，选择**配置虚拟服务器设置**。</span><span class="sxs-lookup"><span data-stu-id="2696e-120">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="2696e-121">上**虚拟服务器列表**页上，单击**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="2696e-121">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="2696e-122">上**虚拟服务器设置**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="2696e-122">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="2696e-123">在中**包含的路径**一部分**定义管理路径**页上，选择**根**，然后单击**删除所选的路径**。</span><span class="sxs-lookup"><span data-stu-id="2696e-123">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="2696e-124">在命令提示符下，执行 IISReset。</span><span class="sxs-lookup"><span data-stu-id="2696e-124">At a command prompt, perform an IISReset.</span></span>  
  
##  <a name="step3"></a> <span data-ttu-id="2696e-125">配置用于安装业务流程管理解决方案的计算机</span><span class="sxs-lookup"><span data-stu-id="2696e-125">Configure the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="2696e-126">若要配置用于安装业务流程管理解决方案的计算机</span><span class="sxs-lookup"><span data-stu-id="2696e-126">To configure the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="2696e-127">从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="2696e-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
2.  <span data-ttu-id="2696e-128">打开命令提示符，键入以下命令，然后按 Enter 设置 %BTSSolutionsPath% 环境变量，以指示 E2E 解决方案的基本文件夹。</span><span class="sxs-lookup"><span data-stu-id="2696e-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable to indicate the base folder for the E2E solutions.</span></span> <span data-ttu-id="2696e-129">然后，退出命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2696e-129">Then, exit the command prompt.</span></span>  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  <span data-ttu-id="2696e-130">如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。</span><span class="sxs-lookup"><span data-stu-id="2696e-130">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2696e-131">有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831)。</span><span class="sxs-lookup"><span data-stu-id="2696e-131">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
3.  <span data-ttu-id="2696e-132">打开命令提示符下，将当前目录更改为 %BTSSolutionsPath%\BPM\HistoryDB 文件夹，键入`CreateDatabase.cmd`，然后按 ENTER 以创建历史记录数据库。</span><span class="sxs-lookup"><span data-stu-id="2696e-132">Open a command prompt, change the current directory to %BTSSolutionsPath%\BPM\HistoryDB folder, type `CreateDatabase.cmd`, and press ENTER to create the history database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2696e-133">运行指定作为 SQL 发送适配器处理程序的主机的用户必须具有对 SouthridgeVideoHistory 数据库执行存储过程的权限。</span><span class="sxs-lookup"><span data-stu-id="2696e-133">The user running the host specified as the handler for the SQL send adapter must have permissions to execute stored procedures on the SouthridgeVideoHistory database.</span></span>  
  
4.  <span data-ttu-id="2696e-134">在命令提示符下，运行以下命令以将默认脚本主机更改为 CScript.exe</span><span class="sxs-lookup"><span data-stu-id="2696e-134">At a command prompt, run the following command to change the default script host to CScript.exe</span></span>  
  
    -   `CScript /H:CScript`  
  
5.  <span data-ttu-id="2696e-135">在命令提示符下，运行以下命令以创建 CSRWebApp Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="2696e-135">At a command prompt, run the following command to create the CSRWebApp Web application</span></span>  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  <span data-ttu-id="2696e-136">有关 iisvdir.vbs 的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=67830 ](http://go.microsoft.com/fwlink/?LinkId=67830)。</span><span class="sxs-lookup"><span data-stu-id="2696e-136">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
6.  <span data-ttu-id="2696e-137">在命令提示符下，运行以下命令以为 OrderBroker_Proxy 创建新的 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="2696e-137">At a command prompt, run the following command to create a new IIS virtual directory for OrderBroker_Proxy.</span></span>  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  <span data-ttu-id="2696e-138">Internet 信息服务 (IIS) 管理器可用于创建 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2696e-138">You can use Internet Information Services (IIS) Manager to create the Web Application.</span></span> <span data-ttu-id="2696e-139">有关如何在 IIS 7.0 中创建应用程序的详细信息，请参阅上的 IIS 7.0 文档[ http://go.microsoft.com/fwlink/?LinkId=59263 ](http://go.microsoft.com/fwlink/?LinkId=59263)。</span><span class="sxs-lookup"><span data-stu-id="2696e-139">For more information about how to create applications in IIS 7.0, see the IIS 7.0 Documentation at [http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263).</span></span>  
  
7.  <span data-ttu-id="2696e-140">创建新的 IIS 应用程序池，并将其标识设置为 BizTalk Isolated Host Users 组和 IIS_WPG 组的成员用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2696e-140">Create a new IIS application pool and set its identity as a user that is a member of the BizTalk Isolated Host Users group and the IIS_WPG group, as follows:</span></span>  
  
    1.  <span data-ttu-id="2696e-141">在 Internet 信息服务 (IIS) 管理器中，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="2696e-141">In Internet Information Services (IIS) Manager, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    2.  <span data-ttu-id="2696e-142">类型**应用程序池 ID** （任何值），然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2696e-142">Type the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="2696e-143">右键单击应用程序池创建，并选择**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="2696e-143">Right-click the application pool that you created, and then select **Advanced Settings**.</span></span>  
  
    4.  <span data-ttu-id="2696e-144">展开**过程模型**，在右侧列中单击**标识**设置，然后依次 **...**</span><span class="sxs-lookup"><span data-stu-id="2696e-144">Expand **Process Model**, click in the right-column for the **Identity** setting, and then click **…**</span></span>  
  
    5.  <span data-ttu-id="2696e-145">选择用户帐户 (任一**内置帐户**或**自定义帐户**) 有权创建和执行在 Windows\Temp 目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="2696e-145">Select a user account (either a **Build-in account** or **Custom account** ) that has permissions to create and execute files in the Windows\Temp directory.</span></span> <span data-ttu-id="2696e-146">在配置 BizTalk 时，配置过程已为添加到 BizTalk Isolated Host Users 组中的用户设置了这些权限。</span><span class="sxs-lookup"><span data-stu-id="2696e-146">When you configured BizTalk, the configuration process already set these permissions for the user it added to the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="2696e-147">最好指定同一用户。</span><span class="sxs-lookup"><span data-stu-id="2696e-147">Specifying the same user is a good choice.</span></span>  
  
8.  <span data-ttu-id="2696e-148">在 Internet 信息服务 (IIS) 管理器中，展开**网站**，展开**Default Web Site**，右键单击**BTSScn.BPM.OrderBroker_Proxy**，指向**管理应用程序**，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="2696e-148">In Internet Information Services (IIS) Manager, expand **Web Sites**, expand **Default Web Site**, right-click **BTSScn.BPM.OrderBroker_Proxy**, point to **Manage Application**, and then click **Advanced Settings**.</span></span>  
  
9. <span data-ttu-id="2696e-149">设置**应用程序池**到上一步中创建的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="2696e-149">Set **Application Pool** to the application pool that you  created in the previous step.</span></span>  
  
10. <span data-ttu-id="2696e-150">重复前面的两个步骤对于**CSRWebApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="2696e-150">Repeat the previous two steps for the **CSRWebApp** application.</span></span>  
  
11. <span data-ttu-id="2696e-151">重置 IIS 以确保所有这些更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="2696e-151">Reset IIS to make sure all these changes take effect immediately.</span></span> <span data-ttu-id="2696e-152">若要执行此操作，请运行**iisreset**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2696e-152">To do this, run **iisreset** at a command prompt.</span></span>  
  
12. <span data-ttu-id="2696e-153">在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm\scripts，类型`CreateQueues.vbs`，然后按 ENTER 以创建以下专用队列。</span><span class="sxs-lookup"><span data-stu-id="2696e-153">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateQueues.vbs`, and then press ENTER to create the following private queues.</span></span>  
  
    |<span data-ttu-id="2696e-154">“属性”</span><span class="sxs-lookup"><span data-stu-id="2696e-154">Name</span></span>|<span data-ttu-id="2696e-155">事务性</span><span class="sxs-lookup"><span data-stu-id="2696e-155">Transactional</span></span>|<span data-ttu-id="2696e-156">事务协议</span><span class="sxs-lookup"><span data-stu-id="2696e-156">Transaction protocol</span></span>|  
    |----------|-------------------|--------------------------|  
    |<span data-ttu-id="2696e-157">ToFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="2696e-157">ToFacilitiesQ</span></span>|<span data-ttu-id="2696e-158">用户帐户控制</span><span class="sxs-lookup"><span data-stu-id="2696e-158">Yes</span></span>|<span data-ttu-id="2696e-159">本机</span><span class="sxs-lookup"><span data-stu-id="2696e-159">Native</span></span>|  
    |<span data-ttu-id="2696e-160">FromFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="2696e-160">FromFacilitiesQ</span></span>|<span data-ttu-id="2696e-161">用户帐户控制</span><span class="sxs-lookup"><span data-stu-id="2696e-161">Yes</span></span>|<span data-ttu-id="2696e-162">本机</span><span class="sxs-lookup"><span data-stu-id="2696e-162">Native</span></span>|  
    |<span data-ttu-id="2696e-163">FromFixedOrdersQ</span><span class="sxs-lookup"><span data-stu-id="2696e-163">FromFixedOrdersQ</span></span>|<span data-ttu-id="2696e-164">用户帐户控制</span><span class="sxs-lookup"><span data-stu-id="2696e-164">Yes</span></span>|<span data-ttu-id="2696e-165">本机</span><span class="sxs-lookup"><span data-stu-id="2696e-165">Native</span></span>|  
    |<span data-ttu-id="2696e-166">ToServicingSystemQ</span><span class="sxs-lookup"><span data-stu-id="2696e-166">ToServicingSystemQ</span></span>|<span data-ttu-id="2696e-167">用户帐户控制</span><span class="sxs-lookup"><span data-stu-id="2696e-167">Yes</span></span>|<span data-ttu-id="2696e-168">本机</span><span class="sxs-lookup"><span data-stu-id="2696e-168">Native</span></span>|  
    |<span data-ttu-id="2696e-169">ToCSRSystemQ</span><span class="sxs-lookup"><span data-stu-id="2696e-169">ToCSRSystemQ</span></span>|<span data-ttu-id="2696e-170">否</span><span class="sxs-lookup"><span data-stu-id="2696e-170">No</span></span>|<span data-ttu-id="2696e-171">HTTP</span><span class="sxs-lookup"><span data-stu-id="2696e-171">HTTP</span></span>|  
    |<span data-ttu-id="2696e-172">ToVendorSystemQ</span><span class="sxs-lookup"><span data-stu-id="2696e-172">ToVendorSystemQ</span></span>|<span data-ttu-id="2696e-173">否</span><span class="sxs-lookup"><span data-stu-id="2696e-173">No</span></span>|<span data-ttu-id="2696e-174">HTTP</span><span class="sxs-lookup"><span data-stu-id="2696e-174">HTTP</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="2696e-175">可以使用**计算机管理**管理单元来创建队列。</span><span class="sxs-lookup"><span data-stu-id="2696e-175">You can use **Computer Management** snap-in to create the queues.</span></span> <span data-ttu-id="2696e-176">有关如何创建专用队列的详细信息，请参阅消息队列文档，网址[ http://go.microsoft.com/fwlink/?LinkId=59264 ](http://go.microsoft.com/fwlink/?LinkId=59264)。</span><span class="sxs-lookup"><span data-stu-id="2696e-176">For more information about how to create a private queue, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264).</span></span> <span data-ttu-id="2696e-177">有关如何安装 MSMQ 3.0 的详细信息，请参阅消息队列文档，网址[ http://go.microsoft.com/fwlink/?LinkId=59265 ](http://go.microsoft.com/fwlink/?LinkId=59265)。</span><span class="sxs-lookup"><span data-stu-id="2696e-177">For more information about how to install MSMQ 3.0, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265).</span></span>  
  
13. <span data-ttu-id="2696e-178">在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm\scripts，类型`CreateTestDirectories.cmd`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2696e-178">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateTestDirectories.cmd`, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="2696e-179">将在 %SystemDrive%\BPMTest 文件夹中创建以下文件夹</span><span class="sxs-lookup"><span data-stu-id="2696e-179">The following folders are crated in %SystemDrive%\BPMTest folder</span></span>  
  
         <span data-ttu-id="2696e-180">CSRResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="2696e-180">CSRResponse-DSP</span></span>  
  
         <span data-ttu-id="2696e-181">VendorResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="2696e-181">VendorResponse-DSP</span></span>  
  
         <span data-ttu-id="2696e-182">OrderErrors-SP</span><span class="sxs-lookup"><span data-stu-id="2696e-182">OrderErrors-SP</span></span>  
  
         <span data-ttu-id="2696e-183">ErrorResponse-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="2696e-183">ErrorResponse-RP-TestRL</span></span>  
  
         <span data-ttu-id="2696e-184">Facilities-SP</span><span class="sxs-lookup"><span data-stu-id="2696e-184">Facilities-SP</span></span>  
  
         <span data-ttu-id="2696e-185">Facilities-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="2696e-185">Facilities-RP-TestRL</span></span>  
  
         <span data-ttu-id="2696e-186">HistoryInsert-SP</span><span class="sxs-lookup"><span data-stu-id="2696e-186">HistoryInsert-SP</span></span>  
  
         <span data-ttu-id="2696e-187">HistoryUpdate-SP</span><span class="sxs-lookup"><span data-stu-id="2696e-187">HistoryUpdate-SP</span></span>  
  
         <span data-ttu-id="2696e-188">Order-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="2696e-188">Order-RP-TestRL</span></span>  
  
         <span data-ttu-id="2696e-189">ServicingSystem-SP</span><span class="sxs-lookup"><span data-stu-id="2696e-189">ServicingSystem-SP</span></span>  
  
         <span data-ttu-id="2696e-190">Vendor-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="2696e-190">Vendor-RP-TestRL</span></span>  
  
         <span data-ttu-id="2696e-191">BizTalkErrors-SP</span><span class="sxs-lookup"><span data-stu-id="2696e-191">BizTalkErrors-SP</span></span>  
  
    -   <span data-ttu-id="2696e-192">在 %SystemDrive%\Inetpub\ftproot 文件夹中创建 FromVendor 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2696e-192">FromVendor folder is created in the %SystemDrive%\Inetpub\ftproot folder.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2696e-193">如果 Windows 系统未安装在 C 驱动器上，则应将 %SystemDrive% 替换为 C:。</span><span class="sxs-lookup"><span data-stu-id="2696e-193">If the Windows system is not installed on the C drive, you should replace %SystemDrive% with C:.</span></span> <span data-ttu-id="2696e-194">文件夹名称必须与 BPM 解决方案所提供的绑定文件中的地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="2696e-194">You have to match the folder names to the address in the binding files that the BPM solution provides.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2696e-195">BizTalk 服务帐户必须对 FromVendor 文件夹具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="2696e-195">The BizTalk service account must have read/write permission to the FromVendor folder.</span></span>  
  
##  <a name="step5"></a> <span data-ttu-id="2696e-196">安装业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="2696e-196">Install the Business Process Management Solution</span></span>  
  
#### <a name="to-install-the-business-process-management-solution"></a><span data-ttu-id="2696e-197">安装业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="2696e-197">To install the Business Process Management Solution</span></span>  
  
1. <span data-ttu-id="2696e-198">在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm，类型`SetupBPM.bat`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2696e-198">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM, type `SetupBPM.bat`, and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2696e-199">在运行 setupbpm.bat 之前，在文件中 **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl**和 **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**，8f8bbebbb3fb375a 的所有实例都替换为 XXXXXXXXXXXXXXXX。</span><span class="sxs-lookup"><span data-stu-id="2696e-199">Before running SetupBPM.bat, in the files **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl** and **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**, replace all instances of 8f8bbebbb3fb375a with XXXXXXXXXXXXXXXX.</span></span>  
  
    <span data-ttu-id="2696e-200">SetupBPM.bat 将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2696e-200">The SetupBPM.bat performs the following tasks:</span></span>  
  
   1.  <span data-ttu-id="2696e-201">创建唯一强名称密钥 (SNK)，用于对 BPM 解决方案的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="2696e-201">Creates a unique strong name key (SNK) for signing the assemblies of the BPM Solution.</span></span>  
  
   2.  <span data-ttu-id="2696e-202">从 SNK 中提取公钥标记。</span><span class="sxs-lookup"><span data-stu-id="2696e-202">Extracts the public key token from the SNK.</span></span>  
  
   3.  <span data-ttu-id="2696e-203">使用该公钥标记更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="2696e-203">Updates the binding files with the public token.</span></span>  
  
   4.  <span data-ttu-id="2696e-204">生成 BPM 解决方案，并安装 OpsAdapter。</span><span class="sxs-lookup"><span data-stu-id="2696e-204">Builds the BPM solution, and installs OpsAdapter.</span></span>  
  
   5.  <span data-ttu-id="2696e-205">在 %BTSSolutionsPath%\Common 文件夹中生成 SSOApplicationConfig。</span><span class="sxs-lookup"><span data-stu-id="2696e-205">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
2. <span data-ttu-id="2696e-206">使用业务规则引擎部署向导部署 Southridge Video 业务规则：</span><span class="sxs-lookup"><span data-stu-id="2696e-206">Deploy the Southridge Video business rules using the Business Rule Engine Deployment Wizard:</span></span>  
  
   1. <span data-ttu-id="2696e-207">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="2696e-207">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="2696e-208">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2696e-208">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2696e-209">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="2696e-209">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
   2. <span data-ttu-id="2696e-210">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-210">On the **Welcome** page, click **Next**.</span></span>  
  
   3. <span data-ttu-id="2696e-211">上**部署任务**页上，选择**导入策略/词汇并发布到数据库文件从**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-211">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
   4. <span data-ttu-id="2696e-212">上**策略存储区**页上，保留所有其他默认设置，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-212">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
   5. <span data-ttu-id="2696e-213">上**导入规则引擎策略/词汇文件**页上，单击**浏览**，选择 %BTSSolutionsPath%\BPM\Rules 文件夹中的 DecodeAndValidateOrderRules.xml 文件，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-213">On the **Import Rules Engine Policy/Vocabulary file** page, click **Browse**, select the DecodeAndValidateOrderRules.xml file in the %BTSSolutionsPath%\BPM\Rules folder, and then click **Next**.</span></span>  
  
   6. <span data-ttu-id="2696e-214">上**准备好**页上，单击**下一步**，然后在**导入策略/词汇**页上，单击**下一步**</span><span class="sxs-lookup"><span data-stu-id="2696e-214">On the **Ready** page, click **Next**, and then on the **Importing Policy/Vocabulary** page, click **Next**</span></span>  
  
   7. <span data-ttu-id="2696e-215">在完成页上选择**再次运行向导**以再次打开该向导，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="2696e-215">On the Completion page, select **Run the wizard again** to open the Wizard again, and then click **Finish**.</span></span>  
  
   8. <span data-ttu-id="2696e-216">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-216">On the **Welcome** page, click **Next**.</span></span>  
  
   9. <span data-ttu-id="2696e-217">上**部署任务**页上，选择**DeployPolicy**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-217">On the **Deployment Task** page, select **DeployPolicy**, and then click **Next**.</span></span>  
  
   10. <span data-ttu-id="2696e-218">上**策略存储区**页上，保留所有其他默认设置，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-218">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
   11. <span data-ttu-id="2696e-219">上**部署策略**页上，选择**DecodeAndValidateOrder 1.0**中**规则引擎策略**下拉列表，再单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="2696e-219">On the **Deploy Policy** page, select **DecodeAndValidateOrder 1.0** in the **Rule Engine Policy** drop-down list, and then click **Next**.</span></span>  
  
   12. <span data-ttu-id="2696e-220">上**准备好**页上，单击**下一步**，然后在**部署策略**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2696e-220">On the **Ready** page, click **Next**, and then on the **Deploying Policy** page, click **Next**.</span></span>  
  
   13. <span data-ttu-id="2696e-221">在完成页上单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="2696e-221">On the Completion page, click **Finish**.</span></span>  
  
3. <span data-ttu-id="2696e-222">如果您安装 BPM 解决方案的 64 位计算机上，然后</span><span class="sxs-lookup"><span data-stu-id="2696e-222">If you install the BPM solution on a 64-bit computer, then</span></span>  
  
   1.  <span data-ttu-id="2696e-223">打开 32 位命令提示符，以下操作： 单击**启动**，单击**运行**，类型`%SYSTEMROOT%\SYSWOW64\CMD.EXE`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2696e-223">Open a 32-bit command prompt as follow: Click **Start**, click **Run**, type `%SYSTEMROOT%\SYSWOW64\CMD.EXE`, and then press ENTER.</span></span>  
  
   2.  <span data-ttu-id="2696e-224">在 32 位命令提示符下，将目录更改为 %BTSSolutionsPath%\BPM\Scripts 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2696e-224">At the 32-bit command prompt, change the directory to the %BTSSolutionsPath%\BPM\Scripts folder.</span></span>  
  
   3.  <span data-ttu-id="2696e-225">使用记事本，打开 CreateSouthridgeVideoApplication.cmd，然后将“%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe”替换为“%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe”。</span><span class="sxs-lookup"><span data-stu-id="2696e-225">Using Notepad, open the CreateSouthridgeVideoApplication.cmd, and then replace "%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" with "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe".</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="2696e-226">在 32 位命令提示符下，%CommonProgramFiles% 变量将更改为“%ProgramFiles(x86)%\Common Files”。</span><span class="sxs-lookup"><span data-stu-id="2696e-226">At a 32-bit command prompt, the %CommonProgramFiles% variable is changed to "%ProgramFiles(x86)%\Common Files".</span></span> <span data-ttu-id="2696e-227">由于 SSO 管理实用工具即使在 64 位计算机上也安装在 %ProgramFiles% 中，因此必须修复该路径。</span><span class="sxs-lookup"><span data-stu-id="2696e-227">Because the SSO administrative utility is installed in the %ProgramFiles% even on a 64-bit computer, you must fix the path.</span></span> <span data-ttu-id="2696e-228">DeployBPM.cmd 将调用 CreateSouthridgeVideoApplication.cmd。</span><span class="sxs-lookup"><span data-stu-id="2696e-228">The DeployBPM.cmd calls CreateSouthridgeVideoApplication.cmd.</span></span>  
  
   4.  <span data-ttu-id="2696e-229">在 32 位命令提示符下键入`DeployBPM.cmd`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2696e-229">At the 32-bit command prompt, type `DeployBPM.cmd`, and then press ENTER.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="2696e-230">DeployBPM.cmd 必须在 32 位命令提示符下运行，因为它所包括的 VB 脚本需要访问 x86 对象，而这样的对象需要 x86 版本的 cscript.exe。</span><span class="sxs-lookup"><span data-stu-id="2696e-230">The DeployBPM.cmd must be run at a 32-bit command prompt because it includes the VB Script accessing x86 objects that requires the x86 version of cscript.exe.</span></span>  
  
4. <span data-ttu-id="2696e-231">在命令提示符下，将当前文件夹更改为 %btssolutionspath%\bpm\scripts，类型`DeployBPM.cmd`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2696e-231">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM\Scripts, type `DeployBPM.cmd`, and then press ENTER.</span></span> <span data-ttu-id="2696e-232">DeployBPM.cmd 将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2696e-232">The DeployBPM.cmd performs the following tasks:</span></span>  
  
   1.  <span data-ttu-id="2696e-233">为 BPM 解决方案创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2696e-233">Creates BizTalk Applications for the BPM Solution.</span></span>  
  
   2.  <span data-ttu-id="2696e-234">添加应用程序之间的引用。</span><span class="sxs-lookup"><span data-stu-id="2696e-234">Adds references between the applications.</span></span>  
  
   3.  <span data-ttu-id="2696e-235">导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="2696e-235">Imports the binding files.</span></span>  
  
   4.  <span data-ttu-id="2696e-236">部署 BAM 定义文件。</span><span class="sxs-lookup"><span data-stu-id="2696e-236">Deploys the BAM definition files.</span></span>  
  
   5.  <span data-ttu-id="2696e-237">注册 SouthridgeVideo 事件源。</span><span class="sxs-lookup"><span data-stu-id="2696e-237">Registers the SouthridgeVideo event source.</span></span>  
  
   6.  <span data-ttu-id="2696e-238">创建单一登录 (SSO) 关联应用程序，并将配置值保存到 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2696e-238">Creates a Single Sign-On (SSO) affiliated application, and saves configuration values to the SSO application.</span></span>  
  
5. <span data-ttu-id="2696e-239">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2696e-239">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
   1.  <span data-ttu-id="2696e-240">在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**应用程序**，展开**BTSScn.BPM.OrderBrokerApp**，展开**接收位置**，右键单击**供应商 RP RL**，再单击属性。</span><span class="sxs-lookup"><span data-stu-id="2696e-240">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand **BTSScn.BPM.OrderBrokerApp**, expand **Receive Locations**, right-click **Vendor-RP-RL**, and then click Properties.</span></span>  
  
   2.  <span data-ttu-id="2696e-241">上**属性**对话框中，单击**配置**，，然后下表作为输入值**传输属性**对话框：</span><span class="sxs-lookup"><span data-stu-id="2696e-241">On the **Properties** dialog box, click **Configure**, and then enter values as the following table on the **Transport Properties** dialog box:</span></span>  
  
       |<span data-ttu-id="2696e-242">属性名称</span><span class="sxs-lookup"><span data-stu-id="2696e-242">Property Name</span></span>|<span data-ttu-id="2696e-243">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="2696e-243">Value</span></span>|  
       |-------------------|-----------|  
       |<span data-ttu-id="2696e-244">**Server**</span><span class="sxs-lookup"><span data-stu-id="2696e-244">**Server**</span></span>|`localhost`|  
       |<span data-ttu-id="2696e-245">**用户名**</span><span class="sxs-lookup"><span data-stu-id="2696e-245">**User Name**</span></span>|<span data-ttu-id="2696e-246">\<*BizTalk 服务帐户名称*\></span><span class="sxs-lookup"><span data-stu-id="2696e-246">\<*BizTalk service account name*\></span></span>|  
       |<span data-ttu-id="2696e-247">**密码**</span><span class="sxs-lookup"><span data-stu-id="2696e-247">**Password**</span></span>|<span data-ttu-id="2696e-248">\<*BizTalk 服务帐户密码*\></span><span class="sxs-lookup"><span data-stu-id="2696e-248">\<*BizTalk service account password*\></span></span>|  
  
6. <span data-ttu-id="2696e-249">运行 BPM 解决方案。</span><span class="sxs-lookup"><span data-stu-id="2696e-249">Run the BPM Solution.</span></span> <span data-ttu-id="2696e-250">有关运行该解决方案的详细信息，请参阅[如何运行业务流程管理解决方案](../core/how-to-run-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="2696e-250">For more information about running the solution, see [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2696e-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2696e-251">Next Steps</span></span>  
 <span data-ttu-id="2696e-252">测试的业务管理解决方案工作原理[如何运行业务流程管理解决方案](../core/how-to-run-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="2696e-252">You test how the Business Management Solution works in [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2696e-253">请参阅</span><span class="sxs-lookup"><span data-stu-id="2696e-253">See Also</span></span>  
 <span data-ttu-id="2696e-254">[安装业务流程管理解决方案之前](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="2696e-254">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="2696e-255">业务流程管理解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="2696e-255">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)
