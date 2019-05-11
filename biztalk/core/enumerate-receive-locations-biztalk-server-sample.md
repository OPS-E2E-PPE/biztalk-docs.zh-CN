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
ms.openlocfilehash: 7941cffb7e796c02b84c2dbd686fa20edbe9c8df
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530766"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a><span data-ttu-id="d5983-102">枚举接收位置 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d5983-102">Enumerate Receive Locations (BizTalk Server Sample)</span></span>
<span data-ttu-id="d5983-103">枚举接收位置示例演示如何检索有关一个详细信息或多个接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5983-103">The Enumerate Receive Locations sample demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d5983-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="d5983-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="d5983-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="d5983-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d5983-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="d5983-106">What This Sample Does</span></span>  
 <span data-ttu-id="d5983-107">此示例包含用于访问 Windows WMI 对象模型中，Visual Basic Scripting Edition (VBScript) 版本和用于访问的 Visual C# 版本**System.Management**由.NET Framework 提供的对象。</span><span class="sxs-lookup"><span data-stu-id="d5983-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows WMI object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="d5983-108">这两个版本最终会访问 BizTalk Server WMI 提供程序，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d5983-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="d5983-109">查询的一套配置接收位置或某一特定接收位置，在给定其名称。</span><span class="sxs-lookup"><span data-stu-id="d5983-109">Query for the set of configured receive locations or for a specific receive location, given its name.</span></span>  
  
-   <span data-ttu-id="d5983-110">检索和显示详细信息，有关每个接收位置所需。</span><span class="sxs-lookup"><span data-stu-id="d5983-110">Retrieve and display details about each receive location of interest.</span></span>  
  
-   <span data-ttu-id="d5983-111">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="d5983-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d5983-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="d5983-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="d5983-113">这些示例位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="d5983-113">The samples are located in the following SDK locations:</span></span>  
  
- <span data-ttu-id="d5983-114">VBScript 版本：\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="d5983-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
- <span data-ttu-id="d5983-115">VisualC#版本：\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="d5983-115">Visual C# version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span></span>  
  
  <span data-ttu-id="d5983-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="d5983-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="d5983-117">文件</span><span class="sxs-lookup"><span data-stu-id="d5983-117">File(s)</span></span>|<span data-ttu-id="d5983-118">Description</span><span class="sxs-lookup"><span data-stu-id="d5983-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5983-119">\VBScript 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="d5983-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="d5983-120">EnumRecLocs.vbs</span><span class="sxs-lookup"><span data-stu-id="d5983-120">EnumRecLocs.vbs</span></span>|<span data-ttu-id="d5983-121">检索有关所有已配置的详细信息的 VBScript 文件接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5983-121">VBScript file that retrieves details about all configured receive locations.</span></span>|  
|<span data-ttu-id="d5983-122">\CSharp 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="d5983-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="d5983-123">App.ico、 AssemblyInfo.cs、 BTSampleEnumerateRLs.csproj、 BTSampleEnumerateRLs.sln 和 EnumRLs.cs</span><span class="sxs-lookup"><span data-stu-id="d5983-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span></span>|<span data-ttu-id="d5983-124">项目、 解决方案和源文件构建的 Visual C# 命令行应用程序检索有关所有已配置的详细信息的接收位置，或有关特定接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5983-124">Project, solution, and source files for building a Visual C# command-line application that retrieves details about all configured receive locations, or about a specific receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="d5983-125">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="d5983-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="d5983-126">枚举接收位置示例的 VBScript 版本包括不需要生成或初始化的单一 Visual Basic 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="d5983-126">The VBScript version of the Enumerate Receive Locations sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a><span data-ttu-id="d5983-127">若要生成的枚举接收位置示例的 Visual C# 版本</span><span class="sxs-lookup"><span data-stu-id="d5983-127">To build the Visual C# version of the Enumerate Receive Locations sample</span></span>  
  
1. <span data-ttu-id="d5983-128">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 BTSampleEnumerateRLs.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d5983-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnumerateRLs.sln.</span></span>  
  
2. <span data-ttu-id="d5983-129">在中**构建**菜单上，单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="d5983-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="d5983-130">运行本示例</span><span class="sxs-lookup"><span data-stu-id="d5983-130">Running This Sample</span></span>  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a><span data-ttu-id="d5983-131">若要运行枚举接收位置示例</span><span class="sxs-lookup"><span data-stu-id="d5983-131">To run the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="d5983-132">在命令窗口中，导航到以下文件夹中，具体取决于是否要运行的 VBScript 版本还是 Visual C# 版本的此示例中，分别之一：</span><span class="sxs-lookup"><span data-stu-id="d5983-132">In a command window, navigate to one of the following folders, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="d5983-133">\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="d5983-133">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
     <span data-ttu-id="d5983-134">\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="d5983-134">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="d5983-135">运行文件使用 cscript 程序的哪一个，或运行文件 EnumRl.exe，具体取决于是否要运行的 VBScript 版本还是 Visual C# 版本的此示例中，分别。</span><span class="sxs-lookup"><span data-stu-id="d5983-135">Either run the file EnumRecLocs.vbs using the cscript program, or run the file EnumRl.exe, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="d5983-136">对于 Visual C# 版本中，传递下列两个命令行参数之一：</span><span class="sxs-lookup"><span data-stu-id="d5983-136">For the Visual C# version, pass one of the following two command-line arguments:</span></span>  
  
    -   <span data-ttu-id="d5983-137">**\<ReceiveLocationName\>。**</span><span class="sxs-lookup"><span data-stu-id="d5983-137">**\<ReceiveLocationName\>.**</span></span> <span data-ttu-id="d5983-138">将显示其详细信息的接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="d5983-138">The name of the receive location for which details will be displayed.</span></span> <span data-ttu-id="d5983-139">如果接收位置名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="d5983-139">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="d5983-140">**/?.**</span><span class="sxs-lookup"><span data-stu-id="d5983-140">**/?.**</span></span> <span data-ttu-id="d5983-141">显示帮助。</span><span class="sxs-lookup"><span data-stu-id="d5983-141">Displays help.</span></span>  
  
         <span data-ttu-id="d5983-142">对于示例 (VBScript):</span><span class="sxs-lookup"><span data-stu-id="d5983-142">For example (VBScript):</span></span>  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         <span data-ttu-id="d5983-143">-或者-(Visual C#):</span><span class="sxs-lookup"><span data-stu-id="d5983-143">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         <span data-ttu-id="d5983-144">-或者-(Visual C#):</span><span class="sxs-lookup"><span data-stu-id="d5983-144">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d5983-145">此示例的 VBScript 版本不接受任何命令行参数，因此仅检索和显示详细信息，有关配置的所有接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5983-145">The VBScript version of this sample does not accept any command-line parameters, and therefore is only capable of retrieving and displaying details about all configured receive locations.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d5983-146">注释</span><span class="sxs-lookup"><span data-stu-id="d5983-146">Comments</span></span>  
 <span data-ttu-id="d5983-147">可以在中执行的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用访问 Windows WMI 对象模型的脚本，并通过使用 Visual C# 访问，也可以执行管理控制台**System.Management**提供对象由.NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="d5983-147">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="d5983-148">哪一个的脚本文件和 Visual C# 源代码文件 EnumRLs.cs 包含详细的注释了进一步说明他们执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d5983-148">The script file EnumRecLocs.vbs and the Visual C# source file EnumRLs.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="d5983-149">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="d5983-149">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5983-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5983-150">See Also</span></span>  
 [<span data-ttu-id="d5983-151">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="d5983-151">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)