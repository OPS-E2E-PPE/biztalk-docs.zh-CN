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
# <a name="composed-message-processor-biztalk-server-sample"></a>组合的消息处理器 （BizTalk Server 示例）
此示例的目的是构建处理聚合消息中的各个行项的组合的消息处理器应用程序。  
  
 特别是我们将该生成业务流程调度：  
  
1. 接收包含多个采购订单的批处理的交换消息。  
  
2. 将交换消息分解为单独的采购订单文档。  
  
3. 处理每个文档-每个采购订单转换为发票消息。  
  
4. 将所有发票消息都组装为批处理交换。  
  
   步骤 #3 得到了简化，示例目的。 例如，在更复杂的应用程序，业务流程可能发送分解到不同后端库存系统的采购订单，然后收集所有的响应之后, 将其聚合为一个批发的票消息。  
  
   组合的消息处理器模式的详细信息请参阅 [1]。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 有以下各节详细地介绍这两个示例解决方案中的两个项目。  
  
### <a name="pipelines-and-schemas"></a>管道和架构  
 管道和架构的项目包含：  
  
-   对于输入的采购订单的交换和用于输出发票交换的平面文件架构。  
  
-   用于将采购订单文档转换为发票文档的映射。  
  
-   接收和发送管道。  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a>输入和输出交换的平面文件架构  
 我们的示例应用程序将使用在平面文件格式交换。 以下是交换采购订单和发票交换的示例：  
  
 采购订单的交换 (CMPInput.txt):  
  
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
  
 采购订单文档或交换，具有标头，用于标识包含哪种类型的文档：  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 此交换包含三个采购订单文档。 一个实例包含如下所示的信息。 正如您所看到的它包含针对计费和传送的已排序的项列表以及地址等信息。  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 我们想要为此生成发票交换应如以下所示：  
  
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
  
 此交换包含已在购买顺序交换和交换的格式以及标头的格式也是不同的信息的子集。  
  
 标头如下所示：  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 和文档实例包括以下：  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 第一件事我们需要创建用于平面文件架构：  
  
- 采购订单文档 (PO.xsd)  
  
- 发票文档 (Invoice.xsd)  
  
- 采购订单标题 (POHeader.xsd)  
  
- 发票标头 (InvoiceHeader.xsd)  
  
  对于此示例，我们不打算介绍创建平面文件架构的过程。 若要了解如何从文档实例创建平面文件架构，请参阅"从文档实例创建平面文件架构"文档部分。  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a>用于将采购订单文档转换为发票文档的映射  
 地图 (PO2Invoice.btm) 将采购订单的实例转换为发票文档。  
  
#### <a name="receive-and-send-pipelines"></a>接收和发送管道  
 接收管道 (FFReceivePipeline.btp) 包含用于处理采购订单交换的平面文件拆装器组件。 具体而言，对于文件 CMPInput.txt 中交换，它删除交换标头，并生成对应于三个采购订单的三个 XML 文档。  
  
 配置接收管道中的平面文件拆装器所示：  
  
- **文档架构：** PipelinesAndSchemas.PO  
  
- **标头架构：** PipelinesAndSchemas.POHeader  
  
- **保留头部：** False  
  
- **可恢复的交换：** False  
  
- **尾部架构：**（无）  
  
- **验证文档结构：** False  
  
  发送管道 (FFSendPipeline.btp) 包含用于创建聚合的发票交换的平面文件组装器组件。  
  
  配置发送管道中的平面文件组装器所示：  
  
- **文档架构：** PipelinesandSchemas.Invoice  
  
- **标头架构：** PipelinesAndSchemas.InvoiceHeader  
  
- **保留字节顺序标记：** False  
  
- **目标字符集：**（无）  
  
- **尾部架构：**（无）  
  
### <a name="orchestration-schedule"></a>业务流程调度  
 业务流程调度 (CMP.odx) 是所有主处理发生的位置。 执行专门的以下操作：  
  
-   接收管道执行以拆装交换采购订单  
  
