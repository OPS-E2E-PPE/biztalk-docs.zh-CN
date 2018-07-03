---
title: 组合消息处理器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d884fba7d19e26613c457ed5789f847a5c23babc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969206"
---
# <a name="composed-message-processor-biztalk-server-sample"></a><span data-ttu-id="74de0-102">组合消息处理器（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="74de0-102">Composed Message Processor (BizTalk Server Sample)</span></span>
<span data-ttu-id="74de0-103">此示例的目的是构建处理聚合消息中的各个行项的组合的消息处理器应用程序。</span><span class="sxs-lookup"><span data-stu-id="74de0-103">The purpose of this sample is to build a composed message processor application that processes individual line items from aggregated messages.</span></span>  
  
 <span data-ttu-id="74de0-104">特别是我们将该生成业务流程调度：</span><span class="sxs-lookup"><span data-stu-id="74de0-104">Specifically we will build an orchestration schedule that:</span></span>  
  
1. <span data-ttu-id="74de0-105">接收包含多个采购订单的批处理的交换消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-105">Receives a batched interchange message consisting of multiple purchase orders.</span></span>  
  
2. <span data-ttu-id="74de0-106">将交换消息分解为单独的采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="74de0-106">Disassembles the interchange message into individual purchase order documents.</span></span>  
  
3. <span data-ttu-id="74de0-107">处理每个文档-每个采购订单转换为发票消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-107">Processes each document – converts each purchase order into an invoice message.</span></span>  
  
4. <span data-ttu-id="74de0-108">将所有发票消息都组装为批处理交换。</span><span class="sxs-lookup"><span data-stu-id="74de0-108">Assembles all the invoice messages into a batched interchange.</span></span>  
  
   <span data-ttu-id="74de0-109">步骤 #3 得到了简化，示例目的。</span><span class="sxs-lookup"><span data-stu-id="74de0-109">Step #3 is simplified for the sample purposes.</span></span> <span data-ttu-id="74de0-110">例如，在更加复杂的应用程序中，业务流程可能会将拆装的采购订单发送给不同的后端库存系统，并在收集到所有响应之后，将这些采购订单聚合为一个批发票消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-110">For example, in more complex applications, an orchestration may send disassembled purchase orders to different back-end inventory systems and then after collecting all the responses, aggregate them into one batched invoice message.</span></span>  
  
   <span data-ttu-id="74de0-111">组合的消息处理器模式的详细信息请参阅 [1]。</span><span class="sxs-lookup"><span data-stu-id="74de0-111">For more information on the composed message processor pattern refer to [1].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="74de0-112">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="74de0-112">What This Sample Does</span></span>  
 <span data-ttu-id="74de0-113">有以下各节详细地介绍这两个示例解决方案中的两个项目。</span><span class="sxs-lookup"><span data-stu-id="74de0-113">There are two projects within the sample solution, both of which are described in detail in the following sections.</span></span>  
  
### <a name="pipelines-and-schemas"></a><span data-ttu-id="74de0-114">管道和架构</span><span class="sxs-lookup"><span data-stu-id="74de0-114">Pipelines and Schemas</span></span>  
 <span data-ttu-id="74de0-115">管道和架构的项目包含：</span><span class="sxs-lookup"><span data-stu-id="74de0-115">Pipelines and schemas project contains:</span></span>  
  
-   <span data-ttu-id="74de0-116">对于输入的采购订单的交换和用于输出发票交换的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="74de0-116">Flat file schemas for input purchase order interchange and for output invoice interchange.</span></span>  
  
-   <span data-ttu-id="74de0-117">用于将采购订单文档转换为发票文档的映射。</span><span class="sxs-lookup"><span data-stu-id="74de0-117">Map to transform purchase order document into an invoice document.</span></span>  
  
-   <span data-ttu-id="74de0-118">接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="74de0-118">Receive and send pipelines.</span></span>  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a><span data-ttu-id="74de0-119">输入和输出交换的平面文件架构</span><span class="sxs-lookup"><span data-stu-id="74de0-119">Flat File Schemas For Input and Output Interchanges</span></span>  
 <span data-ttu-id="74de0-120">我们的示例应用程序将使用在平面文件格式交换。</span><span class="sxs-lookup"><span data-stu-id="74de0-120">Our sample application will be working with the interchanges in the flat file format.</span></span> <span data-ttu-id="74de0-121">以下是交换采购订单和发票交换的示例：</span><span class="sxs-lookup"><span data-stu-id="74de0-121">Below are the examples of the purchase order interchange and invoice interchange:</span></span>  
  
 <span data-ttu-id="74de0-122">采购订单的交换 (CMPInput.txt):</span><span class="sxs-lookup"><span data-stu-id="74de0-122">Purchase order interchange (CMPInput.txt):</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
