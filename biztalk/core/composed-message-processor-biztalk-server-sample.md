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
ms.openlocfilehash: a6a072a889403abd474a31625eba86f9e28a2da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356651"
---
# <a name="composed-message-processor-biztalk-server-sample"></a><span data-ttu-id="ddbbf-102">组合的消息处理器 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ddbbf-102">Composed Message Processor (BizTalk Server Sample)</span></span>
<span data-ttu-id="ddbbf-103">此示例的目的是构建处理聚合消息中的各个行项的组合的消息处理器应用程序。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-103">The purpose of this sample is to build a composed message processor application that processes individual line items from aggregated messages.</span></span>  
  
 <span data-ttu-id="ddbbf-104">特别是我们将该生成业务流程调度：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-104">Specifically we will build an orchestration schedule that:</span></span>  
  
1. <span data-ttu-id="ddbbf-105">接收包含多个采购订单的批处理的交换消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-105">Receives a batched interchange message consisting of multiple purchase orders.</span></span>  
  
2. <span data-ttu-id="ddbbf-106">将交换消息分解为单独的采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-106">Disassembles the interchange message into individual purchase order documents.</span></span>  
  
3. <span data-ttu-id="ddbbf-107">处理每个文档-每个采购订单转换为发票消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-107">Processes each document – converts each purchase order into an invoice message.</span></span>  
  
4. <span data-ttu-id="ddbbf-108">将所有发票消息都组装为批处理交换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-108">Assembles all the invoice messages into a batched interchange.</span></span>  
  
   <span data-ttu-id="ddbbf-109">步骤 #3 得到了简化，示例目的。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-109">Step #3 is simplified for the sample purposes.</span></span> <span data-ttu-id="ddbbf-110">例如，在更复杂的应用程序，业务流程可能发送分解到不同后端库存系统的采购订单，然后收集所有的响应之后, 将其聚合为一个批发的票消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-110">For example, in more complex applications, an orchestration may send disassembled purchase orders to different back-end inventory systems and then after collecting all the responses, aggregate them into one batched invoice message.</span></span>  
  
   <span data-ttu-id="ddbbf-111">组合的消息处理器模式的详细信息请参阅 [1]。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-111">For more information on the composed message processor pattern refer to [1].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ddbbf-112">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="ddbbf-112">What This Sample Does</span></span>  
 <span data-ttu-id="ddbbf-113">有以下各节详细地介绍这两个示例解决方案中的两个项目。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-113">There are two projects within the sample solution, both of which are described in detail in the following sections.</span></span>  
  
### <a name="pipelines-and-schemas"></a><span data-ttu-id="ddbbf-114">管道和架构</span><span class="sxs-lookup"><span data-stu-id="ddbbf-114">Pipelines and Schemas</span></span>  
 <span data-ttu-id="ddbbf-115">管道和架构的项目包含：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-115">Pipelines and schemas project contains:</span></span>  
  
-   <span data-ttu-id="ddbbf-116">对于输入的采购订单的交换和用于输出发票交换的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-116">Flat file schemas for input purchase order interchange and for output invoice interchange.</span></span>  
  
-   <span data-ttu-id="ddbbf-117">用于将采购订单文档转换为发票文档的映射。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-117">Map to transform purchase order document into an invoice document.</span></span>  
  
