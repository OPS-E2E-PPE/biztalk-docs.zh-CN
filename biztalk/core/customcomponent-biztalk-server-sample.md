---
title: CustomComponent （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- messages, streamed
- pipeline components [custom], configuring
ms.assetid: ed0da9f5-8cc7-4528-be8c-35b80744fd38
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f46fe74b6cd8618cdc218048ea057e6968f2d99f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019350"
---
# <a name="customcomponent-biztalk-server-sample"></a><span data-ttu-id="5fb62-102">CustomComponent （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="5fb62-102">CustomComponent (BizTalk Server Sample)</span></span>
<span data-ttu-id="5fb62-103">CustomComponent 示例演示如何创建和使用修改流消息的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="5fb62-103">The CustomComponent sample demonstrates how to create and use a custom pipeline component that modifies a streamed message.</span></span> <span data-ttu-id="5fb62-104">本示例还演示如何在管道设计器中对自定义管道组件进行配置。</span><span class="sxs-lookup"><span data-stu-id="5fb62-104">This sample also demonstrates the configuration of a custom pipeline component in Pipeline Designer.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="5fb62-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="5fb62-105">What This Sample Does</span></span>  
 <span data-ttu-id="5fb62-106">本示例实现了一个可将字符串作为前缀或后缀添加到输入消息中的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="5fb62-106">This sample implements a custom pipeline component that can prefix or append strings to the input message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5fb62-107"> 处理在流式处理模式下，这意味着整个消息永远不会加载到内存中的消息。</span><span class="sxs-lookup"><span data-stu-id="5fb62-107"> processes the message in streaming mode, meaning that the entire message is never loaded into memory.</span></span> <span data-ttu-id="5fb62-108">使用以下一系列步骤演示该自定义管道组件：</span><span class="sxs-lookup"><span data-stu-id="5fb62-108">The custom pipeline component is demonstrated using the following sequence of steps:</span></span>  

1. <span data-ttu-id="5fb62-109">BizTalk 从位于特定文件夹的某个文件中检索文本消息。</span><span class="sxs-lookup"><span data-stu-id="5fb62-109">BizTalk retrieves a text message from a file in a specific folder.</span></span>  

2. <span data-ttu-id="5fb62-110">通过包含 FixMsg 自定义管道组件的接收管道发送文本消息。</span><span class="sxs-lookup"><span data-stu-id="5fb62-110">The text message is sent through a receive pipeline containing the FixMsg custom pipeline component.</span></span> <span data-ttu-id="5fb62-111">您将该组件配置为在消息的开始处插入字符串。</span><span class="sxs-lookup"><span data-stu-id="5fb62-111">You configure this component to insert a string at the beginning of the message.</span></span>  

3. <span data-ttu-id="5fb62-112">通过包含 FixMsg 自定义管道组件的发送管道发送得到的文本消息。</span><span class="sxs-lookup"><span data-stu-id="5fb62-112">You send the resulting text message through a send pipeline with the FixMsg custom pipeline component.</span></span> <span data-ttu-id="5fb62-113">您将该组件配置为将字符串附加到消息的末尾。</span><span class="sxs-lookup"><span data-stu-id="5fb62-113">You configure the component to append a string to the end of the message.</span></span>  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5fb62-114"> 将得到的文本消息写入位于特定文件夹的文件中。</span><span class="sxs-lookup"><span data-stu-id="5fb62-114"> writes the resulting text message to a file in a specific folder.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="5fb62-115">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="5fb62-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="5fb62-116">\<*示例路径*\>\Pipelines\CustomComponent\\</span><span class="sxs-lookup"><span data-stu-id="5fb62-116">\<*Samples Path*\>\Pipelines\CustomComponent\\</span></span>  

 <span data-ttu-id="5fb62-117">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="5fb62-117">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                     <span data-ttu-id="5fb62-118">文件</span><span class="sxs-lookup"><span data-stu-id="5fb62-118">File(s)</span></span>                                                     |                                                                                              <span data-ttu-id="5fb62-119">Description</span><span class="sxs-lookup"><span data-stu-id="5fb62-119">Description</span></span>                                                                                               |
