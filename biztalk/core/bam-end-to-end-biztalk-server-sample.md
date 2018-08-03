---
title: 在 BizTalk Server 中的 BAM 端到端示例 |Microsoft Docs
description: 有关如何关联来自多个组件在 BizTalk Server 中使用业务活动监视的事件的方案
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fca4bd709a872df739d82fbdfbeabc78df9d09f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006494"
---
# <a name="bam-end-to-end-biztalk-server-sample"></a><span data-ttu-id="acb00-103">BAM 端对端（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="acb00-103">BAM End-to-End (BizTalk Server Sample)</span></span>
<span data-ttu-id="acb00-104">端到端示例演示如何使用 BAM 关联来自多个组件 （在这种情况下，三个业务流程和管道） 的事件。</span><span class="sxs-lookup"><span data-stu-id="acb00-104">The End-to-End sample demonstrates how to correlate events from multiple components (in this case, three orchestrations and a pipeline) by using BAM.</span></span>  

 <span data-ttu-id="acb00-105">BAM 重新构造了跨管道组件和业务流程的业务活动。</span><span class="sxs-lookup"><span data-stu-id="acb00-105">BAM reconstructs the business activity that spans the pipeline component and orchestrations.</span></span> <span data-ttu-id="acb00-106">在最低级别，这是通过调用**EventStream.EnableContinuation**从每个实现组件的更多事件的活动。</span><span class="sxs-lookup"><span data-stu-id="acb00-106">At the lowest level, this works by calls to **EventStream.EnableContinuation** from each implementation component that expects more events for the activity.</span></span> <span data-ttu-id="acb00-107">在调用**EnableContinuation**是显式的同时通过将继续符文件夹添加到另一个调度和 ContinuationID 文件夹到遵循的计划中的跟踪配置文件进行 Orchestration1 和 Orchestration2 中的调用它。</span><span class="sxs-lookup"><span data-stu-id="acb00-107">The call to **EnableContinuation** is explicit, while calls in Orchestration1 and Orchestration2 are made by adding a Continuation folder to the Tracking profile in one schedule, and a ContinuationID folder to the schedule that follows it.</span></span>  

 <span data-ttu-id="acb00-108">下图说明了本示例中使用的工作流。</span><span class="sxs-lookup"><span data-stu-id="acb00-108">The following diagram illustrates the workflow used in the sample.</span></span>  

 <span data-ttu-id="acb00-109">![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")</span><span class="sxs-lookup"><span data-stu-id="acb00-109">![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")</span></span>  


## <a name="what-this-sample-does"></a><span data-ttu-id="acb00-110">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="acb00-110">What This Sample Does</span></span>  
 <span data-ttu-id="acb00-111">BAM 端对端示例显示如何使用 BAM 从管道和多个业务流程收集信息并更新单个活动。</span><span class="sxs-lookup"><span data-stu-id="acb00-111">The BAM end-to-end sample shows how you can use BAM to gather information from a pipeline and multiple orchestrations and update a single activity.</span></span>  

## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="acb00-112">本示例的设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="acb00-112">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="acb00-113">BAM 端对端示例旨在阐释下列活动：</span><span class="sxs-lookup"><span data-stu-id="acb00-113">The BAM end-to-end sample was designed to illustrate the following activities:</span></span>  

-   <span data-ttu-id="acb00-114">在管道中使用 BAM。</span><span class="sxs-lookup"><span data-stu-id="acb00-114">Using BAM within a pipeline.</span></span>  

-   <span data-ttu-id="acb00-115">使用跟踪配置文件编辑器 (TPE) 将活动项映射到业务流程中的形状和消息的元素。</span><span class="sxs-lookup"><span data-stu-id="acb00-115">Using the Tracking Profile Editor (TPE) to map activity items to shapes in an orchestration and elements of a message.</span></span>  

-   <span data-ttu-id="acb00-116">当一个解决方案的多个部分都作用于活动时，使用继续符使活动保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="acb00-116">Using continuations to keep an activity active when multiple pieces of a solution contribute to the activity.</span></span>  


<span data-ttu-id="acb00-117">本示例的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="acb00-117">The sample works as follows:</span></span>  

1.  <span data-ttu-id="acb00-118">从输入的消息中检索*\<示例路径\>* \BamEndToEnd\Input 文件夹。</span><span class="sxs-lookup"><span data-stu-id="acb00-118">An input message is retrieved from the *\<Samples Path\>* \BamEndToEnd\Input folder.</span></span>  

