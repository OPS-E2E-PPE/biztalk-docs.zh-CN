---
title: 安装内联和服务的适配器版本面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: 97
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d648db0f3a7c6ad4dccdbcc7555fc3c0727568c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010734"
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a><span data-ttu-id="22c94-102">如何安装面向服务的解决方案的内联版本和适配器版本</span><span class="sxs-lookup"><span data-stu-id="22c94-102">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>
<span data-ttu-id="22c94-103">以下步骤将说明如何准备计算机以安装面向服务的解决方案的内联版本和适配器版本，以及如何在此计算机上安装该解决方案：</span><span class="sxs-lookup"><span data-stu-id="22c94-103">The following steps describe how to prepare the computer for installing the inline and adapter versions of the service oriented solution, and how to install the solution on this computer.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="22c94-104">面向的解决方案位于文件夹中的服务\< *BizTalk Server 安装文件夹*\>\SDK\Scenarios\SO。</span><span class="sxs-lookup"><span data-stu-id="22c94-104">The service oriented solution is located in the folder \<*BizTalk Server Installation Folder*\>\SDK\Scenarios\SO.</span></span>  
>  - <span data-ttu-id="22c94-105">如果没有大型机可用于该解决方案，则可以修改端口绑定以使用存根 Web Services 来模拟挂起事务。</span><span class="sxs-lookup"><span data-stu-id="22c94-105">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="22c94-106">该 Web Services 将在本地生成事务以模拟大型机事务。</span><span class="sxs-lookup"><span data-stu-id="22c94-106">The Web service generates transactions locally to emulate the mainframe transactions.</span></span>  
  
##  <a name="step1"></a><span data-ttu-id="22c94-107">准备计算机以安装服务面向解决方案的适配器和内联版本</span><span class="sxs-lookup"><span data-stu-id="22c94-107">Prepare the computer for installing the adapter and inline versions of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="22c94-108">如果你安装 Windows SharePoint Services，(root) 的默认网站从排除 Windows SharePoint Services 管理路径，如下所示： 单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="22c94-108">If you installed Windows SharePoint Services, exclude the (root) of the Default Web Site from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="22c94-109">下**虚拟服务器配置**，选择**配置虚拟服务器设置**。</span><span class="sxs-lookup"><span data-stu-id="22c94-109">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="22c94-110">上**虚拟服务器列表**页上，单击**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="22c94-110">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="22c94-111">上**虚拟服务器设置**页上，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="22c94-111">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="22c94-112">在**包含的路径**部分**定义托管路径**页上，选择**根**，然后单击**删除所选的路径**。</span><span class="sxs-lookup"><span data-stu-id="22c94-112">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="22c94-113">在命令提示符下，执行 IISReset。</span><span class="sxs-lookup"><span data-stu-id="22c94-113">At a command prompt, perform an IISReset.</span></span>  
  
2.  <span data-ttu-id="22c94-114">单击**启动**，指向**所有程序**，指向**管理工具**，单击**计算机管理**控制台，并将到本地管理员组的 BizTalk 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="22c94-115">从计算机注销，然后使用 BizTalk 服务帐户登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="22c94-115">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
4.  <span data-ttu-id="22c94-116">在命令提示符下，键入以下命令，然后按 Enter 以设置 %BTSSolutionsPath% 环境变量。</span><span class="sxs-lookup"><span data-stu-id="22c94-116">At a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable.</span></span> <span data-ttu-id="22c94-117">然后，退出命令提示符。</span><span class="sxs-lookup"><span data-stu-id="22c94-117">Then, exit the command prompt.</span></span>  
  
    -   <span data-ttu-id="22c94-118">setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="22c94-118">setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="22c94-119">如果使用的是 64 位计算机，则使用 %ProgramFiles(x86)% 而不是 %ProgramFiles%。</span><span class="sxs-lookup"><span data-stu-id="22c94-119">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="22c94-120">有关 SETX 命令的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)。</span><span class="sxs-lookup"><span data-stu-id="22c94-120">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="22c94-121">删除服务面向解决方案的存根 （stub） 版本</span><span class="sxs-lookup"><span data-stu-id="22c94-121">Remove the stub version of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="22c94-122">打开**BizTalk Server 管理控制台**，如下所示： 单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="22c94-122">Open the **BizTalk Server Administration Console** as follows: Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="22c94-123">在**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**的应用程序**，右键单击**BTSScn.SO.CustomerService**，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="22c94-123">In the **BizTalk Server Administration Console**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, right-click **BTSScn.SO.CustomerService**, and then click **Stop**.</span></span> <span data-ttu-id="22c94-124">在**停止应用程序**对话框中，选择**句号-终止实例**，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="22c94-124">In the **Stop Application** dialog box, select **Full Stop - Terminate Instances**, and then click **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-125">若要安装内联版本和适配器版本，则无需删除存根版本。</span><span class="sxs-lookup"><span data-stu-id="22c94-125">You don't need to remove the stub version for installing the inline and adapter versions.</span></span> <span data-ttu-id="22c94-126">如果要将所有版本放在一起，则应跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="22c94-126">If you want to put all the versions together, you should skip this step.</span></span>  
  
3.  <span data-ttu-id="22c94-127">打开命令提示符，键入以下命令，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="22c94-127">Open a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="22c94-128">此命令会将默认脚本主机更改为 CScript.exe：</span><span class="sxs-lookup"><span data-stu-id="22c94-128">This command changes the default script host to CScript.exe:</span></span>  
  
    -   `cscript /H:CScript`  
  
4.  <span data-ttu-id="22c94-129">在命令提示符下，将当前目录更改为 %BTSSolutonsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="22c94-129">At the command prompt, change the current directory to %BTSSolutonsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER:</span></span>  
  
    -   `UnEnlistStub.vbs`  
  
5.  <span data-ttu-id="22c94-130">在命令提示符下键入以下命令，，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="22c94-130">At the command prompt, type the following command, and then press ENTER:</span></span>  
  
    -   `UndeployStub.vbs`  
  
6.  <span data-ttu-id="22c94-131">在命令提示符下运行以下命令</span><span class="sxs-lookup"><span data-stu-id="22c94-131">At the command prompt, run the following command</span></span>  
  
     <span data-ttu-id="22c94-132">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span><span class="sxs-lookup"><span data-stu-id="22c94-132">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span></span>  
  
     <span data-ttu-id="22c94-133">此命令将设置用于查找 BAM 实用工具的路径。</span><span class="sxs-lookup"><span data-stu-id="22c94-133">This sets the path to find the BAM utilities.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-134">如果你使用的 64 位计算机，键入`%ProgramFiles(x86)%`而不是`%ProgramFiles%`。</span><span class="sxs-lookup"><span data-stu-id="22c94-134">If you are using a 64-bit computer, type `%ProgramFiles(x86)%` instead of `%ProgramFiles%`.</span></span>  
  
7.  <span data-ttu-id="22c94-135">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="22c94-135">At the command prompt, change the directory to %BTSSolutionsPath%\SO\BTSSoln\BAM, and then run the following command:</span></span>  
  
    -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  
  
8.  <span data-ttu-id="22c94-136">在命令提示符下，将目录更改为\<*企业单一登录安装目录*\>，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="22c94-136">At the command prompt, change the directory to \<*Enterprise Single Sign-On Install Directory*\>, and then run the following command:</span></span>  
  
    -   `ssomanage -tickets no no`  
  
9. <span data-ttu-id="22c94-137">在命令提示符下，运行以下命令以删除 WoodgroveBank.CustomerService SSO 关联应用程序：</span><span class="sxs-lookup"><span data-stu-id="22c94-137">At the command prompt, run the following command to delete the WoodgroveBank.CustomerService SSO Affiliated application:</span></span>  
  
    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  
  
10. <span data-ttu-id="22c94-138">在命令提示符下，运行以下命令以删除存根版本所使用的网站：</span><span class="sxs-lookup"><span data-stu-id="22c94-138">At the command prompt, run the following commands to delete the Web sites used by the stub version.</span></span> <span data-ttu-id="22c94-139">有关 iisvdir.vbs 的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)。</span><span class="sxs-lookup"><span data-stu-id="22c94-139">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  
  
11. <span data-ttu-id="22c94-140">启动 Internet 信息服务 (IIS) 管理器，如下所示： 单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) 管理器**。</span><span class="sxs-lookup"><span data-stu-id="22c94-140">Start Internet Information Services (IIS) Manager as follows: Click **Start**, point to **All Programs**, point to **Administration Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    -   <span data-ttu-id="22c94-141">展开**应用程序池**，右键单击创建为以前的 Web 应用程序的应用程序池，单击**删除**，然后单击**确定**入确认对话框。</span><span class="sxs-lookup"><span data-stu-id="22c94-141">Expand the **Application Pools**, right-click the application pool you crated for the previous Web applications, click **Delete**, and then click **OK** in the confirmation dialog box.</span></span>  
  
12. <span data-ttu-id="22c94-142">单击**启动**，指向**控制面板**，单击**添加或删除程序**，然后卸载 IBM WebSphere MQ 客户端适用于 Windows 的。</span><span class="sxs-lookup"><span data-stu-id="22c94-142">Click **Start**, point to **Control Panel**, click **Add or Remove Programs**, and then uninstall the IBM WebSphere MQ Client for Windows.</span></span>  
  
13. <span data-ttu-id="22c94-143">启动**Visual Studio 命令提示符**，然后运行以下命令以删除为存根 （stub） 版本安装 amqmdnet.dll。</span><span class="sxs-lookup"><span data-stu-id="22c94-143">Start **Visual Studio Command Prompt** and then run the following command to delete the amqmdnet.dll you installed for the stub version.</span></span>  
  
    -   `gacutil /u amqmdnet`  
  
##  <a name="step5"></a><span data-ttu-id="22c94-144">准备服务面向解决方案访问的后端系统</span><span class="sxs-lookup"><span data-stu-id="22c94-144">Prepare the back-end systems for the Service Oriented Solution to access</span></span>  
  
1.  <span data-ttu-id="22c94-145">在本地计算机上安装 Windows Server IBM WebSphere MQ。</span><span class="sxs-lookup"><span data-stu-id="22c94-145">Install IBM WebSphere MQ for Windows Server on the local computer.</span></span>  
  
    1.  <span data-ttu-id="22c94-146">保留所有默认设置。</span><span class="sxs-lookup"><span data-stu-id="22c94-146">Keep all the default settings.</span></span> <span data-ttu-id="22c94-147">设置**默认配置**末尾**准备 WebSphere MQ 向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-147">Set up the **Default Configuration** at the end of the **Prepare WebSphere MQ Wizard**.</span></span> <span data-ttu-id="22c94-148">队列管理器命名为 QM_\<*您的计算机名称*\>。</span><span class="sxs-lookup"><span data-stu-id="22c94-148">The queue manager is named as QM_\<*your computer name*\>.</span></span>  
  
    2.  <span data-ttu-id="22c94-149">安装 Fix Pack 10 (CSD10)。</span><span class="sxs-lookup"><span data-stu-id="22c94-149">Install the Fix Pack 10 (CSD10).</span></span> <span data-ttu-id="22c94-150">保留所有默认设置。</span><span class="sxs-lookup"><span data-stu-id="22c94-150">Keep all the default settings.</span></span>  
  
2.  <span data-ttu-id="22c94-151">安装 MQSeries 代理。</span><span class="sxs-lookup"><span data-stu-id="22c94-151">Install the MQSeries Agent.</span></span>  
  
    1.  <span data-ttu-id="22c94-152">重新运行 BizTalk Server 安装程序。</span><span class="sxs-lookup"><span data-stu-id="22c94-152">Rerun the BizTalk Server setup program.</span></span>  
  
    2.  <span data-ttu-id="22c94-153">上**程序维护**页上，选择**修改**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-153">On the **Program Maintenance** page, select **Modify**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="22c94-154">上**组件安装**页上，展开**其他软件**节点，，然后选择**MQSeries 代理**。</span><span class="sxs-lookup"><span data-stu-id="22c94-154">On the **Component Installation** page, expand the **Additional Software** node, and then select **MQSeries Agent**.</span></span>  
  
    4.  <span data-ttu-id="22c94-155">上**完成**页上，请确保**启动 BizTalk MQSeries 代理配置向导**未选中。</span><span class="sxs-lookup"><span data-stu-id="22c94-155">On the **Completion** page, make sure that **Launch BizTalk MQSeries Agent Configuration Wizard** is not selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-156">**MQSeries 代理**安装适用于 Windows 的复选框仅在 IBM WebSphere MQ 后激活。</span><span class="sxs-lookup"><span data-stu-id="22c94-156">The **MQSeries Agent** check box is activated only after the IBM WebSphere MQ for Windows is installed.</span></span>  
  
