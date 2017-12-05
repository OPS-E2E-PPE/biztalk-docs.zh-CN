---
title: "枚举接收位置 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fcdc400395d7bbfd6de8f9bc0fca85114a25dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a><span data-ttu-id="df747-102">枚举接收位置 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="df747-102">Enumerate Receive Locations (BizTalk Server Sample)</span></span>
<span data-ttu-id="df747-103">“枚举接收位置”示例演示了如何检索有关一个或多个接收位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df747-103">The Enumerate Receive Locations sample demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="df747-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="df747-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="df747-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="df747-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="df747-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="df747-106">What This Sample Does</span></span>  
 <span data-ttu-id="df747-107">此示例包括访问 Windows WMI 对象模型，Visual Basic Scripting Edition (VBScript) 版本和 Visual C# 版本访问**System.Management**由.NET Framework 提供的对象。</span><span class="sxs-lookup"><span data-stu-id="df747-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows WMI object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="df747-108">上述两个版本最终会访问 BizTalk Server WMI 提供程序，以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="df747-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="df747-109">在已知名称的情况下，查询配置的接收位置集或某一特定接收位置。</span><span class="sxs-lookup"><span data-stu-id="df747-109">Query for the set of configured receive locations or for a specific receive location, given its name.</span></span>  
  
-   <span data-ttu-id="df747-110">检索和显示每个相关接收位置的有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="df747-110">Retrieve and display details about each receive location of interest.</span></span>  
  
-   <span data-ttu-id="df747-111">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="df747-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="df747-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="df747-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="df747-113">本示例位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="df747-113">The samples are located in the following SDK locations:</span></span>  
  
-   <span data-ttu-id="df747-114">VBScript 版本： \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="df747-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
-   <span data-ttu-id="df747-115">Visual C# 版本： \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="df747-115">Visual C# version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span></span>  
  
 <span data-ttu-id="df747-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="df747-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="df747-117">文件</span><span class="sxs-lookup"><span data-stu-id="df747-117">File(s)</span></span>|<span data-ttu-id="df747-118">Description</span><span class="sxs-lookup"><span data-stu-id="df747-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df747-119">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="df747-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="df747-120">EnumRecLocs.vbs</span><span class="sxs-lookup"><span data-stu-id="df747-120">EnumRecLocs.vbs</span></span>|<span data-ttu-id="df747-121">用于检索有关配置的所有接收位置的详细信息的 VBScript 文件。</span><span class="sxs-lookup"><span data-stu-id="df747-121">VBScript file that retrieves details about all configured receive locations.</span></span>|  
|<span data-ttu-id="df747-122">\CSharp 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="df747-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="df747-123">App.ico、AssemblyInfo.cs、BTSampleEnumerateRLs.csproj、BTSampleEnumerateRLs.sln 和 EnumRLs.cs</span><span class="sxs-lookup"><span data-stu-id="df747-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span></span>|<span data-ttu-id="df747-124">用于生成 Visual C# 命令行应用程序的项目、解决方案和源文件，该应用程序检索有关配置的所有接收位置或某一特定接收位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df747-124">Project, solution, and source files for building a Visual C# command-line application that retrieves details about all configured receive locations, or about a specific receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="df747-125">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="df747-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="df747-126">“枚举接收位置”示例的 VBScript 版本包括一个 Visual Basic 脚本文件，您无需生成或初始化该脚本文件。</span><span class="sxs-lookup"><span data-stu-id="df747-126">The VBScript version of the Enumerate Receive Locations sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a><span data-ttu-id="df747-127">生成“枚举接收位置”示例的 Visual C# 版本</span><span class="sxs-lookup"><span data-stu-id="df747-127">To build the Visual C# version of the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="df747-128">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 BTSampleEnumerateRLs.sln。</span><span class="sxs-lookup"><span data-stu-id="df747-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnumerateRLs.sln.</span></span>  
  