|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                   <span data-ttu-id="5fb62-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5fb62-120">Cleanup.bat</span></span>                                                   | <span data-ttu-id="5fb62-121">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="5fb62-121">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="5fb62-122">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="5fb62-122">Removes send and receive ports.</span></span> <span data-ttu-id="5fb62-123">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="5fb62-123">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                                                    <span data-ttu-id="5fb62-124">Input.txt</span><span class="sxs-lookup"><span data-stu-id="5fb62-124">Input.txt</span></span>                                                    |                                                                                           <span data-ttu-id="5fb62-125">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="5fb62-125">Sample input file.</span></span>                                                                                           |
|                                                    <span data-ttu-id="5fb62-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5fb62-126">Setup.bat</span></span>                                                    |                                                                               <span data-ttu-id="5fb62-127">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="5fb62-127">Used to build and initialize this sample.</span></span>                                                                                |
|                  <span data-ttu-id="5fb62-128">在 \FixMsg 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-128">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="5fb62-129">AssemblyInfo.cs、FixMsg.csproj、FixMsg.sln</span><span class="sxs-lookup"><span data-stu-id="5fb62-129">AssemblyInfo.cs, FixMsg.csproj, FixMsg.sln</span></span>                  |                                              <span data-ttu-id="5fb62-130">用于本示例的自定义管道组件部分的项目、解决方案和程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="5fb62-130">Project, solution, and assembly information files for the custom pipeline component portion of this sample.</span></span>                                               |
|                                  <span data-ttu-id="5fb62-131">在 \FixMsg 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-131">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="5fb62-132">FixMsg.cs</span><span class="sxs-lookup"><span data-stu-id="5fb62-132">FixMsg.cs</span></span>                                   |                                                                             <span data-ttu-id="5fb62-133">实现管道组件接口。</span><span class="sxs-lookup"><span data-stu-id="5fb62-133">Implements the pipeline component interfaces.</span></span>                                                                              |
|                               <span data-ttu-id="5fb62-134">在 \FixMsg 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-134">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="5fb62-135">FixMsgStream.cs</span><span class="sxs-lookup"><span data-stu-id="5fb62-135">FixMsgStream.cs</span></span>                                |                                                      <span data-ttu-id="5fb62-136">实现的包装器**System.IO.Stream**类，并启用流式处理的数据。</span><span class="sxs-lookup"><span data-stu-id="5fb62-136">Implements a wrapper for the **System.IO.Stream** class, enabling stream processing of data.</span></span>                                                      |
|                             <span data-ttu-id="5fb62-137">在 \FixMsg 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-137">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="5fb62-138">FixMsgDescription.cs</span><span class="sxs-lookup"><span data-stu-id="5fb62-138">FixMsgDescription.cs</span></span>                             |                                                       <span data-ttu-id="5fb62-139">提供用于在管道设计器中访问和显示组件 UI 资源的方法。</span><span class="sxs-lookup"><span data-stu-id="5fb62-139">Provides methods for accessing and rendering component UI resources in Pipeline Designer.</span></span>                                                        |
|                                 <span data-ttu-id="5fb62-140">在 \FixMsg 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-140">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="5fb62-141">FixMsg.resx</span><span class="sxs-lookup"><span data-stu-id="5fb62-141">FixMsg.resx</span></span>                                  |                                                                      <span data-ttu-id="5fb62-142">包含属性说明、图标和错误消息。</span><span class="sxs-lookup"><span data-stu-id="5fb62-142">Contains property descriptions, an icon, and error messages.</span></span>                                                                      |
| <span data-ttu-id="5fb62-143">在 \PipelineComponentSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-143">In the \PipelineComponentSample folder:</span></span><br /><br /> <span data-ttu-id="5fb62-144">PipelineComponentSample.btproj、PipelineComponentSample.sln</span><span class="sxs-lookup"><span data-stu-id="5fb62-144">PipelineComponentSample.btproj, PipelineComponentSample.sln</span></span> |                                                               <span data-ttu-id="5fb62-145">用于本示例的 BizTalk 项目部分的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5fb62-145">Project and solution files for the BizTalk project portion of this sample.</span></span>                                                               |
|             <span data-ttu-id="5fb62-146">在 \PipelineComponentSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-146">In the \PipelineComponentSample folder:</span></span><br /><br /> <span data-ttu-id="5fb62-147">PipelineComponentSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="5fb62-147">PipelineComponentSampleBinding.xml</span></span>              |                                                                             <span data-ttu-id="5fb62-148">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="5fb62-148">Used for automated setup such as port binding.</span></span>                                                                             |
|      <span data-ttu-id="5fb62-149">在 \PipelineComponentSample 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5fb62-149">In the \PipelineComponentSample folder:</span></span><br /><br /> <span data-ttu-id="5fb62-150">FixMsgReceivePipeline.btp、FixMsgSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="5fb62-150">FixMsgReceivePipeline.btp, FixMsgSendPipeline.btp</span></span>      |  <span data-ttu-id="5fb62-151">包含 FixMsg 自定义管道组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道，分别用于接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="5fb62-151">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines containing the FixMsg custom pipeline component, for the receive and the send pipelines, respectively.</span></span>   |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="5fb62-152">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="5fb62-152">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-customcomponent-sample"></a><span data-ttu-id="5fb62-153">生成并初始化 CustomComponent 示例</span><span class="sxs-lookup"><span data-stu-id="5fb62-153">To build and initialize the CustomComponent sample</span></span>  