3.  <span data-ttu-id="22c94-157">打开**Visual Studio 命令提示符**，将目录更改为\< *IBM MQSeries 安装目录*\>\bin 文件夹，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="22c94-157">Open a **Visual Studio Command Prompt**, change the directory to the \<*IBM MQSeries Installation Directory*\>\bin folder, and then run the following command:</span></span>  
  
    -   `gacutil /i amqmdnet.dll`  
  
4.  <span data-ttu-id="22c94-158">安装 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]如果你想要安装 Microsoft 主机集成 Server 2004 访问大型机。</span><span class="sxs-lookup"><span data-stu-id="22c94-158">Install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] if you want to install Microsoft Host Integration Server 2004 to access the mainframe.</span></span> <span data-ttu-id="22c94-159">在安装程序中，在**选项**页上，选择**Visual C#.NET**，然后清除其他组件复选框。</span><span class="sxs-lookup"><span data-stu-id="22c94-159">In the setup program, on the **Options** page, select **Visual C# .NET**, and then clear other components checkboxes.</span></span> <span data-ttu-id="22c94-160">你不需要安装比其他组件**Visual C#.NET**。</span><span class="sxs-lookup"><span data-stu-id="22c94-160">You don't need to install other components than the **Visual C# .NET**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-161">主机集成 Server 2004 中的 TI 设计器需要[!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="22c94-161">The TI Designer in Host Integration Server 2004 requires [!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)].</span></span>  
  
5.  <span data-ttu-id="22c94-162">如果具有要访问的大型机 ， 则安装并配置 Microsoft Host Integration Server 2004 。</span><span class="sxs-lookup"><span data-stu-id="22c94-162">Install and configure Microsoft Host Integration Server 2004 if you have a mainframe to be accessed.</span></span> <span data-ttu-id="22c94-163">保留所有默认设置。</span><span class="sxs-lookup"><span data-stu-id="22c94-163">Keep all the default settings.</span></span>  
  
#### <a name="create-the-mqseries-queues"></a><span data-ttu-id="22c94-164">创建 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="22c94-164">Create the MQSeries queues</span></span>  
  
1.  <span data-ttu-id="22c94-165">打开 WebSphere MQ 资源管理器中，展开**队列管理器**，然后展开你要在其中创建队列的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="22c94-165">Open the WebSphere MQ Explorer, expand **Queue Managers**, and then expand the queue manager in which you want to create the queues.</span></span> <span data-ttu-id="22c94-166">通常情况下，队列管理器命名为 QM_\<*您的计算机名称*\>。</span><span class="sxs-lookup"><span data-stu-id="22c94-166">Typically, a queue manager is named as QM_\<*your computer name*\>.</span></span>  
  
2.  <span data-ttu-id="22c94-167">在 WebSphere MQ 资源管理器中，右键单击**队列**，指向**新建**，单击**本地队列**，然后创建的适配器版本的以下本地队列解决方案：</span><span class="sxs-lookup"><span data-stu-id="22c94-167">In the WebSphere MQ Explorer, right-click **Queues**, point to **New**, click **Local Queue**, and then create the following local queues for the adapter version of the solution:</span></span>  
  
    -   <span data-ttu-id="22c94-168">AdapterSOAInputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-168">AdapterSOAInputQueue</span></span>  
  
    -   <span data-ttu-id="22c94-169">AdapterSOAOutputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-169">AdapterSOAOutputQueue</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-170">这些队列可以共享 MQSeries 群集，但不要求其执行此操作。</span><span class="sxs-lookup"><span data-stu-id="22c94-170">The queues can share an MQSeries cluster, but they are not required to do so.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-171">MQSeries 队列管理器名称和队列名称均区分大小写。</span><span class="sxs-lookup"><span data-stu-id="22c94-171">MQSeries queue manager names and queue names are case sensitive.</span></span>  
  
3.  <span data-ttu-id="22c94-172">重复上一步骤可为内联版本创建以下本地队列：</span><span class="sxs-lookup"><span data-stu-id="22c94-172">Repeat the previous step to create the following local queues for the inline version:</span></span>  
  
    -   <span data-ttu-id="22c94-173">InlineSOAOutputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-173">InlineSOAOutputQueue</span></span>  
  
    -   <span data-ttu-id="22c94-174">InlineSOAInputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-174">InlineSOAInputQueue</span></span>  
  
4.  <span data-ttu-id="22c94-175">重复上一步骤可为付款跟踪模拟程序创建以下本地队列。</span><span class="sxs-lookup"><span data-stu-id="22c94-175">Repeat the previous step to create the following local queues for the Payment Tracker simulator.</span></span> <span data-ttu-id="22c94-176">（适配器版本和内联版本中都使用付款跟踪模拟程序）：</span><span class="sxs-lookup"><span data-stu-id="22c94-176">(The Payment Tracker simulator is used in both the adapter and inline versions):</span></span>  
  
    -   <span data-ttu-id="22c94-177">LastPaymentsInputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-177">LastPaymentsInputQueue</span></span>  
  
    -   <span data-ttu-id="22c94-178">LastPaymentsOutputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-178">LastPaymentsOutputQueue</span></span>  
  
#### <a name="complete-configuration-of-the-mqseries-adapter"></a><span data-ttu-id="22c94-179">要完成的 MQSeries 适配器配置</span><span class="sxs-lookup"><span data-stu-id="22c94-179">Complete configuration of the MQSeries adapter</span></span>  
  
1.  <span data-ttu-id="22c94-180">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk MQSeries 代理配置向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-180">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk MQSeries Agent Configuration Wizard**.</span></span>  
  
2.  <span data-ttu-id="22c94-181">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-181">On the **Welcome** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="22c94-182">上**应用程序标识**页上，选择**此用户**，然后输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="22c94-182">On the **Application Identity** page, select **This User**, and then enter the user name and password.</span></span> <span data-ttu-id="22c94-183">MQSeries 代理的 COM+ 应用程序将使用此用户帐户运行。</span><span class="sxs-lookup"><span data-stu-id="22c94-183">The COM+ application for the MQSeries Agent will run under this user account.</span></span> <span data-ttu-id="22c94-184">对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-184">For this walkthrough, use the same user account that the BizTalk service is using.</span></span> <span data-ttu-id="22c94-185">如果不是，用户帐户用于承载 MQSeries 适配器的 BizTalk 服务必须可向添加**CreatorOwner** COM + 应用程序的角色。</span><span class="sxs-lookup"><span data-stu-id="22c94-185">If it is not, the user accounts for BizTalk services hosting the MQSeries Adapter must be added to the **CreatorOwner** role of the COM+ application.</span></span>  
  
4.  <span data-ttu-id="22c94-186">单击**是**上**MQSConfigWiz**对话框中，如果系统提示你在上一步中输入的用户帐户具有管理权限。</span><span class="sxs-lookup"><span data-stu-id="22c94-186">Click **Yes** on the **MQSConfigWiz** dialog box, if prompted that the user account that you entered in the previous step has the administrative privilege.</span></span>  
  
5.  <span data-ttu-id="22c94-187">上**名称的角色**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-187">On the **Name of Role** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="22c94-188">上**创建 MQSAgent COM + 应用程序**页上，单击**下一步**，然后单击**完成**上**完成**页。</span><span class="sxs-lookup"><span data-stu-id="22c94-188">On the **Creating the MQSAgent COM+ Application** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="configure-the-mainframe-cics-application"></a><span data-ttu-id="22c94-189">配置大型机 CICS 应用程序</span><span class="sxs-lookup"><span data-stu-id="22c94-189">Configure the mainframe CICS application</span></span>  
  
1.  <span data-ttu-id="22c94-190">使用记事本，打开位于 %BTSSolutionsPath%\SO\MFAccess\HISTIComponent 文件夹中的 bizcbl.txt 及其“副件”(MainFrameProgramVTCS2Description.txt)，然后检查这两个文件的内容。</span><span class="sxs-lookup"><span data-stu-id="22c94-190">Using Notepad, open the bizcbl.txt and its "copy book" (MainFrameProgramVTCS2Description.txt) in the %BTSSolutionsPath%\SO\MFAccess\HISTIComponent folder, and then review the contents.</span></span>  
  
    -   <span data-ttu-id="22c94-191">Bizcbl.txt 包括 COBOL 过程，该过程可根据帐户编号输入返回随机的帐户语句。</span><span class="sxs-lookup"><span data-stu-id="22c94-191">Bizcbl.txt includes the COBOL procedure returning the randomized account statements from account number input.</span></span>  
  
    -   <span data-ttu-id="22c94-192">MainFrameProgramVTCS2Descriptoin.txt 包含用于说明输入和输出数据信息的 COMMAREA。</span><span class="sxs-lookup"><span data-stu-id="22c94-192">MainFrameProgramVTCS2Descriptoin.txt contains COMMAREA which describes the input and output data information.</span></span> <span data-ttu-id="22c94-193">COMMAREA 是用于在被调用的程序和调用方程序之间来回传递数据的连续内存块。</span><span class="sxs-lookup"><span data-stu-id="22c94-193">COMMAREA is a block of contiguous memory used to pass data back and forth between called and calling programs.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-194">印书籍还可用于生成与插件 TI 设计器中使用 Visual Studio 的事务系统集成商 (TI) 元数据文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-194">You can also use the copy book to generate the Transaction Integrator (TI) metadata file using Visual Studio with the TI Designer plug-in.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-195">尽管以下步骤对于成功部署是至关紧要的，但 BizTalk Server 开发人员通常不执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="22c94-195">Although the following steps are crucial to the successful deployment, they are not usually performed by the BizTalk Server developer.</span></span> <span data-ttu-id="22c94-196">必须依赖大型机人员才可正确配置大型机环境。</span><span class="sxs-lookup"><span data-stu-id="22c94-196">You must rely on the mainframe personnel to properly configure the mainframe environment.</span></span> <span data-ttu-id="22c94-197">大多数的大型机环境中通常都安装了此演练所需的软件。</span><span class="sxs-lookup"><span data-stu-id="22c94-197">The software required for this walkthrough is usually installed in the most mainframe environments.</span></span> <span data-ttu-id="22c94-198">有关最小大型机操作系统环境的详细信息，请参阅 Host Integration Server 文档。</span><span class="sxs-lookup"><span data-stu-id="22c94-198">For more information about the minimum mainframe operating system environment, see the Host Integration Server documentation.</span></span>  
  
2.  <span data-ttu-id="22c94-199">采用如 FTP 之类的方法将 COBOL 代码复制到主机。</span><span class="sxs-lookup"><span data-stu-id="22c94-199">Copy the COBOL code to the host by method like FTP.</span></span>  
  
3.  <span data-ttu-id="22c94-200">编译 COBOL 代码和副件。</span><span class="sxs-lookup"><span data-stu-id="22c94-200">Compile the COBOL code and copy book.</span></span> <span data-ttu-id="22c94-201">以下代码显示了 COBOL 编译器的作业控制语言 (JCL) 的示例：</span><span class="sxs-lookup"><span data-stu-id="22c94-201">The following code shows a sample of Job Control Language (JCL) for the COBOL compiler.</span></span>  
  
    ```  
    //COB      EXEC PGM=IGYCRCTL,  
    //            PARM=&COBPARM,  
    //            REGION=&REG  
    //STEPLIB  DD DSN=&COMPINDX..SIGYCOMP,DISP=SHR  
    //SYSLIB   DD DSN=&INDEX..SDFHCOB,DISP=SHR  
    //         DD DSN=&INDEX..SDFHMAC,DISP=SHR  
    //         DD DSN=&HLQ..&COMP..COBCOPY,DISP=SHR  
    //SYSPRINT DD SYSOUT=&OUTC  
    //*SYSPRINT DD DSN=&&INPUT,DISP=(,PASS),UNIT=SYSDA,  
    //*         SPACE=(TRK,(100,50)),  
    //*         DCB=(DSORG=PS,LRECL=121,BLKSIZE=2420,RECFM=FBA)  
    //SYSIN    DD DSN=&&SYSCIN,DISP=(OLD,DELETE)  
    //SYSLIN   DD DSN=&&LOADSET,  
    //            DISP=(MOD,PASS),  
    //            UNIT=&WORK,  
    //            SPACE=(80,(250,100))  
    //SYSUT1   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT2   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT3   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT4   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT5   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT6   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT7   DD UNIT=&WORK,SPACE=(460,(350,150))  
    ```  
  
