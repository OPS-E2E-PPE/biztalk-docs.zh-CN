---
title: "ExpenseReportSubmission |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
ms.assetid: d0bacab3-7092-44b8-a1c6-6f574a2db8bd
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 993d1874a95da2501636f941f1436fec894e87f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="expensereportsubmission"></a><span data-ttu-id="8cc7a-102">ExpenseReportSubmission</span><span class="sxs-lookup"><span data-stu-id="8cc7a-102">ExpenseReportSubmission</span></span>
<span data-ttu-id="8cc7a-103">ExpenseReportSubmission 示例演示了如何从胖客户端（如 Microsoft Excel）向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程提交文档。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-103">The ExpenseReportSubmission sample demonstrates how to submit a document to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration from a rich client such as Microsoft Excel.</span></span>  
  
 <span data-ttu-id="8cc7a-104">胖客户端允许在客户端上执行多种操作，如数据验证和基本计算。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-104">Rich clients enable you to perform a number of actions, such as data validation and preliminary calculations, on the client.</span></span> <span data-ttu-id="8cc7a-105">这有助于最大程度地减少与后端服务器的交互，当只有低带宽连接可用时，将十分有用。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-105">This helps to minimize interactions with the back-end server, which can be useful when only low bandwidth connections are available.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8cc7a-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="8cc7a-106">Prerequisites</span></span>  
 <span data-ttu-id="8cc7a-107">必须确保您的开发环境已正确配置且能够使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-107">You must ensure that your development environment is configured and enabled to work with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services.</span></span> <span data-ttu-id="8cc7a-108">有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-108">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="8cc7a-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="8cc7a-109">What This Sample Does</span></span>  
 <span data-ttu-id="8cc7a-110">本示例演示如何使用以下一系列步骤直接从 Excel 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交费用报告：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-110">This sample shows how you can submit an expense report to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directly from Excel, using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="8cc7a-111">用户执行 Excel 电子表格中提供的手动示例步骤。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-111">The user performs the manual sample steps provided in the Excel spreadsheet.</span></span>  
  
2.  <span data-ttu-id="8cc7a-112">电子表格中的宏代码将电子表格数据转换为可扩展标记语言 (XML) 格式，并使用 HTTP 连接将该 XML 消息提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-112">Macro code in the spreadsheet converts the spreadsheet data to Extensible Markup Language (XML) format, and submits the XML message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using an HTTP connection.</span></span>  
  
3.  <span data-ttu-id="8cc7a-113">运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机检索该 XML 费用报告消息，使用提供的架构验证报告格式，然后将它放到另一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-113">The computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] retrieves the XML expense report message, validates its format using the provided schema, and then drops it into a different folder.</span></span>  
  
4.  <span data-ttu-id="8cc7a-114">在实际使用中，另一个应用程序（如企业资源规划 (ERP) 系统）随后会检索该电子表格文件以进一步处理，但这已经超出了本示例的范围。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-114">In practice, beyond the scope of this sample, another application such as an Enterprise Resource Planning (ERP) system would then retrieve the spreadsheet file for further processing.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="8cc7a-115">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="8cc7a-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="8cc7a-116">\<*示例路径*> \AdaptersUsage\ExpenseReportSubmission\\</span><span class="sxs-lookup"><span data-stu-id="8cc7a-116">\<*Samples Path*>\AdaptersUsage\ExpenseReportSubmission\\</span></span>  
  
 <span data-ttu-id="8cc7a-117">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-117">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="8cc7a-118">文件</span><span class="sxs-lookup"><span data-stu-id="8cc7a-118">File(s)</span></span>|<span data-ttu-id="8cc7a-119">Description</span><span class="sxs-lookup"><span data-stu-id="8cc7a-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8cc7a-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="8cc7a-120">Cleanup.bat</span></span>|<span data-ttu-id="8cc7a-121">取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-121">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="8cc7a-122">ExpenseReport.15.3.xls</span><span class="sxs-lookup"><span data-stu-id="8cc7a-122">ExpenseReport.15.3.xls</span></span>|<span data-ttu-id="8cc7a-123">Excel 电子表格，包含费用报告布局、相关联的宏及调用这些宏的按钮。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-123">Excel spreadsheet with the expense report layout, associated macros, and buttons to invoke the macros.</span></span>|  
