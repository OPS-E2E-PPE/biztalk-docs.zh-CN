---
title: "撰写消息处理器 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3097ef6a0da695c3b07cf68182a374eabed11b5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="composed-message-processor-biztalk-server-sample"></a>组合消息处理器（BizTalk Server 示例）
此示例的目的是构建的撰写的邮件处理器应用程序处理聚合的消息的消息的各个行项。  
  
 具体而言我们将生成一个业务流程计划其中包括：  
  
1.  接收包含多个采购订单的批处理的交换消息。  
  
2.  将交换消息分解为单独的采购订单文档。  
  
3.  处理每个文档 – 将每个采购订单转换成一条发票消息。  
  
4.  组合成批处理的交换的所有发票消息。  
  
 步骤 3 得到了简化，示例目的。 例如，在更加复杂的应用程序中，业务流程可能会将拆装的采购订单发送给不同的后端库存系统，并在收集到所有响应之后，将这些采购订单聚合为一个批发票消息。  
  
 有关撰写的邮件处理器模式的详细信息请参阅 [1]。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 有以下几节中详细介绍这两种示例解决方案中的两个项目。  
  
### <a name="pipelines-and-schemas"></a>管道和架构  
 管道和架构的项目包含：  
  
-   为输入的采购订单的交换和输出发票交换的平面文件架构。  
  
-   若要将采购订单文档转换为发票文档的映射。  
  
-   接收和发送管道。  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a>输入和输出的交换的平面文件架构  
 我们的示例应用程序将使用在平面文件格式交换。 以下是购买顺序交换和发票交换的示例：  
  
 购买顺序交换 (CMPInput.txt):  
  
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
  
 该交换或采购订单文档，具有标识哪种类型的文档包含的标头：  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 此交换由三个采购订单单据组成。 一个实例包含如下所示的信息。 如你所见，它包含针对计费和传送的已排序的项的列表以及地址等信息。  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 我们想要为此生成发票交换应如下所示：  
  
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
  
 此交换包含购买顺序交换以及该交换的格式以及标头的格式不同是中的信息的子集。  
  
 标头是，如下所示：  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 文档实例包括以下方案：  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 第一波我们需要创建平面文件架构：  
  
-   采购订单文档 (PO.xsd)  
  
-   发票文档 (Invoice.xsd)  
  
-   采购订单表头 (POHeader.xsd)  
  
-   发票标头 (InvoiceHeader.xsd)  
  
 此示例中，我们将不会以解释创建平面文件架构的过程。 若要了解如何从文档实例创建平面文件架构，请参阅“从文档实例创建平面文件架构”文档部分。  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a>映射用于将采购订单文档转换为发票文档  
 映射 (PO2Invoice.btm) 将采购订单的实例转换成发票文档。  
  
#### <a name="receive-and-send-pipelines"></a>接收和发送管道  
 接收管道 (FFReceivePipeline.btp) 包含用于处理采购订单交换的平面文件反汇编程序组件。 具体而言，为文件 CMPInput.txt 中的交换，它中移除交换标头，并生成与三个采购订单对应的三个 XML 文档。  
  
 平面文件拆装器接收管道中的进行配置所示：  
  
-   **文档架构：** PipelinesAndSchemas.PO  
  
-   **标头架构：** PipelinesAndSchemas.POHeader  
  
-   **保留标头：** False  
  
-   **可恢复的交换：** False  
  
-   **尾部架构：** （无）  
  
-   **验证文档结构：** False  
  
 发送管道 (FFSendPipeline.btp) 包含用于创建聚合的发票交换的平面文件汇编组件。  
  
 发送管道中的平面文件汇编配置所示：  
  
-   **文档架构：** PipelinesandSchemas.Invoice  
  
-   **标头架构：** PipelinesAndSchemas.InvoiceHeader  
  
-   **保留字节顺序标记：** False  
  
-   **面向 charset:** （无）  
  
-   **尾部架构：** （无）  
  
### <a name="orchestration-schedule"></a>业务流程计划  
 业务流程计划 (CMP.odx) 会所有主处理这种情况。 执行专门的以下操作：  
  