4.  <span data-ttu-id="22c94-202">链接将编辑经过编译的源代码以创建可执行文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-202">Link edit the compiled source to create the executable.</span></span> <span data-ttu-id="22c94-203">以下代码显示了 COBOL 链接编辑的 JCL 示例：</span><span class="sxs-lookup"><span data-stu-id="22c94-203">The following code shows a sample of JCL for COBOL link edit.</span></span>  
  
    ```  
    //LKED     EXEC PGM=IEWL,REGION=&REG,  
    //            PARM=&LNKPARM,COND=(5,LT,COB)  
    //SYSLIB   DD DSN=&INDEX..SDFHLOAD,DISP=SHR  
    //         DD DSN=CEE.SCEELKED,DISP=SHR  
    //         DD DSN=&TCPINDX..SEZATCP,DISP=SHR  
    //SYSLMOD  DD DSN=&LMINDX..&COMP..LOADLIB,DISP=SHR  
    //SYSUT1   DD UNIT=&WORK,  
    //            DCB=BLKSIZE=1024,  
    //            SPACE=(1024,(200,20))  
    //SYSPRINT DD SYSOUT=&OUTC  
    //SYSLIN   DD DSN=&&LOADSET,DISP=(OLD,DELETE)  
    //         DD DSN=&&COPYLINK,DISP=(OLD,DELETE)  
    ```  
  
5.  <span data-ttu-id="22c94-204">配置 CICS 大型机应用程序。</span><span class="sxs-lookup"><span data-stu-id="22c94-204">Configure the CICS mainframe application.</span></span>  
  
    -   <span data-ttu-id="22c94-205">在此步骤中，大型机系统程序员或 CICS 开发人员必须安装 TCPIPSERVICE、会话、连接、事务和程序的资源定义。</span><span class="sxs-lookup"><span data-stu-id="22c94-205">In this step, the mainframe systems programmer or CICS developer must install TCPIPSERVICE, Session, Connection, Transaction, and Program resource definitions.</span></span>  
  
    -   <span data-ttu-id="22c94-206">你应与大型机管理员联系，以获取可访问的 IP 地址、端口号和程序名的链接。</span><span class="sxs-lookup"><span data-stu-id="22c94-206">You should consult with mainframe administrators to get an IP address, port number, and a Link to Program name that you can access.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="22c94-207">此演练假定该大型机使用 CICS 应用程序服务器，并且事务的编程模型为 TCP/IP（增强型侦听器模式（ELM）链接）。</span><span class="sxs-lookup"><span data-stu-id="22c94-207">This walkthrough assumes that the mainframe uses a CICS application server and that the programming model for the transaction is TCP/IP (Enhanced Listener Mode (ELM) Link).</span></span>  
  
##  <a name="step7"></a><span data-ttu-id="22c94-208">配置安全套接字层 (SSL) 的 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="22c94-208">Configure the Web server for Secure Socket Layers (SSL)</span></span>  
  
#### <a name="install-certificate-services"></a><span data-ttu-id="22c94-209">安装证书服务</span><span class="sxs-lookup"><span data-stu-id="22c94-209">Install Certificate Services</span></span>  
  
1.  <span data-ttu-id="22c94-210">单击**启动**，指向**控制面板**，然后单击**添加或删除程序**。</span><span class="sxs-lookup"><span data-stu-id="22c94-210">Click **Start**, point to **Control Panel**, and then click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="22c94-211">在**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="22c94-211">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="22c94-212">在**Windows 组件向导**，选择**证书服务**，单击**下一步**，然后按照屏幕说明完成安装。</span><span class="sxs-lookup"><span data-stu-id="22c94-212">In the **Windows Components Wizard**, select the **Certificate Services**, click **Next**, and then follow the on-screen instructions to complete the installation.</span></span>  
  
#### <a name="create-a-certificate-request"></a><span data-ttu-id="22c94-213">创建一个证书请求</span><span class="sxs-lookup"><span data-stu-id="22c94-213">Create a certificate request</span></span>  
  
1.  <span data-ttu-id="22c94-214">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，单击**属性**单击**目录安全性**选项卡上，并依次**服务器证书**。</span><span class="sxs-lookup"><span data-stu-id="22c94-214">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, click **Properties**, click the **Directory Security** tab, and then click **Server Certificate**.</span></span>  
  
2.  <span data-ttu-id="22c94-215">上**欢迎**页**Web 服务器证书向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-215">On the **Welcome** page of the **Web Server Certificate Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="22c94-216">上**服务证书**页上，选择**创建新证书**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-216">On the **Service Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="22c94-217">上**延迟或立即请求**页上，单击**现在，准备请求，但稍后发送**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-217">On the **Delayed or Immediate Request** page, click **Prepare the request now, but send it later**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="22c94-218">上**名称和安全设置**页上，保留所有默认设置，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-218">On the **Name and Security Settings** page, keep all the default settings, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="22c94-219">上**组织信息**页上，键入你的公司组织和组织单位名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-219">On the **Organization Information** page, type your company's organization and organizational unit names, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="22c94-220">上**站点的公用名称**页上，键入你的计算机名称**公用名**框中，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-220">On the **Your Site's Common Name** page, type your computer name in the **Common name** box, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="22c94-221">上**的地理位置信息**页上，填写你的地理位置信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-221">On the **Geographical Information** page, fill out your geographical information, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="22c94-222">上**证书请求文件名称**页上，键入`c:\certreq.txt`中**文件名**框中，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-222">On the **Certificate Request File Name** page, type `c:\certreq.txt` in the **File name** box, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="22c94-223">上**请求文件摘要**页上，单击**下一步**，然后单击**完成**上**完成**页。</span><span class="sxs-lookup"><span data-stu-id="22c94-223">On the **Request File Summary** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="submit-the-certificate-request-to-the-certification-authority"></a><span data-ttu-id="22c94-224">提交到证书颁发机构证书请求</span><span class="sxs-lookup"><span data-stu-id="22c94-224">Submit the certificate request to the Certification Authority</span></span>  
  
1.  <span data-ttu-id="22c94-225">在 Internet Explorer，在地址框中，键入`http://localhost/certsrvt`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="22c94-225">In Internet Explorer, in the Address box, type `http://localhost/certsrvt`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="22c94-226">上**欢迎**页上，单击**请求证书**，然后单击**高级的证书申请**上**请求证书**页。</span><span class="sxs-lookup"><span data-stu-id="22c94-226">On the **Welcome** page, click **Request a Certificate**, and then click **Advanced certificate request** on the **Request a Certificate** page.</span></span>  
  
3.  <span data-ttu-id="22c94-227">上**高级证书申请**页上，单击**提交证书申请，使用 base64 编码的 PKCS #10 文件或使用 base64 编码的 PKCS #7 文件的续订请求**。</span><span class="sxs-lookup"><span data-stu-id="22c94-227">On the **Advanced Certificate Request** page, click **Submit a certificate request using a base64 encoded PKCS #10 file or a renewal request using a base64 encoded PKCS #7 file**.</span></span>  
  
4.  <span data-ttu-id="22c94-228">从"若要创建证书请求"，将其粘贴到过程中创建 c:\certreq.txt 复制的所有文本**保存请求**框**提交证书申请或续订申请**页，，然后单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="22c94-228">Copy all the text from the c:\certreq.txt that you created in the procedure "To create a certificate request", paste it to the **Saved Request** box on the **Submit a Certificate Request or Renewal Request** page, and then click **Submit**.</span></span>  
  
#### <a name="issue-a-certificate-using-certification-authority-management-tool"></a><span data-ttu-id="22c94-229">颁发证书使用证书颁发机构管理工具</span><span class="sxs-lookup"><span data-stu-id="22c94-229">Issue a certificate using Certification Authority management tool</span></span>  
  
1.  <span data-ttu-id="22c94-230">单击**启动**，指向**管理工具**，然后单击**证书颁发机构**。</span><span class="sxs-lookup"><span data-stu-id="22c94-230">Click **Start**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="22c94-231">在**证书颁发机构**控制台，展开证书颁发机构的名称，展开**挂起请求**，右键单击在上一步骤中，点提交证书请求到**所有任务**，然后单击**问题**。</span><span class="sxs-lookup"><span data-stu-id="22c94-231">In the **Certification Authority** console, expand your certification authority's name, expand the **Pending Request**, right-click the certificate request that you submitted in the previous step, point to **All Tasks**, and then click **Issue**.</span></span>  
  
3.  <span data-ttu-id="22c94-232">关闭**证书颁发机构**控制台。</span><span class="sxs-lookup"><span data-stu-id="22c94-232">Close the **Certification Authority** console.</span></span>  
  
#### <a name="download-the-certificate-to-the-web-server"></a><span data-ttu-id="22c94-233">下载与 Web 服务器的证书</span><span class="sxs-lookup"><span data-stu-id="22c94-233">Download the certificate to the Web server</span></span>  
  
1.  <span data-ttu-id="22c94-234">在 Internet Explorer，在地址框中，键入`http://localhost/certsrvt`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="22c94-234">In Internet Explorer, in the Address box, type `http://localhost/certsrvt`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="22c94-235">上**欢迎**页上，单击**查看挂起的证书申请的状态**。</span><span class="sxs-lookup"><span data-stu-id="22c94-235">On the **Welcome** page, click **View the status of a pending certificate request**.</span></span>  
  
3.  <span data-ttu-id="22c94-236">上**查看挂起的证书申请的状态**页上，单击证书**请求**你在"创建证书请求"的过程中创建。</span><span class="sxs-lookup"><span data-stu-id="22c94-236">On the **View the Status of a Pending Certificate Request** page, click the certificate **request** that you created in the procedure "To create a certificate request".</span></span>  
  
4.  <span data-ttu-id="22c94-237">上**颁发证书**页上，选择编码方案，任一，然后单击**下载证书**。</span><span class="sxs-lookup"><span data-stu-id="22c94-237">On the **Certificate Issued** page, select either of the encoding schemes, and then click **Download certificate**.</span></span>  
  
5.  <span data-ttu-id="22c94-238">上**安全警告**对话框中，单击**保存**，然后将证书保存为 c:\certnew.cer。</span><span class="sxs-lookup"><span data-stu-id="22c94-238">On the **Security Warning** dialog box, click **Save**, and then save the certificate as c:\certnew.cer.</span></span>  
  
#### <a name="install-the-certificate-to-the-web-server"></a><span data-ttu-id="22c94-239">将证书安装到 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="22c94-239">Install the certificate to the Web server</span></span>  
  
1.  <span data-ttu-id="22c94-240">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**为其创建证书请求，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="22c94-240">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site** for which you created the certificate request, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="22c94-241">上**属性**对话框中，单击**目录安全性**选项卡上，并依次**服务器证书**。</span><span class="sxs-lookup"><span data-stu-id="22c94-241">On the **Properties** dialog box, click the **Directory Security** tab, and then click **Server Certificate**.</span></span>  
  
3.  <span data-ttu-id="22c94-242">上**欢迎**页**Web 服务器证书向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-242">On the **Welcome** page of the **Web Server Certificate Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="22c94-243">上**挂起的证书申请**页上，选择**处理挂起的请求和安装证书**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-243">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="22c94-244">上**处理挂起的请求**页上，键入`c:\certnew.cer`中**路径和文件名**文本中，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-244">On the **Process a Pending Request** page, type `c:\certnew.cer` in the **Path and file name** text box, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="22c94-245">单击**下一步**上**SSL 端口**页上，单击**下一步**上**证书 Summery**页，，然后单击**完成**上**确认**页。</span><span class="sxs-lookup"><span data-stu-id="22c94-245">Click **Next** on the **SSL Port** page, click **Next** on the **Certificate Summery** page, and then click **Finish** on the **Confirmation** page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-246">在此演练中，不需要将服务器证书安装到本地计算机上的“受信任的根证书颁发机构”存储区，因为证书服务和 Web 服务器均安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="22c94-246">In this walkthrough you don't need to install the server certificate to the Trusted Root Certification Authorities store on the local computer because both Certificate Services and Web server are installed on the same computer.</span></span>  
  
##  <a name="step9"></a><span data-ttu-id="22c94-247">创建后端系统的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="22c94-247">Create the Web services for the back-end systems</span></span>  
  
1.  <span data-ttu-id="22c94-248">在**Internet Information Services (IIS) Manager**，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**.</span><span class="sxs-lookup"><span data-stu-id="22c94-248">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-249">面向服务的解决方案将通过此 Web Services 访问大型机。</span><span class="sxs-lookup"><span data-stu-id="22c94-249">The service oriented solution accesses the mainframe through this Web service.</span></span>  
  
2.  <span data-ttu-id="22c94-250">上**添加新的应用程序池**对话框框中，输入**应用程序池 ID** （任意值），然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="22c94-250">On the **Add New Application Pool** dialog box, enter the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="22c94-251">在**Internet Information Services (IIS) Manager**，右键单击你刚的应用程序池创建，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="22c94-251">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="22c94-252">上**属性**页上，单击**标识**选项卡上，选择**可配置**，输入**用户名**和**密码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="22c94-252">On the **Properties** page, click the **Identity** tab, select **Configurable**, enter the **User name** and **Password**, and then click **OK**.</span></span> <span data-ttu-id="22c94-253">对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-253">For this walkthrough, use the same user account that the BizTalk service is using.</span></span>  
  
