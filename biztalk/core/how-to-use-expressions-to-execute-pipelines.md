---
title: 如何使用表达式执行管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ExecuteReceivePipeline() method
- pipelines, schema resolution
- ExecuteSendPipeline() method
- SendPipelineInputMessages class
- pipelines, restrictions
- pipelines, errors
- XLANGPipelineManager class
- receive pipelines, orchestrations
- ReceivePipelineOutputMessages class
- orchestrations, pipelines
- pipelines, component types
- send pipelines, orchestrations
- pipelines, states
- pipelines, executing
- Microsoft.XLANGs.Pipeline namespace
- pipelines, transactional
- pipelines, orchestrations
- Message Assignment shape [Orchestration Designer], pipelines
ms.assetid: f947fa73-526c-4747-8de7-df557a93056c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2da3d12ac8df31fc8f63db69b4611b58c58df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383374"
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a><span data-ttu-id="44e0d-102">如何使用表达式执行管道</span><span class="sxs-lookup"><span data-stu-id="44e0d-102">How to Use Expressions to Execute Pipelines</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="44e0d-103">具有以同步方式调用从业务流程内的管道的能力。</span><span class="sxs-lookup"><span data-stu-id="44e0d-103">has the ability to synchronously call a pipeline from within an Orchestration.</span></span> <span data-ttu-id="44e0d-104">这使业务流程能够利用封装在管道中的消息处理 （发送或接收） 针对数据而无需将该数据通过消息传送基础结构发送的正文。</span><span class="sxs-lookup"><span data-stu-id="44e0d-104">This enables orchestrations to leverage the message processing encapsulated within a pipeline (either send or receive) against a body of data without having to send that data through the messaging infrastructure.</span></span>  
  
 <span data-ttu-id="44e0d-105">可以使用此功能，以调用若干消息聚合到单个传出交换的发送管道业务流程。</span><span class="sxs-lookup"><span data-stu-id="44e0d-105">You can use this feature to enable an orchestration to call a send pipeline in order to aggregate several messages into a single outgoing interchange.</span></span> <span data-ttu-id="44e0d-106">相反，业务流程可以调用接收管道进行解码和拆装之外消息传送基础结构，而不会产生的消息框通过处理成本获得的交换。</span><span class="sxs-lookup"><span data-stu-id="44e0d-106">Conversely, an orchestration could call a receive pipeline to decode and disassemble an interchange obtained outside of the messaging infrastructure, without incurring the processing costs of going through the message box.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44e0d-107">详细信息</span><span class="sxs-lookup"><span data-stu-id="44e0d-107">Details</span></span>  
 <span data-ttu-id="44e0d-108">业务流程使用中的方法**XLANGPipelineManager**类 (在**Microsoft.XLANGs.Pipeline**命名空间) 来调用发送或接收管道。</span><span class="sxs-lookup"><span data-stu-id="44e0d-108">Orchestrations use methods in the **XLANGPipelineManager** class (in the **Microsoft.XLANGs.Pipeline** namespace) to call send or receive pipelines.</span></span>  <span data-ttu-id="44e0d-109">接收管道使用单条消息或一个交换并生成零个或多个消息，就像管道在接收 BizTalk 消息传送中的消息的上下文中在执行时。</span><span class="sxs-lookup"><span data-stu-id="44e0d-109">A Receive pipeline consumes either a single message or an interchange and yields zero or more messages, just as when the pipeline executes in the context of receiving a message within BizTalk messaging.</span></span> <span data-ttu-id="44e0d-110">发送管道使用一个或多个消息并生成单条消息或交换，同样，就像管道发送在 BizTalk 消息传送消息的上下文中在执行时。</span><span class="sxs-lookup"><span data-stu-id="44e0d-110">A Send pipeline consumes one or more messages and yields a single message or interchange, again, just as when the pipeline executes in the context of sending a message within BizTalk messaging.</span></span>  
  