-   <span data-ttu-id="ddbbf-118">接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-118">Receive and send pipelines.</span></span>  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a><span data-ttu-id="ddbbf-119">输入和输出交换的平面文件架构</span><span class="sxs-lookup"><span data-stu-id="ddbbf-119">Flat File Schemas For Input and Output Interchanges</span></span>  
 <span data-ttu-id="ddbbf-120">我们的示例应用程序将使用在平面文件格式交换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-120">Our sample application will be working with the interchanges in the flat file format.</span></span> <span data-ttu-id="ddbbf-121">以下是交换采购订单和发票交换的示例：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-121">Below are the examples of the purchase order interchange and invoice interchange:</span></span>  
  
 <span data-ttu-id="ddbbf-122">采购订单的交换 (CMPInput.txt):</span><span class="sxs-lookup"><span data-stu-id="ddbbf-122">Purchase order interchange (CMPInput.txt):</span></span>  
  
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
  
 <span data-ttu-id="ddbbf-123">采购订单文档或交换，具有标头，用于标识包含哪种类型的文档：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-123">The interchange, or purchase order document, has a header that identifies what type of the documents it contains:</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 <span data-ttu-id="ddbbf-124">此交换包含三个采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-124">This interchange consist of three purchase order documents.</span></span> <span data-ttu-id="ddbbf-125">一个实例包含如下所示的信息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-125">One instance consists of the information shown below.</span></span> <span data-ttu-id="ddbbf-126">正如您所看到的它包含针对计费和传送的已排序的项列表以及地址等信息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-126">As you can see, it contains such information as address for billing and shipping as well as the list of items that were ordered.</span></span>  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 <span data-ttu-id="ddbbf-127">我们想要为此生成发票交换应如以下所示：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-127">The invoice interchange we want to generate for this should look like the following:</span></span>  
  
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
  
 <span data-ttu-id="ddbbf-128">此交换包含已在购买顺序交换和交换的格式以及标头的格式也是不同的信息的子集。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-128">This interchange contains a subset of information that was in purchase order interchange and also the format of the interchange as well as format of the header are different.</span></span>  
  
 <span data-ttu-id="ddbbf-129">标头如下所示：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-129">The header is as follows:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 <span data-ttu-id="ddbbf-130">和文档实例包括以下：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-130">And the document instance includes the following:</span></span>  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 <span data-ttu-id="ddbbf-131">第一件事我们需要创建用于平面文件架构：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-131">First thing we need to create flat file schemas for:</span></span>  
  
- <span data-ttu-id="ddbbf-132">采购订单文档 (PO.xsd)</span><span class="sxs-lookup"><span data-stu-id="ddbbf-132">Purchase order document (PO.xsd)</span></span>  
  
- <span data-ttu-id="ddbbf-133">发票文档 (Invoice.xsd)</span><span class="sxs-lookup"><span data-stu-id="ddbbf-133">Invoice document (Invoice.xsd)</span></span>  
  