-   接收管道的每个输出消息转换  
  
-   发送管道执行来汇集的发票交换  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a>创建业务流程调度和定义全局变量  
 我们的业务流程将收到作为输入的平面文件交换，并将作为输出发送平面文件交换。 正因为如此，我们需要定义输入和输出消息 （称为 InputInterchange 和 OutputInterchange 分别） 为的类型无关 （即具有 System.Xml.XmlDocument 类型）。  
  
 此外，我们需要定义我们将在其中处理消息的原子作用域。 这是必需的因为可以在原子作用域内执行接收管道。  
  
#### <a name="executing-receive-pipeline"></a>执行接收管道  
 下一步，我们将添加逻辑来执行接收管道的业务流程中收到的消息。 若要执行此操作，首先我们声明类型将作用域内的变量 （称为 RcvPipeOutput）。 此变量是一个枚举器，可用于循环访问接收管道输出消息。 请注意，为了从业务流程中访问此类型，以及有关执行管道的所有其他类型，您都需要添加对以下程序集的引用：  
  
- Microsoft.XLANGs.Pipeline.dll  
  
- Microsoft.BizTalk.Pipeline.dll  
  
  则均会成功执行接收管道无法保证。 有时消息可能格式不正确，这可能会导致管道处理失败。 当管道失败时执行业务流程中的时，没有可以捕获所引发的异常，并且可以执行错误处理逻辑。 为了使我们能够捕获管道引发的异常，我们需要使用异常处理的非原子作用域内执行管道。 要执行管道的实际代码是从该范围内的表达式形状调用的。  
  
  在 ExecuteRcvPipe 表达式形状中，编写代码以执行接收管道的以下行：  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 让我们来分析这行代码中更多详细信息。 正如您所看到的我们调用静态方法 ExecuteReceivePipeline 将作为参数接收管道执行和到输入的消息的类型。 因此，它将生成输出消息的设置的枚举器对象。 结果赋给类型在此范围中定义的 ReceivePipelineOutputMessages 的变量。  
  
 我们还包含了一个异常处理块为管道执行作用域。 此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义的错误消息的业务流程实例。  
  
 在更复杂的情况下，其他错误处理此时可能会执行，如生成错误通知消息并将其发送给业务用户或管理员使用电子邮件。  
  
#### <a name="transforming-pipeline-output-messages"></a>转换管道输出消息  
 已执行管道并生成拆装消息组之后，我们需要将每个输出消息转换为不同格式。  
  
 若要在业务流程中使用转换，我们需要定义两个消息 – 输入和输出的转换。 我们将定义在原子作用域内的消息。 将名为 TmpMessageIn 的转换输入的消息属于 PipelinesAndSchemas.PO 类型。 将名为 TmpMessageOut 的转换输出消息属于 PipeliensAndSchemas.Invoice 类型。 我们将应用在 PipelinesAndSchemas 项目中定义的 PO2Invoice.btm 映射。  
  
 作为我们想要将每个管道输出消息映射，我们需要在循环中执行转换。 我们将按如下所示退出条件中使用循环形状：  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 Movenext （） 方法是 IEnumerator.NET 接口，用于将管道输出消息集合中的标准方法。 当它到达集合的末尾时返回 false。  
  
 第一个构造形状用于构造管道输出消息从业务流程消息 TmpMessageIn。  
  
 构造形状中的代码：  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 在此代码中我们第一次业务流程消息初始化为 null，然后将其设置为当前消息从管道输出消息集合。  
  
 在执行 TmpMessageIn 的实际转换的第二个构造形状和类型的 TmpMessageOut PipelinesAndSchemas.Invoice 被构造。  
  
