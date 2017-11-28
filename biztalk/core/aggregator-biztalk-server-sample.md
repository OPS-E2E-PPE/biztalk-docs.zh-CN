---
title: "聚合器 （BizTalk Server 示例） |Microsoft 文档"
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
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c200e6c7cf28b0f0e42976f203aaa16aef2871f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="aggregator-biztalk-server-sample"></a><span data-ttu-id="4b739-102">聚合器（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="4b739-102">Aggregator (BizTalk Server Sample)</span></span>
<span data-ttu-id="4b739-103">本示例的目的在于使用业务流程和管道建立消息聚合功能。</span><span class="sxs-lookup"><span data-stu-id="4b739-103">The purpose of this sample is to build a message aggregation functionality using orchestration and pipelines.</span></span> <span data-ttu-id="4b739-104">具体而言，我们将生成一个执行以下操作的业务流程：</span><span class="sxs-lookup"><span data-stu-id="4b739-104">Specifically we will build an orchestration that:</span></span>  
  
1.  <span data-ttu-id="4b739-105">接收一组相关消息。</span><span class="sxs-lookup"><span data-stu-id="4b739-105">Receives a set of correlated messages.</span></span> <span data-ttu-id="4b739-106">根据从消息内容中提取的目标伙伴 URI 信息对消息进行关联。</span><span class="sxs-lookup"><span data-stu-id="4b739-106">Messages are correlated based on the destination partner URI information that is extracted from message content.</span></span>  
  
2.  <span data-ttu-id="4b739-107">通过执行一个 XML 发送管道，将收到的消息聚合到单个交换批中。</span><span class="sxs-lookup"><span data-stu-id="4b739-107">Aggregates received messages into a single interchange batch by executing an XML send pipeline.</span></span>  
  
3.  <span data-ttu-id="4b739-108">每分钟生成一个 XML 交换消息，或者在有足够的消息可供聚合时生成一个 XML 交换消息。</span><span class="sxs-lookup"><span data-stu-id="4b739-108">Produces an XML interchange message every minute or as soon as it has enough messages to aggregate.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4b739-109">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="4b739-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="4b739-110">*\<示例路径 >*\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="4b739-110">*\<Samples Path>*\Pipelines\Aggregator</span></span>  
  
 <span data-ttu-id="4b739-111">下表列出了本示例的文件。</span><span class="sxs-lookup"><span data-stu-id="4b739-111">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="4b739-112">文件</span><span class="sxs-lookup"><span data-stu-id="4b739-112">File(s)</span></span>|<span data-ttu-id="4b739-113">Description</span><span class="sxs-lookup"><span data-stu-id="4b739-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b739-114">Aggregator.sln</span><span class="sxs-lookup"><span data-stu-id="4b739-114">Aggregator.sln</span></span>|<span data-ttu-id="4b739-115">本示例的 Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="4b739-115">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="4b739-116">AggretatorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="4b739-116">AggretatorBinding.xml</span></span>|<span data-ttu-id="4b739-117">本示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="4b739-117">Binding file for the sample.</span></span>|  
