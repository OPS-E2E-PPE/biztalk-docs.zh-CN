---
title: 枚举接收位置 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f92e279ce53f068657e46912eb93093728e3185
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021252"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a><span data-ttu-id="5c149-102">枚举接收位置 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="5c149-102">Enumerate Receive Locations (BizTalk Server Sample)</span></span>
<span data-ttu-id="5c149-103">“枚举接收位置”示例演示了如何检索有关一个或多个接收位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c149-103">The Enumerate Receive Locations sample demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5c149-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="5c149-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="5c149-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="5c149-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5c149-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="5c149-106">What This Sample Does</span></span>  
 <span data-ttu-id="5c149-107">此示例包含用于访问 Windows WMI 对象模型中，Visual Basic Scripting Edition (VBScript) 版本和用于访问的 Visual C# 版本**System.Management**由.NET Framework 提供的对象。</span><span class="sxs-lookup"><span data-stu-id="5c149-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows WMI object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="5c149-108">上述两个版本最终会访问 BizTalk Server WMI 提供程序，以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5c149-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="5c149-109">在已知名称的情况下，查询配置的接收位置集或某一特定接收位置。</span><span class="sxs-lookup"><span data-stu-id="5c149-109">Query for the set of configured receive locations or for a specific receive location, given its name.</span></span>  
  
-   <span data-ttu-id="5c149-110">检索和显示每个相关接收位置的有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c149-110">Retrieve and display details about each receive location of interest.</span></span>  
  
-   <span data-ttu-id="5c149-111">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="5c149-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5c149-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="5c149-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="5c149-113">本示例位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="5c149-113">The samples are located in the following SDK locations:</span></span>  
  
- <span data-ttu-id="5c149-114">VBScript 版本： \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="5c149-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
- <span data-ttu-id="5c149-115">Visual C# 版本： \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="5c149-115">Visual C# version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span></span>  
  
  <span data-ttu-id="5c149-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="5c149-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5c149-117">文件</span><span class="sxs-lookup"><span data-stu-id="5c149-117">File(s)</span></span>|<span data-ttu-id="5c149-118">Description</span><span class="sxs-lookup"><span data-stu-id="5c149-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c149-119">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="5c149-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="5c149-120">EnumRecLocs.vbs</span><span class="sxs-lookup"><span data-stu-id="5c149-120">EnumRecLocs.vbs</span></span>|<span data-ttu-id="5c149-121">用于检索有关配置的所有接收位置的详细信息的 VBScript 文件。</span><span class="sxs-lookup"><span data-stu-id="5c149-121">VBScript file that retrieves details about all configured receive locations.</span></span>|  
|<span data-ttu-id="5c149-122">\CSharp 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="5c149-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="5c149-123">App.ico、AssemblyInfo.cs、BTSampleEnumerateRLs.csproj、BTSampleEnumerateRLs.sln 和 EnumRLs.cs</span><span class="sxs-lookup"><span data-stu-id="5c149-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span></span>|<span data-ttu-id="5c149-124">用于生成 Visual C# 命令行应用程序的项目、解决方案和源文件，该应用程序检索有关配置的所有接收位置或某一特定接收位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c149-124">Project, solution, and source files for building a Visual C# command-line application that retrieves details about all configured receive locations, or about a specific receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="5c149-125">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="5c149-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="5c149-126">“枚举接收位置”示例的 VBScript 版本包括一个 Visual Basic 脚本文件，您无需生成或初始化该脚本文件。</span><span class="sxs-lookup"><span data-stu-id="5c149-126">The VBScript version of the Enumerate Receive Locations sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a><span data-ttu-id="5c149-127">生成“枚举接收位置”示例的 Visual C# 版本</span><span class="sxs-lookup"><span data-stu-id="5c149-127">To build the Visual C# version of the Enumerate Receive Locations sample</span></span>  
  
1. <span data-ttu-id="5c149-128">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 BTSampleEnumerateRLs.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5c149-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnumerateRLs.sln.</span></span>  
  
2. <span data-ttu-id="5c149-129">在中**构建**菜单上，单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="5c149-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="5c149-130">运行本示例</span><span class="sxs-lookup"><span data-stu-id="5c149-130">Running This Sample</span></span>  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a><span data-ttu-id="5c149-131">运行“枚举接收位置”示例</span><span class="sxs-lookup"><span data-stu-id="5c149-131">To run the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="5c149-132">在命令窗口中，导航至下列文件夹之一，具体哪一个文件夹取决于您是要运行本示例的 VBScript 版本还是 Visual C# 版本：</span><span class="sxs-lookup"><span data-stu-id="5c149-132">In a command window, navigate to one of the following folders, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="5c149-133">\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="5c149-133">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
     <span data-ttu-id="5c149-134">\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="5c149-134">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="5c149-135">使用 cscript 程序运行 EnumRecLocs.vbs 文件，或者运行 EnumRl.exe 文件，具体要运行哪一个文件取决于您是要运行本示例的 VBScript 版本还是 Visual C# 版本。</span><span class="sxs-lookup"><span data-stu-id="5c149-135">Either run the file EnumRecLocs.vbs using the cscript program, or run the file EnumRl.exe, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="5c149-136">对于 Visual C# 版本，请传递下列两个命令行参数之一：</span><span class="sxs-lookup"><span data-stu-id="5c149-136">For the Visual C# version, pass one of the following two command-line arguments:</span></span>  
  
    -   <span data-ttu-id="5c149-137">**\<ReceiveLocationName\>。**</span><span class="sxs-lookup"><span data-stu-id="5c149-137">**\<ReceiveLocationName\>.**</span></span> <span data-ttu-id="5c149-138">将显示其详细信息的接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="5c149-138">The name of the receive location for which details will be displayed.</span></span> <span data-ttu-id="5c149-139">如果接收位置名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="5c149-139">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="5c149-140">**/?.**</span><span class="sxs-lookup"><span data-stu-id="5c149-140">**/?.**</span></span> <span data-ttu-id="5c149-141">显示帮助。</span><span class="sxs-lookup"><span data-stu-id="5c149-141">Displays help.</span></span>  
  
         <span data-ttu-id="5c149-142">例如 (VBScript)：</span><span class="sxs-lookup"><span data-stu-id="5c149-142">For example (VBScript):</span></span>  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         <span data-ttu-id="5c149-143">- 或者 - (Visual C#)：</span><span class="sxs-lookup"><span data-stu-id="5c149-143">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         <span data-ttu-id="5c149-144">- 或者 - (Visual C#)：</span><span class="sxs-lookup"><span data-stu-id="5c149-144">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5c149-145">此示例的 VBScript 版本不接受任何命令行参数，因此仅检索和显示详细信息，有关配置的所有接收位置。</span><span class="sxs-lookup"><span data-stu-id="5c149-145">The VBScript version of this sample does not accept any command-line parameters, and therefore is only capable of retrieving and displaying details about all configured receive locations.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="5c149-146">注释</span><span class="sxs-lookup"><span data-stu-id="5c149-146">Comments</span></span>  
 <span data-ttu-id="5c149-147">可以在中执行的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用访问 Windows WMI 对象模型的脚本，并通过使用 Visual C# 访问，也可以执行管理控制台**System.Management**提供对象由.NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="5c149-147">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="5c149-148">哪一个的脚本文件和 Visual C# 源代码文件 EnumRLs.cs 包含详细的注释了进一步说明他们执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5c149-148">The script file EnumRecLocs.vbs and the Visual C# source file EnumRLs.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="5c149-149">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="5c149-149">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c149-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c149-150">See Also</span></span>  
 [<span data-ttu-id="5c149-151">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="5c149-151">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)