#### <a name="executing-send-pipeline"></a>执行发送管道  
 业务流程中的最后一个处理步骤是执行平面文件发送管道以将所有转换的 xml 消息组装为一个平面文件交换。  
  
 为了执行发送管道我们需要使用的变量的类型的变量 sendpipeinput，将保存业务流程需要在发送管道中处理的消息的集合。  
  
 在循环执行转换的最后一个表达式中，我们将编写代码，将添加到消息集合中的发送管道的每个已转换的消息：  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 与执行的过程相似的接收的管道的发送管道执行的代码放置在具有异常处理块的非原子作用域内。 发送管道执行代码位于构造模块的消息赋值形状中。  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 构造模块用于构造类型无关 (即 System.Xml.XmlDocument) 的管道输出消息 OutputInterchange。 然后在消息赋值形状中新构造的消息初始化为 null。 在此之后调用静态方法 ExecuteSendPipeline 以执行发送管道。 此方法采用一种类型的发送管道执行，输入的消息和对存储管道输出的输出消息的引用作为参数。  
  
 与接收管道的执行，此处我们还有一种异常处理块管道执行作用域。 此块会捕获类型为 XLANGPipelineManagerException 的异常，然后为简单起见仅终止具有自定义的错误消息的业务流程实例。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 下表列出了本示例的文件。  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。<br /><br /> 删除发送和接收端口。<br /><br /> 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|ComposedMessageProcessor.sln|该示例的 visual Studio 解决方案文件。|  
|ComposedMessageProcessorBinding.xml|该示例的绑定文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|在业务流程文件夹中：<br /><br /> CMP.odx|业务流程： 运行接收管道以拆装消息，每个已拆装的消息转换，然后运行发送管道以将消息组装为一个交换。|  
|在业务流程文件夹中：<br /><br /> Orchestration.btproj|业务流程的 BizTalk 项目。|  
|在业务流程文件夹中：<br /><br /> SuspendMessage.odx|用于挂起无法进行管道处理的消息的业务流程。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> CMPInput.xml、 CMPOutput.xml|输入和输出的示例文档实例。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> FFReceivePipeline.btp, FFSendPipeline.btp|接收和发送管道使用平面文件组件。 这些管道业务流程内运行。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> Invoice.xsd、 InvoiceHeader.xsd|输出文档和标头的平面文件架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PO.xsd、 POHeader.xsd|输入的文档和标头的平面文件架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PropertySchema.xsd|该示例的属性架构。|  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化示例  
 使用以下过程生成并初始化 Compose 示例。  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>若要生成并初始化 Compose 示例  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<Samples Path\>\Pipelines\ComposedMessageProcessor  
  
2.  运行文件 Setup.bat，以执行以下操作：  
  
    -   创建输入 (In) 和输出 (Out) 文件夹的文件夹中的以下示例：  
  
         \<Samples Path\>\Pipelines\ComposedMessageProcessor  
  
    -   编译此示例的 Visual Studio 项目。  
  
    -   创建名为"CMP Sample"的新应用程序和部署到其中的示例程序集。  
  
    -   创建并绑定 BizTalk Server 接收位置、 发送和接收端口。  
  
    -   登记和启动业务流程，启用接收位置，并启动发送端口。  
  
         如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对可以对生成程序集进行签名。  
  
3.  然后再尝试运行此示例中，确认在生成和初始化过程中 BizTalk Server 未报告任何错误。  
  
     若要撤消 Setup.bat 所做的更改，必须执行以下操作：  
  
    1.  停止并重新启动 BizTalk Server 管理控制台中的主机实例。  
  
    2.  运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行 ComposedMessageProcessor 示例。  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a>若要运行 ComposedMessageProcessor 示例  
  
1.  将复制 CMPInput.txt 位于 PipelinesAndSchemas 文件夹中的文本文件。 将该文件粘贴到 in 文件夹中。  
  
2.  查看在 Out 文件夹中创建的文本文件。此文件包含与 CMPInput.txt，相同的记录，但文件中的数据的格式不同。  
  
     如该消息通过 BizTalk Server 会传递，将发生下列情况：  
  
    1.  拆装消息并将转换为 XML 消息。 每个消息映射到不同的格式。  
  
    2.  所有映射的消息组装到一起并转换为平面文件格式。  
  
## <a name="see-also"></a>请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)