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
# <a name="how-to-use-expressions-to-execute-pipelines"></a>如何使用表达式执行管道
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 具有以同步方式调用从业务流程内的管道的能力。 这使业务流程能够利用封装在管道中的消息处理 （发送或接收） 针对数据而无需将该数据通过消息传送基础结构发送的正文。  
  
 可以使用此功能，以调用若干消息聚合到单个传出交换的发送管道业务流程。 相反，业务流程可以调用接收管道进行解码和拆装之外消息传送基础结构，而不会产生的消息框通过处理成本获得的交换。  
  
## <a name="details"></a>详细信息  
 业务流程使用中的方法**XLANGPipelineManager**类 (在**Microsoft.XLANGs.Pipeline**命名空间) 来调用发送或接收管道。  接收管道使用单条消息或一个交换并生成零个或多个消息，就像管道在接收 BizTalk 消息传送中的消息的上下文中在执行时。 发送管道使用一个或多个消息并生成单条消息或交换，同样，就像管道发送在 BizTalk 消息传送消息的上下文中在执行时。  
  
## <a name="calling-a-receive-pipeline"></a>调用接收管道  
 若要调用接收管道从业务流程，应用程序调用内部**executereceivepipeline （)** 方法**XLANGPipelineManager**类。  此方法使用单个交换并返回零个或多个消息的集合 (包含在的实例中**ReceivePipelineOutputMessages**类)。 有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。  
  
 执行接收管道从业务流程中的 API 是：  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 通常会中完成对接收管道的调用**表达式**形状在业务流程内的。  
  
 若要调用接收管道从业务流程中的，开发人员必须引用业务流程项目中的管道程序集。 下面是调用接收管道的业务流程的示例：  
  
 ![正在调用接收管道屏幕](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")  
  
 有关更详细的示例，请参阅 SDK 示例[组合消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。  
  
> [!NOTE]
>  类型的变量**ReceivePipelineOutputMessages**可以仅在业务流程中的原子作用域内声明。  这是因为此类型的变量不是可序列化，因此还不能在业务流程和业务流程绝对不会保存在原子作用域内执行时。  这意味着，可以仅在原子作用域内执行接收管道。  
  
> [!NOTE]
>  调用时**PassThruReceive**管道或自定义管道组件从业务流程中的，您必须声明传入消息的变量类型，如 System.Xml.XmlDocument 的传入消息类型是否为 XML. 因此，如果你尝试对其进行非 XML 消息，例如平面文件格式的消息传入消息时可能会遇到异常。 这是正因如此，业务流程引擎想要在上面所述的方案中的传入任何的消息类型都会使用 System.Xml.XmlDocument。  
  
## <a name="calling-a-send-pipeline"></a>调用发送管道  
 若要调用发送管道，从业务流程，应用程序调用内部**executesendpipeline （)** 方法**XLANGPipelineManager**类。 此方法使用一个或多个消息的集合 (包含在的实例中**SendPipelineInputMessages**类)，并返回单个交换。 有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。  由于执行发送管道会生成一个新的交换，在调用**executesendpipeline （)** 方法必须在消息赋值形状中，这种情况下发生：  
  
 执行发送管道，从业务流程中的 API 是：  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 对发送管道的调用中必须进行**消息赋值**形状在业务流程内的。  
  
 若要调用从业务流程中的发送管道，开发人员必须引用业务流程项目中的管道程序集。  调用发送管道的业务流程的示例：  
  
 ![正在调用发送管道屏幕](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")  
  
> [!NOTE]
>  在调用默认 XMLTransmit 管道时，必须设置消息上下文属性 XMLNORM。EnvelopeSpecName 为信封架构的完全限定的名称。 例如：  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 有关更详细的示例，请参阅 SDK 示例[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。  
  
## <a name="pipeline-execution---behavioral-differences"></a>管道执行-行为差异  
 执行发送或接收管道时调用的业务流程主要是同一管道内消息传送基础结构在执行时相同 （即在接收位置或发送端口）。  但是，有某些行为差异，如下所示。  
  
### <a name="differences-within-pipeline-stages"></a>管道阶段中的差异  
 执行阶段内发送或接收管道调用从 BizTalk 消息传送基础结构，按阶段所示的异常时，从业务流程中调用的管道是几乎完全相同的那些阶段执行下面。  
  
-   组装器/拆装器：组装器和拆装器阶段不会处理**跟踪配置文件**数据。  
  
-   编码器/解码器：MIME 编码器进行数字签名使用在主机与之关联的主机上配置的证书的消息。  SMIME 编码器对消息传递给管道的消息上下文中使用证书进行加密。  
  
### <a name="schema-resolution"></a>架构解析  
 有两种架构查找算法从业务流程执行管道时受支持：  
  
- 按类型解析  
  
- 按名称解析  
  
  在部署重复架构的情况下，用于选择相应的架构的算法逻辑与消息传送基础结构的上下文中执行时使用完全相同。  
  
### <a name="transactional-pipelines"></a>事务性管道  
 管道的阶段调用了事务性组件没有可用的事务性上下文。  任何对**ipipelinecontext.gettransaction （)** 将引发**NotSupportedException**。  这不会阻止此类管道从业务流程的执行，但确实意味着管道，将需要检测并处理这种情况。  
  
### <a name="message-destination"></a>消息目标  
 在此上下文中不支持由管道组件控制消息目标。  设置上下文属性**MessageDestination**或**SuspendOnRoutingFailure**将导致**XLANGPipelineManagerException**引发。  
  
### <a name="pipeline-component-types"></a>管道组件类型  
 管道组件必须基于任务的以下为了从业务流程内部调用：  
  
-   .NET Framework v1.1  
  
-   .NET Framework v2.0  
  
-   .NET Framework v3.0  
  
-   .NET Framework v3.5  
  
-   .NET Framework v4.0  
  
-   .NET Framework v2.0  
  
-   COM  
  
## <a name="restrictions"></a>限制  
 下列管道类型**不能**从业务流程内部执行：  
  
- 事务性管道  
  
- 可恢复管道  
  
- 管道调用 BAM 侦听器 API ( **NotSupportedException**将引发)。  
  
- 不能并行形状的不同分支中执行相同的管道实例，除非放置每个分支中的同步作用域。  
  
- 依据生成的现有管道 （程序集） [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK。  
  
## <a name="failure-modes-and-effects"></a>故障模式和效果  
 导致生成挂起的消息在管道执行过程中的任何故障时从 BizTalk Server 消息传送基础结构内部调用此管道反而会导致引发异常。  引发的异常的类型是**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**。  可以在 catch 块中调用业务流程中处理这个引发的异常。  如果业务流程没有捕获所引发的异常，则 XLANGs 引擎会报告的错误的文本中引发的异常包括异常信息。  
  
 异常执行管道组件生成的错误消息的格式设置。  
  
 **消息**的属性**XLANGPipelineManagerException**类包含管道的执行错误的详细信息。 此详细信息的以下格式：  
  
- 执行管道失败\<管道类型\>。  错误详细信息\<格式的错误消息\>。  
  
  此消息中，\<管道类型\>是管道类的名称和\<格式的错误消息\>是管道执行过程中发生的具体失败的说明。  
  
  例如，如果业务流程调用接收管道，该管道的执行会失败，因为没有任何管道组件可识别消息的值**XLANGPipelineManagerException**的属性将是：  
  
|XLANGPipelineManagerException 属性|ReplTest1|  
|--------------------------------------------|-----------|  
|消息|执行接收管道"mypipelines.receivepipeline 时失败"时出错。 错误详细信息："没有拆装阶段组件可识别该数据。|  
|组件|String.Empty|  
  
 再举一例，如果业务流程调用发送管道，该管道的执行失败，因为验证失败中的文本**消息**属性的**XLANGPipelineManagerException**将为：  
  
|XLANGPipelineManagerException 属性|ReplTest1|  
|--------------------------------------------|-----------|  
|消息|执行发送管道"mypipelines.sendpipeline 时失败"时出错。  错误详细信息："无法验证文档："\<元素名称\>元素无效-值\<元素的值\>无效根据其数据类型 String 的模式约束失败。""|  
|组件|“Microsoft.BizTalk.Component.XmlValidator”|