-   接收管道执行反汇编采购订单交换  
  
-   接收管道的每个输出消息转换  
  
-   发送管道执行来组合的发票交换  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a>创建业务流程计划，并定义全局变量  
 我们业务流程会收到作为输入平面文件交换，并且将作为输出发送平面文件交换。 正因如此，我们需要定义为类型 （称为 InputInterchange OutputInterchange 分别） 的输入和输出消息不可知的 （即具有 System.Xml.XmlDocument 类型）。  
  
 另外，我们需要定义用于处理消息的原子作用域。 这一步是必需的，因为接收管道可以在原子作用域内执行。  
  
#### <a name="executing-receive-pipeline"></a>执行接收管道  
 下一步，我们将添加用于对业务流程中接收到的消息执行接收管道的逻辑。 为此，首先我们将在作用域内声明一个 Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages 类型的变量（称为 RcvPipeOutput）。 此变量为允许我们循环访问接收管道输出消息的枚举数。 请注意，为了能够访问此类型和用于从业务流程执行管道的所有其他类型，需要添加对以下程序集的引用：  
  
-   Microsoft.XLANGs.Pipeline.dll  
  
-   Microsoft.BizTalk.Pipeline.dll  
  
 无法确保接收管道每次均会成功执行。 有时消息的格式可能不正确，这会使管道处理失败。 在业务流程中管道执行失败时会引发可被捕获的异常，并可以执行错误处理逻辑。 为了捕获管道引发的异常，我们需要在具有异常处理功能的非原子作用域内执行管道。 执行管道的实际代码将从该作用域内的表达式形状调用。  
  
 在 ExecuteRcvPipe 表达式形状中，编写用于执行接收管道的以下代码行：  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 让我们详细分析一下此代码行。 如上所示，我们调用了一个将要执行的接收管道类型和输入消息用作参数的静态方法 ExecuteReceivePipeline。 因此，该方法生成了一个具有输出消息组的枚举数对象。 该结果将赋给之前在此作用域中定义的 ReceivePipelineOutputMessages 类型的变量。  
  
 同时，我们已为管道执行作用域增加了一个异常处理块。 此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义错误消息的业务流程实例。  
  
 在更加复杂的情况下，此时可能会执行其他错误处理，如生成错误通知消息并通过电子邮件将其发送给业务用户或管理员。  
  
#### <a name="transforming-pipeline-output-messages"></a>转换管道输出消息  
 在已执行管道并生成拆装消息组之后，需要将每个输出消息转换为其他格式。  
  
 为在业务流程中使用转换，我们需要定义两种消息，即转换输入消息和转换输出消息。 我们将在原子作用域内定义这些消息。 名为 TmpMessageIn 的转换输入消息属于 PipelinesAndSchemas.PO 类型。 名为 TmpMessageOut 的转换输出消息属于 PipeliensAndSchemas.Invoice 类型。 我们将应用在 PipelinesAndSchemas 项目中定义的 PO2Invoice.btm 映射。  
  
 由于要映射每个管道输出消息，因此需要在循环中执行转换。 我们将使用具有如下所示退出条件的循环形状：  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 MoveNext() 方法是一种允许在管道输出消息集合内移动的标准 IEnumerator .NET 接口方法。 当它到达集合的末尾时会返回 False。  
  
 第一个构造形状用于从管道输出消息构造业务流程消息 TmpMessageIn。  
  
 构造形状中的代码：  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 在此代码中，我们首先将业务流程消息初始化为空，然后将其设置为管道输出消息集合中的当前消息。  
  
 在第二个构造形状中将执行 TmpMessageIn 的实际转换并构造类型为 PipelinesAndSchemas.Invoice 的 TmpMessageOut。  
  
