---
title: 调试自定义管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27e5445a-6415-4c52-a450-b74a71fc4aa2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3841b300647a7a0b5859fca828f8aa5a840e9755
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352570"
---
# <a name="debugging-custom-pipelines"></a><span data-ttu-id="24bce-102">调试自定义管道</span><span class="sxs-lookup"><span data-stu-id="24bce-102">Debugging Custom Pipelines</span></span>
<span data-ttu-id="24bce-103">当消息处理失败时在自定义管道中时，可以使用源级别调试来确定和解决问题。</span><span class="sxs-lookup"><span data-stu-id="24bce-103">When message processing fails in your custom pipeline, you can use source level debugging to identify and correct problems.</span></span> <span data-ttu-id="24bce-104">完成源级别调试使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试器附加到 BTSNTSVC.exe （如果部署自定义管道） 或 Pipeline.exe （如果使用独立的管道工具）。</span><span class="sxs-lookup"><span data-stu-id="24bce-104">Source level debugging is done using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugger by attaching to BTSNTSVC.exe (if the custom pipeline is deployed) or Pipeline.exe (if using the stand-alone pipeline tool).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="24bce-105">过程</span><span class="sxs-lookup"><span data-stu-id="24bce-105">Procedures</span></span>  
 <span data-ttu-id="24bce-106">使用以下过程调试自定义管道。</span><span class="sxs-lookup"><span data-stu-id="24bce-106">Use the following procedures to debug custom pipelines.</span></span>  
  
### <a name="how-to-debug-a-deployed-pipeline"></a><span data-ttu-id="24bce-107">如何调试已部署的管道</span><span class="sxs-lookup"><span data-stu-id="24bce-107">How to Debug a Deployed Pipeline</span></span>  
 <span data-ttu-id="24bce-108">组中心页和事件查看器中的跟踪查询，提供有关已部署组件中消息处理失败的有用信息。</span><span class="sxs-lookup"><span data-stu-id="24bce-108">Tracking queries from the Group Hub page, and the event viewers, provide useful information about message processing failures in deployed components.</span></span> <span data-ttu-id="24bce-109">此信息通常用于缩小问题的来源。</span><span class="sxs-lookup"><span data-stu-id="24bce-109">This information can often be used to narrow down the origin of a problem.</span></span> <span data-ttu-id="24bce-110">一旦已其中涉及自定义管道，源级别调试可用来确定任何有问题的代码。</span><span class="sxs-lookup"><span data-stu-id="24bce-110">Once a custom pipeline has been implicated, source level debugging can be used to identify any problematic code.</span></span>  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a><span data-ttu-id="24bce-111">若要调试已部署的自定义管道使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24bce-111">To Debug a Deployed Custom Pipeline using Visual Studio</span></span>  
  