- <span data-ttu-id="ddbbf-134">采购订单标题 (POHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="ddbbf-134">Purchase order header (POHeader.xsd)</span></span>  
  
- <span data-ttu-id="ddbbf-135">发票标头 (InvoiceHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="ddbbf-135">Invoice header (InvoiceHeader.xsd)</span></span>  
  
  <span data-ttu-id="ddbbf-136">对于此示例，我们不打算介绍创建平面文件架构的过程。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-136">For this sample, we are not going to explain the process of creating flat file schemas.</span></span> <span data-ttu-id="ddbbf-137">若要了解如何从文档实例创建平面文件架构，请参阅"从文档实例创建平面文件架构"文档部分。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-137">To learn how to create flat file schemas from document instances, refer to the "Creating flat file schemas from document instance" documentation section.</span></span>  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a><span data-ttu-id="ddbbf-138">用于将采购订单文档转换为发票文档的映射</span><span class="sxs-lookup"><span data-stu-id="ddbbf-138">Map to Transform Purchase Order Document Into Invoice Document</span></span>  
 <span data-ttu-id="ddbbf-139">地图 (PO2Invoice.btm) 将采购订单的实例转换为发票文档。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-139">The map (PO2Invoice.btm) transforms an instance of the purchase order into an invoice document.</span></span>  
  
#### <a name="receive-and-send-pipelines"></a><span data-ttu-id="ddbbf-140">接收和发送管道</span><span class="sxs-lookup"><span data-stu-id="ddbbf-140">Receive and Send Pipelines</span></span>  
 <span data-ttu-id="ddbbf-141">接收管道 (FFReceivePipeline.btp) 包含用于处理采购订单交换的平面文件拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-141">The receive pipeline (FFReceivePipeline.btp) contains a flat file disassembler component that is used to process a purchase order interchange.</span></span> <span data-ttu-id="ddbbf-142">具体而言，对于文件 CMPInput.txt 中交换，它删除交换标头，并生成对应于三个采购订单的三个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-142">In particular, for the interchange in file CMPInput.txt, it removes the interchange header and produces three XML documents corresponding to three purchase orders.</span></span>  
  
 <span data-ttu-id="ddbbf-143">配置接收管道中的平面文件拆装器所示：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-143">The flat file disassembler in the receive pipeline is configured as shown:</span></span>  
  
- <span data-ttu-id="ddbbf-144">**文档架构：** PipelinesAndSchemas.PO</span><span class="sxs-lookup"><span data-stu-id="ddbbf-144">**Document schema:** PipelinesAndSchemas.PO</span></span>  
  
- <span data-ttu-id="ddbbf-145">**标头架构：** PipelinesAndSchemas.POHeader</span><span class="sxs-lookup"><span data-stu-id="ddbbf-145">**Header schema:** PipelinesAndSchemas.POHeader</span></span>  
  
- <span data-ttu-id="ddbbf-146">**保留头部：** False</span><span class="sxs-lookup"><span data-stu-id="ddbbf-146">**Preserve header:** False</span></span>  
  
- <span data-ttu-id="ddbbf-147">**可恢复的交换：** False</span><span class="sxs-lookup"><span data-stu-id="ddbbf-147">**Recoverable interchange:** False</span></span>  
  
- <span data-ttu-id="ddbbf-148">**尾部架构：**（无）</span><span class="sxs-lookup"><span data-stu-id="ddbbf-148">**Trailer schema:** (None)</span></span>  
  
- <span data-ttu-id="ddbbf-149">**验证文档结构：** False</span><span class="sxs-lookup"><span data-stu-id="ddbbf-149">**Validate document structure:** False</span></span>  
  
  <span data-ttu-id="ddbbf-150">发送管道 (FFSendPipeline.btp) 包含用于创建聚合的发票交换的平面文件组装器组件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-150">The send pipeline (FFSendPipeline.btp) contains a flat file assembler component that is used to create aggregated invoice interchange.</span></span>  
  
  <span data-ttu-id="ddbbf-151">配置发送管道中的平面文件组装器所示：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-151">The flat file assembler in send pipeline is configured as shown:</span></span>  
  
- <span data-ttu-id="ddbbf-152">**文档架构：** PipelinesandSchemas.Invoice</span><span class="sxs-lookup"><span data-stu-id="ddbbf-152">**Document schema:** PipelinesandSchemas.Invoice</span></span>  
  
- <span data-ttu-id="ddbbf-153">**标头架构：** PipelinesAndSchemas.InvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="ddbbf-153">**Header schema:** PipelinesAndSchemas.InvoiceHeader</span></span>  
  
- <span data-ttu-id="ddbbf-154">**保留字节顺序标记：** False</span><span class="sxs-lookup"><span data-stu-id="ddbbf-154">**Preserve byte order mark:** False</span></span>  
  
- <span data-ttu-id="ddbbf-155">**目标字符集：**（无）</span><span class="sxs-lookup"><span data-stu-id="ddbbf-155">**Target charset:** (None)</span></span>  
  
- <span data-ttu-id="ddbbf-156">**尾部架构：**（无）</span><span class="sxs-lookup"><span data-stu-id="ddbbf-156">**Trailer schema:** (None)</span></span>  
  
### <a name="orchestration-schedule"></a><span data-ttu-id="ddbbf-157">业务流程调度</span><span class="sxs-lookup"><span data-stu-id="ddbbf-157">Orchestration Schedule</span></span>  
 <span data-ttu-id="ddbbf-158">业务流程调度 (CMP.odx) 是所有主处理发生的位置。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-158">Orchestration schedule (CMP.odx) is where all the main processing happens.</span></span> <span data-ttu-id="ddbbf-159">执行专门的以下操作：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-159">Specifically the following actions are performed:</span></span>  
  
-   <span data-ttu-id="ddbbf-160">接收管道执行以拆装交换采购订单</span><span class="sxs-lookup"><span data-stu-id="ddbbf-160">Receive pipeline is executed to disassemble purchase order interchange</span></span>  
  
-   <span data-ttu-id="ddbbf-161">接收管道的每个输出消息转换</span><span class="sxs-lookup"><span data-stu-id="ddbbf-161">Every output message of receive pipeline is transformed</span></span>  
  
-   <span data-ttu-id="ddbbf-162">发送管道执行来汇集的发票交换</span><span class="sxs-lookup"><span data-stu-id="ddbbf-162">Send pipeline is executed to assemble an invoice interchange</span></span>  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a><span data-ttu-id="ddbbf-163">创建业务流程调度和定义全局变量</span><span class="sxs-lookup"><span data-stu-id="ddbbf-163">Creating Orchestration Schedule and Defining Global Variables</span></span>  
 <span data-ttu-id="ddbbf-164">我们的业务流程将收到作为输入的平面文件交换，并将作为输出发送平面文件交换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-164">Our orchestration will receive a flat file interchange as an input and will send a flat file interchange as an output.</span></span> <span data-ttu-id="ddbbf-165">正因为如此，我们需要定义输入和输出消息 （称为 InputInterchange 和 OutputInterchange 分别） 为的类型无关 （即具有 System.Xml.XmlDocument 类型）。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-165">Because of that, we need to define input and output messages (called InputInterchange and OutputInterchange respectively) as type agnostic (i.e. having type of System.Xml.XmlDocument).</span></span>  
  
 <span data-ttu-id="ddbbf-166">此外，我们需要定义我们将在其中处理消息的原子作用域。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-166">Also, we need to define an atomic scope where we will process messages.</span></span> <span data-ttu-id="ddbbf-167">这是必需的因为可以在原子作用域内执行接收管道。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-167">This is required because the receive pipeline can be executed within atomic scope.</span></span>  
  
#### <a name="executing-receive-pipeline"></a><span data-ttu-id="ddbbf-168">执行接收管道</span><span class="sxs-lookup"><span data-stu-id="ddbbf-168">Executing Receive Pipeline</span></span>  
 <span data-ttu-id="ddbbf-169">下一步，我们将添加逻辑来执行接收管道的业务流程中收到的消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-169">As a next step, we will add logic to execute a receive pipeline for the message that was received in orchestration.</span></span> <span data-ttu-id="ddbbf-170">若要执行此操作，首先我们声明类型将作用域内的变量 （称为 RcvPipeOutput）。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-170">To do this, first we declare a variable (called RcvPipeOutput) of type Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages within the scope.</span></span> <span data-ttu-id="ddbbf-171">此变量是一个枚举器，可用于循环访问接收管道输出消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-171">This variable is an enumerator that allows us to cycle through the receive pipeline output messages.</span></span> <span data-ttu-id="ddbbf-172">请注意，为了从业务流程中访问此类型，以及有关执行管道的所有其他类型，您都需要添加对以下程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-172">Note that in order to access this type, as well as all the other types for execution of pipelines from orchestration, you need to add references to the following assemblies:</span></span>  
  
- <span data-ttu-id="ddbbf-173">Microsoft.XLANGs.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="ddbbf-173">Microsoft.XLANGs.Pipeline.dll</span></span>  
  
- <span data-ttu-id="ddbbf-174">Microsoft.BizTalk.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="ddbbf-174">Microsoft.BizTalk.Pipeline.dll</span></span>  
  
  <span data-ttu-id="ddbbf-175">则均会成功执行接收管道无法保证。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-175">There is no guarantee that the receive pipeline will always execute successfully.</span></span> <span data-ttu-id="ddbbf-176">有时消息可能格式不正确，这可能会导致管道处理失败。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-176">Sometimes messages may be malformed, which would cause the pipeline processing to fail.</span></span> <span data-ttu-id="ddbbf-177">当管道失败时执行业务流程中的时，没有可以捕获所引发的异常，并且可以执行错误处理逻辑。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-177">When a pipeline fails execution in the orchestration, there is an exception thrown that can be caught and the error handling logic can be performed.</span></span> <span data-ttu-id="ddbbf-178">为了使我们能够捕获管道引发的异常，我们需要使用异常处理的非原子作用域内执行管道。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-178">In order for us to catch the exception thrown by pipeline, we need to execute the pipeline within a non-atomic scope with an exception handling.</span></span> <span data-ttu-id="ddbbf-179">要执行管道的实际代码是从该范围内的表达式形状调用的。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-179">The actual code to execute pipeline is invoked from an expression shape within that scope.</span></span>  
  
  <span data-ttu-id="ddbbf-180">在 ExecuteRcvPipe 表达式形状中，编写代码以执行接收管道的以下行：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-180">In the ExecuteRcvPipe expression shape, write the following line of code to execute the receive pipeline:</span></span>  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 <span data-ttu-id="ddbbf-181">让我们来分析这行代码中更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-181">Let's analyze this line of code in more detail.</span></span> <span data-ttu-id="ddbbf-182">正如您所看到的我们调用静态方法 ExecuteReceivePipeline 将作为参数接收管道执行和到输入的消息的类型。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-182">As you can see, we call a static method ExecuteReceivePipeline that takes as a parameter a type of receive pipeline to execute and an input message.</span></span> <span data-ttu-id="ddbbf-183">因此，它将生成输出消息的设置的枚举器对象。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-183">As a result, it produces an enumerator object with the set of output messages.</span></span> <span data-ttu-id="ddbbf-184">结果赋给类型在此范围中定义的 ReceivePipelineOutputMessages 的变量。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-184">The result is assigned to a variable of type ReceivePipelineOutputMessages that was defined in this scope before.</span></span>  
  
 <span data-ttu-id="ddbbf-185">我们还包含了一个异常处理块为管道执行作用域。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-185">We have also included an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="ddbbf-186">此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义的错误消息的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-186">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
 <span data-ttu-id="ddbbf-187">在更复杂的情况下，其他错误处理此时可能会执行，如生成错误通知消息并将其发送给业务用户或管理员使用电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-187">In more complex scenarios, additional error handling can be performed here, such as generation or the error notification message and sending it to a business user or administrator using email.</span></span>  
  
#### <a name="transforming-pipeline-output-messages"></a><span data-ttu-id="ddbbf-188">转换管道输出消息</span><span class="sxs-lookup"><span data-stu-id="ddbbf-188">Transforming Pipeline Output Messages</span></span>  
 <span data-ttu-id="ddbbf-189">已执行管道并生成拆装消息组之后，我们需要将每个输出消息转换为不同格式。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-189">After the pipeline has been executed and the set of disassembled messages has been produced, we need to transform each output message into a different format.</span></span>  
  
 <span data-ttu-id="ddbbf-190">若要在业务流程中使用转换，我们需要定义两个消息 – 输入和输出的转换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-190">To use transformation in orchestration we need to define two messages – transformation input and output.</span></span> <span data-ttu-id="ddbbf-191">我们将定义在原子作用域内的消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-191">We will define those messages within the atomic scope.</span></span> <span data-ttu-id="ddbbf-192">将名为 TmpMessageIn 的转换输入的消息属于 PipelinesAndSchemas.PO 类型。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-192">The transformation input message called TmpMessageIn will be of type PipelinesAndSchemas.PO.</span></span> <span data-ttu-id="ddbbf-193">将名为 TmpMessageOut 的转换输出消息属于 PipeliensAndSchemas.Invoice 类型。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-193">The transformation output message called TmpMessageOut will be of type PipeliensAndSchemas.Invoice.</span></span> <span data-ttu-id="ddbbf-194">我们将应用在 PipelinesAndSchemas 项目中定义的 PO2Invoice.btm 映射。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-194">We will apply the map PO2Invoice.btm that is defined in project PipelinesAndSchemas.</span></span>  
  
 <span data-ttu-id="ddbbf-195">作为我们想要将每个管道输出消息映射，我们需要在循环中执行转换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-195">As we want to map each pipeline output message we need to perform transformation in the loop.</span></span> <span data-ttu-id="ddbbf-196">我们将按如下所示退出条件中使用循环形状：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-196">We will use a loop shape with the condition for exiting as below:</span></span>  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 <span data-ttu-id="ddbbf-197">Movenext （） 方法是 IEnumerator.NET 接口，用于将管道输出消息集合中的标准方法。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-197">MoveNext() method is a standard method of IEnumerator .NET interface that allows to move within the collection of pipeline output messages.</span></span> <span data-ttu-id="ddbbf-198">当它到达集合的末尾时返回 false。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-198">When it reaches the end of collection it returns false.</span></span>  
  
 <span data-ttu-id="ddbbf-199">第一个构造形状用于构造管道输出消息从业务流程消息 TmpMessageIn。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-199">The first construct shape is used to construct an orchestration message TmpMessageIn out of the pipeline output message.</span></span>  
  
 <span data-ttu-id="ddbbf-200">构造形状中的代码：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-200">The code in the construct shape:</span></span>  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 <span data-ttu-id="ddbbf-201">在此代码中我们第一次业务流程消息初始化为 null，然后将其设置为当前消息从管道输出消息集合。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-201">In this code we first initialize orchestration message to null and then set it to the current message from the pipeline output messages collection.</span></span>  
  
 <span data-ttu-id="ddbbf-202">在执行 TmpMessageIn 的实际转换的第二个构造形状和类型的 TmpMessageOut PipelinesAndSchemas.Invoice 被构造。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-202">In second construct shape the actual transformation of the TmpMessageIn is performed and the TmpMessageOut of type PipelinesAndSchemas.Invoice is constructed.</span></span>  
  
#### <a name="executing-send-pipeline"></a><span data-ttu-id="ddbbf-203">执行发送管道</span><span class="sxs-lookup"><span data-stu-id="ddbbf-203">Executing Send Pipeline</span></span>  
 <span data-ttu-id="ddbbf-204">业务流程中的最后一个处理步骤是执行平面文件发送管道以将所有转换的 xml 消息组装为一个平面文件交换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-204">Last processing step in orchestration is to execute flat file send pipeline to assemble all the transformed xml messages into one flat file interchange.</span></span>  
  
 <span data-ttu-id="ddbbf-205">为了执行发送管道我们需要使用的变量的类型的变量 sendpipeinput，将保存业务流程需要在发送管道中处理的消息的集合。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-205">In order to execute a send pipeline we need to use a variable of type Microsoft.XLANGs.Pipeline.SendPipelineInputMessages called SendPipeInput that will hold a collection of orchestration messages that need to be processed in a send pipeline.</span></span>  
  
 <span data-ttu-id="ddbbf-206">在循环执行转换的最后一个表达式中，我们将编写代码，将添加到消息集合中的发送管道的每个已转换的消息：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-206">In the last expression of the loop where we performed transformation we will write a code that will add each transformed message to a message collection for send pipeline:</span></span>  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 <span data-ttu-id="ddbbf-207">与执行的过程相似的接收的管道的发送管道执行的代码放置在具有异常处理块的非原子作用域内。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-207">Similar to the part where we execute receive pipeline the code for execution of send pipeline is placed within a non-atomic scope with exception handling block.</span></span> <span data-ttu-id="ddbbf-208">发送管道执行代码位于构造模块的消息赋值形状中。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-208">The send pipeline execution code is located in the message assignment shape of the construct block.</span></span>  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 <span data-ttu-id="ddbbf-209">构造模块用于构造类型无关 (即 System.Xml.XmlDocument) 的管道输出消息 OutputInterchange。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-209">The construct block is used to construct type agnostic (i.e. System.Xml.XmlDocument) pipeline output message OutputInterchange.</span></span> <span data-ttu-id="ddbbf-210">然后在消息赋值形状中新构造的消息初始化为 null。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-210">Then in the message assignment shape the newly constructed message is initialized to null.</span></span> <span data-ttu-id="ddbbf-211">在此之后调用静态方法 ExecuteSendPipeline 以执行发送管道。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-211">After that the static method ExecuteSendPipeline is invoked to execute a send pipeline.</span></span> <span data-ttu-id="ddbbf-212">此方法采用一种类型的发送管道执行，输入的消息和对存储管道输出的输出消息的引用作为参数。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-212">This method takes as a parameter a type of the send pipeline to execute, the input message and the reference to output message where the pipeline output will be stored.</span></span>  
  
 <span data-ttu-id="ddbbf-213">与接收管道的执行，此处我们还有一种异常处理块管道执行作用域。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-213">As with the execution of the receive pipeline, here we also have an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="ddbbf-214">此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义的错误消息的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-214">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ddbbf-215">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="ddbbf-215">Where to Find This Sample</span></span>  
 <span data-ttu-id="ddbbf-216">下表列出了本示例的文件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-216">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="ddbbf-217">文件</span><span class="sxs-lookup"><span data-stu-id="ddbbf-217">File(s)</span></span>|<span data-ttu-id="ddbbf-218">Description</span><span class="sxs-lookup"><span data-stu-id="ddbbf-218">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddbbf-219">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="ddbbf-219">Cleanup.bat</span></span>|<span data-ttu-id="ddbbf-220">用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-220">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span><br /><br /> <span data-ttu-id="ddbbf-221">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-221">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="ddbbf-222">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-222">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="ddbbf-223">ComposedMessageProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="ddbbf-223">ComposedMessageProcessor.sln</span></span>|<span data-ttu-id="ddbbf-224">该示例的 visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-224">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="ddbbf-225">ComposedMessageProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="ddbbf-225">ComposedMessageProcessorBinding.xml</span></span>|<span data-ttu-id="ddbbf-226">该示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-226">Binding file for the sample.</span></span>|  
|<span data-ttu-id="ddbbf-227">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ddbbf-227">Setup.bat</span></span>|<span data-ttu-id="ddbbf-228">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-228">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="ddbbf-229">在业务流程文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-229">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-230">CMP.odx</span><span class="sxs-lookup"><span data-stu-id="ddbbf-230">CMP.odx</span></span>|<span data-ttu-id="ddbbf-231">业务流程： 运行接收管道以拆装消息，每个已拆装的消息转换，然后运行发送管道以将消息组装为一个交换。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-231">Orchestration that runs the receive pipeline to disassembler message, transforms each disassembled message and then runs send pipeline to assemble messages into an interchange.</span></span>|  
|<span data-ttu-id="ddbbf-232">在业务流程文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-232">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-233">Orchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="ddbbf-233">Orchestration.btproj</span></span>|<span data-ttu-id="ddbbf-234">业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-234">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="ddbbf-235">在业务流程文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-235">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-236">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="ddbbf-236">SuspendMessage.odx</span></span>|<span data-ttu-id="ddbbf-237">用于挂起无法进行管道处理的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-237">Orchestration used for suspending messages that fail pipeline processing.</span></span>|  
|<span data-ttu-id="ddbbf-238">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-238">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-239">CMPInput.xml、 CMPOutput.xml</span><span class="sxs-lookup"><span data-stu-id="ddbbf-239">CMPInput.xml, CMPOutput.xml</span></span>|<span data-ttu-id="ddbbf-240">输入和输出的示例文档实例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-240">Input and output document instances for the sample.</span></span>|  
|<span data-ttu-id="ddbbf-241">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-241">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-242">FFReceivePipeline.btp, FFSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="ddbbf-242">FFReceivePipeline.btp, FFSendPipeline.btp</span></span>|<span data-ttu-id="ddbbf-243">接收和发送管道使用平面文件组件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-243">Receive and send pipelines with flat file components.</span></span> <span data-ttu-id="ddbbf-244">这些管道业务流程内运行。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-244">These pipelines are run within orchestration.</span></span>|  
|<span data-ttu-id="ddbbf-245">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-245">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-246">Invoice.xsd、 InvoiceHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="ddbbf-246">Invoice.xsd, InvoiceHeader.xsd</span></span>|<span data-ttu-id="ddbbf-247">输出文档和标头的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-247">Flat file schemas for the output document and header.</span></span>|  
|<span data-ttu-id="ddbbf-248">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-248">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-249">PO.xsd、 POHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="ddbbf-249">PO.xsd, POHeader.xsd</span></span>|<span data-ttu-id="ddbbf-250">输入的文档和标头的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-250">Flat file schemas for the input document and header.</span></span>|  
|<span data-ttu-id="ddbbf-251">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-251">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="ddbbf-252">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="ddbbf-252">PropertySchema.xsd</span></span>|<span data-ttu-id="ddbbf-253">该示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-253">Property schema for the sample.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="ddbbf-254">生成并初始化示例</span><span class="sxs-lookup"><span data-stu-id="ddbbf-254">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="ddbbf-255">使用以下过程生成并初始化 Compose 示例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-255">Use the following procedure to build and initialize the Compose sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="ddbbf-256">若要生成并初始化 Compose 示例</span><span class="sxs-lookup"><span data-stu-id="ddbbf-256">To build and initialize the Compose sample</span></span>  
  
1.  <span data-ttu-id="ddbbf-257">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-257">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="ddbbf-258">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="ddbbf-258">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span></span>  
  
2.  <span data-ttu-id="ddbbf-259">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-259">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="ddbbf-260">创建输入 (In) 和输出 (Out) 文件夹的文件夹中的以下示例：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-260">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="ddbbf-261">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="ddbbf-261">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span></span>  
  
    -   <span data-ttu-id="ddbbf-262">编译此示例的 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-262">Compiles the Visual Studio projects for this sample.</span></span>  
  
    -   <span data-ttu-id="ddbbf-263">创建名为"CMP Sample"的新应用程序和部署到其中的示例程序集。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-263">Creates a new application called "CMP Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="ddbbf-264">创建并绑定 BizTalk Server 接收位置、 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-264">Creates and binds the BizTalk Server receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="ddbbf-265">登记和启动业务流程，启用接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-265">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="ddbbf-266">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-266">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="ddbbf-267">使用此密钥对可以对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-267">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="ddbbf-268">然后再尝试运行此示例中，确认在生成和初始化过程中 BizTalk Server 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-268">Before attempting to run this sample, confirm that BizTalk Server did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="ddbbf-269">若要撤消 Setup.bat 所做的更改，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-269">To undo changes made by Setup.bat, you must do the following:</span></span>  
  
    1.  <span data-ttu-id="ddbbf-270">停止并重新启动 BizTalk Server 管理控制台中的主机实例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-270">Stop and restart the host instance from the BizTalk Server Administration console.</span></span>  
  
    2.  <span data-ttu-id="ddbbf-271">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-271">Run Cleanup.bat.</span></span> <span data-ttu-id="ddbbf-272">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-272">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="ddbbf-273">运行示例</span><span class="sxs-lookup"><span data-stu-id="ddbbf-273">Running the sample</span></span>  
 <span data-ttu-id="ddbbf-274">使用以下过程运行 ComposedMessageProcessor 示例。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-274">Use the following procedure to run the ComposedMessageProcessor sample.</span></span>  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a><span data-ttu-id="ddbbf-275">若要运行 ComposedMessageProcessor 示例</span><span class="sxs-lookup"><span data-stu-id="ddbbf-275">To run the ComposedMessageProcessor sample</span></span>  
  
1.  <span data-ttu-id="ddbbf-276">将复制 CMPInput.txt 位于 PipelinesAndSchemas 文件夹中的文本文件。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-276">Copy the text file CMPInput.txt located in the PipelinesAndSchemas folder.</span></span> <span data-ttu-id="ddbbf-277">将该文件粘贴到 in 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-277">Paste the file into the folder In.</span></span>  
  
2.  <span data-ttu-id="ddbbf-278">查看在 Out 文件夹中创建的文本文件。此文件包含与 CMPInput.txt，相同的记录，但文件中的数据的格式不同。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-278">Observe the text file created in the folder Out. This file contains the same records as the CMPInput.txt, but the format of data in the file is different.</span></span>  
  
     <span data-ttu-id="ddbbf-279">如该消息通过 BizTalk Server 会传递，将发生下列情况：</span><span class="sxs-lookup"><span data-stu-id="ddbbf-279">As the message passes through the BizTalk Server, the following happens:</span></span>  
  
    1.  <span data-ttu-id="ddbbf-280">拆装消息并将转换为 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-280">The message gets disassembled and converted into XML messages.</span></span> <span data-ttu-id="ddbbf-281">每个消息映射到不同的格式。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-281">Each message is mapped to a different format.</span></span>  
  
    2.  <span data-ttu-id="ddbbf-282">所有映射的消息组装到一起并转换为平面文件格式。</span><span class="sxs-lookup"><span data-stu-id="ddbbf-282">All mapped messages are assembled together and converted into the flat file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbbf-283">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddbbf-283">See Also</span></span>  
 [<span data-ttu-id="ddbbf-284">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="ddbbf-284">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)