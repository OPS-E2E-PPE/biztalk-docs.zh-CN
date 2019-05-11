---
title: 聚合器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127eb496a6949c0bbf3d6756324f38286e127ea3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360090"
---
# <a name="aggregator-biztalk-server-sample"></a><span data-ttu-id="8a410-102">聚合器 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="8a410-102">Aggregator (BizTalk Server Sample)</span></span>
<span data-ttu-id="8a410-103">此示例的目的是生成消息聚合功能使用业务流程和管道。</span><span class="sxs-lookup"><span data-stu-id="8a410-103">The purpose of this sample is to build a message aggregation functionality using orchestration and pipelines.</span></span> <span data-ttu-id="8a410-104">特别是我们将该生成业务流程：</span><span class="sxs-lookup"><span data-stu-id="8a410-104">Specifically we will build an orchestration that:</span></span>  
  
1.  <span data-ttu-id="8a410-105">接收到一组相关消息。</span><span class="sxs-lookup"><span data-stu-id="8a410-105">Receives a set of correlated messages.</span></span> <span data-ttu-id="8a410-106">根据目标伙伴 URI 信息从消息内容中提取对消息进行关联。</span><span class="sxs-lookup"><span data-stu-id="8a410-106">Messages are correlated based on the destination partner URI information that is extracted from message content.</span></span>  
  
2.  <span data-ttu-id="8a410-107">收到的消息聚合到单个交换批通过执行一个 XML 发送管道。</span><span class="sxs-lookup"><span data-stu-id="8a410-107">Aggregates received messages into a single interchange batch by executing an XML send pipeline.</span></span>  
  
3.  <span data-ttu-id="8a410-108">生成一个 XML 交换消息每隔一分钟或的具有足够多的消息聚合。</span><span class="sxs-lookup"><span data-stu-id="8a410-108">Produces an XML interchange message every minute or as soon as it has enough messages to aggregate.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="8a410-109">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="8a410-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="8a410-110">*\<Samples Path\>* \Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="8a410-110">*\<Samples Path\>* \Pipelines\Aggregator</span></span>  
  
 <span data-ttu-id="8a410-111">下表列出了本示例的文件。</span><span class="sxs-lookup"><span data-stu-id="8a410-111">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="8a410-112">文件</span><span class="sxs-lookup"><span data-stu-id="8a410-112">File(s)</span></span>|<span data-ttu-id="8a410-113">Description</span><span class="sxs-lookup"><span data-stu-id="8a410-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a410-114">Aggregator.sln</span><span class="sxs-lookup"><span data-stu-id="8a410-114">Aggregator.sln</span></span>|<span data-ttu-id="8a410-115">该示例的 visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8a410-115">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="8a410-116">AggretatorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="8a410-116">AggretatorBinding.xml</span></span>|<span data-ttu-id="8a410-117">该示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8a410-117">Binding file for the sample.</span></span>|  