1. <span data-ttu-id="24bce-112">加载到自定义管道项目解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="24bce-112">Load the custom pipeline project solution into [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="24bce-113">更改您的解决方案的输出路径*\<安装文件夹\>* \Pipeline Components。</span><span class="sxs-lookup"><span data-stu-id="24bce-113">Change the output path for your solution to *\<Installation Folder\>* \Pipeline Components.</span></span> <span data-ttu-id="24bce-114">在解决方案资源管理器中右键单击你的项目，单击生成选项卡，然后通过单击更改输出路径**浏览**按钮，然后选择*\<安装文件夹\>* \Pipeline components 目录。</span><span class="sxs-lookup"><span data-stu-id="24bce-114">In Solution Explorer, right-click your project, click the Build tab, and then change the Output Path by clicking the **Browse** button and selecting the *\<Installation Folder\>* \Pipeline Components directory.</span></span>  
  
3. <span data-ttu-id="24bce-115">从内部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过单击部署解决方案**构建** &#124; **部署**。</span><span class="sxs-lookup"><span data-stu-id="24bce-115">From within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the solution by clicking **Build** &#124; **Deploy**.</span></span>  
  
4. <span data-ttu-id="24bce-116">重新启动运行管道的主机实例。</span><span class="sxs-lookup"><span data-stu-id="24bce-116">Restart the host instance that runs the pipeline.</span></span> <span data-ttu-id="24bce-117">使用 BizTalk Server 管理控制台，导航到运行管道的主机实例，右键单击主机实例，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="24bce-117">Using the BizTalk Server Management console, navigate to the host instance that runs the pipeline, right-click the host instance then click **Restart**.</span></span>  
  
5. <span data-ttu-id="24bce-118">附加[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BTSNTSVC.exe 的调试器。</span><span class="sxs-lookup"><span data-stu-id="24bce-118">Attach the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugger to BTSNTSVC.exe.</span></span> <span data-ttu-id="24bce-119">这可以通过单击**调试** &#124; **附加到进程**，在所有会话中，单击显示的进程，然后双击 BTSNTSVC.exe。</span><span class="sxs-lookup"><span data-stu-id="24bce-119">This can be done by clicking **Debug** &#124; **Attach to Process**, click Show processes in all sessions, and then double-click BTSNTSVC.exe.</span></span>  
  
6. <span data-ttu-id="24bce-120">设置断点。</span><span class="sxs-lookup"><span data-stu-id="24bce-120">Set breakpoints.</span></span>  
  
7. <span data-ttu-id="24bce-121">将消息放入适当的位置，可以启动自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="24bce-121">Drop a message in the appropriate location to initiate the custom pipeline component.</span></span> <span data-ttu-id="24bce-122">处理应在你设置的断点处停止。</span><span class="sxs-lookup"><span data-stu-id="24bce-122">Processing should halt on the breakpoints you set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24bce-123">如果你的代码引发异常，BizTalk Server 将其捕获并最终挂起消息。</span><span class="sxs-lookup"><span data-stu-id="24bce-123">If your code throws an exception, BizTalk Server will catch it and ultimately suspend the message.</span></span> <span data-ttu-id="24bce-124">若要避免此行为，应在第一机会异常上中断。</span><span class="sxs-lookup"><span data-stu-id="24bce-124">To avoid this behavior, you should break on first chance exceptions.</span></span>  
  
### <a name="how-to-debug-using-pipelineexe"></a><span data-ttu-id="24bce-125">如何调试使用 Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="24bce-125">How to Debug Using Pipeline.exe</span></span>  
 <span data-ttu-id="24bce-126">此外可以测试自定义管道使用 Pipeline.exe。</span><span class="sxs-lookup"><span data-stu-id="24bce-126">You can also test custom pipelines using Pipeline.exe.</span></span> <span data-ttu-id="24bce-127">这一优点是您无需部署代价是类似于生产的条件下无法运行管道。</span><span class="sxs-lookup"><span data-stu-id="24bce-127">This has the advantage of not requiring you to deploy the pipeline at the expense of not running under conditions similar to production.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24bce-128">如果在自定义管道使用平面文件组装器 / 拆装器，Pipeline.exe 将不会正确执行。</span><span class="sxs-lookup"><span data-stu-id="24bce-128">If your custom pipeline uses the flat file assembler / disassembler, Pipeline.exe will not execute properly.</span></span> <span data-ttu-id="24bce-129">这是因为 Pipeline.exe 不访问 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="24bce-129">This is because Pipeline.exe does not access the BizTalk database.</span></span> <span data-ttu-id="24bce-130">一种解决方案是删除这些组装器 / 拆装器组件并分别使用 FFDasm.exe 和 FFAsm.exe 测试它们。</span><span class="sxs-lookup"><span data-stu-id="24bce-130">One solution is to remove the assembler / disassembler components and test them separately with FFDasm.exe and FFAsm.exe.</span></span> <span data-ttu-id="24bce-131">请参阅[管道工具](../core/pipeline-tools.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="24bce-131">See [Pipeline Tools](../core/pipeline-tools.md) for more information.</span></span>  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a><span data-ttu-id="24bce-132">若要调试自定义管道使用 Pipeline.exe 和 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24bce-132">To Debug a Custom Pipeline using Pipeline.exe and Visual Studio</span></span>  
  
1. <span data-ttu-id="24bce-133">加载到自定义管道项目解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="24bce-133">Load the custom pipeline project solution into [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="24bce-134">更改您的解决方案的输出路径*\<安装文件夹\>* \Pipeline Components。</span><span class="sxs-lookup"><span data-stu-id="24bce-134">Change the output path for your solution to *\<Installation Folder\>* \Pipeline Components.</span></span> <span data-ttu-id="24bce-135">在解决方案资源管理器中右键单击你的项目，单击生成选项卡，然后通过单击更改输出路径**浏览**按钮，然后选择*\<安装文件夹\>* \Pipeline components 目录。</span><span class="sxs-lookup"><span data-stu-id="24bce-135">In Solution Explorer, right-click your project, click the Build tab, and then change the Output Path by clicking the **Browse** button and selecting the *\<Installation Folder\>* \Pipeline Components directory.</span></span>  
  
3. <span data-ttu-id="24bce-136">更改你的解决方案的启动操作。</span><span class="sxs-lookup"><span data-stu-id="24bce-136">Change the start action for your solution.</span></span> <span data-ttu-id="24bce-137">在解决方案资源管理器中右键单击你的项目，单击调试选项卡，单击启动外部程序，然后单击 **...**</span><span class="sxs-lookup"><span data-stu-id="24bce-137">In Solution Explorer, right-click your project, click the Debug tab, click Start external program, then click **…**</span></span> <span data-ttu-id="24bce-138">然后导航到*\<安装文件夹\>* \SDK\Utilities\PipelineTools，然后选择 Pipeline.exe。</span><span class="sxs-lookup"><span data-stu-id="24bce-138">and navigate to *\<Installation Folder\>* \SDK\Utilities\PipelineTools and choose Pipeline.exe.</span></span> <span data-ttu-id="24bce-139">在启动选项下输入适合您的组件的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="24bce-139">Under Start Options, enter the command line arguments appropriate for your component.</span></span> <span data-ttu-id="24bce-140">有关 Pipeline.exe 的详细信息，请参阅[管道工具](../core/pipeline-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="24bce-140">For more information on Pipeline.exe, see [Pipeline Tools](../core/pipeline-tools.md).</span></span> <span data-ttu-id="24bce-141">典型配置指定管道和示例文件：</span><span class="sxs-lookup"><span data-stu-id="24bce-141">A typical configuration specifies the pipeline and a sample file:</span></span>  
  
   ```  
   <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
   ```  
  
4. <span data-ttu-id="24bce-142">设置您的断点。</span><span class="sxs-lookup"><span data-stu-id="24bce-142">Set your breakpoints.</span></span>  
  
5. <span data-ttu-id="24bce-143">按 F5 开始调试。</span><span class="sxs-lookup"><span data-stu-id="24bce-143">Press F5 to begin debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24bce-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="24bce-144">See Also</span></span>  
 [<span data-ttu-id="24bce-145">管道工具</span><span class="sxs-lookup"><span data-stu-id="24bce-145">Pipeline Tools</span></span>](../core/pipeline-tools.md)