2.  <span data-ttu-id="acb00-119">管道组件向消息分配唯一的 DocumentID，然后使用 BAM API 开始一个新 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="acb00-119">The pipeline component assigns a unique DocumentID to the message, and uses the BAM API to begin a new BAM activity.</span></span> <span data-ttu-id="acb00-120">将此 DocumentID 作为此输入消息的一个单独部分附加，以使其可用于业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-120">The DocumentID is attached as a separate part of the input message to make it available to the orchestrations.</span></span>  

3.  <span data-ttu-id="acb00-121">在收到此输入消息时激活服务 Orchestration1。</span><span class="sxs-lookup"><span data-stu-id="acb00-121">The service Orchestration1 is activated when the input message is received.</span></span>  

4.  <span data-ttu-id="acb00-122">Orchestration1 修改此输入消息，然后将其作为参数传递给 Orchestration2。</span><span class="sxs-lookup"><span data-stu-id="acb00-122">Orchestration1 modifies the input message and passes it as a parameter to Orchestration2.</span></span>  

5.  <span data-ttu-id="acb00-123">Orchestration2 修改此输入消息，然后将其发送给 MessageBox 数据库，这便激活了 Orchestration3。</span><span class="sxs-lookup"><span data-stu-id="acb00-123">Orchestration2 modifies the input message and sends it to the MessageBox database, which activates Orchestration3.</span></span>  

6.  <span data-ttu-id="acb00-124">Orchestration3 修改此消息，并将其写入到的文件夹*\<示例路径\>* \BamEndToEnd\Output。</span><span class="sxs-lookup"><span data-stu-id="acb00-124">Orchestration3 modifies the message and writes it to the folder *\<Samples Path\>* \BamEndToEnd\Output.</span></span>  

7.  <span data-ttu-id="acb00-125">每个业务流程都会更新 BAM 活动中的活动项。</span><span class="sxs-lookup"><span data-stu-id="acb00-125">Each orchestration updates activity items in the BAM activity.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="acb00-126">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="acb00-126">Where to Find This Sample</span></span>  
 <span data-ttu-id="acb00-127">您可以找到在此示例*\<示例路径\>* \BAM\BamEndToEnd。</span><span class="sxs-lookup"><span data-stu-id="acb00-127">You can find this sample at *\<Samples Path\>* \BAM\BamEndToEnd.</span></span>  

 <span data-ttu-id="acb00-128">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="acb00-128">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                        <span data-ttu-id="acb00-129">文件</span><span class="sxs-lookup"><span data-stu-id="acb00-129">File(s)</span></span>                                        |                                         <span data-ttu-id="acb00-130">Description</span><span class="sxs-lookup"><span data-stu-id="acb00-130">Description</span></span>                                          |
