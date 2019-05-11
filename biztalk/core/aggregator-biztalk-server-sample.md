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
# <a name="aggregator-biztalk-server-sample"></a>聚合器 （BizTalk Server 示例）
此示例的目的是生成消息聚合功能使用业务流程和管道。 特别是我们将该生成业务流程：  
  
1.  接收到一组相关消息。 根据目标伙伴 URI 信息从消息内容中提取对消息进行关联。  
  
2.  收到的消息聚合到单个交换批通过执行一个 XML 发送管道。  
  
3.  生成一个 XML 交换消息每隔一分钟或的具有足够多的消息聚合。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \Pipelines\Aggregator  
  
 下表列出了本示例的文件。  
  
|文件|Description|  
|---------------|-----------------|  
|Aggregator.sln|该示例的 visual Studio 解决方案文件。|  
|AggretatorBinding.xml|该示例的绑定文件。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 Aggregate 文件夹中：<br /><br /> Aggregate.btproj|用于聚合业务流程的 BizTalk 项目。|  
|在 Aggregator 文件夹中：<br /><br /> Aggregate.odx|业务流程相关的消息收集在一起，然后执行发送管道将其组合到单个交换。|  
|在 Aggregate 文件夹中：<br /><br /> SuspendMessage.odx|用于挂起无法聚合业务流程中处理的消息的业务流程。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> FFReceivePipeline.btp|收到的平面文件拆装器管道。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> Instance1.txt，Instance2.txt，Instance3.txt Instance4.txt|本示例的文档实例。 Instance1.txt 和 Instance2.txt 应添加到针对目标合作伙伴 [ http://www.contoso.com ](http://www.contoso.com/) 而 Instance3.txt 和 Instance4.txt 应添加到针对目标合作伙伴交换 [http://www.northwind.com](http://www.northwind.com/) .|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> Invoice.xsd, InvoiceEnvelope.xsd|文档架构和用于输出交换的信封架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PipelinesAndSchemas.btproj|架构和管道的 BizTalk 项目。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PropertySchema.xsd|该示例的属性架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> XMLAggregatingPipeline.btp|发送管道执行从业务流程，以将收集的消息组装为一个 XML 交换。|  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化示例  
 使用以下过程生成并初始化聚合器示例。  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a>若要生成并初始化聚合器示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<Samples Path\>\Pipelines\Aggregator  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 创建输入 (In) 和输出 (Out) 文件夹的文件夹中的以下示例：  
  
      \<Samples Path\>\Pipelines\Aggregator  
  
   - 编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  
  
   - 创建名为"Aggregator Sample"的新应用程序和部署到其中的示例程序集。  
  
   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  
  
   - 登记和启动业务流程，启用接收位置，并启动发送端口。  
  
      如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对可以对生成程序集进行签名。  
  
3. 在尝试运行此示例之前, 确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成和初始化过程中未报告任何错误。  
  
    若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行聚合器示例。  
  
#### <a name="to-run-the-aggregator-sample"></a>若要运行聚合器示例  
  
1.  打开 Instance1.txt 和 Instance2.txt 文件位于 PipelinesAndSchemas 文件夹以查看其内容中。  
  
     请注意，在这种文件 DestinationPartnerURI 元素包含的值 http://www.contoso.com 。 该值用于将这两条消息关联在一起，以便可以将它们添加到同一个交换中。  
  
     同样 Instance3.txt 和 Instance4.txt 文件具有 DestinationPatnerURI 元素设置为 http://www.northwind.com 。  
  
     这两条消息将一起添加到另一个交换中。  
  
2.  将文本文件 Instance1.txt 和 Instance2.txt，Instance3.txt，和 Instance4.txt 的副本粘贴到 in 文件夹中。  
  
3.  只要它们收集 10 条消息，或者为 1 分钟的超时之后会聚合业务流程生成输出交换。 正因为如此，Out 文件夹中的文件可能会出现延迟。  
  
     若要避免超时，可以将四个输入的文件粘贴四次，这会触发聚合业务流程生成交换。  
  
4.  查看在 Out 文件夹中创建的 XML 文件。应该有两个文件： 每个目标合作伙伴 URI 一个。  
  
     打开其中一个文件并查看其内容。 该文件应包含一个 XML 交换的信封和在其中的两个 XML 文档组成。  
  
    > [!NOTE]
    >  该示例实现可能会导致"已送达，消息未使用"或"已完成有消息被放弃"中的保护方案的高负载下。 这是一条消息路由到业务流程正在结束，任何时间或意外的某一时间消息到达业务流程。  
  
## <a name="see-also"></a>请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)