1. <span data-ttu-id="5fb62-154">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="5fb62-154">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="5fb62-155">\<*示例路径*\>\Pipelines\CustomComponent</span><span class="sxs-lookup"><span data-stu-id="5fb62-155">\<*Samples Path*\>\Pipelines\CustomComponent</span></span>  

2. <span data-ttu-id="5fb62-156">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5fb62-156">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="5fb62-157">在以下文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="5fb62-157">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="5fb62-158">\<*示例路径*\>\Pipelines\CustomComponent</span><span class="sxs-lookup"><span data-stu-id="5fb62-158">\<*Samples Path*\>\Pipelines\CustomComponent</span></span>  

   - <span data-ttu-id="5fb62-159">编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。</span><span class="sxs-lookup"><span data-stu-id="5fb62-159">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="5fb62-160">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="5fb62-160">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="5fb62-161">在创建并绑定端口时，本示例将显示以下警告：</span><span class="sxs-lookup"><span data-stu-id="5fb62-161">This sample displays the following warnings when creating and binding the ports:</span></span>  
     >   
     >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
     >   
     >  <span data-ttu-id="5fb62-162">可以安全地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="5fb62-162">You can safely ignore these warnings.</span></span> <span data-ttu-id="5fb62-163">（若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="5fb62-163">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="5fb62-164">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="5fb62-164">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5fb62-165">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="5fb62-165">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="5fb62-166">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="5fb62-166">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="5fb62-167">使用该密钥对可以对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="5fb62-167">Use this key pair is used to sign the resulting assemblies.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="5fb62-168">若要撤消 Setup.bat 所做的更改，必须首先从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理 MMC 控制台停止并重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="5fb62-168">To undo changes made by Setup.bat, you must first stop and restart the host instance from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration MMC console.</span></span> <span data-ttu-id="5fb62-169">然后运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="5fb62-169">Next, run Cleanup.bat.</span></span> <span data-ttu-id="5fb62-170">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="5fb62-170">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="5fb62-171">运行本示例</span><span class="sxs-lookup"><span data-stu-id="5fb62-171">Running This Sample</span></span>  

#### <a name="to-run-the-customcomponent-sample"></a><span data-ttu-id="5fb62-172">运行 CustomComponent 示例</span><span class="sxs-lookup"><span data-stu-id="5fb62-172">To run the CustomComponent sample</span></span>  