## <a name="calling-a-receive-pipeline"></a><span data-ttu-id="44e0d-111">调用接收管道</span><span class="sxs-lookup"><span data-stu-id="44e0d-111">Calling a Receive Pipeline</span></span>  
 <span data-ttu-id="44e0d-112">若要调用接收管道从业务流程，应用程序调用内部**executereceivepipeline （)** 方法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="44e0d-112">In order to call a receive pipeline from within an orchestration, the application calls the **ExecuteReceivePipeline()** method of the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="44e0d-113">此方法使用单个交换并返回零个或多个消息的集合 (包含在的实例中**ReceivePipelineOutputMessages**类)。</span><span class="sxs-lookup"><span data-stu-id="44e0d-113">This method consumes a single interchange and returns a collection of zero or more messages (contained in an instance of the **ReceivePipelineOutputMessages** class).</span></span> <span data-ttu-id="44e0d-114">有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="44e0d-114">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  
  
 <span data-ttu-id="44e0d-115">执行接收管道从业务流程中的 API 是：</span><span class="sxs-lookup"><span data-stu-id="44e0d-115">The API for executing a receive pipeline from within an orchestration is:</span></span>  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 <span data-ttu-id="44e0d-116">通常会中完成对接收管道的调用**表达式**形状在业务流程内的。</span><span class="sxs-lookup"><span data-stu-id="44e0d-116">A call to a receive pipeline would typically be done in an **Expression** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="44e0d-117">若要调用接收管道从业务流程中的，开发人员必须引用业务流程项目中的管道程序集。</span><span class="sxs-lookup"><span data-stu-id="44e0d-117">In order to call a receive pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span> <span data-ttu-id="44e0d-118">下面是调用接收管道的业务流程的示例：</span><span class="sxs-lookup"><span data-stu-id="44e0d-118">Following is an example of an orchestration that calls a receive pipeline:</span></span>  
  
 <span data-ttu-id="44e0d-119">![正在调用接收管道屏幕](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="44e0d-119">![Calling Receive Pipeline screen](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span></span>  
  
 <span data-ttu-id="44e0d-120">有关更详细的示例，请参阅 SDK 示例[组合消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="44e0d-120">For a more detailed example, see the SDK sample [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44e0d-121">类型的变量**ReceivePipelineOutputMessages**可以仅在业务流程中的原子作用域内声明。</span><span class="sxs-lookup"><span data-stu-id="44e0d-121">A variable of type **ReceivePipelineOutputMessages** can be declared only within an atomic scope in an orchestration.</span></span>  <span data-ttu-id="44e0d-122">这是因为此类型的变量不是可序列化，因此还不能在业务流程和业务流程绝对不会保存在原子作用域内执行时。</span><span class="sxs-lookup"><span data-stu-id="44e0d-122">This is because variables of this type are not serializable and thus would not survive persistence of the orchestration, and orchestrations are never persisted while executing within an atomic scope.</span></span>  <span data-ttu-id="44e0d-123">这意味着，可以仅在原子作用域内执行接收管道。</span><span class="sxs-lookup"><span data-stu-id="44e0d-123">This means that a receive pipeline can be executed only within an atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44e0d-124">调用时**PassThruReceive**管道或自定义管道组件从业务流程中的，您必须声明传入消息的变量类型，如 System.Xml.XmlDocument 的传入消息类型是否为 XML.</span><span class="sxs-lookup"><span data-stu-id="44e0d-124">When calling **PassThruReceive** pipeline or custom pipeline component from within an orchestration, you must declare the variable type for incoming message as System.Xml.XmlDocument despite of the incoming message type is XML or not.</span></span> <span data-ttu-id="44e0d-125">因此，如果你尝试对其进行非 XML 消息，例如平面文件格式的消息传入消息时可能会遇到异常。</span><span class="sxs-lookup"><span data-stu-id="44e0d-125">Therefore, you may encounter exception if you try to operate on it if the incoming message is a non-XML message such as a flat file format message.</span></span> <span data-ttu-id="44e0d-126">这是正因如此，业务流程引擎想要在上面所述的方案中的传入任何的消息类型都会使用 System.Xml.XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="44e0d-126">This is because of that orchestration engine intends to use System.Xml.XmlDocument for any type of incoming message in the scenario described above.</span></span>  
  
## <a name="calling-a-send-pipeline"></a><span data-ttu-id="44e0d-127">调用发送管道</span><span class="sxs-lookup"><span data-stu-id="44e0d-127">Calling a Send Pipeline</span></span>  
 <span data-ttu-id="44e0d-128">若要调用发送管道，从业务流程，应用程序调用内部**executesendpipeline （)** 方法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="44e0d-128">To call a send pipeline from within an orchestration, the application calls the **ExecuteSendPipeline()** method of the **XLANGPipelineManager** class.</span></span> <span data-ttu-id="44e0d-129">此方法使用一个或多个消息的集合 (包含在的实例中**SendPipelineInputMessages**类)，并返回单个交换。</span><span class="sxs-lookup"><span data-stu-id="44e0d-129">This method consumes a collection of one or more messages (contained in an instance of the **SendPipelineInputMessages** class) and returns a single interchange.</span></span> <span data-ttu-id="44e0d-130">有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="44e0d-130">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="44e0d-131">由于执行发送管道会生成一个新的交换，在调用**executesendpipeline （)** 方法必须在消息赋值形状中，这种情况下发生：</span><span class="sxs-lookup"><span data-stu-id="44e0d-131">Because execution of a send pipeline yields a new interchange, the call to **ExecuteSendPipeline()** method must be made within a message assignment shape, as such:</span></span>  
  
 <span data-ttu-id="44e0d-132">执行发送管道，从业务流程中的 API 是：</span><span class="sxs-lookup"><span data-stu-id="44e0d-132">The API for executing a send pipeline from within an orchestration is:</span></span>  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 <span data-ttu-id="44e0d-133">对发送管道的调用中必须进行**消息赋值**形状在业务流程内的。</span><span class="sxs-lookup"><span data-stu-id="44e0d-133">A call to a send pipeline must be done in a **Message Assignment** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="44e0d-134">若要调用从业务流程中的发送管道，开发人员必须引用业务流程项目中的管道程序集。</span><span class="sxs-lookup"><span data-stu-id="44e0d-134">In order to call a send pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span>  <span data-ttu-id="44e0d-135">调用发送管道的业务流程的示例：</span><span class="sxs-lookup"><span data-stu-id="44e0d-135">An example of an orchestration that calls a send pipeline:</span></span>  
  
 <span data-ttu-id="44e0d-136">![正在调用发送管道屏幕](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="44e0d-136">![Calling Send Pipeline screen](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44e0d-137">在调用默认 XMLTransmit 管道时，必须设置消息上下文属性 XMLNORM。EnvelopeSpecName 为信封架构的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="44e0d-137">When calling the default XMLTransmit pipeline, you must set the message context property XMLNORM.EnvelopeSpecName to the fully qualified name of the Envelope schema.</span></span> <span data-ttu-id="44e0d-138">例如：</span><span class="sxs-lookup"><span data-stu-id="44e0d-138">For example:</span></span>  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 <span data-ttu-id="44e0d-139">有关更详细的示例，请参阅 SDK 示例[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="44e0d-139">For a more detailed example, see the SDK sample [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="pipeline-execution---behavioral-differences"></a><span data-ttu-id="44e0d-140">管道执行-行为差异</span><span class="sxs-lookup"><span data-stu-id="44e0d-140">Pipeline Execution - Behavioral Differences</span></span>  
 <span data-ttu-id="44e0d-141">执行发送或接收管道时调用的业务流程主要是同一管道内消息传送基础结构在执行时相同 （即在接收位置或发送端口）。</span><span class="sxs-lookup"><span data-stu-id="44e0d-141">The execution of a send or receive pipeline when called by an orchestration is predominantly the same as when the same pipeline executes within the messaging infrastructure (i.e. at receive location or send port).</span></span>  <span data-ttu-id="44e0d-142">但是，有某些行为差异，如下所示。</span><span class="sxs-lookup"><span data-stu-id="44e0d-142">However, there are certain behavioral differences that are noted below.</span></span>  
  
### <a name="differences-within-pipeline-stages"></a><span data-ttu-id="44e0d-143">管道阶段中的差异</span><span class="sxs-lookup"><span data-stu-id="44e0d-143">Differences Within Pipeline Stages</span></span>  
 <span data-ttu-id="44e0d-144">执行阶段内发送或接收管道调用从 BizTalk 消息传送基础结构，按阶段所示的异常时，从业务流程中调用的管道是几乎完全相同的那些阶段执行下面。</span><span class="sxs-lookup"><span data-stu-id="44e0d-144">The execution of the stages within a send or receive pipeline that is called from within an orchestration is nearly identical to the execution of those stages when the pipeline is called from the BizTalk messaging infrastructure, with the exceptions noted by stage below.</span></span>  
  
-   <span data-ttu-id="44e0d-145">组装器/拆装器：组装器和拆装器阶段不会处理**跟踪配置文件**数据。</span><span class="sxs-lookup"><span data-stu-id="44e0d-145">Assembler/Disassembler:  The assembler and disassembler stages will not process **Tracking Profile** data.</span></span>  
  
-   <span data-ttu-id="44e0d-146">编码器/解码器：MIME 编码器进行数字签名使用在主机与之关联的主机上配置的证书的消息。</span><span class="sxs-lookup"><span data-stu-id="44e0d-146">Encoder/Decoder:  The MIME encoder digitally signs messages using the certificate configured at the host with which the host is associated.</span></span>  <span data-ttu-id="44e0d-147">SMIME 编码器对消息传递给管道的消息上下文中使用证书进行加密。</span><span class="sxs-lookup"><span data-stu-id="44e0d-147">The SMIME encoder encrypts messages using the certificate on the context of the message passed into the pipeline.</span></span>  
  
### <a name="schema-resolution"></a><span data-ttu-id="44e0d-148">架构解析</span><span class="sxs-lookup"><span data-stu-id="44e0d-148">Schema Resolution</span></span>  
 <span data-ttu-id="44e0d-149">有两种架构查找算法从业务流程执行管道时受支持：</span><span class="sxs-lookup"><span data-stu-id="44e0d-149">There are two schema lookup algorithms that are supported when executing a pipeline from an orchestration:</span></span>  
  
- <span data-ttu-id="44e0d-150">按类型解析</span><span class="sxs-lookup"><span data-stu-id="44e0d-150">Resolution by type</span></span>  
  
- <span data-ttu-id="44e0d-151">按名称解析</span><span class="sxs-lookup"><span data-stu-id="44e0d-151">Resolution by name</span></span>  
  
  <span data-ttu-id="44e0d-152">在部署重复架构的情况下，用于选择相应的架构的算法逻辑与消息传送基础结构的上下文中执行时使用完全相同。</span><span class="sxs-lookup"><span data-stu-id="44e0d-152">In cases where duplicate schemas are deployed, the algorithm's logic for selecting the appropriate schema is identical to that used when executing in the context of the messaging infrastructure.</span></span>  
  
### <a name="transactional-pipelines"></a><span data-ttu-id="44e0d-153">事务性管道</span><span class="sxs-lookup"><span data-stu-id="44e0d-153">Transactional Pipelines</span></span>  
 <span data-ttu-id="44e0d-154">管道的阶段调用了事务性组件没有可用的事务性上下文。</span><span class="sxs-lookup"><span data-stu-id="44e0d-154">Pipelines whose stages call transactional components will not have a transactional context available.</span></span>  <span data-ttu-id="44e0d-155">任何对**ipipelinecontext.gettransaction （)** 将引发**NotSupportedException**。</span><span class="sxs-lookup"><span data-stu-id="44e0d-155">Any call to **IPipelineContext.GetTransaction()** will throw **NotSupportedException**.</span></span>  <span data-ttu-id="44e0d-156">这不会阻止此类管道从业务流程的执行，但确实意味着管道，将需要检测并处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="44e0d-156">This does not preclude execution of such a pipeline from an orchestration, but it does mean that the pipeline will have to detect and handle this situation.</span></span>  
  
### <a name="message-destination"></a><span data-ttu-id="44e0d-157">消息目标</span><span class="sxs-lookup"><span data-stu-id="44e0d-157">Message Destination</span></span>  
 <span data-ttu-id="44e0d-158">在此上下文中不支持由管道组件控制消息目标。</span><span class="sxs-lookup"><span data-stu-id="44e0d-158">Controlling message destination by pipeline components is not supported in this context.</span></span>  <span data-ttu-id="44e0d-159">设置上下文属性**MessageDestination**或**SuspendOnRoutingFailure**将导致**XLANGPipelineManagerException**引发。</span><span class="sxs-lookup"><span data-stu-id="44e0d-159">Setting the context properties **MessageDestination** or **SuspendOnRoutingFailure** will cause an **XLANGPipelineManagerException** to be thrown.</span></span>  
  
### <a name="pipeline-component-types"></a><span data-ttu-id="44e0d-160">管道组件类型</span><span class="sxs-lookup"><span data-stu-id="44e0d-160">Pipeline Component Types</span></span>  
 <span data-ttu-id="44e0d-161">管道组件必须基于任务的以下为了从业务流程内部调用：</span><span class="sxs-lookup"><span data-stu-id="44e0d-161">Pipeline components must be based on the following in order to be called from within an orchestration:</span></span>  
  
-   <span data-ttu-id="44e0d-162">.NET Framework v1.1</span><span class="sxs-lookup"><span data-stu-id="44e0d-162">.NET Framework v1.1</span></span>  
  
-   <span data-ttu-id="44e0d-163">.NET Framework v2.0</span><span class="sxs-lookup"><span data-stu-id="44e0d-163">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="44e0d-164">.NET Framework v3.0</span><span class="sxs-lookup"><span data-stu-id="44e0d-164">.NET Framework v3.0</span></span>  
  
-   <span data-ttu-id="44e0d-165">.NET Framework v3.5</span><span class="sxs-lookup"><span data-stu-id="44e0d-165">.NET Framework v3.5</span></span>  
  
-   <span data-ttu-id="44e0d-166">.NET Framework v4.0</span><span class="sxs-lookup"><span data-stu-id="44e0d-166">.NET Framework v4.0</span></span>  
  
-   <span data-ttu-id="44e0d-167">.NET Framework v2.0</span><span class="sxs-lookup"><span data-stu-id="44e0d-167">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="44e0d-168">COM</span><span class="sxs-lookup"><span data-stu-id="44e0d-168">COM</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="44e0d-169">限制</span><span class="sxs-lookup"><span data-stu-id="44e0d-169">Restrictions</span></span>  
 <span data-ttu-id="44e0d-170">下列管道类型**不能**从业务流程内部执行：</span><span class="sxs-lookup"><span data-stu-id="44e0d-170">The following types of pipelines **cannot** be executed from within an orchestration:</span></span>  
  
- <span data-ttu-id="44e0d-171">事务性管道</span><span class="sxs-lookup"><span data-stu-id="44e0d-171">Transactional pipelines</span></span>  
  
- <span data-ttu-id="44e0d-172">可恢复管道</span><span class="sxs-lookup"><span data-stu-id="44e0d-172">Recoverable pipelines</span></span>  
  
- <span data-ttu-id="44e0d-173">管道调用 BAM 侦听器 API ( **NotSupportedException**将引发)。</span><span class="sxs-lookup"><span data-stu-id="44e0d-173">Pipelines which call the BAM interceptor API (a **NotSupportedException** will be thrown).</span></span>  
  
- <span data-ttu-id="44e0d-174">不能并行形状的不同分支中执行相同的管道实例，除非放置每个分支中的同步作用域。</span><span class="sxs-lookup"><span data-stu-id="44e0d-174">The same pipeline instance cannot be executed in different branches of the parallel shape unless it is placed in a synchronized scope in every branch.</span></span>  
  
- <span data-ttu-id="44e0d-175">依据生成的现有管道 （程序集） [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK。</span><span class="sxs-lookup"><span data-stu-id="44e0d-175">Existing pipelines (assemblies) that were built against the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK.</span></span>  
  
## <a name="failure-modes-and-effects"></a><span data-ttu-id="44e0d-176">故障模式和效果</span><span class="sxs-lookup"><span data-stu-id="44e0d-176">Failure Modes and Effects</span></span>  
 <span data-ttu-id="44e0d-177">导致生成挂起的消息在管道执行过程中的任何故障时从 BizTalk Server 消息传送基础结构内部调用此管道反而会导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="44e0d-177">Any failure in pipeline execution which would have resulted in a suspended message were this pipeline to be called from within the BizTalk Server Messaging Infrastructure will instead result in an exception being thrown.</span></span>  <span data-ttu-id="44e0d-178">引发的异常的类型是**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**。</span><span class="sxs-lookup"><span data-stu-id="44e0d-178">The exception thrown is of type **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.</span></span>  <span data-ttu-id="44e0d-179">可以在 catch 块中调用业务流程中处理这个引发的异常。</span><span class="sxs-lookup"><span data-stu-id="44e0d-179">This thrown exception can be handled in a catch block within the calling orchestration.</span></span>  <span data-ttu-id="44e0d-180">如果业务流程没有捕获所引发的异常，则 XLANGs 引擎会报告的错误的文本中引发的异常包括异常信息。</span><span class="sxs-lookup"><span data-stu-id="44e0d-180">If the orchestration does not catch the thrown exception, the XLANGs engine reports an error the text of which includes the exception information in the thrown exception.</span></span>  
  
 <span data-ttu-id="44e0d-181">异常执行管道组件生成的错误消息的格式设置。</span><span class="sxs-lookup"><span data-stu-id="44e0d-181">The exception performs formatting of the error messages generated by the pipeline components.</span></span>  
  
 <span data-ttu-id="44e0d-182">**消息**的属性**XLANGPipelineManagerException**类包含管道的执行错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="44e0d-182">The **Message** property of the **XLANGPipelineManagerException** class contains details of the pipeline's execution error.</span></span> <span data-ttu-id="44e0d-183">此详细信息的以下格式：</span><span class="sxs-lookup"><span data-stu-id="44e0d-183">This detail is in the following format:</span></span>  
  
- <span data-ttu-id="44e0d-184">执行管道失败\<管道类型\>。</span><span class="sxs-lookup"><span data-stu-id="44e0d-184">There was a failure executing pipeline \<pipeline type\>.</span></span>  <span data-ttu-id="44e0d-185">错误详细信息\<格式的错误消息\>。</span><span class="sxs-lookup"><span data-stu-id="44e0d-185">Error details \<formatted error message\>.</span></span>  
  
  <span data-ttu-id="44e0d-186">此消息中，\<管道类型\>是管道类的名称和\<格式的错误消息\>是管道执行过程中发生的具体失败的说明。</span><span class="sxs-lookup"><span data-stu-id="44e0d-186">In this message, \<pipeline type\> is the name of the pipeline class and \<formatted error message\> is a description of the specific failure that occurred during pipeline execution.</span></span>  
  
  <span data-ttu-id="44e0d-187">例如，如果业务流程调用接收管道，该管道的执行会失败，因为没有任何管道组件可识别消息的值**XLANGPipelineManagerException**的属性将是：</span><span class="sxs-lookup"><span data-stu-id="44e0d-187">For example, if an orchestration calls a receive pipeline and that pipeline's execution fails because none of the pipeline's components recognizes the message, the values of the **XLANGPipelineManagerException**'s properties would be:</span></span>  
  
|<span data-ttu-id="44e0d-188">XLANGPipelineManagerException 属性</span><span class="sxs-lookup"><span data-stu-id="44e0d-188">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="44e0d-189">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="44e0d-189">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="44e0d-190">消息</span><span class="sxs-lookup"><span data-stu-id="44e0d-190">Message</span></span>|<span data-ttu-id="44e0d-191">执行接收管道"mypipelines.receivepipeline 时失败"时出错。</span><span class="sxs-lookup"><span data-stu-id="44e0d-191">There was a failure executing the receive pipeline "MyPipelines.ReceivePipeline".</span></span> <span data-ttu-id="44e0d-192">错误详细信息："没有拆装阶段组件可识别该数据。</span><span class="sxs-lookup"><span data-stu-id="44e0d-192">Error details: "No Disassemble stage components can recognize the data.</span></span>|  
|<span data-ttu-id="44e0d-193">组件</span><span class="sxs-lookup"><span data-stu-id="44e0d-193">Component</span></span>|<span data-ttu-id="44e0d-194">String.Empty</span><span class="sxs-lookup"><span data-stu-id="44e0d-194">String.Empty</span></span>|  
  
 <span data-ttu-id="44e0d-195">再举一例，如果业务流程调用发送管道，该管道的执行失败，因为验证失败中的文本**消息**属性的**XLANGPipelineManagerException**将为：</span><span class="sxs-lookup"><span data-stu-id="44e0d-195">As another example, if an orchestration calls a send pipeline and that pipeline's execution fails because there is a validation failure, the text in the **Message** property of **XLANGPipelineManagerException** would be:</span></span>  
  
|<span data-ttu-id="44e0d-196">XLANGPipelineManagerException 属性</span><span class="sxs-lookup"><span data-stu-id="44e0d-196">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="44e0d-197">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="44e0d-197">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="44e0d-198">消息</span><span class="sxs-lookup"><span data-stu-id="44e0d-198">Message</span></span>|<span data-ttu-id="44e0d-199">执行发送管道"mypipelines.sendpipeline 时失败"时出错。</span><span class="sxs-lookup"><span data-stu-id="44e0d-199">There was a failure executing the send pipeline "MyPipelines.SendPipeline".</span></span>  <span data-ttu-id="44e0d-200">错误详细信息："无法验证文档："\<元素名称\>元素无效-值\<元素的值\>无效根据其数据类型 String 的模式约束失败。""</span><span class="sxs-lookup"><span data-stu-id="44e0d-200">Error details:  "Failed to validate the document: "The \<element name\> element is invalid - The value \<element value\> is invalid according to its datatype 'String' - The Pattern constraint failed.""</span></span>|  
|<span data-ttu-id="44e0d-201">组件</span><span class="sxs-lookup"><span data-stu-id="44e0d-201">Component</span></span>|<span data-ttu-id="44e0d-202">“Microsoft.BizTalk.Component.XmlValidator”</span><span class="sxs-lookup"><span data-stu-id="44e0d-202">“Microsoft.BizTalk.Component.XmlValidator”</span></span>|