#### <a name="create-the-pendingtransactions-web-service-for-runtime"></a><span data-ttu-id="22c94-254">创建运行时的 PendingTransactions Web 服务</span><span class="sxs-lookup"><span data-stu-id="22c94-254">Create the PendingTransactions Web service for runtime</span></span>  
  
1.  <span data-ttu-id="22c94-255">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-255">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-256">使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） SAP Web 服务：</span><span class="sxs-lookup"><span data-stu-id="22c94-256">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="22c94-257">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-257">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions</span></span>  
  
     <span data-ttu-id="22c94-258">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-258">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span></span>  
  
     <span data-ttu-id="22c94-259">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-259">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="22c94-260">在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="22c94-260">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="22c94-261">在**目录安全性**选项卡上，单击**编辑**修改**身份验证和访问控制**。</span><span class="sxs-lookup"><span data-stu-id="22c94-261">In the **Directory Security** tab, click **Edit** to modify **Authentication and access control**.</span></span> <span data-ttu-id="22c94-262">选择**基本身份验证 （以明文形式发送密码）**，并清除其他**身份验证访问**复选框。</span><span class="sxs-lookup"><span data-stu-id="22c94-262">Select **Basic authentication (password is sent in clear text)**, and clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="22c94-263">单击**确定**关闭**身份验证方法**对话框。</span><span class="sxs-lookup"><span data-stu-id="22c94-263">Click **OK** to close the **Authentication Methods** dialog box.</span></span>  
  
    2.  <span data-ttu-id="22c94-264">在**目录安全性**选项卡上，单击**编辑**下**安全通信**组框中，，然后检查**要求安全通道 (SSL)** 中**安全通信**对话框。</span><span class="sxs-lookup"><span data-stu-id="22c94-264">In the **Directory Security** tab, click **Edit** under the **Secure Communication** group box, and then check **Require secure channel (SSL)** in the **Secure Communications** dialog box.</span></span>  
  
    3.  <span data-ttu-id="22c94-265">在**虚拟目录**选项卡上，设置**应用程序池**到你在"创建新的 IIS 应用程序池的挂起的事务 Web 服务"的过程中创建的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="22c94-265">In the **Virtual Directory** tab, set the **Application Pool** to the application pool that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
#### <a name="create-the-pendingtransactions-web-service-for-development-environment"></a><span data-ttu-id="22c94-266">创建开发环境 PendingTransactions Web 服务</span><span class="sxs-lookup"><span data-stu-id="22c94-266">Create the PendingTransactions Web service for development environment</span></span>  
  
1.  <span data-ttu-id="22c94-267">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-267">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-268">使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） SAP Web 服务：</span><span class="sxs-lookup"><span data-stu-id="22c94-268">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="22c94-269">别名 = PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-269">Alias = PendingTransactions</span></span>  
  
     <span data-ttu-id="22c94-270">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-270">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span></span>  
  
     <span data-ttu-id="22c94-271">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-271">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="22c94-272">在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击 PendingTransactions，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="22c94-272">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click PendingTransactions, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="22c94-273">在**目录安全性**选项卡上，单击**编辑**修改**身份验证和访问控制**。</span><span class="sxs-lookup"><span data-stu-id="22c94-273">In the **Directory Security** tab, click **Edit** to modify **Authentication and access control**.</span></span> <span data-ttu-id="22c94-274">选择**启用匿名访问**。</span><span class="sxs-lookup"><span data-stu-id="22c94-274">Select **Enable anonymous access**.</span></span> <span data-ttu-id="22c94-275">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="22c94-275">Click **OK** to exit.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="22c94-276">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将使用用于开发环境的 PendingTransactions Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="22c94-276">The PendingTransactions Web application for development environment will be used by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="22c94-277">对于生产环境，则不需要此 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="22c94-277">You don't need this Web application for production environment.</span></span>  
  
    2.  <span data-ttu-id="22c94-278">在**虚拟目录**选项卡上，设置**应用程序池**到你在"创建新的 IIS 应用程序池的挂起的事务 Web 服务"的过程中创建的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="22c94-278">In the **Virtual Directory** tab, set the **Application Pool** to the application pool that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
#### <a name="create-the-stub-sap-web-service"></a><span data-ttu-id="22c94-279">创建存根 （stub) SAP Web 服务</span><span class="sxs-lookup"><span data-stu-id="22c94-279">Create the Stub SAP Web service</span></span>  
  
1.  <span data-ttu-id="22c94-280">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-280">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-281">使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） SAP Web 服务：</span><span class="sxs-lookup"><span data-stu-id="22c94-281">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="22c94-282">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="22c94-282">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
     <span data-ttu-id="22c94-283">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="22c94-283">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
     <span data-ttu-id="22c94-284">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-284">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="22c94-285">在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22c94-285">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="22c94-286">在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你在"创建新的 IIS 的过程中创建应用程序池的挂起的事务 Web 服务"。</span><span class="sxs-lookup"><span data-stu-id="22c94-286">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*\> that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
    2.  <span data-ttu-id="22c94-287">在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**.</span><span class="sxs-lookup"><span data-stu-id="22c94-287">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="22c94-288">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="22c94-288">Click **OK** to exit.</span></span>  
  
##  <a name="step11"></a><span data-ttu-id="22c94-289">为服务面向解决方案创建 TI 组件</span><span class="sxs-lookup"><span data-stu-id="22c94-289">Create the TI component for the Service Oriented Solution</span></span>  
  
#### <a name="create-a-com-application-for-the-ti-component"></a><span data-ttu-id="22c94-290">创建用于 TI 组件的 COM + 应用程序</span><span class="sxs-lookup"><span data-stu-id="22c94-290">Create a COM+ application for the TI component</span></span>  
  
1.  <span data-ttu-id="22c94-291">在命令提示符下，运行 %systemroot%\system32\com\comexp.msc。</span><span class="sxs-lookup"><span data-stu-id="22c94-291">At a command prompt, run %systemroot%\system32\com\comexp.msc.</span></span>  
  
2.  <span data-ttu-id="22c94-292">在**组件服务**控制台中，展开**组件服务**，展开**计算机**，展开**我的电脑**，右键单击**COM + 应用程序**，指向**新建**，然后单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="22c94-292">In **Component Services** console, expand **Component Services**, expand **Computers**, expand **My Computer**, right-click **COM+ Application**, point to **New**, and then click **Application**.</span></span>  
  
    1.  <span data-ttu-id="22c94-293">上**欢迎**页上，单击**下一步**，然后单击**创建空的应用程序**上**安装或创建新的应用程序**页。</span><span class="sxs-lookup"><span data-stu-id="22c94-293">On the **Welcome** page, click **Next**, and then click **Create an empty application** on the **Install or Create a New Application** page.</span></span>  
  
    2.  <span data-ttu-id="22c94-294">类型`BTSScn SO TI Component`中**输入新的应用程序的名称**框中，选择**服务器应用程序**作为**激活类型**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="22c94-294">Type `BTSScn SO TI Component` in the **Enter a name for the new application** box, select **Server application** as **Activation type**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="22c94-295">在**帐户**组框**设置应用程序标识**页上，选择**此用户**，然后键入用户名和密码在**用户**和**密码**框。</span><span class="sxs-lookup"><span data-stu-id="22c94-295">In the **Account** group box of the **Set Application Identity** page, select **This user**, and then type the user name and password in the **User** and **Password** boxes.</span></span> <span data-ttu-id="22c94-296">新的 COM+ 应用程序将使用此用户帐户运行。</span><span class="sxs-lookup"><span data-stu-id="22c94-296">The new COM+ application will run under this user account.</span></span> <span data-ttu-id="22c94-297">此用户帐户必须为本地 HIS Runtime Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="22c94-297">This user account must be a member of local HIS Runtime Users group.</span></span> <span data-ttu-id="22c94-298">对于此演练，请使用 BizTalk 服务所使用的同一用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-298">For this walkthrough, use the same user account that the BizTalk service is using.</span></span>  
  
    4.  <span data-ttu-id="22c94-299">上**添加应用程序角色**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-299">On the **Add Application Roles** page, click **Next**.</span></span>  
  
    5.  <span data-ttu-id="22c94-300">上**向角色添加用户**页上，展开**CreatorOwner**，单击**用户**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="22c94-300">On the **Add Users to Roles** page, expand **CreatorOwner**, click **Users**, and then click **Add**.</span></span>  
  
    6.  <span data-ttu-id="22c94-301">上**选择用户或组**对话框框中，选择将用于访问大型机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-301">On the **Select Users or Groups** dialog box, select a user account that will be used for accessing the mainframe.</span></span> <span data-ttu-id="22c94-302">对于此演练，请添加 UserID 本地帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-302">For this walkthrough, add UserID local account.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="22c94-303">若要通过 TI 组件访问 CICS 事务，则可以使用该 COM+ 应用程序或作为 .NET 远程处理组件宿主的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="22c94-303">To access the CICS transaction through the TI component, you can use the COM+ application or the Web application hosting the .NET Remoting component.</span></span> <span data-ttu-id="22c94-304">此演练使用 COM+ 应用程序和 TI 组件的 COM Interop 来访问大型机，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="22c94-304">This walkthrough uses the COM+ application and COM Interop for TI components to access the mainframe to improve performance.</span></span>  
  
    7.  <span data-ttu-id="22c94-305">上**完成**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="22c94-305">On the **Completion** page, click **Finish**.</span></span>  
  
#### <a name="create-a-remote-environment-to-access-the-mainframe"></a><span data-ttu-id="22c94-306">创建一个远程的环境，以访问主机</span><span class="sxs-lookup"><span data-stu-id="22c94-306">Create a Remote Environment to access the mainframe</span></span>  
  
1.  <span data-ttu-id="22c94-307">单击**启动**，指向**所有程序**，指向**Microsoft 主机集成 Server 2004**，然后单击**TI Manager**。</span><span class="sxs-lookup"><span data-stu-id="22c94-307">Click **Start**, point to **All Programs**, point to **Microsoft Host Integration Server 2004**, and then click **TI Manager**.</span></span>  
  
2.  <span data-ttu-id="22c94-308">在**TI Manager**控制台中，单击**事务系统集成商 （配置）**，展开**Windows 启动处理**，右键单击**远程环境**，指向**新建**，然后单击**远程环境**。</span><span class="sxs-lookup"><span data-stu-id="22c94-308">In the **TI Manager** console, click **Transaction Integrator (Configuration)**, expand **Windows Initiated Processing**, right-click **Remote Environments**, point to **New**, and then click **Remote Environment**.</span></span>  
  
    1.  <span data-ttu-id="22c94-309">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-309">On the **Welcome** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="22c94-310">上**配置一个新的远程环境**页上，键入**远程应用程序名称**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-310">On the **Configure a New Remote Environment** page, type the **Remote Application Name**, and then click **Next**.</span></span> <span data-ttu-id="22c94-311">对于此演练，请使用 Mainframe_TCP 作为名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-311">For this walkthrough, use Mainframe_TCP for the name.</span></span>  
  
    3.  <span data-ttu-id="22c94-312">上**配置宿主环境和编程模型**页上，选择**CICS**为**目标主机**和**榆树链接**为**编程模型**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-312">On the **Configure Host Environment and Programming Model** page, select **CICS** for the **Target host** and **ELM Link** for the **Programming model**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="22c94-313">上**配置终结点 TCP/IP**页上，键入你大型机中的 IP 地址**IP/DNS 地址**框中，并依次**编辑**若要添加的端口号。</span><span class="sxs-lookup"><span data-stu-id="22c94-313">On **the Configure Endpoint TCP/IP** page, type the IP address for your mainframe in the **IP/DNS address** box, and then click **Edit** to add the port number.</span></span> <span data-ttu-id="22c94-314">HIS COM 将通过该终结点地址来访问事务。</span><span class="sxs-lookup"><span data-stu-id="22c94-314">Your HIS COM will access the transactions through the endpoint address.</span></span>  
  
    5.  <span data-ttu-id="22c94-315">上**完成**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="22c94-315">On the **Completion** page, click **Finish**.</span></span>  
  
#### <a name="create-the-ti-component-for-the-service-oriented-solution"></a><span data-ttu-id="22c94-316">为面向服务的解决方案创建 TI 组件</span><span class="sxs-lookup"><span data-stu-id="22c94-316">Create the TI Component for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="22c94-317">单击**启动**，指向**所有程序**，指向**Microsoft 主机集成 Server 2004**，然后单击**TI Manager**。</span><span class="sxs-lookup"><span data-stu-id="22c94-317">Click **Start**, point to **All Programs**, point to **Microsoft Host Integration Server 2004**, and then click **TI Manager**.</span></span>  
  