|<span data-ttu-id="8cc7a-124">MessageExample.xml</span><span class="sxs-lookup"><span data-stu-id="8cc7a-124">MessageExample.xml</span></span>|<span data-ttu-id="8cc7a-125">XML 费用报告格式示例。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-125">Example of the XML expense report format.</span></span>|  
|<span data-ttu-id="8cc7a-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="8cc7a-126">Setup.bat</span></span>|<span data-ttu-id="8cc7a-127">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-127">Builds and initializes this sample.</span></span>|  
|<span data-ttu-id="8cc7a-128">在 \BTSExpenseDemo 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-128">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="8cc7a-129">AssemblyInfo.cs、</span><span class="sxs-lookup"><span data-stu-id="8cc7a-129">AssemblyInfo.cs,</span></span><br /><br /> <span data-ttu-id="8cc7a-130">BTSExpenseDemo.btproj、</span><span class="sxs-lookup"><span data-stu-id="8cc7a-130">BTSExpenseDemo.btproj,</span></span><br /><br /> <span data-ttu-id="8cc7a-131">BTSExpenseDemo.sln</span><span class="sxs-lookup"><span data-stu-id="8cc7a-131">BTSExpenseDemo.sln</span></span>|<span data-ttu-id="8cc7a-132">提供本示例的项目、解决方案和相关文件。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-132">Provides project, solution, and related files for this sample.</span></span>|  
|<span data-ttu-id="8cc7a-133">在 \BTSExpenseDemo 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-133">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="8cc7a-134">BTSExpenseDemoBinding.xml</span><span class="sxs-lookup"><span data-stu-id="8cc7a-134">BTSExpenseDemoBinding.xml</span></span>|<span data-ttu-id="8cc7a-135">用于自动安装，如端口绑定。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-135">Used for automated setup, such as port binding.</span></span>|  
|<span data-ttu-id="8cc7a-136">在 \BTSExpenseDemo 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-136">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="8cc7a-137">BTSExpenseOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="8cc7a-137">BTSExpenseOrchestration.odx</span></span>|<span data-ttu-id="8cc7a-138">提供本示例的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-138">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for this sample.</span></span>|  
|<span data-ttu-id="8cc7a-139">在 \BTSExpenseDemo 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-139">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="8cc7a-140">SchemaExpenseReport.xsd</span><span class="sxs-lookup"><span data-stu-id="8cc7a-140">SchemaExpenseReport.xsd</span></span>|<span data-ttu-id="8cc7a-141">提供 XML 费用报告格式的架构。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-141">Provides a schema for the XML expense report format.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="8cc7a-142">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="8cc7a-142">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="8cc7a-143">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-143">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="8cc7a-144">\<*示例路径*> \AdaptersUsage\ExpenseReportSubmission</span><span class="sxs-lookup"><span data-stu-id="8cc7a-144">\<*Samples Path*>\AdaptersUsage\ExpenseReportSubmission</span></span>  
  
2.  <span data-ttu-id="8cc7a-145">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="8cc7a-146">编译本示例的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，并部署生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-146">Compiles the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample, and deploys the resulting assembly.</span></span>  
  
    -   <span data-ttu-id="8cc7a-147">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-147">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="8cc7a-148">在创建并绑定端口时，本示例将显示以下警告：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-148">This sample displays the following warnings when creating and binding the ports:</span></span>  
        >   
        >  `Warning: Receive handler not specified for receive location "BTSExpenseReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  <span data-ttu-id="8cc7a-149">`Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-149">`Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`.</span></span>  
        >   
        >  <span data-ttu-id="8cc7a-150">可以安全地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-150">You can safely ignore these warnings.</span></span> <span data-ttu-id="8cc7a-151">（考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="8cc7a-151">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="8cc7a-152">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-152">Enables the receive location, and starts the send port.</span></span>  
  
    -   <span data-ttu-id="8cc7a-153">配置 IIS。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-153">Configures IIS.</span></span>  
  
    -   <span data-ttu-id="8cc7a-154">绑定并启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-154">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
    -   <span data-ttu-id="8cc7a-155">将 HTTP 地址设置为 Excel 电子表格需要的位置。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-155">Sets the HTTP address to the location expected by the Excel spreadsheet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc7a-156">有关 BizTalk ISAPI 筛选器的详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-156">For more information about the BizTalk ISAPI filter, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc7a-157">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-157">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc7a-158">如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须首先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-158">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="8cc7a-159">使用此密钥对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-159">Use this key pair to sign the resulting assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc7a-160">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="8cc7a-161">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