|<span data-ttu-id="8a410-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="8a410-118">Cleanup.bat</span></span>|<span data-ttu-id="8a410-119">用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。</span><span class="sxs-lookup"><span data-stu-id="8a410-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="8a410-120">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="8a410-120">Removes send and receive ports.</span></span> <span data-ttu-id="8a410-121">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="8a410-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="8a410-122">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="8a410-122">Setup.bat</span></span>|<span data-ttu-id="8a410-123">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="8a410-123">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="8a410-124">在 Aggregate 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-124">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="8a410-125">Aggregate.btproj</span><span class="sxs-lookup"><span data-stu-id="8a410-125">Aggregate.btproj</span></span>|<span data-ttu-id="8a410-126">用于聚合业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8a410-126">BizTalk project for aggregating orchestration.</span></span>|  
|<span data-ttu-id="8a410-127">在 Aggregator 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-127">In Aggregator folder:</span></span><br /><br /> <span data-ttu-id="8a410-128">Aggregate.odx</span><span class="sxs-lookup"><span data-stu-id="8a410-128">Aggregate.odx</span></span>|<span data-ttu-id="8a410-129">业务流程相关的消息收集在一起，然后执行发送管道将其组合到单个交换。</span><span class="sxs-lookup"><span data-stu-id="8a410-129">Orchestration that collects correlated messages together and then executes send pipeline to assemble them into a single interchange.</span></span>|  
|<span data-ttu-id="8a410-130">在 Aggregate 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-130">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="8a410-131">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="8a410-131">SuspendMessage.odx</span></span>|<span data-ttu-id="8a410-132">用于挂起无法聚合业务流程中处理的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="8a410-132">Orchestration used for suspending messages that cannot be processed within aggregating orchestration.</span></span>|  
|<span data-ttu-id="8a410-133">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-133">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="8a410-134">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="8a410-134">FFReceivePipeline.btp</span></span>|<span data-ttu-id="8a410-135">收到的平面文件拆装器管道。</span><span class="sxs-lookup"><span data-stu-id="8a410-135">Receive pipeline with flat file disassembler.</span></span>|  
|<span data-ttu-id="8a410-136">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-136">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="8a410-137">Instance1.txt，Instance2.txt，Instance3.txt Instance4.txt</span><span class="sxs-lookup"><span data-stu-id="8a410-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span></span>|<span data-ttu-id="8a410-138">本示例的文档实例。</span><span class="sxs-lookup"><span data-stu-id="8a410-138">Document instances for the sample.</span></span> <span data-ttu-id="8a410-139">Instance1.txt 和 Instance2.txt 应添加到针对目标合作伙伴 [ http://www.contoso.com ](http://www.contoso.com/) 而 Instance3.txt 和 Instance4.txt 应添加到针对目标合作伙伴交换 [http://www.northwind.com](http://www.northwind.com/) .</span><span class="sxs-lookup"><span data-stu-id="8a410-139">Instance1.txt and Instance2.txt should be added to an interchange for destination partner [http://www.contoso.com](http://www.contoso.com/) while Instance3.txt and Instance4.txt should be added to an interchange for destination partner [http://www.northwind.com](http://www.northwind.com/).</span></span>|  
|<span data-ttu-id="8a410-140">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-140">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="8a410-141">Invoice.xsd, InvoiceEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="8a410-141">Invoice.xsd, InvoiceEnvelope.xsd</span></span>|<span data-ttu-id="8a410-142">文档架构和用于输出交换的信封架构。</span><span class="sxs-lookup"><span data-stu-id="8a410-142">Document schema and envelope schema for output interchange.</span></span>|  
|<span data-ttu-id="8a410-143">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-143">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="8a410-144">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="8a410-144">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="8a410-145">架构和管道的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8a410-145">BizTalk project for the schemas and pipelines.</span></span>|  
|<span data-ttu-id="8a410-146">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-146">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="8a410-147">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="8a410-147">PropertySchema.xsd</span></span>|<span data-ttu-id="8a410-148">该示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="8a410-148">Property schema for the sample.</span></span>|  
|<span data-ttu-id="8a410-149">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8a410-149">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="8a410-150">XMLAggregatingPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="8a410-150">XMLAggregatingPipeline.btp</span></span>|<span data-ttu-id="8a410-151">发送管道执行从业务流程，以将收集的消息组装为一个 XML 交换。</span><span class="sxs-lookup"><span data-stu-id="8a410-151">Send pipeline that is executed from orchestration to assemble collected messages into an XML interchange.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="8a410-152">生成并初始化示例</span><span class="sxs-lookup"><span data-stu-id="8a410-152">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="8a410-153">使用以下过程生成并初始化聚合器示例。</span><span class="sxs-lookup"><span data-stu-id="8a410-153">Use the following procedure to build and initialize the Aggregator sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a><span data-ttu-id="8a410-154">若要生成并初始化聚合器示例</span><span class="sxs-lookup"><span data-stu-id="8a410-154">To build and initialize the Aggregator sample</span></span>  
  
1. <span data-ttu-id="8a410-155">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="8a410-155">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="8a410-156">\<Samples Path\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="8a410-156">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
2. <span data-ttu-id="8a410-157">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8a410-157">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="8a410-158">创建输入 (In) 和输出 (Out) 文件夹的文件夹中的以下示例：</span><span class="sxs-lookup"><span data-stu-id="8a410-158">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
      <span data-ttu-id="8a410-159">\<Samples Path\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="8a410-159">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
   - <span data-ttu-id="8a410-160">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。</span><span class="sxs-lookup"><span data-stu-id="8a410-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   - <span data-ttu-id="8a410-161">创建名为"Aggregator Sample"的新应用程序和部署到其中的示例程序集。</span><span class="sxs-lookup"><span data-stu-id="8a410-161">Creates a new application called "Aggregator Sample" and deploys the sample assemblies into it.</span></span>  
  
   - <span data-ttu-id="8a410-162">创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="8a410-162">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
   - <span data-ttu-id="8a410-163">登记和启动业务流程，启用接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="8a410-163">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
      <span data-ttu-id="8a410-164">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="8a410-164">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="8a410-165">使用此密钥对可以对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="8a410-165">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3. <span data-ttu-id="8a410-166">在尝试运行此示例之前, 确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="8a410-166">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process.</span></span>  
  
    <span data-ttu-id="8a410-167">若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="8a410-167">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="8a410-168">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="8a410-168">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="8a410-169">运行示例</span><span class="sxs-lookup"><span data-stu-id="8a410-169">Running the Sample</span></span>  
 <span data-ttu-id="8a410-170">使用以下过程运行聚合器示例。</span><span class="sxs-lookup"><span data-stu-id="8a410-170">Use the following procedure to run the Aggregator sample.</span></span>  
  
#### <a name="to-run-the-aggregator-sample"></a><span data-ttu-id="8a410-171">若要运行聚合器示例</span><span class="sxs-lookup"><span data-stu-id="8a410-171">To run the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="8a410-172">打开 Instance1.txt 和 Instance2.txt 文件位于 PipelinesAndSchemas 文件夹以查看其内容中。</span><span class="sxs-lookup"><span data-stu-id="8a410-172">Open Instance1.txt and Instance2.txt files located in PipelinesAndSchemas folder to inspect their content.</span></span>  
  
     <span data-ttu-id="8a410-173">请注意，在这种文件 DestinationPartnerURI 元素包含的值 http://www.contoso.com 。</span><span class="sxs-lookup"><span data-stu-id="8a410-173">Notice that in both files the DestinationPartnerURI element contains the value http://www.contoso.com.</span></span> <span data-ttu-id="8a410-174">该值用于将这两条消息关联在一起，以便可以将它们添加到同一个交换中。</span><span class="sxs-lookup"><span data-stu-id="8a410-174">This value will be used to correlate these two messages together so that they can be added to one interchange.</span></span>  
  
     <span data-ttu-id="8a410-175">同样 Instance3.txt 和 Instance4.txt 文件具有 DestinationPatnerURI 元素设置为 http://www.northwind.com 。</span><span class="sxs-lookup"><span data-stu-id="8a410-175">Similarly Instance3.txt and Instance4.txt files have DestinationPatnerURI element set to http://www.northwind.com.</span></span>  
  
     <span data-ttu-id="8a410-176">这两条消息将一起添加到另一个交换中。</span><span class="sxs-lookup"><span data-stu-id="8a410-176">These two messages together will be added to a different interchange.</span></span>  
  
2.  <span data-ttu-id="8a410-177">将文本文件 Instance1.txt 和 Instance2.txt，Instance3.txt，和 Instance4.txt 的副本粘贴到 in 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8a410-177">Paste copies of the text files Instance1.txt, Instance2.txt, Instance3.txt, and Instance4.txt into the folder In.</span></span>  
  
3.  <span data-ttu-id="8a410-178">只要它们收集 10 条消息，或者为 1 分钟的超时之后会聚合业务流程生成输出交换。</span><span class="sxs-lookup"><span data-stu-id="8a410-178">Aggregating orchestrations produce output interchanges as soon as they collect 10 messages or after timeout of 1 minute.</span></span> <span data-ttu-id="8a410-179">正因为如此，Out 文件夹中的文件可能会出现延迟。</span><span class="sxs-lookup"><span data-stu-id="8a410-179">Because of that, the files in the Out folder may appear with delay.</span></span>  
  
     <span data-ttu-id="8a410-180">若要避免超时，可以将四个输入的文件粘贴四次，这会触发聚合业务流程生成交换。</span><span class="sxs-lookup"><span data-stu-id="8a410-180">To avoid the timeout, you can paste the four input files four more times, which would trigger the aggregating orchestrations to produce the interchanges.</span></span>  
  
4.  <span data-ttu-id="8a410-181">查看在 Out 文件夹中创建的 XML 文件。应该有两个文件： 每个目标合作伙伴 URI 一个。</span><span class="sxs-lookup"><span data-stu-id="8a410-181">Observe the XML files created in the folder Out. There should be two files – one per each destination partner URI.</span></span>  
  
     <span data-ttu-id="8a410-182">打开其中一个文件并查看其内容。</span><span class="sxs-lookup"><span data-stu-id="8a410-182">Open one of the file to inspect its content.</span></span> <span data-ttu-id="8a410-183">该文件应包含一个 XML 交换的信封和在其中的两个 XML 文档组成。</span><span class="sxs-lookup"><span data-stu-id="8a410-183">The file should contain an XML interchange that consists of an envelope and two XML documents within it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a410-184">该示例实现可能会导致"已送达，消息未使用"或"已完成有消息被放弃"中的保护方案的高负载下。</span><span class="sxs-lookup"><span data-stu-id="8a410-184">The sample implementation may cause "Delivered, not consumed messages" or "Completed with discarded messages" under high load in a convoy scenario.</span></span> <span data-ttu-id="8a410-185">这是一条消息路由到业务流程正在结束，任何时间或意外的某一时间消息到达业务流程。</span><span class="sxs-lookup"><span data-stu-id="8a410-185">This occurs any time a message routes to a business process that is in the process of ending, or any time unexpected messages arrive into a business process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a410-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a410-186">See Also</span></span>  
 [<span data-ttu-id="8a410-187">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="8a410-187">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)