|<span data-ttu-id="4b739-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="4b739-118">Cleanup.bat</span></span>|<span data-ttu-id="4b739-119">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="4b739-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="4b739-120">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="4b739-120">Removes send and receive ports.</span></span> <span data-ttu-id="4b739-121">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="4b739-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="4b739-122">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="4b739-122">Setup.bat</span></span>|<span data-ttu-id="4b739-123">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="4b739-123">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="4b739-124">在 Aggregate 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-124">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="4b739-125">Aggregate.btproj</span><span class="sxs-lookup"><span data-stu-id="4b739-125">Aggregate.btproj</span></span>|<span data-ttu-id="4b739-126">用于聚合业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="4b739-126">BizTalk project for aggregating orchestration.</span></span>|  
|<span data-ttu-id="4b739-127">在 Aggregator 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-127">In Aggregator folder:</span></span><br /><br /> <span data-ttu-id="4b739-128">Aggregate.odx</span><span class="sxs-lookup"><span data-stu-id="4b739-128">Aggregate.odx</span></span>|<span data-ttu-id="4b739-129">业务流程，该业务流程将相关的消息收集在一起，然后执行发送管道以将它们组装到单个交换中。</span><span class="sxs-lookup"><span data-stu-id="4b739-129">Orchestration that collects correlated messages together and then executes send pipeline to assemble them into a single interchange.</span></span>|  
|<span data-ttu-id="4b739-130">在 Aggregate 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-130">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="4b739-131">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="4b739-131">SuspendMessage.odx</span></span>|<span data-ttu-id="4b739-132">业务流程，用于挂起那些无法在聚合业务流程中进行处理的消息。</span><span class="sxs-lookup"><span data-stu-id="4b739-132">Orchestration used for suspending messages that cannot be processed within aggregating orchestration.</span></span>|  
|<span data-ttu-id="4b739-133">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-133">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="4b739-134">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="4b739-134">FFReceivePipeline.btp</span></span>|<span data-ttu-id="4b739-135">带有平面文件拆装器的接收管道。</span><span class="sxs-lookup"><span data-stu-id="4b739-135">Receive pipeline with flat file disassembler.</span></span>|  
|<span data-ttu-id="4b739-136">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-136">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="4b739-137">Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt</span><span class="sxs-lookup"><span data-stu-id="4b739-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span></span>|<span data-ttu-id="4b739-138">本示例的文档实例。</span><span class="sxs-lookup"><span data-stu-id="4b739-138">Document instances for the sample.</span></span> <span data-ttu-id="4b739-139">Instance1.txt 和 Instance2.txt 应添加到目标合作伙伴的交换[http://www.contoso.com](http://www.contoso.com/)时 Instance3.txt 和 Instance4.txt 应添加到目标合作伙伴的交换[http://www.northwind.com](http://www.northwind.com/)。</span><span class="sxs-lookup"><span data-stu-id="4b739-139">Instance1.txt and Instance2.txt should be added to an interchange for destination partner [http://www.contoso.com](http://www.contoso.com/) while Instance3.txt and Instance4.txt should be added to an interchange for destination partner [http://www.northwind.com](http://www.northwind.com/).</span></span>|  
|<span data-ttu-id="4b739-140">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-140">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="4b739-141">Invoice.xsd、InvoiceEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="4b739-141">Invoice.xsd, InvoiceEnvelope.xsd</span></span>|<span data-ttu-id="4b739-142">用于输出交换的文档架构和信封架构。</span><span class="sxs-lookup"><span data-stu-id="4b739-142">Document schema and envelope schema for output interchange.</span></span>|  
|<span data-ttu-id="4b739-143">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-143">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="4b739-144">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="4b739-144">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="4b739-145">架构和管道的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="4b739-145">BizTalk project for the schemas and pipelines.</span></span>|  
|<span data-ttu-id="4b739-146">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-146">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="4b739-147">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="4b739-147">PropertySchema.xsd</span></span>|<span data-ttu-id="4b739-148">本示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="4b739-148">Property schema for the sample.</span></span>|  
|<span data-ttu-id="4b739-149">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="4b739-149">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="4b739-150">XMLAggregatingPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="4b739-150">XMLAggregatingPipeline.btp</span></span>|<span data-ttu-id="4b739-151">从业务流程执行的发送管道，用于将收集的消息组装为一个 XML 交换。</span><span class="sxs-lookup"><span data-stu-id="4b739-151">Send pipeline that is executed from orchestration to assemble collected messages into an XML interchange.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="4b739-152">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="4b739-152">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="4b739-153">使用以下过程可以生成并初始化聚合器示例。</span><span class="sxs-lookup"><span data-stu-id="4b739-153">Use the following procedure to build and initialize the Aggregator sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a><span data-ttu-id="4b739-154">生成和初始化聚合器示例</span><span class="sxs-lookup"><span data-stu-id="4b739-154">To build and initialize the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="4b739-155">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="4b739-155">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="4b739-156">\<示例路径 > \Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="4b739-156">\<Samples Path>\Pipelines\Aggregator</span></span>  
  
2.  <span data-ttu-id="4b739-157">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b739-157">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="4b739-158">在以下文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="4b739-158">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="4b739-159">\<示例路径 > \Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="4b739-159">\<Samples Path>\Pipelines\Aggregator</span></span>  
  
    -   <span data-ttu-id="4b739-160">为本示例编译 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="4b739-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    -   <span data-ttu-id="4b739-161">创建名为“Aggregator Sample”的新应用程序并将示例程序集部署到该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="4b739-161">Creates a new application called "Aggregator Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="4b739-162">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="4b739-162">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="4b739-163">登记并启动业务流程，启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="4b739-163">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="4b739-164">如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="4b739-164">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="4b739-165">使用该密钥对可以对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="4b739-165">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="4b739-166">在尝试运行本示例之前，请确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="4b739-166">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="4b739-167">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="4b739-167">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="4b739-168">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="4b739-168">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="4b739-169">运行示例</span><span class="sxs-lookup"><span data-stu-id="4b739-169">Running the Sample</span></span>  
 <span data-ttu-id="4b739-170">使用以下过程运行聚合器示例。</span><span class="sxs-lookup"><span data-stu-id="4b739-170">Use the following procedure to run the Aggregator sample.</span></span>  
  
#### <a name="to-run-the-aggregator-sample"></a><span data-ttu-id="4b739-171">运行聚合器示例</span><span class="sxs-lookup"><span data-stu-id="4b739-171">To run the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="4b739-172">打开位于 PipelinesAndSchemas 文件夹中的 Instance1.txt 和 Instance2.txt 文件以查看其内容。</span><span class="sxs-lookup"><span data-stu-id="4b739-172">Open Instance1.txt and Instance2.txt files located in PipelinesAndSchemas folder to inspect their content.</span></span>  
  
     <span data-ttu-id="4b739-173">请注意，在两个文件中，DestinationPartnerURI 元素的值均为 http://www.contoso.com。该值用于将这两条消息关联在一起，以便可以将它们添加到同一个交换中。</span><span class="sxs-lookup"><span data-stu-id="4b739-173">Notice that in both files the DestinationPartnerURI element contains the value http://www.contoso.com. This value will be used to correlate these two messages together so that they can be added to one interchange.</span></span>  
  
     <span data-ttu-id="4b739-174">与此类似，Instance3.txt 和 Instance4.txt 文件中 DestinationPatnerURI 元素的值均设置为 http://www.northwind.com。</span><span class="sxs-lookup"><span data-stu-id="4b739-174">Similarly Instance3.txt and Instance4.txt files have DestinationPatnerURI element set to http://www.northwind.com.</span></span>  
  
     <span data-ttu-id="4b739-175">这两条消息将一起添加到另一个交换中。</span><span class="sxs-lookup"><span data-stu-id="4b739-175">These two messages together will be added to a different interchange.</span></span>  
  
2.  <span data-ttu-id="4b739-176">将文本文件 Instance1.txt、Instance2.txt、Instance3.txt 和 Instance4.txt 的副本粘贴到文件夹 In。</span><span class="sxs-lookup"><span data-stu-id="4b739-176">Paste copies of the text files Instance1.txt, Instance2.txt, Instance3.txt, and Instance4.txt into the folder In.</span></span>  
  
3.  <span data-ttu-id="4b739-177">聚合业务流程在收集了 10 条消息或达到 1 分钟的超时时间后才会生成输出交换。</span><span class="sxs-lookup"><span data-stu-id="4b739-177">Aggregating orchestrations produce output interchanges as soon as they collect 10 messages or after timeout of 1 minute.</span></span> <span data-ttu-id="4b739-178">所以，Out 文件夹中的文件可能会延迟一段时间才出现。</span><span class="sxs-lookup"><span data-stu-id="4b739-178">Because of that, the files in the Out folder may appear with delay.</span></span>  
  
     <span data-ttu-id="4b739-179">若要避免这段等待时间，可以将四个输入文件再粘贴四次，这样可触发聚合业务流程生成交换。</span><span class="sxs-lookup"><span data-stu-id="4b739-179">To avoid the timeout, you can paste the four input files four more times, which would trigger the aggregating orchestrations to produce the interchanges.</span></span>  
  
4.  <span data-ttu-id="4b739-180">查看在 Out 文件夹中创建的 XML 文件。应该有两个文件：每个目标合作伙伴 URI 一个。</span><span class="sxs-lookup"><span data-stu-id="4b739-180">Observe the XML files created in the folder Out. There should be two files – one per each destination partner URI.</span></span>  
  
     <span data-ttu-id="4b739-181">打开其中一个文件并查看其内容。</span><span class="sxs-lookup"><span data-stu-id="4b739-181">Open one of the file to inspect its content.</span></span> <span data-ttu-id="4b739-182">文件应包含由一个信封和信封内的两个 XML 文档组成的一个 XML 交换。</span><span class="sxs-lookup"><span data-stu-id="4b739-182">The file should contain an XML interchange that consists of an envelope and two XML documents within it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b739-183">在保护方案中的高负载情况下，示例的实现方式可能会导致“已送达，消息未使用”或“已完成，有消息被放弃”。</span><span class="sxs-lookup"><span data-stu-id="4b739-183">The sample implementation may cause "Delivered, not consumed messages" or "Completed with discarded messages" under high load in a convoy scenario.</span></span> <span data-ttu-id="4b739-184">在将消息路由至正处于结束过程中的业务流程时，或者在有预料之外的消息到达业务流程时，都会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="4b739-184">This occurs any time a message routes to a business process that is in the process of ending, or any time unexpected messages arrive into a business process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b739-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b739-185">See Also</span></span>  
 [<span data-ttu-id="4b739-186">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="4b739-186">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)