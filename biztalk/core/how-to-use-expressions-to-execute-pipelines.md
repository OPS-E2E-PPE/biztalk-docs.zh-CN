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
# <a name="how-to-use-expressions-to-execute-pipelines"></a>如何使用表达式执行管道
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 能够从业务流程中同步调用管道。 这使业务流程能够对数据正文利用封装在管道（发送或接收）内的消息处理，而不必通过消息传递基础结构来发送这些数据。  
  
 通过使用此功能，业务流程可调用发送管道将若干消息聚合到单个传出交换。 反之，业务流程也可以调用接收管道对在消息传递基础结构之外获得的交换进行解码和拆装，而无需进行 MessageBox 处理。  
  
## <a name="details"></a>详细信息  
 业务流程使用中的方法**XLANGPipelineManager**类 (在**Microsoft.XLANGs.Pipeline**命名空间) 来调用发送或接收管道。  接收管道使用单条消息或一个交换并生成零条或多条消息，就像在 BizTalk 消息传送过程中管道在接收消息的上下文中执行时一样。 发送管道使用一条或多条消息并生成单条消息或交换，也是像在 BizTalk 消息传送过程中管道在发送消息的上下文中执行时一样。  
  
## <a name="calling-a-receive-pipeline"></a>调用接收管道  
 若要调用接收管道从业务流程，应用程序调用内部**executereceivepipeline （)** 方法**XLANGPipelineManager**类。  此方法使用单个交换并返回零个或多个消息的集合 (包含在的实例中**ReceivePipelineOutputMessages**类)。 有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。  
  
 从业务流程内部执行接收管道的 API 是：  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 通常会中完成对接收管道的调用**表达式**形状在业务流程内的。  
  
 为了从业务流程内部调用接收管道，开发人员必须在业务流程项目中引用管道程序集。 下面是调用接收管道的业务流程示例：  
  
 ![正在调用接收管道屏幕](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")  
  
 有关更详细的示例，请参阅 SDK 示例[组合消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。  
  
> [!NOTE]
>  类型的变量**ReceivePipelineOutputMessages**可以仅在业务流程中的原子作用域内声明。  这是因为此类型的变量不是可序列化的变量，因此不能在业务流程中持久存在，并且在原子作用域内执行时，业务流程也决不会被持久化。  也就是说，接收管道只能在原子作用域内执行。  
  
> [!NOTE]
>  调用时**PassThruReceive**管道或自定义管道组件从业务流程中的，您必须声明传入消息的变量类型，如 System.Xml.XmlDocument 的传入消息类型是否为 XML. 因此，如果在传入消息为非 XML 消息（例如，为平面文件格式的消息）时尝试对其执行操作，则会遇到异常。 这是因为业务流程引擎在上述情况中为任何传入消息类型都会使用 System.Xml.XmlDocument。  
  
## <a name="calling-a-send-pipeline"></a>调用发送管道  
 若要调用发送管道，从业务流程，应用程序调用内部**executesendpipeline （)** 方法**XLANGPipelineManager**类。 此方法使用一个或多个消息的集合 (包含在的实例中**SendPipelineInputMessages**类)，并返回单个交换。 有关.NET 类库参考中详细介绍了此方法的语法**XLANGPipelineManager**类。  由于执行发送管道会生成一个新的交换，在调用**executesendpipeline （)** 方法必须在消息赋值形状中，这种情况下发生：  
  
 从业务流程内部执行发送管道的 API 是：  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 对发送管道的调用中必须进行**消息赋值**形状在业务流程内的。  
  
 要从业务流程内部调用发送管道，开发人员必须在业务流程项目中引用管道程序集。  下面是调用发送管道的业务流程示例：  
  
 ![正在调用发送管道屏幕](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")  
  
> [!NOTE]
>  当调用默认 XMLTransmit 管道时，必须将消息上下文属性 XMLNORM.EnvelopeSpecName 设置为信封架构的完全限定名。 例如：  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 有关更详细的示例，请参阅 SDK 示例[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。  
  
## <a name="pipeline-execution---behavioral-differences"></a>管道执行 - 行为差异  
 业务流程调用发送或接收管道后这些管道的操作与消息传送基础结构内（即，在接收位置或发送端口处）相同管道的操作大致相同。  但也存在某些行为差异，如下所述。  
  
### <a name="differences-within-pipeline-stages"></a>管道阶段内的差异  
 在业务流程内部调用的发送或接收管道中阶段的执行与这些阶段在从 BizTalk 消息传送基础结构中调用管道时的执行大致相同，但下面列出的阶段除外。  
  
-   组装器/拆装器： 组装器和拆装器阶段不会处理**跟踪配置文件**数据。  
  
-   编码器/解码器： MIME 编码器进行数字签名使用在主机与之关联的主机上配置的证书的消息。  SMIME 编码器使用传递给管道的消息上下文中的证书对消息进行加密。  
  
### <a name="schema-resolution"></a>架构解析  
 当从业务流程中执行管道时，支持两种架构查找算法：  
  
- 按类型解析  
  
- 按名称解析  
  
  在部署重复架构的情况下，用于选择适当架构的算法逻辑与在消息传递基础结构上下文中执行时使用的算法逻辑相同。  
  
### <a name="transactional-pipelines"></a>事务性管道  
 如果管道的阶段调用了事务性组件，则管道将没有可用的事务性上下文。  任何对**ipipelinecontext.gettransaction （)** 将引发**NotSupportedException**。  这不会阻止从业务流程中执行此类管道，但确实意味着管道必须检测并处理这种情况。  
  
### <a name="message-destination"></a>消息目标  
 在此上下文中不支持按照管道组件控制消息目标。  设置上下文属性**MessageDestination**或**SuspendOnRoutingFailure**将导致**XLANGPipelineManagerException**引发。  
  
### <a name="pipeline-component-types"></a>管道组件类型  
 为了从业务流程内部调用某管道组件，该管道组件必须基于以下内容：  
  
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
  
- 在并行形状的不同分支中不能执行相同的管道实例，除非将该实例放置在每个分支的同步作用域中。  
  
- 依据生成的现有管道 （程序集） [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK。  
  
## <a name="failure-modes-and-effects"></a>失败模式和影响  
 如果管道执行过程中出现任何失败，并导致生成挂起消息指出此管道将从 BizTalk Server 消息传递基础结构内部调用，则反而会导致引发异常。  引发的异常的类型是**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**。  可以在调用业务流程内的 catch 块中处理这个引发的异常。  如果业务流程没有捕获引发的异常，则 XLANGs 引擎会报告错误，错误文本包括了所引发异常的异常信息。  
  
 该异常对管道组件生成的错误消息执行格式化。  
  
 **消息**的属性**XLANGPipelineManagerException**类包含管道的执行错误的详细信息。 该详细信息的格式如下：  
  
- 执行管道失败\<管道类型\>。  错误详细信息\<格式的错误消息\>。  
  
  此消息中，\<管道类型\>是管道类的名称和\<格式的错误消息\>是管道执行过程中发生的具体失败的说明。  
  
  例如，如果业务流程调用接收管道，该管道的执行会失败，因为没有任何管道组件可识别消息的值**XLANGPipelineManagerException**的属性将是：  
  
|XLANGPipelineManagerException 属性|ReplTest1|  
|--------------------------------------------|-----------|  
|消息|执行接收管道“MyPipelines.ReceivePipeline”时失败。 错误详细信息:"没有拆装阶段组件可识别该数据。|  
|组件|String.Empty|  
  
 再举一例，如果业务流程调用发送管道，该管道的执行失败，因为验证失败中的文本**消息**属性的**XLANGPipelineManagerException**将为：  
  
|XLANGPipelineManagerException 属性|ReplTest1|  
|--------------------------------------------|-----------|  
|消息|执行发送管道“MyPipelines.SendPipeline”时失败。  错误详细信息:"无法验证文档:"\<元素名称\>元素无效-值\<元素的值\>无效根据其数据类型 String 的模式约束失败。""|  
|组件|“Microsoft.BizTalk.Component.XmlValidator”|