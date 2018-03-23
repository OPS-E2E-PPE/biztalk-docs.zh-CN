---
title: 聚合器 （BizTalk Server 示例） |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f4d28214a815aca88f214e5efb9cd883e7192
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="aggregator-biztalk-server-sample"></a>聚合器（BizTalk Server 示例）
本示例的目的在于使用业务流程和管道建立消息聚合功能。 具体而言，我们将生成一个执行以下操作的业务流程：  
  
1.  接收一组相关消息。 根据从消息内容中提取的目标伙伴 URI 信息对消息进行关联。  
  
2.  通过执行一个 XML 发送管道，将收到的消息聚合到单个交换批中。  
  
3.  每分钟生成一个 XML 交换消息，或者在有足够的消息可供聚合时生成一个 XML 交换消息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>*\Pipelines\Aggregator  
  
 下表列出了本示例的文件。  
  
|文件|Description|  
|---------------|-----------------|  
|Aggregator.sln|本示例的 Visual Studio 解决方案文件。|  
|AggretatorBinding.xml|本示例的绑定文件。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 Aggregate 文件夹中：<br /><br /> Aggregate.btproj|用于聚合业务流程的 BizTalk 项目。|  
|在 Aggregator 文件夹中：<br /><br /> Aggregate.odx|业务流程，该业务流程将相关的消息收集在一起，然后执行发送管道以将它们组装到单个交换中。|  
|在 Aggregate 文件夹中：<br /><br /> SuspendMessage.odx|业务流程，用于挂起那些无法在聚合业务流程中进行处理的消息。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> FFReceivePipeline.btp|带有平面文件拆装器的接收管道。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt|本示例的文档实例。 Instance1.txt 和 Instance2.txt 应添加到目标合作伙伴的交换[ http://www.contoso.com ](http://www.contoso.com/)时 Instance3.txt 和 Instance4.txt 应添加到目标合作伙伴的交换[ http://www.northwind.com](http://www.northwind.com/).|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> Invoice.xsd、InvoiceEnvelope.xsd|用于输出交换的文档架构和信封架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PipelinesAndSchemas.btproj|架构和管道的 BizTalk 项目。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PropertySchema.xsd|本示例的属性架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> XMLAggregatingPipeline.btp|从业务流程执行的发送管道，用于将收集的消息组装为一个 XML 交换。|  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化本示例  
 使用以下过程可以生成并初始化聚合器示例。  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a>生成和初始化聚合器示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<示例路径\>\Pipelines\Aggregator  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在以下文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：  
  
         \<示例路径\>\Pipelines\Aggregator  
  
    -   为本示例编译 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。  
  
    -   创建名为“Aggregator Sample”的新应用程序并将示例程序集部署到该应用程序中。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
    -   登记并启动业务流程，启用接收位置并启动发送端口。  
  
         如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集进行签名。  
  
3.  在尝试运行本示例之前，请确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
     若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行聚合器示例。  
  
#### <a name="to-run-the-aggregator-sample"></a>运行聚合器示例  
  
1.  打开位于 PipelinesAndSchemas 文件夹中的 Instance1.txt 和 Instance2.txt 文件以查看其内容。  
  
     请注意，在这两文件 DestinationPartnerURI 元素包含的值http://www.contoso.com。该值用于将这两条消息关联在一起，以便可以将它们添加到同一个交换中。  
  
     同样 Instance3.txt 和 Instance4.txt 文件具有 DestinationPatnerURI 元素设置为http://www.northwind.com。  
  
     这两条消息将一起添加到另一个交换中。  
  
2.  将文本文件 Instance1.txt、Instance2.txt、Instance3.txt 和 Instance4.txt 的副本粘贴到文件夹 In。  
  
3.  聚合业务流程在收集了 10 条消息或达到 1 分钟的超时时间后才会生成输出交换。 所以，Out 文件夹中的文件可能会延迟一段时间才出现。  
  
     若要避免这段等待时间，可以将四个输入文件再粘贴四次，这样可触发聚合业务流程生成交换。  
  
4.  查看在 Out 文件夹中创建的 XML 文件。应该有两个文件：每个目标合作伙伴 URI 一个。  
  
     打开其中一个文件并查看其内容。 文件应包含由一个信封和信封内的两个 XML 文档组成的一个 XML 交换。  
  
    > [!NOTE]
    >  在保护方案中的高负载情况下，示例的实现方式可能会导致“已送达，消息未使用”或“已完成，有消息被放弃”。 在将消息路由至正处于结束过程中的业务流程时，或者在有预料之外的消息到达业务流程时，都会出现此情况。  
  
## <a name="see-also"></a>另请参阅  
 [管道（BizTalk Server 示例文件夹）](../core/pipelines-biztalk-server-samples-folder.md)