PO1999-10-21  
US    John Dow       123 Elm Street      Mill Valley    CA 90952  
US    July Dow       8 Pine Avenue       Old Town       PA 95819  
Please ship it urgent!  
ITEMS,ITEM398-BB|Tire|4|324.99|Wrap them up nicely,ITEM201-BB|Engine Oil|1|12.99|SAE10W30|1999-05-22  
PO1999-10-23  
US    John Connor    123 Cedar Street    Mill Valley    CA 90952  
US    Sarah Connor   8 Grass Avenue      Old Town       PA 95819  
Use cheapest shipping method.  
ITEMS,ITEM101-TT|Plastic flowers|10|4.99|Fragile handle with care,ITEM202-RR|Fertilizer|1|10.99|Lawn fertilizer,ITEM453-XS|Weed killer|1|5.99|Lawn weed killer|1999-05-25  
```  
  
 <span data-ttu-id="74de0-123">采购订单文档或交换，具有标头，用于标识包含哪种类型的文档：</span><span class="sxs-lookup"><span data-stu-id="74de0-123">The interchange, or purchase order document, has a header that identifies what type of the documents it contains:</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 <span data-ttu-id="74de0-124">此交换包含三个采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="74de0-124">This interchange consist of three purchase order documents.</span></span> <span data-ttu-id="74de0-125">一个实例包含如下所示的信息。</span><span class="sxs-lookup"><span data-stu-id="74de0-125">One instance consists of the information shown below.</span></span> <span data-ttu-id="74de0-126">正如您所看到的它包含针对计费和传送的已排序的项列表以及地址等信息。</span><span class="sxs-lookup"><span data-stu-id="74de0-126">As you can see, it contains such information as address for billing and shipping as well as the list of items that were ordered.</span></span>  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 <span data-ttu-id="74de0-127">我们想要为此生成发票交换应如以下所示：</span><span class="sxs-lookup"><span data-stu-id="74de0-127">The invoice interchange we want to generate for this should look like the following:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
INVOICE1999-10-21  
BILLTO,US,John Dow,123 Elm Street,Mill Valley,CA,90952  
398-BB    Tire              4    324.99    Wrap them up nicely  
201-BB    Engine Oil        1    12.99     SAE10W30  
INVOICE1999-10-20  
BILLTO,US,John Connor,123 Cedar Street,Mill Valley,CA,90952  
101-TT    Plastic flowers   10   4.99      Fragile handle with care  
202-RR    Fertilizer        1    10.99     Lawn fertilizer  
453-XS    Weed killer       1    5.99      Lawn weed killer  
```  
  
 <span data-ttu-id="74de0-128">此交换包含已在购买顺序交换和交换的格式以及标头的格式也是不同的信息的子集。</span><span class="sxs-lookup"><span data-stu-id="74de0-128">This interchange contains a subset of information that was in purchase order interchange and also the format of the interchange as well as format of the header are different.</span></span>  
  
 <span data-ttu-id="74de0-129">标头如下所示：</span><span class="sxs-lookup"><span data-stu-id="74de0-129">The header is as follows:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 <span data-ttu-id="74de0-130">和文档实例包括以下：</span><span class="sxs-lookup"><span data-stu-id="74de0-130">And the document instance includes the following:</span></span>  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 <span data-ttu-id="74de0-131">第一件事我们需要创建用于平面文件架构：</span><span class="sxs-lookup"><span data-stu-id="74de0-131">First thing we need to create flat file schemas for:</span></span>  
  
- <span data-ttu-id="74de0-132">采购订单文档 (PO.xsd)</span><span class="sxs-lookup"><span data-stu-id="74de0-132">Purchase order document (PO.xsd)</span></span>  
  
- <span data-ttu-id="74de0-133">发票文档 (Invoice.xsd)</span><span class="sxs-lookup"><span data-stu-id="74de0-133">Invoice document (Invoice.xsd)</span></span>  
  