1.  <span data-ttu-id="5fb62-173">将文本文件 Input.txt 的副本粘贴到 In 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5fb62-173">Paste a copy of the text file Input.txt into the folder In.</span></span>  

2.  <span data-ttu-id="5fb62-174">查看在 Out 文件夹中创建的文本文件。该文件包含 Input.txt 文件的内容以及在 Input.txt 文件内容的开头（由接收管道）和末尾（由发送管道）插入的其他文本。</span><span class="sxs-lookup"><span data-stu-id="5fb62-174">Observe the text file created in the folder Out. This file contains the contents of the file Input.txt with additional text inserted at the beginning (by the receive pipeline) and at the end (by the send pipeline).</span></span> <span data-ttu-id="5fb62-175">此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.</span><span class="sxs-lookup"><span data-stu-id="5fb62-175">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  

## <a name="comments"></a><span data-ttu-id="5fb62-176">注释</span><span class="sxs-lookup"><span data-stu-id="5fb62-176">Comments</span></span>  
 <span data-ttu-id="5fb62-177">通过执行以下步骤，可以在管道设计器中查看预配置管道：</span><span class="sxs-lookup"><span data-stu-id="5fb62-177">You can view the preconfigured pipelines in Pipeline Designer by following these steps:</span></span>  

1.  <span data-ttu-id="5fb62-178">在解决方案资源管理器中，双击 ReceivePipeline.btp 以便在管道设计器中打开该接收管道。</span><span class="sxs-lookup"><span data-stu-id="5fb62-178">In Solution Explorer, double-click ReceivePipeline.btp to open the receive pipeline in Pipeline Designer.</span></span> <span data-ttu-id="5fb62-179">查看 FixMsg 组件是否位于**验证**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="5fb62-179">Observe that the FixMsg component is placed in the **Validate** stage of the receive pipeline.</span></span>  

2.  <span data-ttu-id="5fb62-180">单击中的 FixMsg 组件**验证**设计图面上的阶段。</span><span class="sxs-lookup"><span data-stu-id="5fb62-180">Click the FixMsg component in the **Validate** stage on the design surface.</span></span> <span data-ttu-id="5fb62-181">在“属性”窗口中，可以看到该管道组件的配置属性。</span><span class="sxs-lookup"><span data-stu-id="5fb62-181">In the Properties window, you can see the configuration properties of the pipeline component.</span></span> <span data-ttu-id="5fb62-182">观察**PrependData**属性设置为**数据在前面加上在接收管道字符串**。</span><span class="sxs-lookup"><span data-stu-id="5fb62-182">Observe that the **PrependData** property is set to **Data to prepend in receive pipeline string**.</span></span>  

3.  <span data-ttu-id="5fb62-183">在解决方案资源管理器中，双击 SendPipeline.btp 以便在管道设计器中打开该发送管道。</span><span class="sxs-lookup"><span data-stu-id="5fb62-183">In Solution Explorer, double-click SendPipeline.btp to open the send pipeline in Pipeline Designer.</span></span> <span data-ttu-id="5fb62-184">查看 FixMsg 组件是否位于**预组装**发送管道阶段。</span><span class="sxs-lookup"><span data-stu-id="5fb62-184">Observe that the FixMsg component is placed in the **Pre-Assemble** stage of the send pipeline.</span></span>  

4.  <span data-ttu-id="5fb62-185">单击中的 FixMsg 组件**预组装**设计图面上的阶段。</span><span class="sxs-lookup"><span data-stu-id="5fb62-185">Click the FixMsg component in **Pre-Assemble** stage on the design surface.</span></span> <span data-ttu-id="5fb62-186">请注意， **AppendData**属性设置为**要中追加数据在发送管道字符串**。</span><span class="sxs-lookup"><span data-stu-id="5fb62-186">Note that the **AppendData** property is set to **Data to append in send pipeline string**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5fb62-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fb62-187">See Also</span></span>  
 [<span data-ttu-id="5fb62-188">管道（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="5fb62-188">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)