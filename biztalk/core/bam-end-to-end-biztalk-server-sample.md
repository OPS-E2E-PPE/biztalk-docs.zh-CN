---
title: "BAM BizTalk Server 中的端到端示例 |Microsoft 文档"
description: "有关如何将来自多个组件在 BizTalk Server 中使用业务活动监视的事件相关联的方案"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21cf3bcfae53d3204a1b4de23c1476591be2b453
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-end-to-end-biztalk-server-sample"></a><span data-ttu-id="b8303-103">BAM 端对端（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="b8303-103">BAM End-to-End (BizTalk Server Sample)</span></span>
<span data-ttu-id="b8303-104">端到端示例演示如何通过使用 BAM 关联中 （在这种情况下，三个业务流程和管道） 的多个组件的事件。</span><span class="sxs-lookup"><span data-stu-id="b8303-104">The End-to-End sample demonstrates how to correlate events from multiple components (in this case, three orchestrations and a pipeline) by using BAM.</span></span>  
  
 <span data-ttu-id="b8303-105">BAM 重新构造了跨管道组件和业务流程的业务活动。</span><span class="sxs-lookup"><span data-stu-id="b8303-105">BAM reconstructs the business activity that spans the pipeline component and orchestrations.</span></span> <span data-ttu-id="b8303-106">在最低级别，之所以能够通过调用**EventStream.EnableContinuation**从每个需要更多事件活动的实现组件。</span><span class="sxs-lookup"><span data-stu-id="b8303-106">At the lowest level, this works by calls to **EventStream.EnableContinuation** from each implementation component that expects more events for the activity.</span></span> <span data-ttu-id="b8303-107">调用**EnableContinuation**是显式的调用由在 Orchestration1 和 Orchestration2 将延续文件夹添加到一个计划，并遵循的计划的 ContinuationID 文件夹中的跟踪配置文件时它。</span><span class="sxs-lookup"><span data-stu-id="b8303-107">The call to **EnableContinuation** is explicit, while calls in Orchestration1 and Orchestration2 are made by adding a Continuation folder to the Tracking profile in one schedule, and a ContinuationID folder to the schedule that follows it.</span></span>  
  
 <span data-ttu-id="b8303-108">下图说明了本示例中使用的工作流。</span><span class="sxs-lookup"><span data-stu-id="b8303-108">The following diagram illustrates the workflow used in the sample.</span></span>  
  
 ![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")  

  
## <a name="what-this-sample-does"></a><span data-ttu-id="b8303-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="b8303-109">What This Sample Does</span></span>  
 <span data-ttu-id="b8303-110">BAM 端对端示例显示如何使用 BAM 从管道和多个业务流程收集信息并更新单个活动。</span><span class="sxs-lookup"><span data-stu-id="b8303-110">The BAM end-to-end sample shows how you can use BAM to gather information from a pipeline and multiple orchestrations and update a single activity.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="b8303-111">本示例的设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="b8303-111">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="b8303-112">BAM 端对端示例旨在阐释下列活动：</span><span class="sxs-lookup"><span data-stu-id="b8303-112">The BAM end-to-end sample was designed to illustrate the following activities:</span></span>  
  
-   <span data-ttu-id="b8303-113">在管道中使用 BAM。</span><span class="sxs-lookup"><span data-stu-id="b8303-113">Using BAM within a pipeline.</span></span>  
  
-   <span data-ttu-id="b8303-114">使用跟踪配置文件编辑器 (TPE) 将活动项映射到业务流程中的形状和消息的元素。</span><span class="sxs-lookup"><span data-stu-id="b8303-114">Using the Tracking Profile Editor (TPE) to map activity items to shapes in an orchestration and elements of a message.</span></span>  
  
-   <span data-ttu-id="b8303-115">当一个解决方案的多个部分都作用于活动时，使用继续符使活动保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="b8303-115">Using continuations to keep an activity active when multiple pieces of a solution contribute to the activity.</span></span>  
  

<span data-ttu-id="b8303-116">本示例的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="b8303-116">The sample works as follows:</span></span>  
  
1.  <span data-ttu-id="b8303-117">从检索到输入的消息*\<示例路径 >*\BamEndToEnd\Input 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b8303-117">An input message is retrieved from the *\<Samples Path>*\BamEndToEnd\Input folder.</span></span>  
  
2.  <span data-ttu-id="b8303-118">管道组件向消息分配唯一的 DocumentID，然后使用 BAM API 开始一个新 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="b8303-118">The pipeline component assigns a unique DocumentID to the message, and uses the BAM API to begin a new BAM activity.</span></span> <span data-ttu-id="b8303-119">将此 DocumentID 作为此输入消息的一个单独部分附加，以使其可用于业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-119">The DocumentID is attached as a separate part of the input message to make it available to the orchestrations.</span></span>  
  
3.  <span data-ttu-id="b8303-120">在收到此输入消息时激活服务 Orchestration1。</span><span class="sxs-lookup"><span data-stu-id="b8303-120">The service Orchestration1 is activated when the input message is received.</span></span>  
  
4.  <span data-ttu-id="b8303-121">Orchestration1 修改此输入消息，然后将其作为参数传递给 Orchestration2。</span><span class="sxs-lookup"><span data-stu-id="b8303-121">Orchestration1 modifies the input message and passes it as a parameter to Orchestration2.</span></span>  
  
5.  <span data-ttu-id="b8303-122">Orchestration2 修改此输入消息，然后将其发送给 MessageBox 数据库，这便激活了 Orchestration3。</span><span class="sxs-lookup"><span data-stu-id="b8303-122">Orchestration2 modifies the input message and sends it to the MessageBox database, which activates Orchestration3.</span></span>  
  
6.  <span data-ttu-id="b8303-123">Orchestration3 修改消息并将其写入文件夹*\<示例路径 >*\BamEndToEnd\Output。</span><span class="sxs-lookup"><span data-stu-id="b8303-123">Orchestration3 modifies the message and writes it to the folder *\<Samples Path>*\BamEndToEnd\Output.</span></span>  
  
7.  <span data-ttu-id="b8303-124">每个业务流程都会更新 BAM 活动中的活动项。</span><span class="sxs-lookup"><span data-stu-id="b8303-124">Each orchestration updates activity items in the BAM activity.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b8303-125">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="b8303-125">Where to Find This Sample</span></span>  
 <span data-ttu-id="b8303-126">你可以找到在此示例*\<示例路径 >*\BAM\BamEndToEnd。</span><span class="sxs-lookup"><span data-stu-id="b8303-126">You can find this sample at *\<Samples Path>*\BAM\BamEndToEnd.</span></span>  
  
 <span data-ttu-id="b8303-127">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="b8303-127">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b8303-128">文件</span><span class="sxs-lookup"><span data-stu-id="b8303-128">File(s)</span></span>|<span data-ttu-id="b8303-129">Description</span><span class="sxs-lookup"><span data-stu-id="b8303-129">Description</span></span>|  
|----|---|  
|<span data-ttu-id="b8303-130">BamEndToEnd.sln</span><span class="sxs-lookup"><span data-stu-id="b8303-130">BamEndToEnd.sln</span></span>|<span data-ttu-id="b8303-131">BAM 端对端示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="b8303-131">BAM End-to-End sample solution.</span></span>|  
|<span data-ttu-id="b8303-132">BamEndToEnd.xls</span><span class="sxs-lookup"><span data-stu-id="b8303-132">BamEndToEnd.xls</span></span>|<span data-ttu-id="b8303-133">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="b8303-133">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="b8303-134">BamEndToEnd.xml</span><span class="sxs-lookup"><span data-stu-id="b8303-134">BamEndToEnd.xml</span></span>|<span data-ttu-id="b8303-135">BAM 定义 XML。</span><span class="sxs-lookup"><span data-stu-id="b8303-135">BAM definition XML.</span></span>|  
|<span data-ttu-id="b8303-136">BAMEndToEndBinding.xml</span><span class="sxs-lookup"><span data-stu-id="b8303-136">BAMEndToEndBinding.xml</span></span>|<span data-ttu-id="b8303-137">BAM 绑定。</span><span class="sxs-lookup"><span data-stu-id="b8303-137">BAM binding.</span></span>|  
|<span data-ttu-id="b8303-138">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="b8303-138">Cleanup.bat</span></span>|<span data-ttu-id="b8303-139">用于取消部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-139">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="b8303-140">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="b8303-140">InputMessage.xml</span></span>|<span data-ttu-id="b8303-141">输入消息。</span><span class="sxs-lookup"><span data-stu-id="b8303-141">Input message.</span></span>|  
|<span data-ttu-id="b8303-142">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="b8303-142">Setup.bat</span></span>|<span data-ttu-id="b8303-143">用于编译和部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-143">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="b8303-144">\Components\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="b8303-144">\Components\AssemblyInfo.cs</span></span>|<span data-ttu-id="b8303-145">管道组件代码。</span><span class="sxs-lookup"><span data-stu-id="b8303-145">Pipeline component code.</span></span>|  
|<span data-ttu-id="b8303-146">\Components\BAMMessagePartPLComponent.cs</span><span class="sxs-lookup"><span data-stu-id="b8303-146">\Components\BAMMessagePartPLComponent.cs</span></span>|<span data-ttu-id="b8303-147">管道组件代码。</span><span class="sxs-lookup"><span data-stu-id="b8303-147">Pipeline component code.</span></span>|  
|<span data-ttu-id="b8303-148">\Components\Components.csproj</span><span class="sxs-lookup"><span data-stu-id="b8303-148">\Components\Components.csproj</span></span>|<span data-ttu-id="b8303-149">管道组件项目。</span><span class="sxs-lookup"><span data-stu-id="b8303-149">Pipeline component project.</span></span>|  
|<span data-ttu-id="b8303-150">\Messages\InputMessage01.xml</span><span class="sxs-lookup"><span data-stu-id="b8303-150">\Messages\InputMessage01.xml</span></span><br /><br /> <span data-ttu-id="b8303-151">...</span><span class="sxs-lookup"><span data-stu-id="b8303-151">...</span></span><br /><br /> <span data-ttu-id="b8303-152">\Messages\InputMessage10.xml</span><span class="sxs-lookup"><span data-stu-id="b8303-152">\Messages\InputMessage10.xml</span></span>|<span data-ttu-id="b8303-153">示例输入的消息。</span><span class="sxs-lookup"><span data-stu-id="b8303-153">Sample input messages.</span></span>|  
|<span data-ttu-id="b8303-154">\Services\BAMInbound.btp</span><span class="sxs-lookup"><span data-stu-id="b8303-154">\Services\BAMInbound.btp</span></span>|<span data-ttu-id="b8303-155">入站管道文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-155">Inbound pipeline file.</span></span>|  
|<span data-ttu-id="b8303-156">\Services\BAMPartSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="b8303-156">\Services\BAMPartSchema.xsd</span></span>|<span data-ttu-id="b8303-157">BAM 部分消息架构。</span><span class="sxs-lookup"><span data-stu-id="b8303-157">BAM part message schema.</span></span>|  
|<span data-ttu-id="b8303-158">\Services\Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="b8303-158">\Services\Orchestration1.odx</span></span>|<span data-ttu-id="b8303-159">业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-159">Orchestration.</span></span>|  
|<span data-ttu-id="b8303-160">\Services\Orchestration2.odx</span><span class="sxs-lookup"><span data-stu-id="b8303-160">\Services\Orchestration2.odx</span></span>|<span data-ttu-id="b8303-161">业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-161">Orchestration.</span></span>|  
|<span data-ttu-id="b8303-162">\Services\Orchestration3.odx</span><span class="sxs-lookup"><span data-stu-id="b8303-162">\Services\Orchestration3.odx</span></span>|<span data-ttu-id="b8303-163">业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-163">Orchestration.</span></span>|  
|<span data-ttu-id="b8303-164">\Services\PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="b8303-164">\Services\PropertySchema.xsd</span></span>|<span data-ttu-id="b8303-165">属性架构。</span><span class="sxs-lookup"><span data-stu-id="b8303-165">Property schema.</span></span>|  
|<span data-ttu-id="b8303-166">\Services\Schema1.xsd</span><span class="sxs-lookup"><span data-stu-id="b8303-166">\Services\Schema1.xsd</span></span>|<span data-ttu-id="b8303-167">消息架构。</span><span class="sxs-lookup"><span data-stu-id="b8303-167">Message schema.</span></span>|  
|<span data-ttu-id="b8303-168">\Services\Schema2.xsd</span><span class="sxs-lookup"><span data-stu-id="b8303-168">\Services\Schema2.xsd</span></span>|<span data-ttu-id="b8303-169">消息架构。</span><span class="sxs-lookup"><span data-stu-id="b8303-169">Message schema.</span></span>|  
<span data-ttu-id="b8303-170">Services\Schema3.xsd</span><span class="sxs-lookup"><span data-stu-id="b8303-170">Services\Schema3.xsd</span></span>|<span data-ttu-id="b8303-171">消息架构。</span><span class="sxs-lookup"><span data-stu-id="b8303-171">Message schema.</span></span>|  
|<span data-ttu-id="b8303-172">\Services\Services.btproj</span><span class="sxs-lookup"><span data-stu-id="b8303-172">\Services\Services.btproj</span></span>|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="b8303-173">BizTalk 文件项目。</span><span class="sxs-lookup"><span data-stu-id="b8303-173"> BizTalk file project.</span></span>|  
|<span data-ttu-id="b8303-174">\Services\Transform_1.btm</span><span class="sxs-lookup"><span data-stu-id="b8303-174">\Services\Transform_1.btm</span></span>|<span data-ttu-id="b8303-175">映射文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-175">Map file.</span></span>|  
|<span data-ttu-id="b8303-176">\Services\Transform_2.btm</span><span class="sxs-lookup"><span data-stu-id="b8303-176">\Services\Transform_2.btm</span></span>|<span data-ttu-id="b8303-177">映射文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-177">Map file.</span></span>|  
|<span data-ttu-id="b8303-178">\Services\Transform_3.btm</span><span class="sxs-lookup"><span data-stu-id="b8303-178">\Services\Transform_3.btm</span></span>|<span data-ttu-id="b8303-179">映射文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-179">Map file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="b8303-180">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="b8303-180">How to Use This Sample</span></span>  
 <span data-ttu-id="b8303-181">请按下面的过程生成并运行 BAM 端对端示例：</span><span class="sxs-lookup"><span data-stu-id="b8303-181">Use the following procedures to build and run the BAM End-to-End sample:</span></span>  
  
-   [<span data-ttu-id="b8303-182">若要生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="b8303-182">To build and initialize this sample</span></span>](#To_Build_Sample)  
  
-   [<span data-ttu-id="b8303-183">若要运行此示例</span><span class="sxs-lookup"><span data-stu-id="b8303-183">To run this sample</span></span>](#To_Run_Sample)  
  
-   [<span data-ttu-id="b8303-184">若要查看 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="b8303-184">To view the BAM data</span></span>](#To_View_Data)  
  
##  <span data-ttu-id="b8303-185"><a name="To_Build_Sample"></a>生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="b8303-185"><a name="To_Build_Sample"></a>Build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="b8303-186">打开命令提示符以管理员身份，并运行*\<示例路径 >*\BAM\BAMEndToEnd\Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="b8303-186">Open a command prompt as Administrator, and run *\<Samples Path>*\BAM\BAMEndToEnd\Setup.bat.</span></span> <span data-ttu-id="b8303-187">Setup.bat 为此示例生成并初始化 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="b8303-187">Setup.bat builds and initializes the BAM infrastructure for this sample.</span></span> <span data-ttu-id="b8303-188">保持命令提示符处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="b8303-188">Keep the command prompt open.</span></span>  
  
2.  <span data-ttu-id="b8303-189">创建一个跟踪配置文件，以将 Orchestration1、Orchestration2 和 Orchestration3 映射到 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="b8303-189">Create a tracking profile to map Orchestration1, Orchestration2, and Orchestration3 to the BAM activity.</span></span> <span data-ttu-id="b8303-190">(由于创建跟踪配置文件是一个复杂的过程，在单独的过程调用了的详细的说明**创建跟踪配置文件**。</span><span class="sxs-lookup"><span data-stu-id="b8303-190">(Because creating the tracking profile is a complex process, the detailed instructions are in a separate procedure called **To create a tracking profile**.</span></span> <span data-ttu-id="b8303-191">此过程位于本文档后面的部分中。）</span><span class="sxs-lookup"><span data-stu-id="b8303-191">This procedure appears later in this document.)</span></span>  
  
3.  <span data-ttu-id="b8303-192">部署上一步中创建的跟踪配置文件 BamEndToEnd.btt。</span><span class="sxs-lookup"><span data-stu-id="b8303-192">Deploy the tracking profile BamEndToEnd.btt that you created in the previous step.</span></span>  <span data-ttu-id="b8303-193">在命令提示符将更改为*\<示例路径 >*\BAM\BamEndToEnd 目录。</span><span class="sxs-lookup"><span data-stu-id="b8303-193">In the command prompt change to the *\<Samples Path>*\BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="b8303-194">若要部署的跟踪配置文件，请键入以下行，，然后按**Enter**:</span><span class="sxs-lookup"><span data-stu-id="b8303-194">To deploy the tracking profile, type the following line, and then press **Enter**:</span></span>  
  
    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`
  
     <span data-ttu-id="b8303-195">[如何部署跟踪配置文件使用跟踪配置文件管理实用程序](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="b8303-195">[How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md) provides more information.</span></span>
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b8303-196">你可以忽略 ContinuationID Orch1_ 没有匹配继续符的消息。</span><span class="sxs-lookup"><span data-stu-id="b8303-196">You can ignore the message that the ContinuationID Orch1_ does not have a matching Continuation.</span></span> <span data-ttu-id="b8303-197">预期会出现此消息，因为名为 Orch1_ 的继续符是在管道组件中定义的，而不是在踪配置文件中。</span><span class="sxs-lookup"><span data-stu-id="b8303-197">This message is expected, because the continuation named Orch1_ is defined in the pipeline component, and not in the tracking profile.</span></span>  
  
##  <span data-ttu-id="b8303-198"><a name="To_Run_Sample"></a>运行此示例</span><span class="sxs-lookup"><span data-stu-id="b8303-198"><a name="To_Run_Sample"></a>Run this sample</span></span>  
  
<span data-ttu-id="b8303-199">将文件复制*\<示例路径 >*到文件夹 \BamEndToEnd\InputMessage.xml *\<示例路径 >*\BamEndToEnd\Input。</span><span class="sxs-lookup"><span data-stu-id="b8303-199">Copy the file *\<Samples Path>*\BamEndToEnd\InputMessage.xml into the folder *\<Samples Path>*\BamEndToEnd\Input.</span></span> <span data-ttu-id="b8303-200">在几秒钟后，消息消失从输入文件夹中，并输出消息出现在*\<示例路径 >*\BamEndToEnd\Output 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b8303-200">After a few seconds, the message disappears from the Input folder, and an output message appears in the *\<Samples Path>*\BamEndToEnd\Output folder.</span></span>  
  
##  <span data-ttu-id="b8303-201"><a name="To_View_Data"></a>查看 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="b8303-201"><a name="To_View_Data"></a>View the BAM data</span></span>  
  
1.  <span data-ttu-id="b8303-202">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="b8303-202">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="b8303-203">在 SQL Server Management Studio，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。</span><span class="sxs-lookup"><span data-stu-id="b8303-203">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="b8303-204">右键单击**dbo.bam_EndToEndActivity_Completed**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="b8303-204">Right-click **dbo.bam_EndToEndActivity_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="b8303-205">如果你使用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="b8303-205">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="b8303-206">右窗格中会显示 bam_EndToEndActivity_Completed 表的内容。</span><span class="sxs-lookup"><span data-stu-id="b8303-206">The contents of the bam_EndToEndActivity_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="b8303-207">表中的每一行均代表一个已完成的 EndToEndActivity 活动。</span><span class="sxs-lookup"><span data-stu-id="b8303-207">Each row in the table represents an EndToEndActivity activity that has been completed.</span></span>  
  
#### <a name="rerun-this-sample"></a><span data-ttu-id="b8303-208">重新运行此示例</span><span class="sxs-lookup"><span data-stu-id="b8303-208">Rerun this sample</span></span>  
  
1.  <span data-ttu-id="b8303-209">打开命令提示符以管理员身份，并将更改为*\<示例路径 >*\BAM\BamEndToEnd 目录。</span><span class="sxs-lookup"><span data-stu-id="b8303-209">Open a command prompt as Administrator, and change to the *\<Samples Path>*\BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="b8303-210">键入以下行：</span><span class="sxs-lookup"><span data-stu-id="b8303-210">Type the following line:</span></span>  
  
    `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  
  
    > [!NOTE]
    >  <span data-ttu-id="b8303-211">如果你未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 C 驱动器中，将"C"替换为你的安装位置的驱动器号[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b8303-211">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the C drive, replace "C" with the drive letter where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="b8303-212">运行*\<示例路径 >*\BAM\BAMEndToEnd\Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="b8303-212">Run *\<Samples Path>*\BAM\BAMEndToEnd\Cleanup.bat.</span></span> <span data-ttu-id="b8303-213">Cleanup.bat 移除此示例的 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="b8303-213">Cleanup.bat removes the BAM infrastructure for this sample.</span></span>  
  
3.  <span data-ttu-id="b8303-214">执行中的步骤**生成并初始化此示例**本主题中的部分。</span><span class="sxs-lookup"><span data-stu-id="b8303-214">Perform the steps in **To build and initialize this sample** section in this topic.</span></span>  
  
##  <span data-ttu-id="b8303-215"><a name="TPE_procedure"></a>创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b8303-215"><a name="TPE_procedure"></a>Create a tracking profile</span></span>  
  
1.  <span data-ttu-id="b8303-216">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b8303-216">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)].</span></span> <span data-ttu-id="b8303-217">右键单击**跟踪配置文件编辑器**，和**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="b8303-217">Right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="b8303-218">在左窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处以导入 BAM 活动定义**。</span><span class="sxs-lookup"><span data-stu-id="b8303-218">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
3.  <span data-ttu-id="b8303-219">在**BAM 活动定义名称**部分**导入 BAM 活动定义**对话框中，选择**EndToEndActivity**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="b8303-219">In the  **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **EndToEndActivity**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b8303-220">在右窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处选择的事件源**。</span><span class="sxs-lookup"><span data-stu-id="b8303-220">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
5.  <span data-ttu-id="b8303-221">在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b8303-221">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="b8303-222">在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration1**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="b8303-222">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration1**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b8303-223">在左窗格中**跟踪配置文件编辑器**窗口中，右键单击**EndToEndActivity**，然后单击**新 ContinuationID**。</span><span class="sxs-lookup"><span data-stu-id="b8303-223">In the left pane of the **Tracking Profile Editor** window, right-click **EndToEndActivity**, and then click **New ContinuationID**.</span></span> <span data-ttu-id="b8303-224">命名新的延续 ID **Orch1_**。</span><span class="sxs-lookup"><span data-stu-id="b8303-224">Name the new continuation ID **Orch1_**.</span></span> <span data-ttu-id="b8303-225">重复此步骤以创建两个多个延续 Id 名为**Orch2_**和**Orch3_**。</span><span class="sxs-lookup"><span data-stu-id="b8303-225">Repeat this step to create two more continuation IDs named **Orch2_** and **Orch3_**.</span></span>  
  
8.  <span data-ttu-id="b8303-226">右键单击**EndToEndActivity**，然后单击**新的延续**。</span><span class="sxs-lookup"><span data-stu-id="b8303-226">Right-click **EndToEndActivity**, and then click **New Continuation**.</span></span> <span data-ttu-id="b8303-227">命名新的延续**Orch2_**。</span><span class="sxs-lookup"><span data-stu-id="b8303-227">Name the new continuation **Orch2_**.</span></span> <span data-ttu-id="b8303-228">重复此步骤以创建名为的另一个延续**Orch3_**。</span><span class="sxs-lookup"><span data-stu-id="b8303-228">Repeat this step to create another continuation named **Orch3_**.</span></span>  
  
9. <span data-ttu-id="b8303-229">右键单击**Receive1**形状，并依次**上下文属性架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-229">Right-click the **Receive1** shape, and then click **Context Property Schemas**.</span></span>  
  
10. <span data-ttu-id="b8303-230">滚动到末尾**上下文属性名称**列表，，然后双击**BAMEndToEnd.Services.PropertySchema.DocumentID**。</span><span class="sxs-lookup"><span data-stu-id="b8303-230">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  
  
11. <span data-ttu-id="b8303-231">展开**\<架构 >**，然后拖动**DocumentID**到右窗格中**Orch1_**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-231">Expand **\<Schema>**, and then drag **DocumentID** in the right pane to **Orch1_** in the left pane.</span></span>  
  
12. <span data-ttu-id="b8303-232">单击文件夹图标带有箭头 (![使用文件夹和向上箭头的按钮](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-232">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  
  
13. <span data-ttu-id="b8303-233">拖动**Receive1**到右窗格中的形状**SBegin1**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-233">Drag the **Receive1** shape in the right pane to **SBegin1** in the left pane.</span></span>  
  
14. <span data-ttu-id="b8303-234">拖动**StartOrchestration_1**到右窗格中的形状**SEnd1**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-234">Drag the **StartOrchestration_1** shape in the right pane to **SEnd1** in the left pane.</span></span>  
  
15. <span data-ttu-id="b8303-235">右键单击**StartOrchestration_1**形状，并依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-235">Right-click the **StartOrchestration_1** shape, and then click **Message Payload Schemas**.</span></span>  
  
16. <span data-ttu-id="b8303-236">在双击包含"Message_2"的值的行**消息**列和值"MessageBody"中**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="b8303-236">Double-click the row that contains the value “Message_2” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  
  
     <span data-ttu-id="b8303-237">![键入消息负载架构显示消息和 #95; 2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span><span class="sxs-lookup"><span data-stu-id="b8303-237">![TPE Message Payload schema showing message&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span></span>  
  
17. <span data-ttu-id="b8303-238">展开**Schema2**，然后拖动**Data2**到右窗格中**Data1**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-238">Expand **Schema2**, and then drag **Data2** in the right pane to **Data1** in the left pane.</span></span>  
  
18. <span data-ttu-id="b8303-239">单击**选择事件源**，然后单击**选择上下文属性**。</span><span class="sxs-lookup"><span data-stu-id="b8303-239">Click **Select Event Source**, and then click **Select Context Property**.</span></span>  
  
19. <span data-ttu-id="b8303-240">滚动到末尾**上下文属性名称**列表，，然后双击**BAMEndToEnd.Services.PropertySchema.DocumentID**。</span><span class="sxs-lookup"><span data-stu-id="b8303-240">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  
  
20. <span data-ttu-id="b8303-241">展开**\<架构 >**，然后拖动**DocumentID**到**Orch2_**延续的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-241">Expand **\<Schema>**, and then drag **DocumentID** to the **Orch2_** continuation in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8303-242">不要混淆 Orch2_ 延续替换 Orch2_ 延续 id。</span><span class="sxs-lookup"><span data-stu-id="b8303-242">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="b8303-243">表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="b8303-243">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
21. <span data-ttu-id="b8303-244">单击**选择事件源**，然后单击**选择业务流程计划**。</span><span class="sxs-lookup"><span data-stu-id="b8303-244">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  
  
22. <span data-ttu-id="b8303-245">在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b8303-245">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  
  
23. <span data-ttu-id="b8303-246">在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration2**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="b8303-246">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration2**, and then click **OK**.</span></span>  
  
24. <span data-ttu-id="b8303-247">右键单击**ConstructMessage_1**形状，并依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-247">Right-click the **ConstructMessage_1** shape, and then click **Message Payload Schemas**.</span></span>  
  
25. <span data-ttu-id="b8303-248">在双击包含"Message_3"的值的行**消息**列和值"BAMPart"中**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="b8303-248">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  
  
26. <span data-ttu-id="b8303-249">展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch2_**延续的左窗格中的 ID。</span><span class="sxs-lookup"><span data-stu-id="b8303-249">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch2_** continuation ID in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8303-250">不要混淆 Orch2_ 延续替换 Orch2_ 延续 id。</span><span class="sxs-lookup"><span data-stu-id="b8303-250">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="b8303-251">表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="b8303-251">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
27. <span data-ttu-id="b8303-252">单击文件夹图标带有箭头 (![使用文件夹和向上按钮 &#45; 箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-252">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  
  
28. <span data-ttu-id="b8303-253">拖动**ConstructMessage_1**到右窗格中的形状**SBegin2**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-253">Drag the **ConstructMessage_1** shape in the right pane to **SBegin2** in the left pane.</span></span>  
  
29. <span data-ttu-id="b8303-254">拖动**Send_1**到右窗格中的形状**SEnd2**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-254">Drag the **Send_1** shape in the right pane to **SEnd2** in the left pane.</span></span>  
  
30. <span data-ttu-id="b8303-255">右键单击**Send_1**形状，并依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-255">Right-click the **Send_1** shape, and then click **Message Payload Schemas**.</span></span>  
  
31. <span data-ttu-id="b8303-256">在双击包含"Message_3"的值的行**消息**列和值"MessageBody"中**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="b8303-256">Double-click the row that contains the value “Message_3” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  
  
32. <span data-ttu-id="b8303-257">展开**Schema3**，然后拖动**Data3**到右窗格中**Data2**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-257">Expand **Schema3**, and then drag **Data3** in the right pane to **Data2** in the left pane.</span></span>  
  
33. <span data-ttu-id="b8303-258">从右侧窗格上的下拉列表列表中选择**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-258">From the drop-down list above the right pane, select **Message Payload Schemas**.</span></span>  
  
34. <span data-ttu-id="b8303-259">在双击包含"Message_3"的值的行**消息**列和值"BAMPart"中**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="b8303-259">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  
  
35. <span data-ttu-id="b8303-260">展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch3_**延续的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-260">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8303-261">不要混淆 Orch3_ 延续替换 Orch3_ 延续 id。</span><span class="sxs-lookup"><span data-stu-id="b8303-261">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="b8303-262">表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="b8303-262">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
36. <span data-ttu-id="b8303-263">单击**选择事件源**，然后单击**选择业务流程计划**。</span><span class="sxs-lookup"><span data-stu-id="b8303-263">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  
  
37. <span data-ttu-id="b8303-264">在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b8303-264">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  
  
38. <span data-ttu-id="b8303-265">在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration3**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="b8303-265">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration3**, and then click **OK**.</span></span>  
  
39. <span data-ttu-id="b8303-266">右键单击**Receive1**形状，并依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-266">Right-click the **Receive1** shape, and then click **Message Payload Schemas**.</span></span>  
  
40. <span data-ttu-id="b8303-267">在双击包含"Message_3"的值的行**消息**列和值"BAMPart"中**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="b8303-267">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  
  
41. <span data-ttu-id="b8303-268">展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch3_**延续的左窗格中的 ID。</span><span class="sxs-lookup"><span data-stu-id="b8303-268">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation ID in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8303-269">不要混淆 Orch3_ 延续替换 Orch3_ 延续 id。</span><span class="sxs-lookup"><span data-stu-id="b8303-269">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="b8303-270">表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="b8303-270">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
42. <span data-ttu-id="b8303-271">单击文件夹图标带有箭头 (![使用文件夹和向上箭头的按钮](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="b8303-271">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  
  
43. <span data-ttu-id="b8303-272">拖动**Receive1**到右窗格中的形状**SBegin3**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-272">Drag the **Receive1** shape in the right pane to **SBegin3** in the left pane.</span></span>  
  
44. <span data-ttu-id="b8303-273">拖动**Send_1**到右窗格中的形状**SEnd3**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-273">Drag the **Send_1** shape in the right pane to **SEnd3** in the left pane.</span></span>  
  
45. <span data-ttu-id="b8303-274">右键单击**Send_1**形状，并依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="b8303-274">Right-click the **Send_1** shape, and then click **Message Payload Schema**.</span></span>  
  
46. <span data-ttu-id="b8303-275">展开**Schema3**，然后拖动**Data3**到右窗格中**Data3**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b8303-275">Expand **Schema3**, and then drag **Data3** in the right pane to **Data3** in the left pane.</span></span>  
  
47. <span data-ttu-id="b8303-276">右键单击**DocumentID**下面**Orch2_**延续任务，，然后单击**集端口映射**。</span><span class="sxs-lookup"><span data-stu-id="b8303-276">Right-click **DocumentID** below the **Orch2_** continuation, and then click **Set Port Mappings**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8303-277">不要混淆 Orch2_ 延续替换 Orch2_ 延续 id。</span><span class="sxs-lookup"><span data-stu-id="b8303-277">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="b8303-278">表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="b8303-278">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
48. <span data-ttu-id="b8303-279">在**选择端口**部分**选择端口**对话框中，单击**BamEndToEnd_ReceivePort**，单击大于-号 ( **>**)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b8303-279">In the **Select Ports** section of the **Select Ports** dialog box, click **BamEndToEnd_ReceivePort**, click the greater-than sign (**>**), and then click **OK**.</span></span>  
  
49. <span data-ttu-id="b8303-280">保存跟踪配置文件到*\<示例路径 >*\BAM\BamEndToEnd\BamEndToEnd.btt。</span><span class="sxs-lookup"><span data-stu-id="b8303-280">Save the tracking profile to *\<Samples Path>*\BAM\BamEndToEnd\BamEndToEnd.btt.</span></span>  
  
## <a name="important-details"></a><span data-ttu-id="b8303-281">重要详细信息</span><span class="sxs-lookup"><span data-stu-id="b8303-281">Important details</span></span>  
 <span data-ttu-id="b8303-282">管道不支持跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="b8303-282">Tracking profiles are not supported for pipelines.</span></span> <span data-ttu-id="b8303-283">但是，对的调用**BeginActivity**在管道组件是在业务流程中使用 ActivityID 相同。</span><span class="sxs-lookup"><span data-stu-id="b8303-283">However, the call to **BeginActivity** in the pipeline component is the same as using ActivityID in an orchestration.</span></span> <span data-ttu-id="b8303-284">调用**EnableContinuation**等同于业务流程中使用延续。</span><span class="sxs-lookup"><span data-stu-id="b8303-284">The call to **EnableContinuation** is the same as using a continuation in an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8303-285">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8303-285">See Also</span></span>  
 [<span data-ttu-id="b8303-286">业务活动监视 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="b8303-286">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)