3.  <span data-ttu-id="8cc7a-162">setup.bat 文件将本示例的虚拟目录配置为在与默认网站相关联的 IIS 应用程序池中运行。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-162">The setup.bat file configures the virtual directory for this sample to run in the IIS application pool associated with the default web site.</span></span>  <span data-ttu-id="8cc7a-163">若要配置此示例中的用户的上下文中运行的虚拟目录**BizTalk 独立主机用户**和**IIS_WPG**用户组，你应配置要运行在新的虚拟目录IIS 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-163">To configure the virtual directory for this sample to run under the context of a user in the **BizTalk Isolated Host Users** and **IIS_WPG** user groups, you should configure the virtual directory to run in a new IIS application pool.</span></span>  <span data-ttu-id="8cc7a-164">通过完成以下步骤，可将虚拟目录配置为在新的 IIS 应用程序池中运行：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-164">Configure the virtual directory to run in a new IIS application pool by completing the following steps:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cc7a-165">如果已经为另一个 SDK 示例创建了新的应用程序池，可继续进行以下步骤中的最后一项。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-165">If you have already created a new application pool for another SDK sample then you can proceed to the last bullet item below.</span></span>  
  
    1.  <span data-ttu-id="8cc7a-166">单击**启动**，指向**程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="8cc7a-166">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    2.  <span data-ttu-id="8cc7a-167">在**Internet Information Services (IIS) Manager**，导航到**应用程序池**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-167">In the **Internet Information Services (IIS) Manager**, navigate to the **Application Pools** folder.</span></span>  
  
    3.  <span data-ttu-id="8cc7a-168">右键单击**应用程序池**文件夹，然后单击**新建**，**应用程序池...**</span><span class="sxs-lookup"><span data-stu-id="8cc7a-168">Right-click the **Application Pools** folder and click **New**, **Application Pool...**</span></span>  
  
    4.  <span data-ttu-id="8cc7a-169">输入的名称**应用程序池 ID:** BizTalkSDKSamples，如验证**对新应用程序池使用默认设置**选项已选中，然后单击**确定**到创建新的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-169">Enter a name for the **Application Pool ID:** such as BizTalkSDKSamples, verify that the **Use default settings for new application pool** option is selected and click **OK** to create the new application pool.</span></span>  
  
    5.  <span data-ttu-id="8cc7a-170">右键单击新的应用程序池，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-170">Right-click the new application pool and then click **Properties**.</span></span>  
  
    6.  <span data-ttu-id="8cc7a-171">单击**标识**选项卡的属性对话框框中，并将更改此应用程序池运行是的成员的用户的标识**BizTalk 独立主机用户**用户组。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-171">Click the **Identity** tab of the properties dialog box and change the identity under which this application pool runs to a user that is a member of the **BizTalk Isolated Host Users** user group.</span></span>  <span data-ttu-id="8cc7a-172">此用户还应属于本地**IIS_WPG**用户组。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-172">This user should also be a member of the local **IIS_WPG** user group.</span></span>  
  
    7.  <span data-ttu-id="8cc7a-173">将本 SDK 示例的虚拟目录配置为在新应用程序池下运行。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-173">Configure the virtual directory for this SDK sample to run under the new application pool.</span></span> <span data-ttu-id="8cc7a-174">**应用程序池：**设置位于**虚拟目录**虚拟目录属性对话框中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-174">The **Application pool:** setting is available on the **Virtual Directory** tab of the Virtual Directory properties dialog box.</span></span> <span data-ttu-id="8cc7a-175">为此示例是创建的虚拟目录**ExpenseReportSubmission**。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-175">The virtual directory created for this sample is **ExpenseReportSubmission**.</span></span>  
  