2.  <span data-ttu-id="22c94-318">在**TI Manager**控制台中，单击**事务系统集成商 （配置）**，单击**Windows 启动处理**，然后单击**对象**.</span><span class="sxs-lookup"><span data-stu-id="22c94-318">In the **TI Manager** console, click **Transaction Integrator (Configuration)**, click **Windows Initiated Processing**, and then click **Objects**.</span></span> <span data-ttu-id="22c94-319">右键单击**对象**，单击**新建**，然后单击**对象**。</span><span class="sxs-lookup"><span data-stu-id="22c94-319">Right-click **Objects**, click **New**, and then click **Object**.</span></span>  
  
    1.  <span data-ttu-id="22c94-320">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="22c94-320">On the **Welcome** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="22c94-321">上**指定或查找对象**页上，单击**浏览**，在 %BTSSolutionsPath%\SO\MFAccess\HISTIComponent 文件夹中，选择 SOHISTIUsingCOM.TLB，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="22c94-321">On the **Specify Or Locate An Object** page, click **Browse**, choose the SOHISTIUsingCOM.TLB in the %BTSSolutionsPath%\SO\MFAccess\HISTIComponent folder, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="22c94-322">上**定义 COM 对象的环境特征**页上，选择**BTSScn 因此 TI 组件**为**COM + 应用程序**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="22c94-322">On the **Define Environment Characteristics for The COM Object** page, select **BTSScn SO TI Component** for the **COM+ application**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="22c94-323">上**定义远程环境**页上，选择你在前面的过程中创建的远程环境**远程环境中，然后单击下一步。**</span><span class="sxs-lookup"><span data-stu-id="22c94-323">On the **Define Remote Environment** page, select the remote environment that you created in the previous procedure for the **Remote environment, and then click Next.**</span></span>  
  
    5.  <span data-ttu-id="22c94-324">上**WIP 对象创建**页上，单击**下一步**，然后单击**完成**上**完成**页。</span><span class="sxs-lookup"><span data-stu-id="22c94-324">On the **Creation of WIP Objects** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="test-the-connectivity-to-the-mainframe"></a><span data-ttu-id="22c94-325">测试到大型机连接</span><span class="sxs-lookup"><span data-stu-id="22c94-325">Test the connectivity to the mainframe</span></span>  
  
1.  <span data-ttu-id="22c94-326">在 Windows 资源管理器中，浏览至 %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester 文件夹，然后双击 Interop.SOHISTIUsingCOM.dll.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-326">In Windows Explorer, browse to the %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester folder, and then double-click the Interop.SOHISTIUsingCOM.dll.reg file.</span></span> <span data-ttu-id="22c94-327">这将添加 HISTISimpleTester 应用程序的注册表值，以便通过运行库可调用包装 (RCW) 来调用 TI 组件。</span><span class="sxs-lookup"><span data-stu-id="22c94-327">This adds registry values for the HISTISimpleTester application to call the TI component through the Runtime Callable Wrapper (RCW).</span></span>  
  
2.  <span data-ttu-id="22c94-328">在 Windows 资源管理器中，浏览至 %BTSSolutionsPath%\SO\MFAccess\ 文件夹，然后运行 SetupMFAccess.bat。</span><span class="sxs-lookup"><span data-stu-id="22c94-328">In Windows Explorer, browse to the %BTSSolutionsPath%\SO\MFAccess\ folder, and then run SetupMFAccess.bat.</span></span>  
  
3.  <span data-ttu-id="22c94-329">在 Windows 资源管理器中，导航到 %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug 文件夹，然后运行 BTSScnSOHISTIComponentSimpleTester.exe。</span><span class="sxs-lookup"><span data-stu-id="22c94-329">In Windows Explorer, navigate to the %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug folder, and then run BTSScnSOHISTIComponentSimpleTester.exe.</span></span>  
  
    -   <span data-ttu-id="22c94-330">在 HISTISimpleTester 应用程序中，单击**调用大型机程序-使用 COM**。</span><span class="sxs-lookup"><span data-stu-id="22c94-330">In the HISTISimpleTester application, click **Call Mainframe Program - Using COM**.</span></span> <span data-ttu-id="22c94-331">这样将从运行在大型机上的 COBOL 应用程序返回五条记录。</span><span class="sxs-lookup"><span data-stu-id="22c94-331">It returns five records from the COBOL application running on the mainframe.</span></span>  
  
##  <a name="step13"></a><span data-ttu-id="22c94-332">创建 Web 服务的业务流程的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="22c94-332">Create the virtual directories for the orchestration Web services</span></span>  
  
1.  <span data-ttu-id="22c94-333">在**Internet Information Services (IIS) Manager**，右键单击**应用程序池**，选择**新建**，然后选择**应用程序池**.</span><span class="sxs-lookup"><span data-stu-id="22c94-333">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    1.  <span data-ttu-id="22c94-334">上**添加新的应用程序池**对话框框中，输入**应用程序池 ID** （任意值），然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="22c94-334">On the **Add New Application Pool** dialog box, enter the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="22c94-335">右键单击你刚的应用程序池创建，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="22c94-335">Right-click the application pool that you just created, and then select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="22c94-336">上**属性**页上，单击**标识**选项卡上，选择**可配置**，输入**用户名**和**密码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="22c94-336">On the **Properties** page, click the **Identity** tab, select **Configurable**, enter the **User name** and **Password**, and then click **OK**.</span></span> <span data-ttu-id="22c94-337">对于本演练使用 BizTalk 服务正在使用的相同用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-337">For this walkthrough use the same user account that the BizTalk service is using.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-338">此用户必须有权执行业务流程代理 Web Services，并且必须添加到 BizTalk Server Administrators、SSO Administrators 或 SSO Affiliated Administrators 组中。</span><span class="sxs-lookup"><span data-stu-id="22c94-338">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
2.  <span data-ttu-id="22c94-339">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-339">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-340">使用**虚拟目录创建向导**，为代理的适配器版本的 Web 服务创建以下虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="22c94-340">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="22c94-341">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter</span><span class="sxs-lookup"><span data-stu-id="22c94-341">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter</span></span>  
  
     <span data-ttu-id="22c94-342">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter</span><span class="sxs-lookup"><span data-stu-id="22c94-342">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter</span></span>  
  
     <span data-ttu-id="22c94-343">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-343">Access Permissions = Read, Run scripts</span></span>  
  
3.  <span data-ttu-id="22c94-344">在**Internet Information Services (IIS) Manager**，展开**网站，** 展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22c94-344">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="22c94-345">在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你在上一步中创建。</span><span class="sxs-lookup"><span data-stu-id="22c94-345">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*\> that you created in the previous step.</span></span>  
  
    2.  <span data-ttu-id="22c94-346">在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证启用**，然后清除其他**身份验证访问**复选框。</span><span class="sxs-lookup"><span data-stu-id="22c94-346">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="22c94-347">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="22c94-347">Click **OK** to exit.</span></span>  
  
4.  <span data-ttu-id="22c94-348">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-348">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-349">使用**虚拟目录创建向导**，为代理的内联版本的 Web 服务创建以下虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="22c94-349">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the inline version:</span></span>  
  
     <span data-ttu-id="22c94-350">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline</span><span class="sxs-lookup"><span data-stu-id="22c94-350">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline</span></span>  
  
     <span data-ttu-id="22c94-351">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline</span><span class="sxs-lookup"><span data-stu-id="22c94-351">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline</span></span>  
  
     <span data-ttu-id="22c94-352">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-352">Access Permissions = Read, Run scripts</span></span>  
  
5.  <span data-ttu-id="22c94-353">在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22c94-353">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="22c94-354">上**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>你刚创建。</span><span class="sxs-lookup"><span data-stu-id="22c94-354">On the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*\> you just created.</span></span>  
  
    2.  <span data-ttu-id="22c94-355">单击**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，选择**仅集成 Windows 身份验证启用**，然后清除其他**身份验证访问**复选框。</span><span class="sxs-lookup"><span data-stu-id="22c94-355">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="22c94-356">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="22c94-356">Click **OK** to exit.</span></span>  
  
##  <a name="step15"></a><span data-ttu-id="22c94-357">生成面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="22c94-357">Build the Service Oriented Solution</span></span>  
  
-   <span data-ttu-id="22c94-358">在命令提示符下，将目录更改为 %btssolutionspath%\so\btssoln，类型`SetupBTSSoln.bat`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="22c94-358">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln, type `SetupBTSSoln.bat`, and then press ENTER.</span></span> <span data-ttu-id="22c94-359">SetupBTSSoln.bat 将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="22c94-359">The SetupBTSSoln.bat performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="22c94-360">创建唯一的强名称密钥 (SNK) 进行签名等解决方案的程序集。</span><span class="sxs-lookup"><span data-stu-id="22c94-360">Creates a unique strong name key (SNK) for signing the assemblies of the SO Solution.</span></span>  
  
    -   <span data-ttu-id="22c94-361">从 SNK 中提取公钥标记，并使用该公钥标记更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-361">Extracts the public key token from the SNK and updates the binding files with the public token.</span></span>  
  
    -   <span data-ttu-id="22c94-362">生成 SO 解决方案。</span><span class="sxs-lookup"><span data-stu-id="22c94-362">Builds the SO solution.</span></span>  
  
    -   <span data-ttu-id="22c94-363">在 %BTSSolutionsPath%\Common 文件夹中生成 SSOApplicationConfig。</span><span class="sxs-lookup"><span data-stu-id="22c94-363">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
##  <a name="step17"></a><span data-ttu-id="22c94-364">创建 SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="22c94-364">Create the SSO affiliate applications</span></span>  
  