|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
|                                    <span data-ttu-id="acb00-131">BamEndToEnd.sln</span><span class="sxs-lookup"><span data-stu-id="acb00-131">BamEndToEnd.sln</span></span>                                    |                               <span data-ttu-id="acb00-132">BAM 端对端示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="acb00-132">BAM End-to-End sample solution.</span></span>                                |
|                                    <span data-ttu-id="acb00-133">BamEndToEnd.xls</span><span class="sxs-lookup"><span data-stu-id="acb00-133">BamEndToEnd.xls</span></span>                                    |                                 <span data-ttu-id="acb00-134">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="acb00-134">BAM definition style sheet.</span></span>                                  |
|                                    <span data-ttu-id="acb00-135">BamEndToEnd.xml</span><span class="sxs-lookup"><span data-stu-id="acb00-135">BamEndToEnd.xml</span></span>                                    |                                     <span data-ttu-id="acb00-136">BAM 定义 XML。</span><span class="sxs-lookup"><span data-stu-id="acb00-136">BAM definition XML.</span></span>                                      |
|                                <span data-ttu-id="acb00-137">BAMEndToEndBinding.xml</span><span class="sxs-lookup"><span data-stu-id="acb00-137">BAMEndToEndBinding.xml</span></span>                                 |                                         <span data-ttu-id="acb00-138">BAM 绑定。</span><span class="sxs-lookup"><span data-stu-id="acb00-138">BAM binding.</span></span>                                         |
|                                      <span data-ttu-id="acb00-139">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="acb00-139">Cleanup.bat</span></span>                                      |                              <span data-ttu-id="acb00-140">用于取消部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-140">Batch file to undeploy the sample.</span></span>                              |
|                                   <span data-ttu-id="acb00-141">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="acb00-141">InputMessage.xml</span></span>                                    |                                        <span data-ttu-id="acb00-142">输入消息。</span><span class="sxs-lookup"><span data-stu-id="acb00-142">Input message.</span></span>                                        |
|                                       <span data-ttu-id="acb00-143">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="acb00-143">Setup.bat</span></span>                                       |                         <span data-ttu-id="acb00-144">用于编译和部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-144">Batch file to compile and deploy the sample.</span></span>                         |
|                              <span data-ttu-id="acb00-145">\Components\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="acb00-145">\Components\AssemblyInfo.cs</span></span>                              |                                   <span data-ttu-id="acb00-146">管道组件代码。</span><span class="sxs-lookup"><span data-stu-id="acb00-146">Pipeline component code.</span></span>                                   |
|                       <span data-ttu-id="acb00-147">\Components\BAMMessagePartPLComponent.cs</span><span class="sxs-lookup"><span data-stu-id="acb00-147">\Components\BAMMessagePartPLComponent.cs</span></span>                        |                                   <span data-ttu-id="acb00-148">管道组件代码。</span><span class="sxs-lookup"><span data-stu-id="acb00-148">Pipeline component code.</span></span>                                   |
|                             <span data-ttu-id="acb00-149">\Components\Components.csproj</span><span class="sxs-lookup"><span data-stu-id="acb00-149">\Components\Components.csproj</span></span>                             |                                 <span data-ttu-id="acb00-150">管道组件项目。</span><span class="sxs-lookup"><span data-stu-id="acb00-150">Pipeline component project.</span></span>                                  |
| <span data-ttu-id="acb00-151">\Messages\InputMessage01.xml</span><span class="sxs-lookup"><span data-stu-id="acb00-151">\Messages\InputMessage01.xml</span></span><br /><br /> <span data-ttu-id="acb00-152">...</span><span class="sxs-lookup"><span data-stu-id="acb00-152">...</span></span><br /><br /> <span data-ttu-id="acb00-153">\Messages\InputMessage10.xml</span><span class="sxs-lookup"><span data-stu-id="acb00-153">\Messages\InputMessage10.xml</span></span> |                                    <span data-ttu-id="acb00-154">示例输入的消息。</span><span class="sxs-lookup"><span data-stu-id="acb00-154">Sample input messages.</span></span>                                    |
|                               <span data-ttu-id="acb00-155">\Services\BAMInbound.btp</span><span class="sxs-lookup"><span data-stu-id="acb00-155">\Services\BAMInbound.btp</span></span>                                |                                    <span data-ttu-id="acb00-156">入站管道文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-156">Inbound pipeline file.</span></span>                                    |
|                              <span data-ttu-id="acb00-157">\Services\BAMPartSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="acb00-157">\Services\BAMPartSchema.xsd</span></span>                              |                                   <span data-ttu-id="acb00-158">BAM 部分消息架构。</span><span class="sxs-lookup"><span data-stu-id="acb00-158">BAM part message schema.</span></span>                                   |
|                             <span data-ttu-id="acb00-159">\Services\Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="acb00-159">\Services\Orchestration1.odx</span></span>                              |                                        <span data-ttu-id="acb00-160">业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-160">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="acb00-161">\Services\Orchestration2.odx</span><span class="sxs-lookup"><span data-stu-id="acb00-161">\Services\Orchestration2.odx</span></span>                              |                                        <span data-ttu-id="acb00-162">业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-162">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="acb00-163">\Services\Orchestration3.odx</span><span class="sxs-lookup"><span data-stu-id="acb00-163">\Services\Orchestration3.odx</span></span>                              |                                        <span data-ttu-id="acb00-164">业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-164">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="acb00-165">\Services\PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="acb00-165">\Services\PropertySchema.xsd</span></span>                              |                                       <span data-ttu-id="acb00-166">属性架构。</span><span class="sxs-lookup"><span data-stu-id="acb00-166">Property schema.</span></span>                                       |
|                                 <span data-ttu-id="acb00-167">\Services\Schema1.xsd</span><span class="sxs-lookup"><span data-stu-id="acb00-167">\Services\Schema1.xsd</span></span>                                 |                                       <span data-ttu-id="acb00-168">消息架构。</span><span class="sxs-lookup"><span data-stu-id="acb00-168">Message schema.</span></span>                                        |
|                                 <span data-ttu-id="acb00-169">\Services\Schema2.xsd</span><span class="sxs-lookup"><span data-stu-id="acb00-169">\Services\Schema2.xsd</span></span>                                 |                                       <span data-ttu-id="acb00-170">消息架构。</span><span class="sxs-lookup"><span data-stu-id="acb00-170">Message schema.</span></span>                                        |
|                                 <span data-ttu-id="acb00-171">Services\Schema3.xsd</span><span class="sxs-lookup"><span data-stu-id="acb00-171">Services\Schema3.xsd</span></span>                                  |                                       <span data-ttu-id="acb00-172">消息架构。</span><span class="sxs-lookup"><span data-stu-id="acb00-172">Message schema.</span></span>                                        |
|                               <span data-ttu-id="acb00-173">\Services\Services.btproj</span><span class="sxs-lookup"><span data-stu-id="acb00-173">\Services\Services.btproj</span></span>                               | [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="acb00-174"> 文件的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="acb00-174"> BizTalk file project.</span></span> |
|                               <span data-ttu-id="acb00-175">\Services\Transform_1.btm</span><span class="sxs-lookup"><span data-stu-id="acb00-175">\Services\Transform_1.btm</span></span>                               |                                          <span data-ttu-id="acb00-176">映射文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-176">Map file.</span></span>                                           |
|                               <span data-ttu-id="acb00-177">\Services\Transform_2.btm</span><span class="sxs-lookup"><span data-stu-id="acb00-177">\Services\Transform_2.btm</span></span>                               |                                          <span data-ttu-id="acb00-178">映射文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-178">Map file.</span></span>                                           |
|                               <span data-ttu-id="acb00-179">\Services\Transform_3.btm</span><span class="sxs-lookup"><span data-stu-id="acb00-179">\Services\Transform_3.btm</span></span>                               |                                          <span data-ttu-id="acb00-180">映射文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-180">Map file.</span></span>                                           |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="acb00-181">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="acb00-181">How to Use This Sample</span></span>  
 <span data-ttu-id="acb00-182">请按下面的过程生成并运行 BAM 端对端示例：</span><span class="sxs-lookup"><span data-stu-id="acb00-182">Use the following procedures to build and run the BAM End-to-End sample:</span></span>  

-   [<span data-ttu-id="acb00-183">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="acb00-183">To build and initialize this sample</span></span>](#To_Build_Sample)  

-   [<span data-ttu-id="acb00-184">若要运行此示例</span><span class="sxs-lookup"><span data-stu-id="acb00-184">To run this sample</span></span>](#To_Run_Sample)  

-   [<span data-ttu-id="acb00-185">若要查看 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="acb00-185">To view the BAM data</span></span>](#To_View_Data)  

##  <a name="To_Build_Sample"></a><span data-ttu-id="acb00-186">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="acb00-186">Build and initialize this sample</span></span>  

1.  <span data-ttu-id="acb00-187">打开命令提示符下以管理员身份，并运行*\<示例路径\>* \BAM\BAMEndToEnd\Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="acb00-187">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BAMEndToEnd\Setup.bat.</span></span> <span data-ttu-id="acb00-188">Setup.bat 为此示例生成并初始化 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="acb00-188">Setup.bat builds and initializes the BAM infrastructure for this sample.</span></span> <span data-ttu-id="acb00-189">保持命令提示符处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="acb00-189">Keep the command prompt open.</span></span>  

2.  <span data-ttu-id="acb00-190">创建一个跟踪配置文件，以将 Orchestration1、Orchestration2 和 Orchestration3 映射到 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="acb00-190">Create a tracking profile to map Orchestration1, Orchestration2, and Orchestration3 to the BAM activity.</span></span> <span data-ttu-id="acb00-191">(在名为一个单独的过程中创建跟踪配置文件是一个复杂的过程，因为的详细的说明**创建跟踪配置文件**。</span><span class="sxs-lookup"><span data-stu-id="acb00-191">(Because creating the tracking profile is a complex process, the detailed instructions are in a separate procedure called **To create a tracking profile**.</span></span> <span data-ttu-id="acb00-192">此过程位于本文档后面的部分中。）</span><span class="sxs-lookup"><span data-stu-id="acb00-192">This procedure appears later in this document.)</span></span>  

3.  <span data-ttu-id="acb00-193">部署上一步中创建的跟踪配置文件 BamEndToEnd.btt。</span><span class="sxs-lookup"><span data-stu-id="acb00-193">Deploy the tracking profile BamEndToEnd.btt that you created in the previous step.</span></span>  <span data-ttu-id="acb00-194">在命令提示符将更改为*\<示例路径\>* \BAM\BamEndToEnd 目录。</span><span class="sxs-lookup"><span data-stu-id="acb00-194">In the command prompt change to the *\<Samples Path\>* \BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="acb00-195">若要部署跟踪配置文件，请键入以下行，然后按**Enter**:</span><span class="sxs-lookup"><span data-stu-id="acb00-195">To deploy the tracking profile, type the following line, and then press **Enter**:</span></span>  

    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`

     <span data-ttu-id="acb00-196">[如何部署跟踪配置文件使用跟踪配置文件管理实用程序](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="acb00-196">[How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md) provides more information.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="acb00-197">你可以忽略 ContinuationID Orch1_ 没有匹配继续符的消息。</span><span class="sxs-lookup"><span data-stu-id="acb00-197">You can ignore the message that the ContinuationID Orch1_ does not have a matching Continuation.</span></span> <span data-ttu-id="acb00-198">预期会出现此消息，因为名为 Orch1_ 的继续符是在管道组件中定义的，而不是在踪配置文件中。</span><span class="sxs-lookup"><span data-stu-id="acb00-198">This message is expected, because the continuation named Orch1_ is defined in the pipeline component, and not in the tracking profile.</span></span>  

##  <a name="To_Run_Sample"></a><span data-ttu-id="acb00-199">运行此示例</span><span class="sxs-lookup"><span data-stu-id="acb00-199">Run this sample</span></span>  

<span data-ttu-id="acb00-200">将文件复制*\<示例路径\>* \BamEndToEnd\InputMessage.xml 到文件夹*\<示例路径\>* \BamEndToEnd\Input。</span><span class="sxs-lookup"><span data-stu-id="acb00-200">Copy the file *\<Samples Path\>* \BamEndToEnd\InputMessage.xml into the folder *\<Samples Path\>* \BamEndToEnd\Input.</span></span> <span data-ttu-id="acb00-201">在几秒钟后，该消息消失从 Input 文件夹中，并且输出消息将出现在*\<示例路径\>* \BamEndToEnd\Output 文件夹。</span><span class="sxs-lookup"><span data-stu-id="acb00-201">After a few seconds, the message disappears from the Input folder, and an output message appears in the *\<Samples Path\>* \BamEndToEnd\Output folder.</span></span>  

##  <a name="To_View_Data"></a><span data-ttu-id="acb00-202">查看 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="acb00-202">View the BAM data</span></span>  

1.  <span data-ttu-id="acb00-203">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="acb00-203">Open SQL Server Management Studio.</span></span>  

2.  <span data-ttu-id="acb00-204">在 SQL Server Management Studio 中，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。</span><span class="sxs-lookup"><span data-stu-id="acb00-204">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  

3.  <span data-ttu-id="acb00-205">右键单击**dbo.bam_EndToEndActivity_Completed**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="acb00-205">Right-click **dbo.bam_EndToEndActivity_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="acb00-206">如果使用 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="acb00-206">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  

     <span data-ttu-id="acb00-207">右窗格中会显示 bam_EndToEndActivity_Completed 表的内容。</span><span class="sxs-lookup"><span data-stu-id="acb00-207">The contents of the bam_EndToEndActivity_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="acb00-208">表中的每一行均代表一个已完成的 EndToEndActivity 活动。</span><span class="sxs-lookup"><span data-stu-id="acb00-208">Each row in the table represents an EndToEndActivity activity that has been completed.</span></span>  

#### <a name="rerun-this-sample"></a><span data-ttu-id="acb00-209">重新运行此示例</span><span class="sxs-lookup"><span data-stu-id="acb00-209">Rerun this sample</span></span>  

1. <span data-ttu-id="acb00-210">打开命令提示符以管理员身份，并将更改为*\<示例路径\>* \BAM\BamEndToEnd 目录。</span><span class="sxs-lookup"><span data-stu-id="acb00-210">Open a command prompt as Administrator, and change to the *\<Samples Path\>* \BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="acb00-211">键入以下行：</span><span class="sxs-lookup"><span data-stu-id="acb00-211">Type the following line:</span></span>  

   `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  

   > [!NOTE]
   >  <span data-ttu-id="acb00-212">如果未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 C 驱动器中，将"C"替换为你安装的驱动器号[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="acb00-212">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the C drive, replace "C" with the drive letter where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

2. <span data-ttu-id="acb00-213">运行*\<示例路径\>* \BAM\BAMEndToEnd\Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="acb00-213">Run *\<Samples Path\>* \BAM\BAMEndToEnd\Cleanup.bat.</span></span> <span data-ttu-id="acb00-214">Cleanup.bat 会删除此示例的 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="acb00-214">Cleanup.bat removes the BAM infrastructure for this sample.</span></span>  

3. <span data-ttu-id="acb00-215">执行中的步骤**生成并初始化本示例**本主题中的部分。</span><span class="sxs-lookup"><span data-stu-id="acb00-215">Perform the steps in **To build and initialize this sample** section in this topic.</span></span>  

##  <a name="TPE_procedure"></a><span data-ttu-id="acb00-216">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="acb00-216">Create a tracking profile</span></span>  

1. <span data-ttu-id="acb00-217">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="acb00-217">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)].</span></span> <span data-ttu-id="acb00-218">右键单击**跟踪配置文件编辑器**，并**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="acb00-218">Right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>  

2. <span data-ttu-id="acb00-219">在左窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处可导入 BAM 活动定义**。</span><span class="sxs-lookup"><span data-stu-id="acb00-219">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  

3. <span data-ttu-id="acb00-220">中**BAM 活动定义名称**一部分**导入 BAM 活动定义**对话框中，选择**EndToEndActivity**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="acb00-220">In the  **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **EndToEndActivity**, and then click **OK**.</span></span>  

4. <span data-ttu-id="acb00-221">在右窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处可选择事件源**。</span><span class="sxs-lookup"><span data-stu-id="acb00-221">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  

5. <span data-ttu-id="acb00-222">在中**程序集名称**一部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="acb00-222">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

6. <span data-ttu-id="acb00-223">在中**业务流程名称**一部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration1**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="acb00-223">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration1**, and then click **OK**.</span></span>  

7. <span data-ttu-id="acb00-224">在左窗格中**跟踪配置文件编辑器**窗口中，右键单击**EndToEndActivity**，然后单击**新建 ContinuationID**。</span><span class="sxs-lookup"><span data-stu-id="acb00-224">In the left pane of the **Tracking Profile Editor** window, right-click **EndToEndActivity**, and then click **New ContinuationID**.</span></span> <span data-ttu-id="acb00-225">命名新的继续符 ID **Orch1_**。</span><span class="sxs-lookup"><span data-stu-id="acb00-225">Name the new continuation ID **Orch1_**.</span></span> <span data-ttu-id="acb00-226">重复此步骤以创建两个多个继续符 Id 名为**Orch2_** 并**Orch3_**。</span><span class="sxs-lookup"><span data-stu-id="acb00-226">Repeat this step to create two more continuation IDs named **Orch2_** and **Orch3_**.</span></span>  

8. <span data-ttu-id="acb00-227">右键单击**EndToEndActivity**，然后单击**新的延续**。</span><span class="sxs-lookup"><span data-stu-id="acb00-227">Right-click **EndToEndActivity**, and then click **New Continuation**.</span></span> <span data-ttu-id="acb00-228">命名新的延续**Orch2_**。</span><span class="sxs-lookup"><span data-stu-id="acb00-228">Name the new continuation **Orch2_**.</span></span> <span data-ttu-id="acb00-229">重复此步骤以创建名为另一个继续符**Orch3_**。</span><span class="sxs-lookup"><span data-stu-id="acb00-229">Repeat this step to create another continuation named **Orch3_**.</span></span>  

9. <span data-ttu-id="acb00-230">右键单击**Receive1**形状，然后依次**上下文属性架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-230">Right-click the **Receive1** shape, and then click **Context Property Schemas**.</span></span>  

10. <span data-ttu-id="acb00-231">滚动到末尾**上下文属性名称**列表，然后再双击**BAMEndToEnd.Services.PropertySchema.DocumentID**。</span><span class="sxs-lookup"><span data-stu-id="acb00-231">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  

11. <span data-ttu-id="acb00-232">展开**\<架构\>**，然后将拖**DocumentID**到右窗格中**Orch1_** 的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-232">Expand **\<Schema\>**, and then drag **DocumentID** in the right pane to **Orch1_** in the left pane.</span></span>  

12. <span data-ttu-id="acb00-233">单击带箭头的文件夹图标 (![具有文件夹和向上箭头按钮](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-233">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

13. <span data-ttu-id="acb00-234">拖动**Receive1**到右窗格中的形状**SBegin1**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-234">Drag the **Receive1** shape in the right pane to **SBegin1** in the left pane.</span></span>  

14. <span data-ttu-id="acb00-235">拖动**StartOrchestration_1**到右窗格中的形状**SEnd1**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-235">Drag the **StartOrchestration_1** shape in the right pane to **SEnd1** in the left pane.</span></span>  

15. <span data-ttu-id="acb00-236">右键单击**StartOrchestration_1**形状，然后依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-236">Right-click the **StartOrchestration_1** shape, and then click **Message Payload Schemas**.</span></span>  

16. <span data-ttu-id="acb00-237">在双击包含值"Message_2"的行**消息**列和值"MessageBody"在**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="acb00-237">Double-click the row that contains the value “Message_2” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  

     <span data-ttu-id="acb00-238">![TPE 消息负载架构显示消息&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span><span class="sxs-lookup"><span data-stu-id="acb00-238">![TPE Message Payload schema showing message&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span></span>  

17. <span data-ttu-id="acb00-239">展开**Schema2**，然后拖动**Data2**到右窗格中**Data1**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-239">Expand **Schema2**, and then drag **Data2** in the right pane to **Data1** in the left pane.</span></span>  

18. <span data-ttu-id="acb00-240">单击**选择事件源**，然后单击**选择上下文属性**。</span><span class="sxs-lookup"><span data-stu-id="acb00-240">Click **Select Event Source**, and then click **Select Context Property**.</span></span>  

19. <span data-ttu-id="acb00-241">滚动到末尾**上下文属性名称**列表，然后再双击**BAMEndToEnd.Services.PropertySchema.DocumentID**。</span><span class="sxs-lookup"><span data-stu-id="acb00-241">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  

20. <span data-ttu-id="acb00-242">展开**\<架构\>**，然后将拖**DocumentID**到**Orch2_** 的左窗格中的继续符。</span><span class="sxs-lookup"><span data-stu-id="acb00-242">Expand **\<Schema\>**, and then drag **DocumentID** to the **Orch2_** continuation in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="acb00-243">不要混淆 Orch2_ 继续符与 Orch2_ 继续符 id。</span><span class="sxs-lookup"><span data-stu-id="acb00-243">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="acb00-244">表示继续符 ID 的图标包含一个键 (![延续 ID 的图标](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示继续符的图标不包含密钥 （![继续符的图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="acb00-244">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

21. <span data-ttu-id="acb00-245">单击**选择事件源**，然后单击**选择业务流程计划**。</span><span class="sxs-lookup"><span data-stu-id="acb00-245">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  

22. <span data-ttu-id="acb00-246">在中**程序集名称**一部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="acb00-246">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

23. <span data-ttu-id="acb00-247">在中**业务流程名称**一部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration2**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="acb00-247">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration2**, and then click **OK**.</span></span>  

24. <span data-ttu-id="acb00-248">右键单击**ConstructMessage_1**形状，然后依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-248">Right-click the **ConstructMessage_1** shape, and then click **Message Payload Schemas**.</span></span>  

25. <span data-ttu-id="acb00-249">在双击包含值"Message_3"的行**消息**列和值"BAMPart"在**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="acb00-249">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

26. <span data-ttu-id="acb00-250">展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch2_** 的左窗格中的继续符 ID。</span><span class="sxs-lookup"><span data-stu-id="acb00-250">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch2_** continuation ID in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="acb00-251">不要混淆 Orch2_ 继续符与 Orch2_ 继续符 id。</span><span class="sxs-lookup"><span data-stu-id="acb00-251">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="acb00-252">表示继续符 ID 的图标包含一个键 (![延续 ID 的图标](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示继续符的图标不包含密钥 （![继续符的图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="acb00-252">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

27. <span data-ttu-id="acb00-253">单击带箭头的文件夹图标 (![与文件夹按钮，然后向上&#45;箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-253">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

28. <span data-ttu-id="acb00-254">拖动**ConstructMessage_1**到右窗格中的形状**SBegin2**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-254">Drag the **ConstructMessage_1** shape in the right pane to **SBegin2** in the left pane.</span></span>  

29. <span data-ttu-id="acb00-255">拖动**Send_1**到右窗格中的形状**SEnd2**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-255">Drag the **Send_1** shape in the right pane to **SEnd2** in the left pane.</span></span>  

30. <span data-ttu-id="acb00-256">右键单击**Send_1**形状，然后依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-256">Right-click the **Send_1** shape, and then click **Message Payload Schemas**.</span></span>  

31. <span data-ttu-id="acb00-257">在双击包含值"Message_3"的行**消息**列和值"MessageBody"在**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="acb00-257">Double-click the row that contains the value “Message_3” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  

32. <span data-ttu-id="acb00-258">展开**Schema3**，然后拖动**Data3**到右窗格中**Data2**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-258">Expand **Schema3**, and then drag **Data3** in the right pane to **Data2** in the left pane.</span></span>  

33. <span data-ttu-id="acb00-259">从右窗格上方的下拉列表中选择**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-259">From the drop-down list above the right pane, select **Message Payload Schemas**.</span></span>  

34. <span data-ttu-id="acb00-260">在双击包含值"Message_3"的行**消息**列和值"BAMPart"在**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="acb00-260">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

35. <span data-ttu-id="acb00-261">展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch3_** 的左窗格中的继续符。</span><span class="sxs-lookup"><span data-stu-id="acb00-261">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="acb00-262">不要混淆 Orch3_ 继续符与 Orch3_ 继续符 id。</span><span class="sxs-lookup"><span data-stu-id="acb00-262">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="acb00-263">表示继续符 ID 的图标包含一个键 (![延续 ID 的图标](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示继续符的图标不包含密钥 （![继续符的图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="acb00-263">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

36. <span data-ttu-id="acb00-264">单击**选择事件源**，然后单击**选择业务流程计划**。</span><span class="sxs-lookup"><span data-stu-id="acb00-264">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  

37. <span data-ttu-id="acb00-265">在中**程序集名称**一部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="acb00-265">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

38. <span data-ttu-id="acb00-266">在中**业务流程名称**一部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration3**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="acb00-266">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration3**, and then click **OK**.</span></span>  

39. <span data-ttu-id="acb00-267">右键单击**Receive1**形状，然后依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-267">Right-click the **Receive1** shape, and then click **Message Payload Schemas**.</span></span>  

40. <span data-ttu-id="acb00-268">在双击包含值"Message_3"的行**消息**列和值"BAMPart"在**一部分**列。</span><span class="sxs-lookup"><span data-stu-id="acb00-268">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

41. <span data-ttu-id="acb00-269">展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch3_** 的左窗格中的继续符 ID。</span><span class="sxs-lookup"><span data-stu-id="acb00-269">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation ID in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="acb00-270">不要混淆 Orch3_ 继续符与 Orch3_ 继续符 id。</span><span class="sxs-lookup"><span data-stu-id="acb00-270">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="acb00-271">表示继续符 ID 的图标包含一个键 (![延续 ID 的图标](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示继续符的图标不包含密钥 （![继续符的图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="acb00-271">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

42. <span data-ttu-id="acb00-272">单击带箭头的文件夹图标 (![具有文件夹和向上箭头按钮](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="acb00-272">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

43. <span data-ttu-id="acb00-273">拖动**Receive1**到右窗格中的形状**SBegin3**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-273">Drag the **Receive1** shape in the right pane to **SBegin3** in the left pane.</span></span>  

44. <span data-ttu-id="acb00-274">拖动**Send_1**到右窗格中的形状**SEnd3**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-274">Drag the **Send_1** shape in the right pane to **SEnd3** in the left pane.</span></span>  

45. <span data-ttu-id="acb00-275">右键单击**Send_1**形状，然后依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="acb00-275">Right-click the **Send_1** shape, and then click **Message Payload Schema**.</span></span>  

46. <span data-ttu-id="acb00-276">展开**Schema3**，然后拖动**Data3**到右窗格中**Data3**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="acb00-276">Expand **Schema3**, and then drag **Data3** in the right pane to **Data3** in the left pane.</span></span>  

47. <span data-ttu-id="acb00-277">右键单击**DocumentID**如下**Orch2_** 继续符，并单击**设置端口映射**。</span><span class="sxs-lookup"><span data-stu-id="acb00-277">Right-click **DocumentID** below the **Orch2_** continuation, and then click **Set Port Mappings**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="acb00-278">不要混淆 Orch2_ 继续符与 Orch2_ 继续符 id。</span><span class="sxs-lookup"><span data-stu-id="acb00-278">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="acb00-279">表示继续符 ID 的图标包含一个键 (![延续 ID 的图标](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示继续符的图标不包含密钥 （![继续符的图标](../core/media/test.gif "测试"))。</span><span class="sxs-lookup"><span data-stu-id="acb00-279">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

48. <span data-ttu-id="acb00-280">在**选择端口**一部分**选择端口**对话框中，单击**BamEndToEnd_ReceivePort**，单击中较大的-号 ( **>**)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="acb00-280">In the **Select Ports** section of the **Select Ports** dialog box, click **BamEndToEnd_ReceivePort**, click the greater-than sign (**>**), and then click **OK**.</span></span>  

49. <span data-ttu-id="acb00-281">保存到跟踪配置文件*\<示例路径\>* \BAM\BamEndToEnd\BamEndToEnd.btt。</span><span class="sxs-lookup"><span data-stu-id="acb00-281">Save the tracking profile to *\<Samples Path\>* \BAM\BamEndToEnd\BamEndToEnd.btt.</span></span>  

## <a name="important-details"></a><span data-ttu-id="acb00-282">重要详细信息</span><span class="sxs-lookup"><span data-stu-id="acb00-282">Important details</span></span>  
 <span data-ttu-id="acb00-283">管道不支持跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="acb00-283">Tracking profiles are not supported for pipelines.</span></span> <span data-ttu-id="acb00-284">但是，在调用**BeginActivity**在管道组件是在业务流程中使用 ActivityID 相同。</span><span class="sxs-lookup"><span data-stu-id="acb00-284">However, the call to **BeginActivity** in the pipeline component is the same as using ActivityID in an orchestration.</span></span> <span data-ttu-id="acb00-285">在调用**EnableContinuation**等同于在业务流程中使用继续符。</span><span class="sxs-lookup"><span data-stu-id="acb00-285">The call to **EnableContinuation** is the same as using a continuation in an orchestration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="acb00-286">请参阅</span><span class="sxs-lookup"><span data-stu-id="acb00-286">See Also</span></span>  
 [<span data-ttu-id="acb00-287">业务活动监视（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="acb00-287">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)