4.  <span data-ttu-id="8cc7a-176">在 IIS 中为 HTTPReceive.dll 添加一个 Web 服务扩展</span><span class="sxs-lookup"><span data-stu-id="8cc7a-176">Add a web service extension to IIS for HTTPReceive.dll</span></span>  
  
    1.  <span data-ttu-id="8cc7a-177">在**Internet Information Services (IIS) Manager**，导航到**Web 服务扩展**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-177">In the **Internet Information Services (IIS) Manager**, navigate to the **Web Service Extensions** folder.</span></span>  
  
    2.  <span data-ttu-id="8cc7a-178">右键单击**Web 服务扩展**文件夹，然后选择**添加一个新的 Web 服务扩展**以显示**新建 Web 服务扩展**对话框。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-178">Right-click the **Web Service Extensions** folder and select **Add a new Web service extension** to display the **New Web Service Extension** dialog box.</span></span>  
  
    3.  <span data-ttu-id="8cc7a-179">输入**ExpenseReportSubmission**为**扩展名：**</span><span class="sxs-lookup"><span data-stu-id="8cc7a-179">Enter **ExpenseReportSubmission** for **Extension name:**</span></span>  
  
    4.  <span data-ttu-id="8cc7a-180">单击**添加**以显示**Add file**对话框。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-180">Click **Add** to display the **Add file** dialog box.</span></span>  
  
    5.  <span data-ttu-id="8cc7a-181">单击**浏览**以显示**打开**对话框框中，并导航到 *\<BizTalk Server 安装文件夹 >*\HttpReceive\BTSHTTPReceive.dll 和单击**打开**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-181">Click **Browse** to display the **Open** dialog box and navigate to *\<BizTalk Server Installation folder>*\HttpReceive\BTSHTTPReceive.dll and click **Open**, then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="8cc7a-182">启用到选项**设置扩展状态为允许**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-182">Enable the option to **Set extension status to Allowed** and click **OK**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="8cc7a-183">运行本示例</span><span class="sxs-lookup"><span data-stu-id="8cc7a-183">Running This Sample</span></span>  
 <span data-ttu-id="8cc7a-184">使用以下过程运行 ExpenseReportSubmission 示例。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-184">Use the following procedure to run the ExpenseReportSubmission sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cc7a-185">如果使用的是 Microsoft Excel 的增强安全功能，则电子表格中的宏可能会被禁用。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-185">If you are using the enhanced security features of Microsoft Excel, the macros in the spreadsheet may be disabled.</span></span> <span data-ttu-id="8cc7a-186">请遵循 Excel 提供的有关如何运行来自受信任来源的未签名宏的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-186">Follow the instructions provided by Excel about how to run unsigned macros from a trusted source.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="8cc7a-187">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="8cc7a-187">To run this sample</span></span>  
  
1.  <span data-ttu-id="8cc7a-188">打开本示例附带的 Excel 文件 ExpenseReport.15.3.xls。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-188">Open the Excel file ExpenseReport.15.3.xls included with this sample.</span></span>  
  
2.  <span data-ttu-id="8cc7a-189">（可选）更改电子表格中的示例数据但是不更改其格式。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-189">Optionally, change the sample data in the spreadsheet without changing its format.</span></span>  
  
3.  <span data-ttu-id="8cc7a-190">在电子表格中，单击**启动**来执行本地计算。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-190">In the spreadsheet, click **Start** to perform local calculations.</span></span>  
  
     <span data-ttu-id="8cc7a-191">从按钮的文本更改**启动**到**提交**。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-191">The text of the button changes from **Start** to **Submit**.</span></span>  
  
4.  <span data-ttu-id="8cc7a-192">在电子表格中，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-192">In the spreadsheet, click **Submit**.</span></span>  
  
