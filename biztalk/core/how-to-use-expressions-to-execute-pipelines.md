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
ms.openlocfilehash: e8c0b0e79f79c351d84ed22b12a5eba8bdc9f3a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005166"
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a><span data-ttu-id="af91e-102">如何使用表达式执行管道</span><span class="sxs-lookup"><span data-stu-id="af91e-102">How to Use Expressions to Execute Pipelines</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="af91e-103"> 能够从业务流程中同步调用管道。</span><span class="sxs-lookup"><span data-stu-id="af91e-103"> has the ability to synchronously call a pipeline from within an Orchestration.</span></span> <span data-ttu-id="af91e-104">这使业务流程能够对数据正文利用封装在管道（发送或接收）内的消息处理，而不必通过消息传递基础结构来发送这些数据。</span><span class="sxs-lookup"><span data-stu-id="af91e-104">This enables orchestrations to leverage the message processing encapsulated within a pipeline (either send or receive) against a body of data without having to send that data through the messaging infrastructure.</span></span>  
  
 <span data-ttu-id="af91e-105">通过使用此功能，业务流程可调用发送管道将若干消息聚合到单个传出交换。</span><span class="sxs-lookup"><span data-stu-id="af91e-105">You can use this feature to enable an orchestration to call a send pipeline in order to aggregate several messages into a single outgoing interchange.</span></span> <span data-ttu-id="af91e-106">反之，业务流程也可以调用接收管道对在消息传递基础结构之外获得的交换进行解码和拆装，而无需进行 MessageBox 处理。</span><span class="sxs-lookup"><span data-stu-id="af91e-106">Conversely, an orchestration could call a receive pipeline to decode and disassemble an interchange obtained outside of the messaging infrastructure, without incurring the processing costs of going through the message box.</span></span>  
  
## <a name="details"></a><span data-ttu-id="af91e-107">详细信息</span><span class="sxs-lookup"><span data-stu-id="af91e-107">Details</span></span>  
 <span data-ttu-id="af91e-108">业务流程使用中的方法**XLANGPipelineManager**类 (在**Microsoft.XLANGs.Pipeline**命名空间) 来调用发送或接收管道。</span><span class="sxs-lookup"><span data-stu-id="af91e-108">Orchestrations use methods in the **XLANGPipelineManager** class (in the **Microsoft.XLANGs.Pipeline** namespace) to call send or receive pipelines.</span></span>  <span data-ttu-id="af91e-109">接收管道使用单条消息或一个交换并生成零条或多条消息，就像在 BizTalk 消息传送过程中管道在接收消息的上下文中执行时一样。</span><span class="sxs-lookup"><span data-stu-id="af91e-109">A Receive pipeline consumes either a single message or an interchange and yields zero or more messages, just as when the pipeline executes in the context of receiving a message within BizTalk messaging.</span></span> <span data-ttu-id="af91e-110">发送管道使用一条或多条消息并生成单条消息或交换，也是像在 BizTalk 消息传送过程中管道在发送消息的上下文中执行时一样。</span><span class="sxs-lookup"><span data-stu-id="af91e-110">A Send pipeline consumes one or more messages and yields a single message or interchange, again, just as when the pipeline executes in the context of sending a message within BizTalk messaging.</span></span>  
  