1.  <span data-ttu-id="22c94-365">打开命令提示符，然后将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。</span><span class="sxs-lookup"><span data-stu-id="22c94-365">Open a command prompt, and then change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="22c94-366">在命令提示符下，使用记事本打开 PendTransAffApp.xml，并对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="22c94-366">At the command prompt, open the PendTransAffApp.xml using Notepad, and review it.</span></span> <span data-ttu-id="22c94-367">不需要更改此文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-367">No changes to this file are necessary.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-368">PendTransAffApp.xml 文件定义了用于挂起事务后端系统的 SSO 关联应用程序 WoodgroveBank.PendingTransactions。</span><span class="sxs-lookup"><span data-stu-id="22c94-368">The PendTransAffApp.xml file defines the SSO affiliate application, WoodgroveBank.PendingTransactions, for the Pending Transactions back-end system.</span></span> <span data-ttu-id="22c94-369">该文件还定义了 SSO 关联应用程序的用户组和管理组。</span><span class="sxs-lookup"><span data-stu-id="22c94-369">It also defines the user and administrative groups for the SSO affiliate application.</span></span> <span data-ttu-id="22c94-370">对于本演练中，使用**BizTalk 应用程序用户**和**BizTalk Server Administrators**。</span><span class="sxs-lookup"><span data-stu-id="22c94-370">For this walkthrough, use **BizTalk Application Users** and **BizTalk Server Administrators**.</span></span>  
    >   
    >  <span data-ttu-id="22c94-371">如果你想要为 SSO 关联应用程序使用不同的组，则需要 Active Directory 中创建 Windows 组 （使用任何名称），然后更改**appAdminAccount**和**appUserAccount**PendTransAffApp.xml 中的节点。</span><span class="sxs-lookup"><span data-stu-id="22c94-371">If you want to use different groups for the SSO affiliate application, you need to create Windows groups (with any name) in the Active Directory, and then change the **appAdminAccount** and **appUserAccount** nodes in the PendTransAffApp.xml.</span></span> <span data-ttu-id="22c94-372">如果执行此操作时，应将值设置**groupApp**属性**标志**节点为"yes"。</span><span class="sxs-lookup"><span data-stu-id="22c94-372">If you do this, you should set the value for **groupApp** attribute of **flags** node to "yes".</span></span>  
    >   
    >  <span data-ttu-id="22c94-373">SSO 关联应用程序有关的详细信息，请参阅[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="22c94-373">For more information about SSO affiliate applications, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
3.  <span data-ttu-id="22c94-374">在命令提示符下，使用记事本打开 PendTransUserMap.xml 文件，然后进行以下编辑：</span><span class="sxs-lookup"><span data-stu-id="22c94-374">At the command prompt, open the PendTransUserMap.xml file using Notepad, and then make the following edits:</span></span>  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-375">PendTransUserMap.xml 文件包含用于挂起事务后端系统的用户映射。</span><span class="sxs-lookup"><span data-stu-id="22c94-375">The PendTransUserMap.xml file contains the user mappings for the Pending Transactions back-end system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-376">有关**externalUserId**节点，待执行事务后端系统使用的外部用户 ID。</span><span class="sxs-lookup"><span data-stu-id="22c94-376">For the **externalUserId** node, use the external user ID for the Pending Transactions back-end system.</span></span> <span data-ttu-id="22c94-377">对于此演练，请使用 UserID 作为外部 ID。</span><span class="sxs-lookup"><span data-stu-id="22c94-377">For this walkthrough, use UserID for the external ID.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-378">有关**windowsUserId**节点，输入用户将其命名**externalUserId**将映射到。</span><span class="sxs-lookup"><span data-stu-id="22c94-378">For the **windowsUserId** node, enter the user name which the **externalUserId** will map to.</span></span> <span data-ttu-id="22c94-379">可以使用域组和域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-379">You can use both a domain group and a domain user account.</span></span> <span data-ttu-id="22c94-380">此用户必须是将允许其使用挂起事务后端系统的组的成员。</span><span class="sxs-lookup"><span data-stu-id="22c94-380">This user must be a member of the group that will be allowed to use the Pending Transactions back-end system.</span></span> <span data-ttu-id="22c94-381">对于此演练，请使用 BizTalk 服务的用户名。</span><span class="sxs-lookup"><span data-stu-id="22c94-381">For this walkthrough, use the user name of the BizTalk service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-382">有关**windowsDomain**节点，输入的域名称**windowsUserId**。</span><span class="sxs-lookup"><span data-stu-id="22c94-382">For the **windowsDomain** node, enter the domain name of the **windowsUserId**.</span></span>  
  
4.  <span data-ttu-id="22c94-383">在命令提示符下，使用记事本打开 PmntTrckAffApp.xml 文件，并检查该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="22c94-383">At the command prompt, open the PmntTrckAffApp.xml file using Notepad, and review the contents of the file.</span></span> <span data-ttu-id="22c94-384">不需要更改此文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-384">No changes to this file are necessary.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-385">PmntTrckAffApp.xml 文件定义了用于付款跟踪程序后端系统的 SSO 关联应用程序 WoodgroveBank.PaymentTracker。</span><span class="sxs-lookup"><span data-stu-id="22c94-385">The PmntTrckAffApp.xml file defines the SSO affiliate application, WoodgroveBank.PaymentTracker, for the Payment Tracker back-end system.</span></span>  
  
5.  <span data-ttu-id="22c94-386">在命令提示符下，使用记事本打开 PmntTrckUserMap.xml 文件，然后进行以下编辑：</span><span class="sxs-lookup"><span data-stu-id="22c94-386">At the command prompt, open the PmntTrckUserMap.xml file using Notepad, and then make the following edits:</span></span>  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-387">付款跟踪程序 SSO 关联应用程序将用于 MQSeries 适配器，并且所映射的外部用户 ID/密码将通过 MQSeries 标头属性进行发送。</span><span class="sxs-lookup"><span data-stu-id="22c94-387">The Payment Tracker SSO affiliated application will be used for the MQSeries Adapter and the mapped external user ID/password are sent through MQSeries header properties.</span></span> <span data-ttu-id="22c94-388">MQSeries 服务器只验证运行 MQSeries 适配器时所使用的 BizTalk 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="22c94-388">The MQSeries Server validates only the BizTalk service account, under which MQSeries Adapter is running.</span></span> <span data-ttu-id="22c94-389">它不验证任何外部用户凭据。</span><span class="sxs-lookup"><span data-stu-id="22c94-389">It doesn't validate any external user credential.</span></span>  
    >   
    >  <span data-ttu-id="22c94-390">有关 SSO 的详细信息相关联 MQSeries 适配器的应用程序，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="22c94-390">For more information about SSO affiliated applications for the MQSeries Adapter, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-391">PmntTrckUserMap.xml 文件包含用于付款跟踪程序后端系统的 SSO 用户映射。</span><span class="sxs-lookup"><span data-stu-id="22c94-391">The PmntTrckUserMap.xml file contains the SSO user mappings for the Payment Tracker back-end system.</span></span> <span data-ttu-id="22c94-392">付款跟踪模拟程序可模拟用户身份验证的成功条件和失败条件。</span><span class="sxs-lookup"><span data-stu-id="22c94-392">The Payment Tracker simulator program simulates both success and failure conditions for user authentication.</span></span>  
    >   
    >  <span data-ttu-id="22c94-393">程序成功进行身份验证以字母开头的所有用户 Id **PT** (例如， **PTUserID**)，并且无法进行身份验证不始于的 Id 的任何用户**PT**.</span><span class="sxs-lookup"><span data-stu-id="22c94-393">The program successfully authenticates all user IDs that begin with the letters **PT** (for example, **PTUserID**), and fails to authenticate any user IDs that do not begin with **PT**.</span></span> <span data-ttu-id="22c94-394">这样，你就能根据要测试的条件来选择适当的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="22c94-394">This enables you to choose the appropriate user ID depending on the condition that you would like to test.</span></span> <span data-ttu-id="22c94-395">您也可以重复整个**映射**针对每个用户 ID 的节点并在同一个文件中定义的多个映射。</span><span class="sxs-lookup"><span data-stu-id="22c94-395">You can also repeat the entire **mapping** node for each user ID and define multiple mappings in the same file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-396">有关**externalUserId**节点，外部用户 ID 输入付款跟踪器后端系统。</span><span class="sxs-lookup"><span data-stu-id="22c94-396">For the **externalUserId** node, enter the external user ID for the Payment Tracker back-end system.</span></span> <span data-ttu-id="22c94-397">对于此演练，请使用 PTUserID 作为外部 ID。</span><span class="sxs-lookup"><span data-stu-id="22c94-397">For this walkthrough, use PTUserID for the external ID.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-398">有关**windowsUserId**节点，输入用户将其命名**externalUserId**将映射到。</span><span class="sxs-lookup"><span data-stu-id="22c94-398">For the **windowsUserId** node, enter the user name which the **externalUserId** will map to.</span></span> <span data-ttu-id="22c94-399">此用户必须是将允许其使用付款跟踪程序后端系统的组的成员。</span><span class="sxs-lookup"><span data-stu-id="22c94-399">This user must be a member of the group that will be allowed to use the Payment Tracker back-end system.</span></span> <span data-ttu-id="22c94-400">对于此演练，请使用 BizTalk 服务的用户名。</span><span class="sxs-lookup"><span data-stu-id="22c94-400">For this walkthrough, use the user name of the BizTalk service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-401">有关**windowsDomain**节点，输入的域名称**windowsUserId**。</span><span class="sxs-lookup"><span data-stu-id="22c94-401">For the **windowsDomain** node, enter the domain name of the **windowsUserId**.</span></span>  
  
6.  <span data-ttu-id="22c94-402">在命令提示符下，使用记事本打开 ConfigStoreApp.xml 文件，然后检查该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="22c94-402">At the command prompt, open the ConfigStoreApp.xml file using Notepad, and then review the contents of the file.</span></span>  
  
     <span data-ttu-id="22c94-403">此文件定义了 SSO 中该方案用于存储配置参数的配置存储应用程序。</span><span class="sxs-lookup"><span data-stu-id="22c94-403">This file defines the configuration store application in SSO that the scenario uses to keep configuration parameters.</span></span> <span data-ttu-id="22c94-404">其中的某些配置参数包括与 SAP 进行通信时的超时值（适用于适配器版本和内联版本），以及队列管理器的名称和使用内联版本时要使用的队列。</span><span class="sxs-lookup"><span data-stu-id="22c94-404">Some of the configuration parameters include the Timeout value when communicating with SAP (for both the adapter and inline versions) and the name of the queue manager and queues to use when using the inline version.</span></span> <span data-ttu-id="22c94-405">不需要更改此文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-405">No changes to this file are necessary.</span></span>  
  
7.  <span data-ttu-id="22c94-406">在命令提示符下，使用记事本打开 SetConfigValuesInSSO.cmd 文件，并按下表检查和更改文件的内容。</span><span class="sxs-lookup"><span data-stu-id="22c94-406">At the command prompt, open the SetConfigValuesInSSO.cmd file using Notepad, review and change the contents of the file as the following table.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-407">此命令文件设置 SSO 数据库中各配置参数的值。</span><span class="sxs-lookup"><span data-stu-id="22c94-407">This command file sets the values for the configuration parameters in the SSO database.</span></span> <span data-ttu-id="22c94-408">该命令文件的开头包含几个为局部变量赋值的 set 语句。</span><span class="sxs-lookup"><span data-stu-id="22c94-408">It contains several set commands that assign the values to local variables in the beginning of the command file.</span></span>  
    >   
    >  <span data-ttu-id="22c94-409">SAPAdapterTimeout、PendingTransactionsAdapterTimeout 和 PaymentTrackingAdapterTimeout 值用于适配器版本中。</span><span class="sxs-lookup"><span data-stu-id="22c94-409">The SAPAdapterTimeout, PendingTransactionsAdapterTimeout, and PaymentTrackingAdapterTimeout values are used in the adapter version.</span></span> <span data-ttu-id="22c94-410">其余的值用于内联版本。</span><span class="sxs-lookup"><span data-stu-id="22c94-410">The remaining values are used in the inline version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-411">你可以输入""（两个双引号） 有关标记的默认值\<用户指定\>下表中。</span><span class="sxs-lookup"><span data-stu-id="22c94-411">You can enter " " (two double quotes) for the default values marked \<User Specified\> in the following table.</span></span>  
  
    |<span data-ttu-id="22c94-412">参数</span><span class="sxs-lookup"><span data-stu-id="22c94-412">Parameter</span></span>|<span data-ttu-id="22c94-413">默认值</span><span class="sxs-lookup"><span data-stu-id="22c94-413">Default Value</span></span>|<span data-ttu-id="22c94-414">Description</span><span class="sxs-lookup"><span data-stu-id="22c94-414">Description</span></span>|  
    |---------------|-------------------|-----------------|  
    |<span data-ttu-id="22c94-415">SAPAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="22c94-415">SAPAdapterTimeout</span></span>|<span data-ttu-id="22c94-416">20000</span><span class="sxs-lookup"><span data-stu-id="22c94-416">20000</span></span>|<span data-ttu-id="22c94-417">对 SAP 后端的请求的最大超时值（毫秒）</span><span class="sxs-lookup"><span data-stu-id="22c94-417">Max timeout (millisecond) for a request to the SAP back-end</span></span>|  
    |<span data-ttu-id="22c94-418">SAPInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="22c94-418">SAPInlineTimeout</span></span>|<span data-ttu-id="22c94-419">20000</span><span class="sxs-lookup"><span data-stu-id="22c94-419">20000</span></span>|<span data-ttu-id="22c94-420">对 SAP 后端的请求的最大超时值（毫秒）</span><span class="sxs-lookup"><span data-stu-id="22c94-420">Max timeout (millisecond) for a request to the SAP back-end</span></span>|  
    |<span data-ttu-id="22c94-421">SAPInlineHostName</span><span class="sxs-lookup"><span data-stu-id="22c94-421">SAPInlineHostName</span></span>|<span data-ttu-id="22c94-422">\<指定用户\></span><span class="sxs-lookup"><span data-stu-id="22c94-422">\<User Specified\></span></span>|<span data-ttu-id="22c94-423">SAP 后端标识符</span><span class="sxs-lookup"><span data-stu-id="22c94-423">SAP back-end identifier</span></span>|  
    |<span data-ttu-id="22c94-424">SAPInlineClientNumber</span><span class="sxs-lookup"><span data-stu-id="22c94-424">SAPInlineClientNumber</span></span>|<span data-ttu-id="22c94-425">\<指定用户\></span><span class="sxs-lookup"><span data-stu-id="22c94-425">\<User Specified\></span></span>|<span data-ttu-id="22c94-426">SAP 客户端编号</span><span class="sxs-lookup"><span data-stu-id="22c94-426">SAP Client number</span></span>|  
    |<span data-ttu-id="22c94-427">SAPInlineSystemNumber</span><span class="sxs-lookup"><span data-stu-id="22c94-427">SAPInlineSystemNumber</span></span>|<span data-ttu-id="22c94-428">\<指定用户\></span><span class="sxs-lookup"><span data-stu-id="22c94-428">\<User Specified\></span></span>|<span data-ttu-id="22c94-429">SAP 系统编号</span><span class="sxs-lookup"><span data-stu-id="22c94-429">SAP System number</span></span>|  
    |<span data-ttu-id="22c94-430">SAPInlineUserName</span><span class="sxs-lookup"><span data-stu-id="22c94-430">SAPInlineUserName</span></span>|<span data-ttu-id="22c94-431">\<指定用户\></span><span class="sxs-lookup"><span data-stu-id="22c94-431">\<User Specified\></span></span>|<span data-ttu-id="22c94-432">用于连接到 SAP 后端的用户名</span><span class="sxs-lookup"><span data-stu-id="22c94-432">The user name used to connect to the SAP back-end</span></span>|  
    |<span data-ttu-id="22c94-433">SAPInlinePassword</span><span class="sxs-lookup"><span data-stu-id="22c94-433">SAPInlinePassword</span></span>|<span data-ttu-id="22c94-434">\<指定用户\></span><span class="sxs-lookup"><span data-stu-id="22c94-434">\<User Specified\></span></span>|<span data-ttu-id="22c94-435">用于连接到 SAP 后端的密码</span><span class="sxs-lookup"><span data-stu-id="22c94-435">The password used to connect to the SAP back-end</span></span>|  
    |<span data-ttu-id="22c94-436">PendingTransactionsAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="22c94-436">PendingTransactionsAdapterTimeout</span></span>|<span data-ttu-id="22c94-437">20000</span><span class="sxs-lookup"><span data-stu-id="22c94-437">20000</span></span>|<span data-ttu-id="22c94-438">对挂起事务服务器的请求的最大超时值（毫秒）</span><span class="sxs-lookup"><span data-stu-id="22c94-438">Max timeout (millisecond) for a request to the Pending Transactions server</span></span>|  
    |<span data-ttu-id="22c94-439">PendingTransactionsInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="22c94-439">PendingTransactionsInlineTimeout</span></span>|<span data-ttu-id="22c94-440">20000</span><span class="sxs-lookup"><span data-stu-id="22c94-440">20000</span></span>|<span data-ttu-id="22c94-441">对挂起事务服务器的请求的最大超时值（毫秒）</span><span class="sxs-lookup"><span data-stu-id="22c94-441">Max timeout (millisecond) for a request to the Pending Transactions server</span></span>|  
    |<span data-ttu-id="22c94-442">PendingTransactionsInlineURL</span><span class="sxs-lookup"><span data-stu-id="22c94-442">PendingTransactionsInlineURL</span></span>|<span data-ttu-id="22c94-443">https://\<*您的计算机名称*\>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx</span><span class="sxs-lookup"><span data-stu-id="22c94-443">https://\<*your computer name*\>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx</span></span>|<span data-ttu-id="22c94-444">挂起事务服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="22c94-444">URL of the Pending Transactions service.</span></span> <span data-ttu-id="22c94-445">\<*你的计算机名*\>必须匹配**公用名**中"创建证书请求"的过程。</span><span class="sxs-lookup"><span data-stu-id="22c94-445">\<*Your computer name*\> must match the **common name** in the procedure "To create a certificate request".</span></span> <span data-ttu-id="22c94-446">您必须对不使用"localhost" \<*您的计算机名称*\>。</span><span class="sxs-lookup"><span data-stu-id="22c94-446">You must not use "localhost" for \<*Your computer name*\>.</span></span>|  
    |<span data-ttu-id="22c94-447">PendingTransactionsInlineSSOAffiliateApp</span><span class="sxs-lookup"><span data-stu-id="22c94-447">PendingTransactionsInlineSSOAffiliateApp</span></span>|<span data-ttu-id="22c94-448">WoodgroveBank.PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-448">WoodgroveBank.PendingTransactions</span></span>|<span data-ttu-id="22c94-449">挂起事务 SSO 应用程序名</span><span class="sxs-lookup"><span data-stu-id="22c94-449">Pending Transactions SSO application name</span></span>|  
    |<span data-ttu-id="22c94-450">PaymentTrackingAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="22c94-450">PaymentTrackingAdapterTimeout</span></span>|<span data-ttu-id="22c94-451">20000</span><span class="sxs-lookup"><span data-stu-id="22c94-451">20000</span></span>|<span data-ttu-id="22c94-452">对付款跟踪系统的请求的最大超时值（毫秒）</span><span class="sxs-lookup"><span data-stu-id="22c94-452">Max timeout (millisecond) for a request to the Payment Tracking system</span></span>|  
    |<span data-ttu-id="22c94-453">PaymentTrackingInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="22c94-453">PaymentTrackingInlineTimeout</span></span>|<span data-ttu-id="22c94-454">20000</span><span class="sxs-lookup"><span data-stu-id="22c94-454">20000</span></span>|<span data-ttu-id="22c94-455">对付款跟踪系统的请求的最大超时值（毫秒）</span><span class="sxs-lookup"><span data-stu-id="22c94-455">Max timeout (millisecond) for a request to the Payment Tracking system</span></span>|  
    |<span data-ttu-id="22c94-456">PaymentTrackingInlineQManager</span><span class="sxs-lookup"><span data-stu-id="22c94-456">PaymentTrackingInlineQManager</span></span>|<span data-ttu-id="22c94-457">\<用户指定\>(通常 QM_\<*您的计算机名称*\>)。</span><span class="sxs-lookup"><span data-stu-id="22c94-457">\<User Specified\> (Typically QM_\<*your computer name*\>).</span></span>|<span data-ttu-id="22c94-458">MQSeries 队列管理器名称</span><span class="sxs-lookup"><span data-stu-id="22c94-458">MQSeries Queue Manager name</span></span>|  
    |<span data-ttu-id="22c94-459">PaymentTrackingInlineMQChannelDefinition</span><span class="sxs-lookup"><span data-stu-id="22c94-459">PaymentTrackingInlineMQChannelDefinition</span></span>|<span data-ttu-id="22c94-460">" "（需要输入两个双引号）。</span><span class="sxs-lookup"><span data-stu-id="22c94-460">" " (need to enter the two double quotes).</span></span>|<span data-ttu-id="22c94-461">如果为本地，则此项为空字符串，也可以为远程 MQ 服务器的格式化通道名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-461">Empty string if local, or formatted channel name of the remote MQ server.</span></span> <span data-ttu-id="22c94-462">如果在配置 IBM WebSphere MQ 保留所有默认设置，通道定义将 S__\<*您的计算机名称*\>/TCP/\<*您的计算机名称*\>(1414)。</span><span class="sxs-lookup"><span data-stu-id="22c94-462">If you keep all default settings in configuring IBM WebSphere MQ, the channel definition will be S__\<*your computer name*\>/TCP/\<*your computer name*\>(1414).</span></span>|  
    |<span data-ttu-id="22c94-463">PaymentTrackingInlineRequestQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-463">PaymentTrackingInlineRequestQueue</span></span>|<span data-ttu-id="22c94-464">LastPaymentsInputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-464">LastPaymentsInputQueue</span></span>|<span data-ttu-id="22c94-465">付款跟踪请求的 MQ 队列名称</span><span class="sxs-lookup"><span data-stu-id="22c94-465">The MQ Queue name for payment tracking requests</span></span>|  
    |<span data-ttu-id="22c94-466">PaymentTrackingInlineResponseQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-466">PaymentTrackingInlineResponseQueue</span></span>|<span data-ttu-id="22c94-467">LastPaymentsOutputQueue</span><span class="sxs-lookup"><span data-stu-id="22c94-467">LastPaymentsOutputQueue</span></span>|<span data-ttu-id="22c94-468">付款跟踪响应的 MQ 队列名称</span><span class="sxs-lookup"><span data-stu-id="22c94-468">The MQ Queue name for payment tracking responses</span></span>|  
    |<span data-ttu-id="22c94-469">PaymentTrackingInlineSSOAffiliateApp</span><span class="sxs-lookup"><span data-stu-id="22c94-469">PaymentTrackingInlineSSOAffiliateApp</span></span>|<span data-ttu-id="22c94-470">WoodgroveBank.PaymentTracker</span><span class="sxs-lookup"><span data-stu-id="22c94-470">WoodgroveBank.PaymentTracker</span></span>|<span data-ttu-id="22c94-471">付款跟踪 SSO 应用程序名</span><span class="sxs-lookup"><span data-stu-id="22c94-471">Payment tracking SSO application name</span></span>|  
    |<span data-ttu-id="22c94-472">StubSAPWebServiceURL</span><span class="sxs-lookup"><span data-stu-id="22c94-472">StubSAPWebServiceURL</span></span>|<span data-ttu-id="22c94-473">http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx</span><span class="sxs-lookup"><span data-stu-id="22c94-473">http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx</span></span>|<span data-ttu-id="22c94-474">信用限额 SAP 系统的存根 Web Services URL</span><span class="sxs-lookup"><span data-stu-id="22c94-474">The stub Web service URL of the Credit Limit SAP system</span></span>|  
  
8.  <span data-ttu-id="22c94-475">在命令提示符下，运行以下命令以设置 PATH 环境：</span><span class="sxs-lookup"><span data-stu-id="22c94-475">At the command prompt, run the following command to set the PATH environment:</span></span>  
  
    -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  
  
9. <span data-ttu-id="22c94-476">在命令提示符下运行 CreateInitialConfigInSSO.cmd。</span><span class="sxs-lookup"><span data-stu-id="22c94-476">At the command prompt, run the CreateInitialConfigInSSO.cmd.</span></span> <span data-ttu-id="22c94-477">它将创建 SSO Affiliate 应用程序、 SSO 配置存储应用程序和关联应用程序的用户映射。</span><span class="sxs-lookup"><span data-stu-id="22c94-477">It creates the SSO Affiliate Applications, the SSO configuration store application, and the user mappings for the affiliate applications.</span></span> <span data-ttu-id="22c94-478">然后，它将执行 SetConfigValuesInSSO.cmd，以便将配置值存储在 SSO 配置存储应用程序中。</span><span class="sxs-lookup"><span data-stu-id="22c94-478">Then, it executes the SetConfigValuesInSSO.cmd to store configuration values in the SSO configuration store application.</span></span>  
  
10. <span data-ttu-id="22c94-479">在命令提示符下，运行以下命令以设置挂起事务关联应用程序的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="22c94-479">At the command prompt, run the following command to set the user credential for the Pending Transactions affiliate application.</span></span> <span data-ttu-id="22c94-480">使用\< **DomainName** \>和\< **UserID** \>中为 PendTransUserMap.xml 定义\<WindowsDomain\> \\< WindowsUserId\>。</span><span class="sxs-lookup"><span data-stu-id="22c94-480">Use the \<**DomainName**\> and \<**UserID**\> defined in the PendTransUserMap.xml for the \<WindowsDomain\>\\<WindowsUserId\>.</span></span> <span data-ttu-id="22c94-481">此命令要求你输入此演练中所使用的外部用户的密码和 UserID。</span><span class="sxs-lookup"><span data-stu-id="22c94-481">This command asks you to enter the password of the external user, UserID, used in this walkthrough.</span></span>  
  
    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  
  
11. <span data-ttu-id="22c94-482">在命令提示符下，运行以下命令以设置付款跟踪关联应用程序的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="22c94-482">At the command prompt, run the following command to set the user credential for the Payment Tracker affiliate application.</span></span> <span data-ttu-id="22c94-483">使用\< **DomainName** \>和\< **UserID** \>中为 PmntTrckUserMap.xml 定义\<WindowsDomain\> \\< WindowsUserId\>。</span><span class="sxs-lookup"><span data-stu-id="22c94-483">Use the \<**DomainName**\> and \<**UserID**\> defined in the PmntTrckUserMap.xml for the \<WindowsDomain\>\\<WindowsUserId\>.</span></span> <span data-ttu-id="22c94-484">此命令要求你输入此演练中所使用的外部用户的密码和 PTUserID。</span><span class="sxs-lookup"><span data-stu-id="22c94-484">This command asks you to enter the password of the external user, PTUserID, used in this walkthrough.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-485">付款跟踪模拟程序不验证外部用户凭据。</span><span class="sxs-lookup"><span data-stu-id="22c94-485">The Payment Tracker simulator doesn't validate the external user credential.</span></span> <span data-ttu-id="22c94-486">可以为 PTUserID 输入任何密码。</span><span class="sxs-lookup"><span data-stu-id="22c94-486">You can enter any password for the PTUserID.</span></span>  
  
    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  
  
##  <a name="step19"></a><span data-ttu-id="22c94-487">为服务面向解决方案部署的 BAM 定义文件</span><span class="sxs-lookup"><span data-stu-id="22c94-487">Deploy the BAM definition file for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="22c94-488">打开命令提示符，键入以下命令，然后按 Enter 以设置用于查找 BAM 实用工具的路径：</span><span class="sxs-lookup"><span data-stu-id="22c94-488">Open a command prompt, type the following command, and then press ENTER to set the path to find the BAM utilities:</span></span>  
  
    -   <span data-ttu-id="22c94-489">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span><span class="sxs-lookup"><span data-stu-id="22c94-489">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span></span>  
  
2.  <span data-ttu-id="22c94-490">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\BAM，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="22c94-490">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM, type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
##  <a name="step21"></a><span data-ttu-id="22c94-491">部署面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="22c94-491">Deploy the Service Oriented Solution</span></span>  
  
#### <a name="update-the-binding-files-for-the-service-oriented-solution"></a><span data-ttu-id="22c94-492">更新服务面向解决方案绑定文件</span><span class="sxs-lookup"><span data-stu-id="22c94-492">Update the binding files for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="22c94-493">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，使用记事本打开 Deployallbinding.xml，然后进行以下编辑：</span><span class="sxs-lookup"><span data-stu-id="22c94-493">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open the Deployallbinding.xml using Notepad, and then make the following edits:</span></span>  
  
    -   <span data-ttu-id="22c94-494">将 SET MGMT_DB_SERVER 和 MBMT_DB 中的服务器名称更改为 BizTalk Server 正在使用的服务器和数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-494">Change the name of the server in the SET MGMT_DB_SERVER and MBMT_DB to the name of the server and database that BizTalk Server is using.</span></span>  
  
    -   <span data-ttu-id="22c94-495">将 SOLNDIR 变量的值更改为“%BTSSolutionsPath%\SO\BTSSoln”。</span><span class="sxs-lookup"><span data-stu-id="22c94-495">Change the value of the SOLNDIR variable to "%BTSSolutionsPath%\SO\BTSSoln".</span></span>  
  
2.  <span data-ttu-id="22c94-496">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Bindings 文件夹。</span><span class="sxs-lookup"><span data-stu-id="22c94-496">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Bindings folder.</span></span>  
  
3.  <span data-ttu-id="22c94-497">对于适配器版本，使用记事本打开 AdapterSOAOrchBindings.xml，然后按如下所述进行编辑：</span><span class="sxs-lookup"><span data-stu-id="22c94-497">For the adapter version, open the AdapterSOAOrchBindings.xml using Notepad, and then edit as follows:</span></span>  
  
    -   <span data-ttu-id="22c94-498">替换所有出现的 __MQ_SERVER_NAME\_ \_ MQSeries 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-498">Replace all occurrences of __MQ_SERVER_NAME\_\_ with the MQSeries Server name.</span></span>  
  
    -   <span data-ttu-id="22c94-499">替换所有出现的 __MQ_QMANAGER_NAME\_ \_具有 MQSeries 队列管理器名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-499">Replace all occurrences of __MQ_QMANAGER_NAME\_\_ with the MQSeries Queue Manager name.</span></span>  
  
    -   <span data-ttu-id="22c94-500">替换所有出现的 __PT_WS_SERVER_NAME\_ \_字符串中"\<地址\>https://\__PT_WS_SERVER_NAME\_\_"的服务器名称其中 Pending部署事务 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="22c94-500">Replace all occurrences of __PT_WS_SERVER_NAME\_\_ in the string "\<Address\>https://\__PT_WS_SERVER_NAME\_\_" with the server name where the Pending Transactions Web service is deployed.</span></span> <span data-ttu-id="22c94-501">服务器名称必须匹配**公用名**在步骤中，"若要配置 Web 服务器用于 SSL"。</span><span class="sxs-lookup"><span data-stu-id="22c94-501">The server name must match the **common name** in the step, "To configure the Web server for SSL".</span></span> <span data-ttu-id="22c94-502">不应使用“localhost”。</span><span class="sxs-lookup"><span data-stu-id="22c94-502">You shouldn't use localhost.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-503">绑定文件 AdapterSOAOrchBindings.xml 为以下项使用存根 Web Services：</span><span class="sxs-lookup"><span data-stu-id="22c94-503">The binding file, AdapterSOAOrchBindings.xml, uses the stub Web service for:</span></span>  
    >   
    >  1.  <span data-ttu-id="22c94-504">信用限额后端 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="22c94-504">The Credit Limit back-end SAP system.</span></span>  
    > 2.  <span data-ttu-id="22c94-505">用于与付款跟踪后端系统相集成的 MQSeries 适配器。</span><span class="sxs-lookup"><span data-stu-id="22c94-505">The MQSeries adapter to integrate with the Payment Tracking back-end system.</span></span>  
    > 3.  <span data-ttu-id="22c94-506">用于调用 HIS TI .NET 组件以与大型机后端系统相集成的挂起事务 Web Services。</span><span class="sxs-lookup"><span data-stu-id="22c94-506">The Pending Transactions Web service to call the HIS TI .NET component to integrate with the mainframe back-end system.</span></span>  
    >   
    >  <span data-ttu-id="22c94-507">如果不是使用大型机，则必须使用存根 Web Services 为挂起事务系统生成数据。</span><span class="sxs-lookup"><span data-stu-id="22c94-507">If you aren’t using the mainframe, you must use the stub Web service to generate data for the Pending Transactions system.</span></span>  
  
4.  <span data-ttu-id="22c94-508">对于内联版本，使用记事本打开 InlineSOAOrchBindings.xml，然后按如下所述进行编辑：</span><span class="sxs-lookup"><span data-stu-id="22c94-508">For the inline version, open the InlineSOAOrchBindings.xml using Notepad, and then edit as follows:</span></span>  
  
    -   <span data-ttu-id="22c94-509">替换所有出现的 __MQ_SERVER_NAME\_ \_ MQSeries 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-509">Replace all occurrences of __MQ_SERVER_NAME\_\_ with the MQSeries Server name.</span></span>  
  
    -   <span data-ttu-id="22c94-510">替换所有出现的 __MQ_QMANAGER_NAME\_ \_具有 MQSeries 队列管理器名称。</span><span class="sxs-lookup"><span data-stu-id="22c94-510">Replace all occurrences of __MQ_QMANAGER_NAME\_\_ with the MQSeries Queue Manager name.</span></span>  
  
#### <a name="deploy-the-service-oriented-solution"></a><span data-ttu-id="22c94-511">部署面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="22c94-511">Deploy the Service Oriented solution</span></span>  
  
-   <span data-ttu-id="22c94-512">在命令提示符下，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="22c94-512">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER.</span></span>  
  
    -   `Deployallbinding.cmd`  
  
    > [!NOTE]
    >  <span data-ttu-id="22c94-513">Deployallbinding.cmd 将创建名为 BTSScn.SO.CustomerService 的 BizTalk 应用程序，并为适配器版本和内联版本导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="22c94-513">The Deployallbinding.cmd creates the BizTalk application named BTSScn.SO.CustomerService and imports binding files for the adapter and inline versions.</span></span>  
  
##  <a name="step23"></a><span data-ttu-id="22c94-514">配置存根 （stub） 挂起的事务 Web 服务主机不可用时</span><span class="sxs-lookup"><span data-stu-id="22c94-514">Configure the stub Pending Transactions Web Services when a mainframe is not available</span></span>  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a><span data-ttu-id="22c94-515">配置存根 （stub） 挂起的事务 Web 服务 （适用于使用而无需大型机的适配器版本）</span><span class="sxs-lookup"><span data-stu-id="22c94-515">Configure the stub Pending Transactions Web service (for using the adapter version without a mainframe)</span></span>  
  
1.  <span data-ttu-id="22c94-516">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-516">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-517">使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） 适配器版本的挂起的事务 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="22c94-517">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for stub Pending Transactions Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="22c94-518">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-518">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
     <span data-ttu-id="22c94-519">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="22c94-519">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
     <span data-ttu-id="22c94-520">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-520">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="22c94-521">在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，然后修改的设置，如下所示使用**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="22c94-521">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows using the **Properties** dialog box.</span></span>  
  
    1.  <span data-ttu-id="22c94-522">在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>创建在步骤中，创建虚拟目录在 IIS 中的解决方案"。</span><span class="sxs-lookup"><span data-stu-id="22c94-522">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*\> you created in the step, "To create the virtual directories in IIS for the solution".</span></span>  
  
    2.  <span data-ttu-id="22c94-523">在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**.</span><span class="sxs-lookup"><span data-stu-id="22c94-523">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="22c94-524">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="22c94-524">Click **OK** to exit.</span></span>  
  
3.  <span data-ttu-id="22c94-525">在**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**应用程序**，展开 BTSScn.SO.CustomerService，展开**发送端口**，右键单击**PendingTransactionSolicitResponsePort**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="22c94-525">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand BTSScn.SO.CustomerService, expand **Send Ports**, right-click **PendingTransactionSolicitResponsePort**, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="22c94-526">在**常规**页上，单击**配置**以显示**传输属性**对话框框中，，然后修改**Web 服务 URL**到存根 （stub） 挂起的事务 Web 服务，例如：</span><span class="sxs-lookup"><span data-stu-id="22c94-526">In the **General** page, click **Configure** to display the **Transport Properties** dialog box, and then modify the **Web Service URL** to the stub Pending Transaction Web service, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
    2.  <span data-ttu-id="22c94-527">关闭所有对话框。</span><span class="sxs-lookup"><span data-stu-id="22c94-527">Close all of the dialog boxes.</span></span>  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a><span data-ttu-id="22c94-528">配置存根 （stub） 挂起的事务 Web 服务 （适用于使用而无需大型机的内联版本）</span><span class="sxs-lookup"><span data-stu-id="22c94-528">Configure the stub Pending Transactions Web service (for using the inline version without a mainframe)</span></span>  
  
1.  <span data-ttu-id="22c94-529">在**Internet Information Services (IIS) Manager**，展开**网站**，右键单击**Default Web Site**，指向**新建**，和然后单击**虚拟目录**运行**虚拟目录创建向导**。</span><span class="sxs-lookup"><span data-stu-id="22c94-529">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="22c94-530">使用**虚拟目录创建向导**，创建以下虚拟目录存根 （stub） 适配器版本的挂起的事务 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="22c94-530">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for stub Pending Transactions Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="22c94-531">别名 = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="22c94-531">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
     <span data-ttu-id="22c94-532">路径 = \< *BizTalk 安装目录*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="22c94-532">PATH = \<*BizTalk Install Directory*\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
     <span data-ttu-id="22c94-533">访问权限 = 读取，运行脚本</span><span class="sxs-lookup"><span data-stu-id="22c94-533">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="22c94-534">在**Internet Information Services (IIS) Manager**，展开**网站**，展开**Default Web Site**，右键单击Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions，单击**属性**，，然后修改设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22c94-534">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="22c94-535">在**虚拟目录**选项卡上，设置**应用程序池**到\< *YourAppPool* \>创建在步骤中，创建虚拟目录在 IIS 中的解决方案"。</span><span class="sxs-lookup"><span data-stu-id="22c94-535">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*\> you created in the step, "To create the virtual directories in IIS for the solution".</span></span>  
  
    2.  <span data-ttu-id="22c94-536">在**目录安全性**选项卡上，单击**编辑**中**身份验证和访问控制**组框中，，然后选择**启用匿名访问**.</span><span class="sxs-lookup"><span data-stu-id="22c94-536">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="22c94-537">单击**确定**退出。</span><span class="sxs-lookup"><span data-stu-id="22c94-537">Click **OK** to exit.</span></span>  
  
3.  <span data-ttu-id="22c94-538">打开命令提示符，然后将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹。</span><span class="sxs-lookup"><span data-stu-id="22c94-538">Open a command prompt, and then change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
4.  <span data-ttu-id="22c94-539">在命令提示符下，SetConfigValuesInSSO.cmd 使用记事本打开文件，并将的值**PendingTransactionsInlineURL**存根 （stub) 挂起的事务 Web 服务的 url。</span><span class="sxs-lookup"><span data-stu-id="22c94-539">At the command prompt, open the SetConfigValuesInSSO.cmd file using Notepad, and then set the value of the **PendingTransactionsInlineURL** to the URL of the stub Pending Transaction Web Service.</span></span>  
  
    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