5.  <span data-ttu-id="8cc7a-193">观察所提交消息的文本、黄色背景的表（单元格 C7）上方的结果以及下方和右侧（单元格 G23）的实际返回代码和文本说明。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-193">Observe the text of the submitted message, the result above the table with yellow background (cell C7), and the actual return code and text description below and to the right (cell G23).</span></span>  
  
     <span data-ttu-id="8cc7a-194">如果提交失败，请重试。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-194">If submission fails, try again.</span></span> <span data-ttu-id="8cc7a-195">另请参阅“注释”部分中的故障排除表。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-195">Also, refer to the troubleshooting table in the Comments section.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="8cc7a-196">注释</span><span class="sxs-lookup"><span data-stu-id="8cc7a-196">Comments</span></span>  
 <span data-ttu-id="8cc7a-197">这种情况是可能发生的，例如，某位现场销售人员配有不支持 .NET Framework 的 Microsoft Windows 早期版本，并且升级到较新版本的 Windows 也不可行。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-197">Scenarios such as this can occur when, for example, a field sales force is equipped with older versions of Microsoft Windows that do not support the .NET Framework, and for which the requirement to upgrade to a more current version of Windows is not a viable option.</span></span>  
  
 <span data-ttu-id="8cc7a-198">本示例中演示的重要功能包括：</span><span class="sxs-lookup"><span data-stu-id="8cc7a-198">Essential features demonstrated in this sample are:</span></span>  
  
-   <span data-ttu-id="8cc7a-199">从胖客户端（不基于 .NET）进行提交</span><span class="sxs-lookup"><span data-stu-id="8cc7a-199">Submission from a rich client (not .NET-based)</span></span>  
  
-   <span data-ttu-id="8cc7a-200">Microsoft Office 集成</span><span class="sxs-lookup"><span data-stu-id="8cc7a-200">Microsoft Office integration</span></span>  
  
-   <span data-ttu-id="8cc7a-201">HTTP 接收连接</span><span class="sxs-lookup"><span data-stu-id="8cc7a-201">HTTP receive connections</span></span>  
  
-   <span data-ttu-id="8cc7a-202">简单业务流程</span><span class="sxs-lookup"><span data-stu-id="8cc7a-202">Simple orchestration</span></span>  
  
-   <span data-ttu-id="8cc7a-203">文件适配器</span><span class="sxs-lookup"><span data-stu-id="8cc7a-203">File adapter</span></span>  
  
 <span data-ttu-id="8cc7a-204">下表显示了一些可能的提交错误及其解决方案。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-204">The following table shows some possible submission errors and their solutions.</span></span>  
  
|<span data-ttu-id="8cc7a-205">HTTP 错误代码</span><span class="sxs-lookup"><span data-stu-id="8cc7a-205">HTTP error code</span></span>|<span data-ttu-id="8cc7a-206">可能的操作</span><span class="sxs-lookup"><span data-stu-id="8cc7a-206">Possible action</span></span>|  
|---------------------|---------------------|  
|<span data-ttu-id="8cc7a-207">401 未经授权</span><span class="sxs-lookup"><span data-stu-id="8cc7a-207">401 Unauthorized</span></span>|<span data-ttu-id="8cc7a-208">在虚拟目录上启用匿名访问。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-208">Enable anonymous access on the virtual directory.</span></span>|  
|<span data-ttu-id="8cc7a-209">503 服务不可用，以及大多数介于 400 和 500 之间的其他 HTTP 代码</span><span class="sxs-lookup"><span data-stu-id="8cc7a-209">503 Service Unavailable, and most other HTTP codes in the 400 and 500 ranges</span></span>|<span data-ttu-id="8cc7a-210">确保主机运行，并将服务部署、绑定到正确的端口并启动。</span><span class="sxs-lookup"><span data-stu-id="8cc7a-210">Ensure that the host runs and that the service is deployed, bound to the correct port, and started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cc7a-211">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cc7a-211">See Also</span></span>  
 [<span data-ttu-id="8cc7a-212">适配器示例-使用情况</span><span class="sxs-lookup"><span data-stu-id="8cc7a-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)