2.  <span data-ttu-id="df747-129">在**生成**菜单上，单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="df747-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="df747-130">运行本示例</span><span class="sxs-lookup"><span data-stu-id="df747-130">Running This Sample</span></span>  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a><span data-ttu-id="df747-131">运行“枚举接收位置”示例</span><span class="sxs-lookup"><span data-stu-id="df747-131">To run the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="df747-132">在命令窗口中，导航至下列文件夹之一，具体哪一个文件夹取决于您是要运行本示例的 VBScript 版本还是 Visual C# 版本：</span><span class="sxs-lookup"><span data-stu-id="df747-132">In a command window, navigate to one of the following folders, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="df747-133">\<*示例路径*\>\Admin\WMI\Enumerate 接收 Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="df747-133">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
     <span data-ttu-id="df747-134">\<*示例路径*\>\Admin\WMI\Enumerate 接收 Locations\CSharp\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="df747-134">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="df747-135">使用 cscript 程序运行 EnumRecLocs.vbs 文件，或者运行 EnumRl.exe 文件，具体要运行哪一个文件取决于您是要运行本示例的 VBScript 版本还是 Visual C# 版本。</span><span class="sxs-lookup"><span data-stu-id="df747-135">Either run the file EnumRecLocs.vbs using the cscript program, or run the file EnumRl.exe, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="df747-136">对于 Visual C# 版本，请传递下列两个命令行参数之一：</span><span class="sxs-lookup"><span data-stu-id="df747-136">For the Visual C# version, pass one of the following two command-line arguments:</span></span>  
  
    -   <span data-ttu-id="df747-137">**\<ReceiveLocationName\>。**</span><span class="sxs-lookup"><span data-stu-id="df747-137">**\<ReceiveLocationName\>.**</span></span> <span data-ttu-id="df747-138">将显示其详细信息的接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="df747-138">The name of the receive location for which details will be displayed.</span></span> <span data-ttu-id="df747-139">如果接收位置名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="df747-139">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="df747-140">**/?.**</span><span class="sxs-lookup"><span data-stu-id="df747-140">**/?.**</span></span> <span data-ttu-id="df747-141">显示帮助。</span><span class="sxs-lookup"><span data-stu-id="df747-141">Displays help.</span></span>  
  
         <span data-ttu-id="df747-142">例如 (VBScript)：</span><span class="sxs-lookup"><span data-stu-id="df747-142">For example (VBScript):</span></span>  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         <span data-ttu-id="df747-143">- 或者 - (Visual C#)：</span><span class="sxs-lookup"><span data-stu-id="df747-143">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         <span data-ttu-id="df747-144">- 或者 - (Visual C#)：</span><span class="sxs-lookup"><span data-stu-id="df747-144">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="df747-145">此示例的 VBScript 版本不接受任何命令行参数，并因此才能够检索和显示有关所有配置的详细信息接收位置。</span><span class="sxs-lookup"><span data-stu-id="df747-145">The VBScript version of this sample does not accept any command-line parameters, and therefore is only capable of retrieving and displaying details about all configured receive locations.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="df747-146">注释</span><span class="sxs-lookup"><span data-stu-id="df747-146">Comments</span></span>  
 <span data-ttu-id="df747-147">你可以执行中的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用访问 Windows WMI 对象模型的脚本以及通过使用 Visual C# 访问，还可以执行管理控制台**System.Management**提供的对象.NET framework 中。</span><span class="sxs-lookup"><span data-stu-id="df747-147">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="df747-148">脚本文件 EnumRecLocs.vbs 和 Visual C# 源文件 EnumRLs.cs 包含详细的注释，使用更多有关他们执行的操作的说明。</span><span class="sxs-lookup"><span data-stu-id="df747-148">The script file EnumRecLocs.vbs and the Visual C# source file EnumRLs.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="df747-149">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="df747-149">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df747-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df747-150">See Also</span></span>  
 [<span data-ttu-id="df747-151">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="df747-151">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)