- <span data-ttu-id="74de0-134">采购订单标题 (POHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="74de0-134">Purchase order header (POHeader.xsd)</span></span>  
  
- <span data-ttu-id="74de0-135">发票标头 (InvoiceHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="74de0-135">Invoice header (InvoiceHeader.xsd)</span></span>  
  
  <span data-ttu-id="74de0-136">对于此示例，我们不打算介绍创建平面文件架构的过程。</span><span class="sxs-lookup"><span data-stu-id="74de0-136">For this sample, we are not going to explain the process of creating flat file schemas.</span></span> <span data-ttu-id="74de0-137">若要了解如何从文档实例创建平面文件架构，请参阅“从文档实例创建平面文件架构”文档部分。</span><span class="sxs-lookup"><span data-stu-id="74de0-137">To learn how to create flat file schemas from document instances, refer to the "Creating flat file schemas from document instance" documentation section.</span></span>  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a><span data-ttu-id="74de0-138">用于将采购订单文档转换为发票文档的映射</span><span class="sxs-lookup"><span data-stu-id="74de0-138">Map to Transform Purchase Order Document Into Invoice Document</span></span>  
 <span data-ttu-id="74de0-139">地图 (PO2Invoice.btm) 将采购订单的实例转换为发票文档。</span><span class="sxs-lookup"><span data-stu-id="74de0-139">The map (PO2Invoice.btm) transforms an instance of the purchase order into an invoice document.</span></span>  
  
#### <a name="receive-and-send-pipelines"></a><span data-ttu-id="74de0-140">接收和发送管道</span><span class="sxs-lookup"><span data-stu-id="74de0-140">Receive and Send Pipelines</span></span>  
 <span data-ttu-id="74de0-141">接收管道 (FFReceivePipeline.btp) 包含用于处理采购订单交换的平面文件拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="74de0-141">The receive pipeline (FFReceivePipeline.btp) contains a flat file disassembler component that is used to process a purchase order interchange.</span></span> <span data-ttu-id="74de0-142">具体而言，对于文件 CMPInput.txt 中交换，它删除交换标头，并生成对应于三个采购订单的三个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="74de0-142">In particular, for the interchange in file CMPInput.txt, it removes the interchange header and produces three XML documents corresponding to three purchase orders.</span></span>  
  
 <span data-ttu-id="74de0-143">配置接收管道中的平面文件拆装器所示：</span><span class="sxs-lookup"><span data-stu-id="74de0-143">The flat file disassembler in the receive pipeline is configured as shown:</span></span>  
  
- <span data-ttu-id="74de0-144">**文档架构：** 属于 PipelinesAndSchemas.PO</span><span class="sxs-lookup"><span data-stu-id="74de0-144">**Document schema:** PipelinesAndSchemas.PO</span></span>  
  
- <span data-ttu-id="74de0-145">**标头架构：** PipelinesAndSchemas.POHeader</span><span class="sxs-lookup"><span data-stu-id="74de0-145">**Header schema:** PipelinesAndSchemas.POHeader</span></span>  
  
- <span data-ttu-id="74de0-146">**保留头部：** False</span><span class="sxs-lookup"><span data-stu-id="74de0-146">**Preserve header:** False</span></span>  
  
- <span data-ttu-id="74de0-147">**可恢复的交换：** False</span><span class="sxs-lookup"><span data-stu-id="74de0-147">**Recoverable interchange:** False</span></span>  
  
- <span data-ttu-id="74de0-148">**尾部架构：** （无）</span><span class="sxs-lookup"><span data-stu-id="74de0-148">**Trailer schema:** (None)</span></span>  
  
- <span data-ttu-id="74de0-149">**验证文档结构：** False</span><span class="sxs-lookup"><span data-stu-id="74de0-149">**Validate document structure:** False</span></span>  
  
  <span data-ttu-id="74de0-150">发送管道 (FFSendPipeline.btp) 包含用于创建聚合的发票交换的平面文件组装器组件。</span><span class="sxs-lookup"><span data-stu-id="74de0-150">The send pipeline (FFSendPipeline.btp) contains a flat file assembler component that is used to create aggregated invoice interchange.</span></span>  
  
  <span data-ttu-id="74de0-151">配置发送管道中的平面文件组装器所示：</span><span class="sxs-lookup"><span data-stu-id="74de0-151">The flat file assembler in send pipeline is configured as shown:</span></span>  
  
- <span data-ttu-id="74de0-152">**文档架构：** PipelinesandSchemas.Invoice</span><span class="sxs-lookup"><span data-stu-id="74de0-152">**Document schema:** PipelinesandSchemas.Invoice</span></span>  
  
- <span data-ttu-id="74de0-153">**标头架构：** PipelinesAndSchemas.InvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="74de0-153">**Header schema:** PipelinesAndSchemas.InvoiceHeader</span></span>  
  
- <span data-ttu-id="74de0-154">**保留字节顺序标记：** False</span><span class="sxs-lookup"><span data-stu-id="74de0-154">**Preserve byte order mark:** False</span></span>  
  
- <span data-ttu-id="74de0-155">**目标字符集：** （无）</span><span class="sxs-lookup"><span data-stu-id="74de0-155">**Target charset:** (None)</span></span>  
  
- <span data-ttu-id="74de0-156">**尾部架构：** （无）</span><span class="sxs-lookup"><span data-stu-id="74de0-156">**Trailer schema:** (None)</span></span>  
  
### <a name="orchestration-schedule"></a><span data-ttu-id="74de0-157">业务流程调度</span><span class="sxs-lookup"><span data-stu-id="74de0-157">Orchestration Schedule</span></span>  
 <span data-ttu-id="74de0-158">业务流程调度 (CMP.odx) 是所有主处理发生的位置。</span><span class="sxs-lookup"><span data-stu-id="74de0-158">Orchestration schedule (CMP.odx) is where all the main processing happens.</span></span> <span data-ttu-id="74de0-159">执行专门的以下操作：</span><span class="sxs-lookup"><span data-stu-id="74de0-159">Specifically the following actions are performed:</span></span>  
  
-   <span data-ttu-id="74de0-160">接收管道执行以拆装交换采购订单</span><span class="sxs-lookup"><span data-stu-id="74de0-160">Receive pipeline is executed to disassemble purchase order interchange</span></span>  
  
-   <span data-ttu-id="74de0-161">接收管道的每个输出消息转换</span><span class="sxs-lookup"><span data-stu-id="74de0-161">Every output message of receive pipeline is transformed</span></span>  
  
-   <span data-ttu-id="74de0-162">发送管道执行来汇集的发票交换</span><span class="sxs-lookup"><span data-stu-id="74de0-162">Send pipeline is executed to assemble an invoice interchange</span></span>  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a><span data-ttu-id="74de0-163">创建业务流程调度和定义全局变量</span><span class="sxs-lookup"><span data-stu-id="74de0-163">Creating Orchestration Schedule and Defining Global Variables</span></span>  
 <span data-ttu-id="74de0-164">我们的业务流程将收到作为输入的平面文件交换，并将作为输出发送平面文件交换。</span><span class="sxs-lookup"><span data-stu-id="74de0-164">Our orchestration will receive a flat file interchange as an input and will send a flat file interchange as an output.</span></span> <span data-ttu-id="74de0-165">正因为如此，我们需要定义输入和输出消息 （称为 InputInterchange 和 OutputInterchange 分别） 为的类型无关 （即具有 System.Xml.XmlDocument 类型）。</span><span class="sxs-lookup"><span data-stu-id="74de0-165">Because of that, we need to define input and output messages (called InputInterchange and OutputInterchange respectively) as type agnostic (i.e. having type of System.Xml.XmlDocument).</span></span>  
  
 <span data-ttu-id="74de0-166">另外，我们需要定义用于处理消息的原子作用域。</span><span class="sxs-lookup"><span data-stu-id="74de0-166">Also, we need to define an atomic scope where we will process messages.</span></span> <span data-ttu-id="74de0-167">这一步是必需的，因为接收管道可以在原子作用域内执行。</span><span class="sxs-lookup"><span data-stu-id="74de0-167">This is required because the receive pipeline can be executed within atomic scope.</span></span>  
  
#### <a name="executing-receive-pipeline"></a><span data-ttu-id="74de0-168">执行接收管道</span><span class="sxs-lookup"><span data-stu-id="74de0-168">Executing Receive Pipeline</span></span>  
 <span data-ttu-id="74de0-169">下一步，我们将添加用于对业务流程中接收到的消息执行接收管道的逻辑。</span><span class="sxs-lookup"><span data-stu-id="74de0-169">As a next step, we will add logic to execute a receive pipeline for the message that was received in orchestration.</span></span> <span data-ttu-id="74de0-170">为此，首先我们将在作用域内声明一个 Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages 类型的变量（称为 RcvPipeOutput）。</span><span class="sxs-lookup"><span data-stu-id="74de0-170">To do this, first we declare a variable (called RcvPipeOutput) of type Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages within the scope.</span></span> <span data-ttu-id="74de0-171">此变量为允许我们循环访问接收管道输出消息的枚举数。</span><span class="sxs-lookup"><span data-stu-id="74de0-171">This variable is an enumerator that allows us to cycle through the receive pipeline output messages.</span></span> <span data-ttu-id="74de0-172">请注意，为了能够访问此类型和用于从业务流程执行管道的所有其他类型，需要添加对以下程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="74de0-172">Note that in order to access this type, as well as all the other types for execution of pipelines from orchestration, you need to add references to the following assemblies:</span></span>  
  
- <span data-ttu-id="74de0-173">Microsoft.XLANGs.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="74de0-173">Microsoft.XLANGs.Pipeline.dll</span></span>  
  
- <span data-ttu-id="74de0-174">Microsoft.BizTalk.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="74de0-174">Microsoft.BizTalk.Pipeline.dll</span></span>  
  
  <span data-ttu-id="74de0-175">无法确保接收管道每次均会成功执行。</span><span class="sxs-lookup"><span data-stu-id="74de0-175">There is no guarantee that the receive pipeline will always execute successfully.</span></span> <span data-ttu-id="74de0-176">有时消息的格式可能不正确，这会使管道处理失败。</span><span class="sxs-lookup"><span data-stu-id="74de0-176">Sometimes messages may be malformed, which would cause the pipeline processing to fail.</span></span> <span data-ttu-id="74de0-177">在业务流程中管道执行失败时会引发可被捕获的异常，并可以执行错误处理逻辑。</span><span class="sxs-lookup"><span data-stu-id="74de0-177">When a pipeline fails execution in the orchestration, there is an exception thrown that can be caught and the error handling logic can be performed.</span></span> <span data-ttu-id="74de0-178">为了捕获管道引发的异常，我们需要在具有异常处理功能的非原子作用域内执行管道。</span><span class="sxs-lookup"><span data-stu-id="74de0-178">In order for us to catch the exception thrown by pipeline, we need to execute the pipeline within a non-atomic scope with an exception handling.</span></span> <span data-ttu-id="74de0-179">执行管道的实际代码将从该作用域内的表达式形状调用。</span><span class="sxs-lookup"><span data-stu-id="74de0-179">The actual code to execute pipeline is invoked from an expression shape within that scope.</span></span>  
  
  <span data-ttu-id="74de0-180">在 ExecuteRcvPipe 表达式形状中，编写用于执行接收管道的以下代码行：</span><span class="sxs-lookup"><span data-stu-id="74de0-180">In the ExecuteRcvPipe expression shape, write the following line of code to execute the receive pipeline:</span></span>  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 <span data-ttu-id="74de0-181">让我们详细分析一下此代码行。</span><span class="sxs-lookup"><span data-stu-id="74de0-181">Let's analyze this line of code in more detail.</span></span> <span data-ttu-id="74de0-182">如上所示，我们调用了一个将要执行的接收管道类型和输入消息用作参数的静态方法 ExecuteReceivePipeline。</span><span class="sxs-lookup"><span data-stu-id="74de0-182">As you can see, we call a static method ExecuteReceivePipeline that takes as a parameter a type of receive pipeline to execute and an input message.</span></span> <span data-ttu-id="74de0-183">因此，该方法生成了一个具有输出消息组的枚举数对象。</span><span class="sxs-lookup"><span data-stu-id="74de0-183">As a result, it produces an enumerator object with the set of output messages.</span></span> <span data-ttu-id="74de0-184">该结果将赋给之前在此作用域中定义的 ReceivePipelineOutputMessages 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="74de0-184">The result is assigned to a variable of type ReceivePipelineOutputMessages that was defined in this scope before.</span></span>  
  
 <span data-ttu-id="74de0-185">同时，我们已为管道执行作用域增加了一个异常处理块。</span><span class="sxs-lookup"><span data-stu-id="74de0-185">We have also included an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="74de0-186">此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义错误消息的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="74de0-186">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
 <span data-ttu-id="74de0-187">在更加复杂的情况下，此时可能会执行其他错误处理，如生成错误通知消息并通过电子邮件将其发送给业务用户或管理员。</span><span class="sxs-lookup"><span data-stu-id="74de0-187">In more complex scenarios, additional error handling can be performed here, such as generation or the error notification message and sending it to a business user or administrator using email.</span></span>  
  
#### <a name="transforming-pipeline-output-messages"></a><span data-ttu-id="74de0-188">转换管道输出消息</span><span class="sxs-lookup"><span data-stu-id="74de0-188">Transforming Pipeline Output Messages</span></span>  
 <span data-ttu-id="74de0-189">在已执行管道并生成拆装消息组之后，需要将每个输出消息转换为其他格式。</span><span class="sxs-lookup"><span data-stu-id="74de0-189">After the pipeline has been executed and the set of disassembled messages has been produced, we need to transform each output message into a different format.</span></span>  
  
 <span data-ttu-id="74de0-190">为在业务流程中使用转换，我们需要定义两种消息，即转换输入消息和转换输出消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-190">To use transformation in orchestration we need to define two messages – transformation input and output.</span></span> <span data-ttu-id="74de0-191">我们将在原子作用域内定义这些消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-191">We will define those messages within the atomic scope.</span></span> <span data-ttu-id="74de0-192">名为 TmpMessageIn 的转换输入消息属于 PipelinesAndSchemas.PO 类型。</span><span class="sxs-lookup"><span data-stu-id="74de0-192">The transformation input message called TmpMessageIn will be of type PipelinesAndSchemas.PO.</span></span> <span data-ttu-id="74de0-193">名为 TmpMessageOut 的转换输出消息属于 PipeliensAndSchemas.Invoice 类型。</span><span class="sxs-lookup"><span data-stu-id="74de0-193">The transformation output message called TmpMessageOut will be of type PipeliensAndSchemas.Invoice.</span></span> <span data-ttu-id="74de0-194">我们将应用在 PipelinesAndSchemas 项目中定义的 PO2Invoice.btm 映射。</span><span class="sxs-lookup"><span data-stu-id="74de0-194">We will apply the map PO2Invoice.btm that is defined in project PipelinesAndSchemas.</span></span>  
  
 <span data-ttu-id="74de0-195">由于要映射每个管道输出消息，因此需要在循环中执行转换。</span><span class="sxs-lookup"><span data-stu-id="74de0-195">As we want to map each pipeline output message we need to perform transformation in the loop.</span></span> <span data-ttu-id="74de0-196">我们将使用具有如下所示退出条件的循环形状：</span><span class="sxs-lookup"><span data-stu-id="74de0-196">We will use a loop shape with the condition for exiting as below:</span></span>  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 <span data-ttu-id="74de0-197">MoveNext() 方法是一种允许在管道输出消息集合内移动的标准 IEnumerator .NET 接口方法。</span><span class="sxs-lookup"><span data-stu-id="74de0-197">MoveNext() method is a standard method of IEnumerator .NET interface that allows to move within the collection of pipeline output messages.</span></span> <span data-ttu-id="74de0-198">当它到达集合的末尾时会返回 False。</span><span class="sxs-lookup"><span data-stu-id="74de0-198">When it reaches the end of collection it returns false.</span></span>  
  
 <span data-ttu-id="74de0-199">第一个构造形状用于从管道输出消息构造业务流程消息 TmpMessageIn。</span><span class="sxs-lookup"><span data-stu-id="74de0-199">The first construct shape is used to construct an orchestration message TmpMessageIn out of the pipeline output message.</span></span>  
  
 <span data-ttu-id="74de0-200">构造形状中的代码：</span><span class="sxs-lookup"><span data-stu-id="74de0-200">The code in the construct shape:</span></span>  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 <span data-ttu-id="74de0-201">在此代码中，我们首先将业务流程消息初始化为空，然后将其设置为管道输出消息集合中的当前消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-201">In this code we first initialize orchestration message to null and then set it to the current message from the pipeline output messages collection.</span></span>  
  
 <span data-ttu-id="74de0-202">在第二个构造形状中将执行 TmpMessageIn 的实际转换并构造类型为 PipelinesAndSchemas.Invoice 的 TmpMessageOut。</span><span class="sxs-lookup"><span data-stu-id="74de0-202">In second construct shape the actual transformation of the TmpMessageIn is performed and the TmpMessageOut of type PipelinesAndSchemas.Invoice is constructed.</span></span>  
  
#### <a name="executing-send-pipeline"></a><span data-ttu-id="74de0-203">执行发送管道</span><span class="sxs-lookup"><span data-stu-id="74de0-203">Executing Send Pipeline</span></span>  
 <span data-ttu-id="74de0-204">业务流程中的最后一个处理步骤是执行平面文件发送管道以将所有转换的 xml 消息组装为一个平面文件交换。</span><span class="sxs-lookup"><span data-stu-id="74de0-204">Last processing step in orchestration is to execute flat file send pipeline to assemble all the transformed xml messages into one flat file interchange.</span></span>  
  
 <span data-ttu-id="74de0-205">为了执行发送管道我们需要使用 Microsoft.XLANGs.Pipeline.SendPipelineInputMessages 类型的变量 SendPipeInput，该变量用于存放需要在发送管道中进行处理的业务流程消息集合。</span><span class="sxs-lookup"><span data-stu-id="74de0-205">In order to execute a send pipeline we need to use a variable of type Microsoft.XLANGs.Pipeline.SendPipelineInputMessages called SendPipeInput that will hold a collection of orchestration messages that need to be processed in a send pipeline.</span></span>  
  
 <span data-ttu-id="74de0-206">在前一个用于执行转换的循环表达式中我们将编写一行代码，为发送管道将每个转换的消息添加到消息集合中。</span><span class="sxs-lookup"><span data-stu-id="74de0-206">In the last expression of the loop where we performed transformation we will write a code that will add each transformed message to a message collection for send pipeline:</span></span>  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 <span data-ttu-id="74de0-207">与执行接收管道的过程相似，用于执行发送管道的代码放在具有异常处理块的非原子作用域内。</span><span class="sxs-lookup"><span data-stu-id="74de0-207">Similar to the part where we execute receive pipeline the code for execution of send pipeline is placed within a non-atomic scope with exception handling block.</span></span> <span data-ttu-id="74de0-208">发送管道执行代码位于构造模块的消息赋值形状中。</span><span class="sxs-lookup"><span data-stu-id="74de0-208">The send pipeline execution code is located in the message assignment shape of the construct block.</span></span>  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 <span data-ttu-id="74de0-209">构造模块用于构造与类型无关（即 System.Xml.XmlDocument）的管道输出消息 OutputInterchange。</span><span class="sxs-lookup"><span data-stu-id="74de0-209">The construct block is used to construct type agnostic (i.e. System.Xml.XmlDocument) pipeline output message OutputInterchange.</span></span> <span data-ttu-id="74de0-210">然后在消息赋值形状中将新构造的消息初始化为空。</span><span class="sxs-lookup"><span data-stu-id="74de0-210">Then in the message assignment shape the newly constructed message is initialized to null.</span></span> <span data-ttu-id="74de0-211">接下来会调用静态方法 ExecuteSendPipeline 以执行发送管道。</span><span class="sxs-lookup"><span data-stu-id="74de0-211">After that the static method ExecuteSendPipeline is invoked to execute a send pipeline.</span></span> <span data-ttu-id="74de0-212">此方法采用以下项作为参数：要执行的发送管道的类型；输入消息；对用于存储管道输出的输出消息的引用。</span><span class="sxs-lookup"><span data-stu-id="74de0-212">This method takes as a parameter a type of the send pipeline to execute, the input message and the reference to output message where the pipeline output will be stored.</span></span>  
  
 <span data-ttu-id="74de0-213">与执行接收管道时相同，在此我们也在管道执行作用域中包含了一个异常处理块。</span><span class="sxs-lookup"><span data-stu-id="74de0-213">As with the execution of the receive pipeline, here we also have an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="74de0-214">此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义错误消息的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="74de0-214">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="74de0-215">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="74de0-215">Where to Find This Sample</span></span>  
 <span data-ttu-id="74de0-216">下表列出了本示例的文件。</span><span class="sxs-lookup"><span data-stu-id="74de0-216">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="74de0-217">文件</span><span class="sxs-lookup"><span data-stu-id="74de0-217">File(s)</span></span>|<span data-ttu-id="74de0-218">Description</span><span class="sxs-lookup"><span data-stu-id="74de0-218">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74de0-219">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="74de0-219">Cleanup.bat</span></span>|<span data-ttu-id="74de0-220">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="74de0-220">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span><br /><br /> <span data-ttu-id="74de0-221">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="74de0-221">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="74de0-222">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="74de0-222">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="74de0-223">ComposedMessageProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="74de0-223">ComposedMessageProcessor.sln</span></span>|<span data-ttu-id="74de0-224">本示例的 Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="74de0-224">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="74de0-225">ComposedMessageProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="74de0-225">ComposedMessageProcessorBinding.xml</span></span>|<span data-ttu-id="74de0-226">本示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="74de0-226">Binding file for the sample.</span></span>|  
|<span data-ttu-id="74de0-227">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="74de0-227">Setup.bat</span></span>|<span data-ttu-id="74de0-228">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="74de0-228">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="74de0-229">在 Orchestration 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-229">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="74de0-230">CMP.odx</span><span class="sxs-lookup"><span data-stu-id="74de0-230">CMP.odx</span></span>|<span data-ttu-id="74de0-231">用于执行以下操作的业务流程：运行接收管道以拆装消息，转换每个拆装的消息，然后运行发送管道以将多个消息组装为一个交换。</span><span class="sxs-lookup"><span data-stu-id="74de0-231">Orchestration that runs the receive pipeline to disassembler message, transforms each disassembled message and then runs send pipeline to assemble messages into an interchange.</span></span>|  
|<span data-ttu-id="74de0-232">在 Orchestration 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-232">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="74de0-233">Orchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="74de0-233">Orchestration.btproj</span></span>|<span data-ttu-id="74de0-234">业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="74de0-234">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="74de0-235">在 Orchestration 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-235">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="74de0-236">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="74de0-236">SuspendMessage.odx</span></span>|<span data-ttu-id="74de0-237">用于挂起无法进行管道处理的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="74de0-237">Orchestration used for suspending messages that fail pipeline processing.</span></span>|  
|<span data-ttu-id="74de0-238">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-238">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="74de0-239">CMPInput.xml、CMPOutput.xml</span><span class="sxs-lookup"><span data-stu-id="74de0-239">CMPInput.xml, CMPOutput.xml</span></span>|<span data-ttu-id="74de0-240">示例的输入和输出文档实例。</span><span class="sxs-lookup"><span data-stu-id="74de0-240">Input and output document instances for the sample.</span></span>|  
|<span data-ttu-id="74de0-241">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-241">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="74de0-242">FFReceivePipeline.btp、FFSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="74de0-242">FFReceivePipeline.btp, FFSendPipeline.btp</span></span>|<span data-ttu-id="74de0-243">具有平面文件组件的接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="74de0-243">Receive and send pipelines with flat file components.</span></span> <span data-ttu-id="74de0-244">这些管道在业务流程内运行。</span><span class="sxs-lookup"><span data-stu-id="74de0-244">These pipelines are run within orchestration.</span></span>|  
|<span data-ttu-id="74de0-245">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-245">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="74de0-246">Invoice.xsd、InvoiceHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="74de0-246">Invoice.xsd, InvoiceHeader.xsd</span></span>|<span data-ttu-id="74de0-247">用于输出文档和标头的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="74de0-247">Flat file schemas for the output document and header.</span></span>|  
|<span data-ttu-id="74de0-248">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-248">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="74de0-249">PO.xsd、POHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="74de0-249">PO.xsd, POHeader.xsd</span></span>|<span data-ttu-id="74de0-250">用于输入文档和标头的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="74de0-250">Flat file schemas for the input document and header.</span></span>|  
|<span data-ttu-id="74de0-251">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="74de0-251">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="74de0-252">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="74de0-252">PropertySchema.xsd</span></span>|<span data-ttu-id="74de0-253">本示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="74de0-253">Property schema for the sample.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="74de0-254">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="74de0-254">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="74de0-255">使用以下过程可以生成并初始化 Compose 示例。</span><span class="sxs-lookup"><span data-stu-id="74de0-255">Use the following procedure to build and initialize the Compose sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="74de0-256">生成并初始化 Compose 示例</span><span class="sxs-lookup"><span data-stu-id="74de0-256">To build and initialize the Compose sample</span></span>  
  
1.  <span data-ttu-id="74de0-257">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="74de0-257">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="74de0-258">\<示例路径\>\Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="74de0-258">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span></span>  
  
2.  <span data-ttu-id="74de0-259">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74de0-259">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="74de0-260">在以下文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="74de0-260">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="74de0-261">\<示例路径\>\Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="74de0-261">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span></span>  
  
    -   <span data-ttu-id="74de0-262">编译此示例的 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="74de0-262">Compiles the Visual Studio projects for this sample.</span></span>  
  
    -   <span data-ttu-id="74de0-263">创建名为“CMP Sample”的新应用程序并将示例程序集部署到该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="74de0-263">Creates a new application called "CMP Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="74de0-264">创建并绑定 BizTalk Server 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="74de0-264">Creates and binds the BizTalk Server receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="74de0-265">登记并启动业务流程，启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="74de0-265">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="74de0-266">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="74de0-266">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="74de0-267">使用该密钥对可以对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="74de0-267">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="74de0-268">在尝试运行本示例之前，请确认在生成和初始化过程中 BizTalk Server 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="74de0-268">Before attempting to run this sample, confirm that BizTalk Server did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="74de0-269">若要撤销 Setup.bat 所做的更改，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74de0-269">To undo changes made by Setup.bat, you must do the following:</span></span>  
  
    1.  <span data-ttu-id="74de0-270">从 BizTalk Server 管理控制台停止并重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="74de0-270">Stop and restart the host instance from the BizTalk Server Administration console.</span></span>  
  
    2.  <span data-ttu-id="74de0-271">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="74de0-271">Run Cleanup.bat.</span></span> <span data-ttu-id="74de0-272">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="74de0-272">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="74de0-273">运行示例</span><span class="sxs-lookup"><span data-stu-id="74de0-273">Running the sample</span></span>  
 <span data-ttu-id="74de0-274">使用以下过程运行 ComposedMessageProcessor 示例。</span><span class="sxs-lookup"><span data-stu-id="74de0-274">Use the following procedure to run the ComposedMessageProcessor sample.</span></span>  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a><span data-ttu-id="74de0-275">运行 ComposedMessageProcessor 示例</span><span class="sxs-lookup"><span data-stu-id="74de0-275">To run the ComposedMessageProcessor sample</span></span>  
  
1.  <span data-ttu-id="74de0-276">将复制 CMPInput.txt 位于 PipelinesAndSchemas 文件夹中的文本文件。</span><span class="sxs-lookup"><span data-stu-id="74de0-276">Copy the text file CMPInput.txt located in the PipelinesAndSchemas folder.</span></span> <span data-ttu-id="74de0-277">将该文件粘贴到 In 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="74de0-277">Paste the file into the folder In.</span></span>  
  
2.  <span data-ttu-id="74de0-278">查看在 Out 文件夹中创建的文本文件。此文件包含与 CMPInput.txt 相同的记录，但是文件中的数据格式不同。</span><span class="sxs-lookup"><span data-stu-id="74de0-278">Observe the text file created in the folder Out. This file contains the same records as the CMPInput.txt, but the format of data in the file is different.</span></span>  
  
     <span data-ttu-id="74de0-279">在消息通过 BizTalk Server 期间，执行了以下操作：</span><span class="sxs-lookup"><span data-stu-id="74de0-279">As the message passes through the BizTalk Server, the following happens:</span></span>  
  
    1.  <span data-ttu-id="74de0-280">拆装消息并将其转换为 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="74de0-280">The message gets disassembled and converted into XML messages.</span></span> <span data-ttu-id="74de0-281">将每个消息映射为其他格式。</span><span class="sxs-lookup"><span data-stu-id="74de0-281">Each message is mapped to a different format.</span></span>  
  
    2.  <span data-ttu-id="74de0-282">将所有映射消息组装到一起并将其转换为平面文件格式。</span><span class="sxs-lookup"><span data-stu-id="74de0-282">All mapped messages are assembled together and converted into the flat file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74de0-283">请参阅</span><span class="sxs-lookup"><span data-stu-id="74de0-283">See Also</span></span>  
 [<span data-ttu-id="74de0-284">管道（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="74de0-284">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)