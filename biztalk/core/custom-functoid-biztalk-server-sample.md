---
title: 自定义 Functoid （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de71eb45faa6c5705cca2ef47061686608126577
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013381"
---
# <a name="custom-functoid-biztalk-server-sample"></a><span data-ttu-id="2cc44-102">自定义 Functoid （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="2cc44-102">Custom Functoid (BizTalk Server Sample)</span></span>
<span data-ttu-id="2cc44-103">自定义 functoid 示例演示如何为 BizTalk 映射器编写自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="2cc44-103">The Custom Functoid sample demonstrates how to write a custom functoid for BizTalk Mapper.</span></span> <span data-ttu-id="2cc44-104">你可以向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加此 functoid。</span><span class="sxs-lookup"><span data-stu-id="2cc44-104">You can add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="2cc44-105">当 BizTalk 映射器获得焦点时，该 functoid 将显示在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="2cc44-105">The functoid will be displayed in the Toolbox when BizTalk Mapper is in focus.</span></span>  
  
 <span data-ttu-id="2cc44-106">自定义 functoid 应位于 BizTalk 映射器程序集中以便识别。</span><span class="sxs-lookup"><span data-stu-id="2cc44-106">A custom functoid should reside in a BizTalk Mapper assembly to recognize it.</span></span> <span data-ttu-id="2cc44-107">它可以使用任何一种符合 .NET 的语言进行编写，例如 C# 或 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="2cc44-107">It can be written in any .NET-compliant language, such as C# or Visual Basic.</span></span>  
  
 <span data-ttu-id="2cc44-108">此外，自定义 functoid 必须派生自`Microsoft.BizTalk.BaseFunctoids`类，并必须通过重写它们提供对某些方法的实现。</span><span class="sxs-lookup"><span data-stu-id="2cc44-108">Also, a custom functoid must derive from the `Microsoft.BizTalk.BaseFunctoids` class, and it must provide implementation for some methods by overriding them.</span></span> <span data-ttu-id="2cc44-109">(`BaseFunctoid`随附的 Microsoft.BizTalk.BaseFunctoids.dll 程序集中定义类[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="2cc44-109">(The `BaseFunctoid` class is defined in the Microsoft.BizTalk.BaseFunctoids.dll assembly included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2cc44-110">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="2cc44-110">What This Sample Does</span></span>  
 <span data-ttu-id="2cc44-111">自定义 Functoid 示例实现多个 functoid，每个派生自`BaseFunctoid`重写几个方法。</span><span class="sxs-lookup"><span data-stu-id="2cc44-111">The Custom Functoid sample implements several functoids, each deriving from the `BaseFunctoid` class and overriding several methods.</span></span>  
  
 <span data-ttu-id="2cc44-112">实现自定义 functoid 时，可以公开其内联代码。</span><span class="sxs-lookup"><span data-stu-id="2cc44-112">When implementing a custom functoid, you can expose its code inline.</span></span> <span data-ttu-id="2cc44-113">内联代码负责为 functoid 执行计算。</span><span class="sxs-lookup"><span data-stu-id="2cc44-113">The inline code is what performs the computation for the functoid.</span></span> <span data-ttu-id="2cc44-114">BizTalk 映射器的编译器从 functoid 提取内联代码，并在生成项目时将其嵌入编译的 XSLT 中。</span><span class="sxs-lookup"><span data-stu-id="2cc44-114">The BizTalk Mapper compiler extracts inline code from a functoid and embeds it in the compiled XSLT when you build the project.</span></span>  
  
 <span data-ttu-id="2cc44-115">如果自定义 functoid 不公开任何内联代码，则 BizTalk 映射器将生成调用自定义 functoid 所在程序集的 XSLT。</span><span class="sxs-lookup"><span data-stu-id="2cc44-115">If your custom functoid does not expose any inline code, BizTalk Mapper generates XSLT that calls into the assembly where the custom functoid resides.</span></span> <span data-ttu-id="2cc44-116">在此情况下，必须确保自定义 functoid 程序集在全局程序集缓存中可用，以便 XSLT 引擎能够找到它。</span><span class="sxs-lookup"><span data-stu-id="2cc44-116">In this case, you must be sure your custom functoid assembly is available in the global assembly cache (GAC) so the XSLT engine can find it.</span></span> <span data-ttu-id="2cc44-117">自定义 functoid 还必须具有唯一的 GUID 属性。</span><span class="sxs-lookup"><span data-stu-id="2cc44-117">A custom functoid must also have a unique GUID attribute.</span></span> <span data-ttu-id="2cc44-118">BizTalk 映射器使用 GUID 标识要加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="2cc44-118">BizTalk Mapper uses the GUID to identify which assembly to load.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2cc44-119">如果你重用自定义 functoid 示例代码以实现自己的 functoid，则必须确保将 GUID 属性更改为唯一值。</span><span class="sxs-lookup"><span data-stu-id="2cc44-119">If you reuse the Custom Functoid sample code to implement your own functoid(s), you must be sure to change the GUID attribute to one that is unique.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2cc44-120">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="2cc44-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="2cc44-121">*\<示例路径\>* \XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="2cc44-121">*\<Samples Path\>* \XmlTools\CustomFunctoid</span></span>  
  
 <span data-ttu-id="2cc44-122">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="2cc44-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="2cc44-123">文件</span><span class="sxs-lookup"><span data-stu-id="2cc44-123">File(s)</span></span>|<span data-ttu-id="2cc44-124">Description</span><span class="sxs-lookup"><span data-stu-id="2cc44-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cc44-125">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="2cc44-125">AssemblyInfo.cs</span></span>|<span data-ttu-id="2cc44-126">程序集信息 C# 源代码。</span><span class="sxs-lookup"><span data-stu-id="2cc44-126">Assembly information C# source code.</span></span>|  
|<span data-ttu-id="2cc44-127">CBuildArray.bmp</span><span class="sxs-lookup"><span data-stu-id="2cc44-127">CBuildArray.bmp</span></span>|<span data-ttu-id="2cc44-128">工具箱位图。</span><span class="sxs-lookup"><span data-stu-id="2cc44-128">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="2cc44-129">CConcat.bmp</span><span class="sxs-lookup"><span data-stu-id="2cc44-129">CConcat.bmp</span></span>|<span data-ttu-id="2cc44-130">工具箱位图。</span><span class="sxs-lookup"><span data-stu-id="2cc44-130">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="2cc44-131">CExtractArray.bmp</span><span class="sxs-lookup"><span data-stu-id="2cc44-131">CExtractArray.bmp</span></span>|<span data-ttu-id="2cc44-132">工具箱位图。</span><span class="sxs-lookup"><span data-stu-id="2cc44-132">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="2cc44-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="2cc44-133">Cleanup.bat</span></span>|<span data-ttu-id="2cc44-134">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集，同时删除 CustomFunctoid.dll。</span><span class="sxs-lookup"><span data-stu-id="2cc44-134">Used to undeploy assemblies and remove them from the global assembly cache (GAC) and to delete CustomFunctoid.dll.</span></span>|  
|<span data-ttu-id="2cc44-135">CLongestString.bmp</span><span class="sxs-lookup"><span data-stu-id="2cc44-135">CLongestString.bmp</span></span>|<span data-ttu-id="2cc44-136">工具箱位图。</span><span class="sxs-lookup"><span data-stu-id="2cc44-136">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="2cc44-137">CMultiply.bmp</span><span class="sxs-lookup"><span data-stu-id="2cc44-137">CMultiply.bmp</span></span>|<span data-ttu-id="2cc44-138">工具箱位图。</span><span class="sxs-lookup"><span data-stu-id="2cc44-138">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="2cc44-139">CustomFunctoid.cs</span><span class="sxs-lookup"><span data-stu-id="2cc44-139">CustomFunctoid.cs</span></span>|<span data-ttu-id="2cc44-140">自定义 functoid C# 源代码。</span><span class="sxs-lookup"><span data-stu-id="2cc44-140">Custom functoid C# source code.</span></span>|  
|<span data-ttu-id="2cc44-141">CustomFunctoid.csproj</span><span class="sxs-lookup"><span data-stu-id="2cc44-141">CustomFunctoid.csproj</span></span>|<span data-ttu-id="2cc44-142">自定义 functoid C# 项目。</span><span class="sxs-lookup"><span data-stu-id="2cc44-142">Custom functoid C# project.</span></span>|  
|<span data-ttu-id="2cc44-143">CustomFunctoid.sln</span><span class="sxs-lookup"><span data-stu-id="2cc44-143">CustomFunctoid.sln</span></span>|<span data-ttu-id="2cc44-144">自定义 functoid 解决方案。</span><span class="sxs-lookup"><span data-stu-id="2cc44-144">Custom functoid solution.</span></span>|  
|<span data-ttu-id="2cc44-145">CustomFunctoidResources.resx</span><span class="sxs-lookup"><span data-stu-id="2cc44-145">CustomFunctoidResources.resx</span></span>|<span data-ttu-id="2cc44-146">自定义 functoid 资源。</span><span class="sxs-lookup"><span data-stu-id="2cc44-146">Custom functoid resources.</span></span>|  
|<span data-ttu-id="2cc44-147">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="2cc44-147">Setup.bat</span></span>|<span data-ttu-id="2cc44-148">用于生成、部署和启动示例。</span><span class="sxs-lookup"><span data-stu-id="2cc44-148">Used to build, deploy, and start the sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="2cc44-149">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="2cc44-149">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="2cc44-150">使用以下过程可以生成并初始化自定义 functoid 示例。</span><span class="sxs-lookup"><span data-stu-id="2cc44-150">Use the following procedure to build and initialize the Custom Functoid sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="2cc44-151">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="2cc44-151">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="2cc44-152">在命令窗口中，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="2cc44-152">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="2cc44-153">\<*示例路径*\>\XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="2cc44-153">\<*Samples Path*\>\XmlTools\CustomFunctoid</span></span>  
  
2.  <span data-ttu-id="2cc44-154">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2cc44-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="2cc44-155">生成示例项目。</span><span class="sxs-lookup"><span data-stu-id="2cc44-155">Builds the sample project.</span></span>  
  
    -   <span data-ttu-id="2cc44-156">将生成的程序集复制到 Developer Tools\Mapper Extensions 目录中。</span><span class="sxs-lookup"><span data-stu-id="2cc44-156">Copies the generated assembly to the Developer Tools\Mapper Extensions directory.</span></span>  
  
    -   <span data-ttu-id="2cc44-157">向 GAC 添加生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="2cc44-157">Adds the generated assembly to the GAC.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2cc44-158">在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="2cc44-158">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="2cc44-159">运行本示例</span><span class="sxs-lookup"><span data-stu-id="2cc44-159">Running This Sample</span></span>  
 <span data-ttu-id="2cc44-160">使用以下过程运行自定义 functoid 示例。</span><span class="sxs-lookup"><span data-stu-id="2cc44-160">Use the following procedure to run the Custom Functoid sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="2cc44-161">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="2cc44-161">To run this sample</span></span>  
  
1. <span data-ttu-id="2cc44-162">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具**菜单，然后选择**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-162">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
2. <span data-ttu-id="2cc44-163">在中**选择工具箱项**对话框中，选择**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2cc44-163">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
3. <span data-ttu-id="2cc44-164">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-164">Click **Reset**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2cc44-165">如果自定义 functoid 没有公开任何内联代码，请确保 GAC 中包含其程序集。</span><span class="sxs-lookup"><span data-stu-id="2cc44-165">If your custom functoid does not expose any inline code, make sure its assembly is made available in the GAC.</span></span>  
  
4. <span data-ttu-id="2cc44-166">从**文件**菜单中，选择**退出**以关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2cc44-166">From the **File** menu, select **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
5. <span data-ttu-id="2cc44-167">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-167">Start **Visual Studio Command Prompt**.</span></span>  
  
6. <span data-ttu-id="2cc44-168">在命令提示符处，键入**devenv /setup**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-168">At the command prompt, type **devenv /setup**.</span></span>  
  
7. <span data-ttu-id="2cc44-169">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-169">Start **Microsoft Visual Studio**.</span></span>  
  
    <span data-ttu-id="2cc44-170">自定义 functoid （自定义 concatenate functoid、 最长字符串、 生成数组 functoid 和提取数组 functoid） 上显示**字符串 Functoid**工具箱和累计乘 functoid 的选项卡将显示在**累计 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2cc44-170">The custom functoids (Custom concatenate functoid, Longest String, Build array functoid, and Extract array functoid) appear on the **String Functoids** tab of the Toolbox, and the Cumulative Multiply functoid appears on the **Cumulative Functoids** tab.</span></span>  
  
## <a name="removing-this-sample"></a><span data-ttu-id="2cc44-171">删除此示例</span><span class="sxs-lookup"><span data-stu-id="2cc44-171">Removing This Sample</span></span>  
 <span data-ttu-id="2cc44-172">使用以下过程可以删除此自定义 functoid 示例。</span><span class="sxs-lookup"><span data-stu-id="2cc44-172">Use the following procedure to remove the Custom Functoid sample.</span></span>  
  
#### <a name="to-remove-this-sample"></a><span data-ttu-id="2cc44-173">删除本示例</span><span class="sxs-lookup"><span data-stu-id="2cc44-173">To remove this sample</span></span>  
  
1. <span data-ttu-id="2cc44-174">从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱中删除 functoid。</span><span class="sxs-lookup"><span data-stu-id="2cc44-174">Remove the functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   > [!WARNING]
   >  <span data-ttu-id="2cc44-175">如果在运行 Cleanup.bat 后，仍在工具箱中看到过时的自定义 functoid（可能是由于 Visual Studio 内部缓存），请按照下面的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="2cc44-175">If after running Cleanup.bat, you still see the stale custom functoids in the toolbox (probably due to internal caching by Visual Studio), then follow the procedures below:</span></span>  
  
   1. <span data-ttu-id="2cc44-176">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具**菜单，然后选择**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-176">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
   2. <span data-ttu-id="2cc44-177">在中**选择工具箱项**对话框中，选择**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2cc44-177">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
   3. <span data-ttu-id="2cc44-178">在列表中找到自定义 functoid（“自定义连接”functoid、“最长字符串”、“构建数组”functoid、“提取数组”functoid 和“累计乘”）。</span><span class="sxs-lookup"><span data-stu-id="2cc44-178">Find the custom functoids (Custom concatenate functoid, Longest String, Build array functoid, Extract array functoid, and Cumulative Multiply) in the list.</span></span> <span data-ttu-id="2cc44-179">单击各自**复选框**以删除 functoid，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-179">Click the respective **check box** to remove the functoids, and then click **OK**.</span></span>  
  
      <span data-ttu-id="2cc44-180">如果上述过程不起作用，则执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="2cc44-180">If the above procedure does not work, follow the below procedure.</span></span>  
  
   4. <span data-ttu-id="2cc44-181">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具箱**时编辑映射以打开工具箱面板的选项卡。</span><span class="sxs-lookup"><span data-stu-id="2cc44-181">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
   5. <span data-ttu-id="2cc44-182">右键单击工具中，选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-182">Right-click the tool box and select **Choose Items**.</span></span>  
  
   6. <span data-ttu-id="2cc44-183">在选择项对话框中，单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-183">In the Choose Items dialog box, click **Reset**, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="2cc44-184">关闭 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="2cc44-184">Close all instances of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
      <span data-ttu-id="2cc44-185">如果上述过程不起作用，则执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="2cc44-185">If the above procedure does not work, follow the below procedure.</span></span>  
  
   8. <span data-ttu-id="2cc44-186">启动**Visual Studio 命令提示符**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="2cc44-186">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
   9. <span data-ttu-id="2cc44-187">关闭所有正在运行的 Visual Studio 的实例。</span><span class="sxs-lookup"><span data-stu-id="2cc44-187">Close all the running instances of Visual Studio.</span></span>  
  
   10. <span data-ttu-id="2cc44-188">发出以下命令：</span><span class="sxs-lookup"><span data-stu-id="2cc44-188">Give the following commands:</span></span>  
  
        `devenv /resetsettings`  
  
        `devenv /setup`  
  
   11. <span data-ttu-id="2cc44-189">可以从工具箱中手动选择不需要的 functoid。</span><span class="sxs-lookup"><span data-stu-id="2cc44-189">You can manually select the unwanted functoids from the toolbox.</span></span> <span data-ttu-id="2cc44-190">然后，右键单击该 functoid，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="2cc44-190">Then, right click the functoid, and click **Delete**.</span></span>  
  
       <span data-ttu-id="2cc44-191">如果上述过程不起作用，则执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="2cc44-191">If the above procedure does not work, follow the below procedure.</span></span>  
  
   12. <span data-ttu-id="2cc44-192">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目中编辑映射时，单击“工具箱”选项卡打开工具箱面板。</span><span class="sxs-lookup"><span data-stu-id="2cc44-192">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the Toolbox tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
   13. <span data-ttu-id="2cc44-193">单击**累计 Functoid**组。</span><span class="sxs-lookup"><span data-stu-id="2cc44-193">Click the **Cumulative Functoids** group.</span></span>  
  
   14. <span data-ttu-id="2cc44-194">右键单击你想要删除，然后选择的 functoid**删除**或按 delete 键。</span><span class="sxs-lookup"><span data-stu-id="2cc44-194">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
   15. <span data-ttu-id="2cc44-195">单击**字符串 Functoid**组。</span><span class="sxs-lookup"><span data-stu-id="2cc44-195">Click the **String Functoids** group.</span></span>  
  
   16. <span data-ttu-id="2cc44-196">右键单击你想要删除，然后选择的 functoid**删除**或按 delete 键。</span><span class="sxs-lookup"><span data-stu-id="2cc44-196">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
2. <span data-ttu-id="2cc44-197">在命令窗口中，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="2cc44-197">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
    <span data-ttu-id="2cc44-198">\<*示例路径*\>\XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="2cc44-198">\<*Samples Path*\>\XmlTools\CustomFunctoid</span></span>  
  
3. <span data-ttu-id="2cc44-199">运行 Cleanup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2cc44-199">Run the file Cleanup.bat, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="2cc44-200">从 Developer Tools\Mapper Extensions 目录中删除程序集。</span><span class="sxs-lookup"><span data-stu-id="2cc44-200">Deletes the assembly from the Developer Tools\Mapper Extensions directory.</span></span>  
  
   -   <span data-ttu-id="2cc44-201">从 GAC 删除程序集。</span><span class="sxs-lookup"><span data-stu-id="2cc44-201">Removes the assembly from the GAC.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="2cc44-202">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="2cc44-202">Classes or Methods Used in This Sample</span></span>  
 [<span data-ttu-id="2cc44-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span><span class="sxs-lookup"><span data-stu-id="2cc44-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="2cc44-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cc44-204">See Also</span></span>  
 <span data-ttu-id="2cc44-205">[使用 BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="2cc44-205">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 [<span data-ttu-id="2cc44-206">XML 工具（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="2cc44-206">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)