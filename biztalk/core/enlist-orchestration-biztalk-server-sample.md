---
title: "登记业务流程 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, enlisting
- examples, orchestrations
ms.assetid: d8d53e59-2313-40dd-a278-0a29d8eb4ce8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e8d85a49b410f0571e8e9cb0be816f1feda139e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="enlist-orchestration-biztalk-server-sample"></a><span data-ttu-id="e4bce-102">登记业务流程 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e4bce-102">Enlist Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="e4bce-103">“登记业务流程”示例演示如何将 BizTalk Server 业务流程登记到主机。</span><span class="sxs-lookup"><span data-stu-id="e4bce-103">The Enlist Orchestration sample demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e4bce-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="e4bce-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="e4bce-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="e4bce-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e4bce-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="e4bce-106">What This Sample Does</span></span>  
 <span data-ttu-id="e4bce-107">此示例包括访问 Windows Management Instrumentation (WMI) 对象模型，Visual Basic Scripting Edition (VBScript) 版本和 Visual C# 版本访问**System.Management**由提供的对象.NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="e4bce-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows Management Instrumentation (WMI) object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="e4bce-108">上述两个版本最终会访问 BizTalk Server WMI 提供程序，以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e4bce-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="e4bce-109">根据给定的业务流程名称和程序集名称，查询部署的特定 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4bce-109">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="e4bce-110">将此业务流程登记到默认主机。</span><span class="sxs-lookup"><span data-stu-id="e4bce-110">Enlist that orchestration to the default host.</span></span>  
  
-   <span data-ttu-id="e4bce-111">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="e4bce-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e4bce-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="e4bce-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="e4bce-113">本示例位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="e4bce-113">The samples are located in the following SDK locations:</span></span>  
  
-   <span data-ttu-id="e4bce-114">VBScript 版本： \<*示例路径*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="e4bce-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
-   <span data-ttu-id="e4bce-115">Visusal C# 版本： \<*示例路径*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="e4bce-115">Visusal C# version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span></span>  
  
 <span data-ttu-id="e4bce-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="e4bce-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e4bce-117">文件</span><span class="sxs-lookup"><span data-stu-id="e4bce-117">File(s)</span></span>|<span data-ttu-id="e4bce-118">Description</span><span class="sxs-lookup"><span data-stu-id="e4bce-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4bce-119">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="e4bce-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="e4bce-120">EnlistOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="e4bce-120">EnlistOrch.vbs</span></span>|<span data-ttu-id="e4bce-121">采用参数指定要登记到主机的业务流程的 VBScript 文件。</span><span class="sxs-lookup"><span data-stu-id="e4bce-121">VBScript file that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
|<span data-ttu-id="e4bce-122">\CSharp 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="e4bce-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="e4bce-123">App.ico、AssemblyInfo.cs、BTSampleEnlistOrc.csproj、BTSampleEnlistOrc.sln 和 EnlistOrc.cs</span><span class="sxs-lookup"><span data-stu-id="e4bce-123">App.ico, AssemblyInfo.cs, BTSampleEnlistOrc.csproj, BTSampleEnlistOrc.sln, EnlistOrc.cs</span></span>|<span data-ttu-id="e4bce-124">用于生成 Visual C# 命令行应用程序的项目、解决方案和源文件，该应用程序采用参数指定要登记到主机的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4bce-124">Project, solution, and source files for building a Visual C# command-line application that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e4bce-125">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="e4bce-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="e4bce-126">“登记业务流程”示例的 VBScript 版本包括一个 Visual Basic 脚本文件，您无需生成或初始化该脚本文件。</span><span class="sxs-lookup"><span data-stu-id="e4bce-126">The VBScript version of the Enlist Orchestration sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a><span data-ttu-id="e4bce-127">生成“登记业务流程”示例的 Visual C# 版本</span><span class="sxs-lookup"><span data-stu-id="e4bce-127">To build the Visual C# version of the Enlist Orchestration sample</span></span>  
  
1.  <span data-ttu-id="e4bce-128">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 BTSampleEnlistOrc.sln。</span><span class="sxs-lookup"><span data-stu-id="e4bce-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnlistOrc.sln.</span></span>  
  
2.  <span data-ttu-id="e4bce-129">在**生成**菜单上，单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="e4bce-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a><span data-ttu-id="e4bce-130">运行登记业务流程示例</span><span class="sxs-lookup"><span data-stu-id="e4bce-130">To run the Enlist Orchestration sample.</span></span>  
  
1.  <span data-ttu-id="e4bce-131">在命令窗口中，导航至下列文件夹之一，具体哪一个文件夹取决于您打算运行本示例的 VBScript 版本还是 Visual C# 版本：</span><span class="sxs-lookup"><span data-stu-id="e4bce-131">In a command window, navigate to one of the following folders, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="e4bce-132">\<*示例路径*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="e4bce-132">\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
     <span data-ttu-id="e4bce-133">\<*示例路径*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span><span class="sxs-lookup"><span data-stu-id="e4bce-133">\<*Samples Path*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span></span>  
  
2.  <span data-ttu-id="e4bce-134">使用 cscript 程序运行 EnlistOrch.vbs 文件，或者运行 EnlistOrc.exe 文件，具体要运行哪一个文件取决于您打算运行本示例的 VBScript 版本还是 Visual C# 版本。</span><span class="sxs-lookup"><span data-stu-id="e4bce-134">Either run the file EnlistOrch.vbs using the cscript program, or run the file EnlistOrc.exe, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="e4bce-135">在任何事件中，传递以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="e4bce-135">In any event, pass the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="e4bce-136">**\<** ***OrchestrationName* \>。**</span><span class="sxs-lookup"><span data-stu-id="e4bce-136">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="e4bce-137">要登记的业务流程的名称。</span><span class="sxs-lookup"><span data-stu-id="e4bce-137">The name of the orchestration to be enlisted.</span></span>  
  
    -   <span data-ttu-id="e4bce-138">**\<** ***AssemblyName* \>。**</span><span class="sxs-lookup"><span data-stu-id="e4bce-138">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="e4bce-139">在其中部署业务流程的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="e4bce-139">The name of the assembly in which the orchestration was deployed.</span></span> <span data-ttu-id="e4bce-140">如果程序集名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="e4bce-140">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="e4bce-141">例如: (VBScript):</span><span class="sxs-lookup"><span data-stu-id="e4bce-141">For example: (VBScript):</span></span>  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="e4bce-142">- 或者 - (Visual C#)：</span><span class="sxs-lookup"><span data-stu-id="e4bce-142">-OR- (Visual C#):</span></span>  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a><span data-ttu-id="e4bce-143">注释</span><span class="sxs-lookup"><span data-stu-id="e4bce-143">Comments</span></span>  
 <span data-ttu-id="e4bce-144">你可以执行中的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用访问 Windows WMI 对象模型的脚本以及通过使用 Visual C# 访问，还可以执行管理控制台**System.Management**提供的对象.NET framework 中。</span><span class="sxs-lookup"><span data-stu-id="e4bce-144">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="e4bce-145">EnlistOrch.vbs 脚本文件和 Visual C# 源文件 EnlistOrc.cs 包含详细注释，对其执行的操作做了进一步说明。</span><span class="sxs-lookup"><span data-stu-id="e4bce-145">The script file EnlistOrch.vbs and the Visual C# source file EnlistOrc.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="e4bce-146">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="e4bce-146">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4bce-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4bce-147">See Also</span></span>  
 [<span data-ttu-id="e4bce-148">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="e4bce-148">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)