#### <a name="executing-send-pipeline"></a>执行发送管道  
 业务流程中的最后一个处理步骤是执行平面文件发送管道以将所有转换的 xml 消息组装为一个平面文件交换。  
  
 为了执行发送管道我们需要使用 Microsoft.XLANGs.Pipeline.SendPipelineInputMessages 类型的变量 SendPipeInput，该变量用于存放需要在发送管道中进行处理的业务流程消息集合。  
  
 在前一个用于执行转换的循环表达式中我们将编写一行代码，为发送管道将每个转换的消息添加到消息集合中。  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 与执行接收管道的过程相似，用于执行发送管道的代码放在具有异常处理块的非原子作用域内。 发送管道执行代码位于构造模块的消息赋值形状中。  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 构造模块用于构造与类型无关（即 System.Xml.XmlDocument）的管道输出消息 OutputInterchange。 然后在消息赋值形状中将新构造的消息初始化为空。 接下来会调用静态方法 ExecuteSendPipeline 以执行发送管道。 此方法采用以下项作为参数：要执行的发送管道的类型；输入消息；对用于存储管道输出的输出消息的引用。  
  
 与执行接收管道时相同，在此我们也在管道执行作用域中包含了一个异常处理块。 此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义错误消息的业务流程实例。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 下表列出了本示例的文件。  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。<br /><br /> 删除发送和接收端口。<br /><br /> 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|ComposedMessageProcessor.sln|本示例的 Visual Studio 解决方案文件。|  
|ComposedMessageProcessorBinding.xml|本示例的绑定文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 Orchestration 文件夹中：<br /><br /> CMP.odx|用于执行以下操作的业务流程：运行接收管道以拆装消息，转换每个拆装的消息，然后运行发送管道以将多个消息组装为一个交换。|  
|在 Orchestration 文件夹中：<br /><br /> Orchestration.btproj|业务流程的 BizTalk 项目。|  
|在 Orchestration 文件夹中：<br /><br /> SuspendMessage.odx|用于挂起无法进行管道处理的消息的业务流程。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> CMPInput.xml、CMPOutput.xml|示例的输入和输出文档实例。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> FFReceivePipeline.btp、FFSendPipeline.btp|具有平面文件组件的接收和发送管道。 这些管道在业务流程内运行。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> Invoice.xsd、InvoiceHeader.xsd|用于输出文档和标头的平面文件架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PO.xsd、POHeader.xsd|用于输入文档和标头的平面文件架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PropertySchema.xsd|本示例的属性架构。|  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化本示例  
 使用以下过程可以生成并初始化 Compose 示例。  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>生成并初始化 Compose 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<示例路径\>\Pipelines\ComposedMessageProcessor  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在以下文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：  
  
         \<示例路径\>\Pipelines\ComposedMessageProcessor  
  
    -   编译此示例的 Visual Studio 项目。  
  
    -   创建名为“CMP Sample”的新应用程序并将示例程序集部署到该应用程序中。  
  
    -   创建并绑定 BizTalk Server 接收位置、发送和接收端口。  
  
    -   登记并启动业务流程，启用接收位置并启动发送端口。  
  
         如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集进行签名。  
  
3.  在尝试运行本示例之前，请确认在生成和初始化过程中 BizTalk Server 未报告任何错误。  
  
     若要撤销 Setup.bat 所做的更改，必须执行以下操作：  
  
    1.  从 BizTalk Server 管理控制台停止并重新启动主机实例。  
  
    2.  运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行 ComposedMessageProcessor 示例。  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a>运行 ComposedMessageProcessor 示例  
  
1.  CMPInput.txt 位于 PipelinesAndSchemas 文件夹中的文本文件复制。 将该文件粘贴到 In 文件夹中。  
  
2.  查看在 Out 文件夹中创建的文本文件。此文件包含与 CMPInput.txt 相同的记录，但是文件中的数据格式不同。  
  
     在消息通过 BizTalk Server 期间，执行了以下操作：  
  
    1.  拆装消息并将其转换为 XML 消息。 将每个消息映射为其他格式。  
  
    2.  将所有映射消息组装到一起并将其转换为平面文件格式。  
  
## <a name="see-also"></a>另请参阅  
 [管道（BizTalk Server 示例文件夹）](../core/pipelines-biztalk-server-samples-folder.md)