## <a name="calling-a-receive-pipeline"></a><span data-ttu-id="af91e-111">调用接收管道</span><span class="sxs-lookup"><span data-stu-id="af91e-111">Calling a Receive Pipeline</span></span>  
 <span data-ttu-id="af91e-112">若要调用接收管道从业务流程，应用程序调用内部**executereceivepipeline （)** 方法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="af91e-112">In order to call a receive pipeline from within an orchestration, the application calls the **ExecuteReceivePipeline()** method of the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="af91e-113">此方法使用单个交换并返回零个或多个消息的集合 (包含在的实例中**ReceivePipelineOutputMessages**类)。</span><span class="sxs-lookup"><span data-stu-id="af91e-113">This method consumes a single interchange and returns a collection of zero or more messages (contained in an instance of the **ReceivePipelineOutputMessages** class).</span></span> <span data-ttu-id="af91e-114">有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="af91e-114">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  
  
 <span data-ttu-id="af91e-115">从业务流程内部执行接收管道的 API 是：</span><span class="sxs-lookup"><span data-stu-id="af91e-115">The API for executing a receive pipeline from within an orchestration is:</span></span>  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 <span data-ttu-id="af91e-116">通常会中完成对接收管道的调用**表达式**形状在业务流程内的。</span><span class="sxs-lookup"><span data-stu-id="af91e-116">A call to a receive pipeline would typically be done in an **Expression** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="af91e-117">为了从业务流程内部调用接收管道，开发人员必须在业务流程项目中引用管道程序集。</span><span class="sxs-lookup"><span data-stu-id="af91e-117">In order to call a receive pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span> <span data-ttu-id="af91e-118">下面是调用接收管道的业务流程示例：</span><span class="sxs-lookup"><span data-stu-id="af91e-118">Following is an example of an orchestration that calls a receive pipeline:</span></span>  
  
 <span data-ttu-id="af91e-119">![正在调用接收管道屏幕](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="af91e-119">![Calling Receive Pipeline screen](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")</span></span>  
  
 <span data-ttu-id="af91e-120">有关更详细的示例，请参阅 SDK 示例[组合消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="af91e-120">For a more detailed example, see the SDK sample [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af91e-121">类型的变量**ReceivePipelineOutputMessages**可以仅在业务流程中的原子作用域内声明。</span><span class="sxs-lookup"><span data-stu-id="af91e-121">A variable of type **ReceivePipelineOutputMessages** can be declared only within an atomic scope in an orchestration.</span></span>  <span data-ttu-id="af91e-122">这是因为此类型的变量不是可序列化的变量，因此不能在业务流程中持久存在，并且在原子作用域内执行时，业务流程也决不会被持久化。</span><span class="sxs-lookup"><span data-stu-id="af91e-122">This is because variables of this type are not serializable and thus would not survive persistence of the orchestration, and orchestrations are never persisted while executing within an atomic scope.</span></span>  <span data-ttu-id="af91e-123">也就是说，接收管道只能在原子作用域内执行。</span><span class="sxs-lookup"><span data-stu-id="af91e-123">This means that a receive pipeline can be executed only within an atomic scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af91e-124">调用时**PassThruReceive**管道或自定义管道组件从业务流程中的，您必须声明传入消息的变量类型，如 System.Xml.XmlDocument 的传入消息类型是否为 XML.</span><span class="sxs-lookup"><span data-stu-id="af91e-124">When calling **PassThruReceive** pipeline or custom pipeline component from within an orchestration, you must declare the variable type for incoming message as System.Xml.XmlDocument despite of the incoming message type is XML or not.</span></span> <span data-ttu-id="af91e-125">因此，如果在传入消息为非 XML 消息（例如，为平面文件格式的消息）时尝试对其执行操作，则会遇到异常。</span><span class="sxs-lookup"><span data-stu-id="af91e-125">Therefore, you may encounter exception if you try to operate on it if the incoming message is a non-XML message such as a flat file format message.</span></span> <span data-ttu-id="af91e-126">这是因为业务流程引擎在上述情况中为任何传入消息类型都会使用 System.Xml.XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="af91e-126">This is because of that orchestration engine intends to use System.Xml.XmlDocument for any type of incoming message in the scenario described above.</span></span>  
  
## <a name="calling-a-send-pipeline"></a><span data-ttu-id="af91e-127">调用发送管道</span><span class="sxs-lookup"><span data-stu-id="af91e-127">Calling a Send Pipeline</span></span>  
 <span data-ttu-id="af91e-128">若要调用发送管道，从业务流程，应用程序调用内部**executesendpipeline （)** 方法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="af91e-128">To call a send pipeline from within an orchestration, the application calls the **ExecuteSendPipeline()** method of the **XLANGPipelineManager** class.</span></span> <span data-ttu-id="af91e-129">此方法使用一个或多个消息的集合 (包含在的实例中**SendPipelineInputMessages**类)，并返回单个交换。</span><span class="sxs-lookup"><span data-stu-id="af91e-129">This method consumes a collection of one or more messages (contained in an instance of the **SendPipelineInputMessages** class) and returns a single interchange.</span></span> <span data-ttu-id="af91e-130">有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。</span><span class="sxs-lookup"><span data-stu-id="af91e-130">The syntax of this method is detailed in the .NET class library reference for the **XLANGPipelineManager** class.</span></span>  <span data-ttu-id="af91e-131">由于执行发送管道会生成一个新的交换，在调用**executesendpipeline （)** 方法必须在消息赋值形状中，这种情况下发生：</span><span class="sxs-lookup"><span data-stu-id="af91e-131">Because execution of a send pipeline yields a new interchange, the call to **ExecuteSendPipeline()** method must be made within a message assignment shape, as such:</span></span>  
  
 <span data-ttu-id="af91e-132">从业务流程内部执行发送管道的 API 是：</span><span class="sxs-lookup"><span data-stu-id="af91e-132">The API for executing a send pipeline from within an orchestration is:</span></span>  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 <span data-ttu-id="af91e-133">对发送管道的调用中必须进行**消息赋值**形状在业务流程内的。</span><span class="sxs-lookup"><span data-stu-id="af91e-133">A call to a send pipeline must be done in a **Message Assignment** shape within the orchestration.</span></span>  
  
 <span data-ttu-id="af91e-134">要从业务流程内部调用发送管道，开发人员必须在业务流程项目中引用管道程序集。</span><span class="sxs-lookup"><span data-stu-id="af91e-134">In order to call a send pipeline from within an orchestration, the developer must reference the pipeline assembly in the orchestration project.</span></span>  <span data-ttu-id="af91e-135">下面是调用发送管道的业务流程示例：</span><span class="sxs-lookup"><span data-stu-id="af91e-135">An example of an orchestration that calls a send pipeline:</span></span>  
  
 <span data-ttu-id="af91e-136">![正在调用发送管道屏幕](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span><span class="sxs-lookup"><span data-stu-id="af91e-136">![Calling Send Pipeline screen](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af91e-137">当调用默认 XMLTransmit 管道时，必须将消息上下文属性 XMLNORM.EnvelopeSpecName 设置为信封架构的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="af91e-137">When calling the default XMLTransmit pipeline, you must set the message context property XMLNORM.EnvelopeSpecName to the fully qualified name of the Envelope schema.</span></span> <span data-ttu-id="af91e-138">例如：</span><span class="sxs-lookup"><span data-stu-id="af91e-138">For example:</span></span>  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 <span data-ttu-id="af91e-139">有关更详细的示例，请参阅 SDK 示例[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="af91e-139">For a more detailed example, see the SDK sample [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="pipeline-execution---behavioral-differences"></a><span data-ttu-id="af91e-140">管道执行 - 行为差异</span><span class="sxs-lookup"><span data-stu-id="af91e-140">Pipeline Execution - Behavioral Differences</span></span>  
 <span data-ttu-id="af91e-141">业务流程调用发送或接收管道后这些管道的操作与消息传送基础结构内（即，在接收位置或发送端口处）相同管道的操作大致相同。</span><span class="sxs-lookup"><span data-stu-id="af91e-141">The execution of a send or receive pipeline when called by an orchestration is predominantly the same as when the same pipeline executes within the messaging infrastructure (i.e. at receive location or send port).</span></span>  <span data-ttu-id="af91e-142">但也存在某些行为差异，如下所述。</span><span class="sxs-lookup"><span data-stu-id="af91e-142">However, there are certain behavioral differences that are noted below.</span></span>  
  
### <a name="differences-within-pipeline-stages"></a><span data-ttu-id="af91e-143">管道阶段内的差异</span><span class="sxs-lookup"><span data-stu-id="af91e-143">Differences Within Pipeline Stages</span></span>  
 <span data-ttu-id="af91e-144">在业务流程内部调用的发送或接收管道中阶段的执行与这些阶段在从 BizTalk 消息传送基础结构中调用管道时的执行大致相同，但下面列出的阶段除外。</span><span class="sxs-lookup"><span data-stu-id="af91e-144">The execution of the stages within a send or receive pipeline that is called from within an orchestration is nearly identical to the execution of those stages when the pipeline is called from the BizTalk messaging infrastructure, with the exceptions noted by stage below.</span></span>  
  
-   <span data-ttu-id="af91e-145">组装器/拆装器： 组装器和拆装器阶段不会处理**跟踪配置文件**数据。</span><span class="sxs-lookup"><span data-stu-id="af91e-145">Assembler/Disassembler:  The assembler and disassembler stages will not process **Tracking Profile** data.</span></span>  
  
-   <span data-ttu-id="af91e-146">编码器/解码器： MIME 编码器进行数字签名使用在主机与之关联的主机上配置的证书的消息。</span><span class="sxs-lookup"><span data-stu-id="af91e-146">Encoder/Decoder:  The MIME encoder digitally signs messages using the certificate configured at the host with which the host is associated.</span></span>  <span data-ttu-id="af91e-147">SMIME 编码器使用传递给管道的消息上下文中的证书对消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="af91e-147">The SMIME encoder encrypts messages using the certificate on the context of the message passed into the pipeline.</span></span>  
  
### <a name="schema-resolution"></a><span data-ttu-id="af91e-148">架构解析</span><span class="sxs-lookup"><span data-stu-id="af91e-148">Schema Resolution</span></span>  
 <span data-ttu-id="af91e-149">当从业务流程中执行管道时，支持两种架构查找算法：</span><span class="sxs-lookup"><span data-stu-id="af91e-149">There are two schema lookup algorithms that are supported when executing a pipeline from an orchestration:</span></span>  
  
- <span data-ttu-id="af91e-150">按类型解析</span><span class="sxs-lookup"><span data-stu-id="af91e-150">Resolution by type</span></span>  
  
- <span data-ttu-id="af91e-151">按名称解析</span><span class="sxs-lookup"><span data-stu-id="af91e-151">Resolution by name</span></span>  
  
  <span data-ttu-id="af91e-152">在部署重复架构的情况下，用于选择适当架构的算法逻辑与在消息传递基础结构上下文中执行时使用的算法逻辑相同。</span><span class="sxs-lookup"><span data-stu-id="af91e-152">In cases where duplicate schemas are deployed, the algorithm's logic for selecting the appropriate schema is identical to that used when executing in the context of the messaging infrastructure.</span></span>  
  
### <a name="transactional-pipelines"></a><span data-ttu-id="af91e-153">事务性管道</span><span class="sxs-lookup"><span data-stu-id="af91e-153">Transactional Pipelines</span></span>  
 <span data-ttu-id="af91e-154">如果管道的阶段调用了事务性组件，则管道将没有可用的事务性上下文。</span><span class="sxs-lookup"><span data-stu-id="af91e-154">Pipelines whose stages call transactional components will not have a transactional context available.</span></span>  <span data-ttu-id="af91e-155">任何对**ipipelinecontext.gettransaction （)** 将引发**NotSupportedException**。</span><span class="sxs-lookup"><span data-stu-id="af91e-155">Any call to **IPipelineContext.GetTransaction()** will throw **NotSupportedException**.</span></span>  <span data-ttu-id="af91e-156">这不会阻止从业务流程中执行此类管道，但确实意味着管道必须检测并处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="af91e-156">This does not preclude execution of such a pipeline from an orchestration, but it does mean that the pipeline will have to detect and handle this situation.</span></span>  
  
### <a name="message-destination"></a><span data-ttu-id="af91e-157">消息目标</span><span class="sxs-lookup"><span data-stu-id="af91e-157">Message Destination</span></span>  
 <span data-ttu-id="af91e-158">在此上下文中不支持按照管道组件控制消息目标。</span><span class="sxs-lookup"><span data-stu-id="af91e-158">Controlling message destination by pipeline components is not supported in this context.</span></span>  <span data-ttu-id="af91e-159">设置上下文属性**MessageDestination**或**SuspendOnRoutingFailure**将导致**XLANGPipelineManagerException**引发。</span><span class="sxs-lookup"><span data-stu-id="af91e-159">Setting the context properties **MessageDestination** or **SuspendOnRoutingFailure** will cause an **XLANGPipelineManagerException** to be thrown.</span></span>  
  
### <a name="pipeline-component-types"></a><span data-ttu-id="af91e-160">管道组件类型</span><span class="sxs-lookup"><span data-stu-id="af91e-160">Pipeline Component Types</span></span>  
 <span data-ttu-id="af91e-161">为了从业务流程内部调用某管道组件，该管道组件必须基于以下内容：</span><span class="sxs-lookup"><span data-stu-id="af91e-161">Pipeline components must be based on the following in order to be called from within an orchestration:</span></span>  
  
-   <span data-ttu-id="af91e-162">.NET Framework v1.1</span><span class="sxs-lookup"><span data-stu-id="af91e-162">.NET Framework v1.1</span></span>  
  
-   <span data-ttu-id="af91e-163">.NET Framework v2.0</span><span class="sxs-lookup"><span data-stu-id="af91e-163">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="af91e-164">.NET Framework v3.0</span><span class="sxs-lookup"><span data-stu-id="af91e-164">.NET Framework v3.0</span></span>  
  
-   <span data-ttu-id="af91e-165">.NET Framework v3.5</span><span class="sxs-lookup"><span data-stu-id="af91e-165">.NET Framework v3.5</span></span>  
  
-   <span data-ttu-id="af91e-166">.NET Framework v4.0</span><span class="sxs-lookup"><span data-stu-id="af91e-166">.NET Framework v4.0</span></span>  
  
-   <span data-ttu-id="af91e-167">.NET Framework v2.0</span><span class="sxs-lookup"><span data-stu-id="af91e-167">.NET Framework v2.0</span></span>  
  
-   <span data-ttu-id="af91e-168">COM</span><span class="sxs-lookup"><span data-stu-id="af91e-168">COM</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="af91e-169">限制</span><span class="sxs-lookup"><span data-stu-id="af91e-169">Restrictions</span></span>  
 <span data-ttu-id="af91e-170">下列管道类型**不能**从业务流程内部执行：</span><span class="sxs-lookup"><span data-stu-id="af91e-170">The following types of pipelines **cannot** be executed from within an orchestration:</span></span>  
  
- <span data-ttu-id="af91e-171">事务性管道</span><span class="sxs-lookup"><span data-stu-id="af91e-171">Transactional pipelines</span></span>  
  
- <span data-ttu-id="af91e-172">可恢复管道</span><span class="sxs-lookup"><span data-stu-id="af91e-172">Recoverable pipelines</span></span>  
  
- <span data-ttu-id="af91e-173">管道调用 BAM 侦听器 API ( **NotSupportedException**将引发)。</span><span class="sxs-lookup"><span data-stu-id="af91e-173">Pipelines which call the BAM interceptor API (a **NotSupportedException** will be thrown).</span></span>  
  
- <span data-ttu-id="af91e-174">在并行形状的不同分支中不能执行相同的管道实例，除非将该实例放置在每个分支的同步作用域中。</span><span class="sxs-lookup"><span data-stu-id="af91e-174">The same pipeline instance cannot be executed in different branches of the parallel shape unless it is placed in a synchronized scope in every branch.</span></span>  
  
- <span data-ttu-id="af91e-175">依据生成的现有管道 （程序集） [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK。</span><span class="sxs-lookup"><span data-stu-id="af91e-175">Existing pipelines (assemblies) that were built against the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK.</span></span>  
  
## <a name="failure-modes-and-effects"></a><span data-ttu-id="af91e-176">失败模式和影响</span><span class="sxs-lookup"><span data-stu-id="af91e-176">Failure Modes and Effects</span></span>  
 <span data-ttu-id="af91e-177">如果管道执行过程中出现任何失败，并导致生成挂起消息指出此管道将从 BizTalk Server 消息传递基础结构内部调用，则反而会导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="af91e-177">Any failure in pipeline execution which would have resulted in a suspended message were this pipeline to be called from within the BizTalk Server Messaging Infrastructure will instead result in an exception being thrown.</span></span>  <span data-ttu-id="af91e-178">引发的异常的类型是**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**。</span><span class="sxs-lookup"><span data-stu-id="af91e-178">The exception thrown is of type **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.</span></span>  <span data-ttu-id="af91e-179">可以在调用业务流程内的 catch 块中处理这个引发的异常。</span><span class="sxs-lookup"><span data-stu-id="af91e-179">This thrown exception can be handled in a catch block within the calling orchestration.</span></span>  <span data-ttu-id="af91e-180">如果业务流程没有捕获引发的异常，则 XLANGs 引擎会报告错误，错误文本包括了所引发异常的异常信息。</span><span class="sxs-lookup"><span data-stu-id="af91e-180">If the orchestration does not catch the thrown exception, the XLANGs engine reports an error the text of which includes the exception information in the thrown exception.</span></span>  
  
 <span data-ttu-id="af91e-181">该异常对管道组件生成的错误消息执行格式化。</span><span class="sxs-lookup"><span data-stu-id="af91e-181">The exception performs formatting of the error messages generated by the pipeline components.</span></span>  
  
 <span data-ttu-id="af91e-182">**消息**的属性**XLANGPipelineManagerException**类包含管道的执行错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af91e-182">The **Message** property of the **XLANGPipelineManagerException** class contains details of the pipeline's execution error.</span></span> <span data-ttu-id="af91e-183">该详细信息的格式如下：</span><span class="sxs-lookup"><span data-stu-id="af91e-183">This detail is in the following format:</span></span>  
  
- <span data-ttu-id="af91e-184">执行管道失败\<管道类型\>。</span><span class="sxs-lookup"><span data-stu-id="af91e-184">There was a failure executing pipeline \<pipeline type\>.</span></span>  <span data-ttu-id="af91e-185">错误详细信息\<格式的错误消息\>。</span><span class="sxs-lookup"><span data-stu-id="af91e-185">Error details \<formatted error message\>.</span></span>  
  
  <span data-ttu-id="af91e-186">此消息中，\<管道类型\>是管道类的名称和\<格式的错误消息\>是管道执行过程中发生的具体失败的说明。</span><span class="sxs-lookup"><span data-stu-id="af91e-186">In this message, \<pipeline type\> is the name of the pipeline class and \<formatted error message\> is a description of the specific failure that occurred during pipeline execution.</span></span>  
  
  <span data-ttu-id="af91e-187">例如，如果业务流程调用接收管道，该管道的执行会失败，因为没有任何管道组件可识别消息的值**XLANGPipelineManagerException**的属性将是：</span><span class="sxs-lookup"><span data-stu-id="af91e-187">For example, if an orchestration calls a receive pipeline and that pipeline's execution fails because none of the pipeline's components recognizes the message, the values of the **XLANGPipelineManagerException**'s properties would be:</span></span>  
  
|<span data-ttu-id="af91e-188">XLANGPipelineManagerException 属性</span><span class="sxs-lookup"><span data-stu-id="af91e-188">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="af91e-189">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="af91e-189">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="af91e-190">消息</span><span class="sxs-lookup"><span data-stu-id="af91e-190">Message</span></span>|<span data-ttu-id="af91e-191">执行接收管道“MyPipelines.ReceivePipeline”时失败。</span><span class="sxs-lookup"><span data-stu-id="af91e-191">There was a failure executing the receive pipeline "MyPipelines.ReceivePipeline".</span></span> <span data-ttu-id="af91e-192">错误详细信息:"没有拆装阶段组件可识别该数据。</span><span class="sxs-lookup"><span data-stu-id="af91e-192">Error details: "No Disassemble stage components can recognize the data.</span></span>|  
|<span data-ttu-id="af91e-193">组件</span><span class="sxs-lookup"><span data-stu-id="af91e-193">Component</span></span>|<span data-ttu-id="af91e-194">String.Empty</span><span class="sxs-lookup"><span data-stu-id="af91e-194">String.Empty</span></span>|  
  
 <span data-ttu-id="af91e-195">再举一例，如果业务流程调用发送管道，该管道的执行失败，因为验证失败中的文本**消息**属性的**XLANGPipelineManagerException**将为：</span><span class="sxs-lookup"><span data-stu-id="af91e-195">As another example, if an orchestration calls a send pipeline and that pipeline's execution fails because there is a validation failure, the text in the **Message** property of **XLANGPipelineManagerException** would be:</span></span>  
  
|<span data-ttu-id="af91e-196">XLANGPipelineManagerException 属性</span><span class="sxs-lookup"><span data-stu-id="af91e-196">XLANGPipelineManagerException property</span></span>|<span data-ttu-id="af91e-197">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="af91e-197">Value</span></span>|  
|--------------------------------------------|-----------|  
|<span data-ttu-id="af91e-198">消息</span><span class="sxs-lookup"><span data-stu-id="af91e-198">Message</span></span>|<span data-ttu-id="af91e-199">执行发送管道“MyPipelines.SendPipeline”时失败。</span><span class="sxs-lookup"><span data-stu-id="af91e-199">There was a failure executing the send pipeline "MyPipelines.SendPipeline".</span></span>  <span data-ttu-id="af91e-200">错误详细信息:"无法验证文档:"\<元素名称\>元素无效-值\<元素的值\>无效根据其数据类型 String 的模式约束失败。""</span><span class="sxs-lookup"><span data-stu-id="af91e-200">Error details:  "Failed to validate the document: "The \<element name\> element is invalid - The value \<element value\> is invalid according to its datatype 'String' - The Pattern constraint failed.""</span></span>|  
|<span data-ttu-id="af91e-201">组件</span><span class="sxs-lookup"><span data-stu-id="af91e-201">Component</span></span>|<span data-ttu-id="af91e-202">“Microsoft.BizTalk.Component.XmlValidator”</span><span class="sxs-lookup"><span data-stu-id="af91e-202">“Microsoft.BizTalk.Component.XmlValidator”</span></span>|