5.  <span data-ttu-id="22c94-540">在命令提示符下，键入 `SetConfigValuesInSSO.cmd`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="22c94-540">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER.</span></span>  
  
##  <a name="step25"></a><span data-ttu-id="22c94-541">启动服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="22c94-541">Start the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="22c94-542">打开命令提示符，将目录更改为 %BTSSolutionsPath%\SO\BTSSoln\Scripts 文件夹，键入以下命令，然后按 Enter 以启动内联版本和适配器版本的所有业务流程：</span><span class="sxs-lookup"><span data-stu-id="22c94-542">Open a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER to start all orchestrations for the inline and adapter versions.</span></span>  
  
    -   `startAll.vbs`  
  
2.  <span data-ttu-id="22c94-543">运行面向服务的解决方案。</span><span class="sxs-lookup"><span data-stu-id="22c94-543">Run the service-oriented solution.</span></span> <span data-ttu-id="22c94-544">有关运行解决方案的详细信息，请参阅[如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="22c94-544">For more information about running the solution, see [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="22c94-545">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22c94-545">Next Steps</span></span>  
 <span data-ttu-id="22c94-546">测试中的面向服务的解决方案的内联和适配器版本[如何运行服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="22c94-546">You test the inline and adapter version of the service-oriented solution in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c94-547">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22c94-547">See Also</span></span>  
 <span data-ttu-id="22c94-548">[在安装之前面向服务解决方案](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="22c94-548">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="22c94-549">[如何安装服务的存根 （stub） 版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="22c94-549">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="22c94-550">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="22c94-550">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)