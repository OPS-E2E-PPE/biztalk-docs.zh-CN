---
title: "将系统连接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c4895e5-7272-415f-a0de-905256fa0a43
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d042d067fa68c6d54d95f3b0e658c20db4961d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connecting-systems"></a>连接系统
若要进行集成，必须在不同计算机上的不同软件之间进行有效的消息交换。 考虑到现有通信方式多种多样，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 必须支持各种协议和消息格式。 如后文所述，该引擎的一个重要部分专用于实现此通信。 但请注意，该引擎内部只使用 XML 文档。 不管消息以何种格式到达，在收到消息后都必须将其转换为 XML 文档。 同样，如果文档的收件人无法以 XML 格式接收文档，则引擎会将其转换为目标所需的格式。  
  
## <a name="sending-and-receiving-messages-adapters"></a>发送和接收消息： 适配器  
 由于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 必须与其他各种软件进行通信，因此它依赖适配器来实现此类通信。 适配器用于实现某种通信机制，例如特定的协议。 开发人员确定在给定情况下要使用的适配器。 例如，开发人员可以选择 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 提供的内置适配器之一，也可以使用为诸如 Windows SharePoint Services 之类的常用产品创建的适配器，甚至可以创建自定义适配器。 在上述每一种情况下，适配器都是构建在称为“适配器框架”的标准结构之上的。 此框架为创建和运行适配器提供了常用方法，并且支持用于管理所有适配器类型的相同工具。  
  
 Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 包括以下本地适配器：  
  
-   文件适配器： 支持读取和写入 Windows 文件系统中的文件。 由于业务流程中包含的应用程序可能会经常访问本地或网络中的同一文件系统，因此通过文件交换消息可能较为方便。  
  
-   FTP 适配器： 支持发送和接收文件传输协议 (FTP) 服务器和 BizTalk Server 之间的信息。  
  
-   HTTP 适配器： 支持发送和接收使用 HTTP 的信息。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 公开了一个或多个 URL，以便其他应用程序能够向其发送数据，然后该引擎可使用此适配器将数据发送给其他 URL。  
  
-   MSMQ 适配器： 支持发送和接收消息使用 Microsoft 消息队列 (MSMQ)。  
  
-   WebSphere MQ 适配器： 支持发送和接收使用 IBM WebSphere MQ （以前称为 MQSeries） 的消息。  
  
-   POP3 适配器： 支持在接收电子邮件和使用邮局协议 (POP3) 的第三版其附件。  
  
-   SMTP 适配器： 支持使用 SMTP 发送消息。 使用标准电子邮件地址标识参与方。  
  
-   SOAP 适配器： 支持发送和接收 Web 服务请求，以使连接到 Web 服务的 BizTalk Server。  
  
-   WCF 适配器： 支持发送和接收使用 Windows Communication Foundation 的信息。  
  
-   Windows SharePoint Services (WSS) 适配器： 支持访问和发布 Microsoft Windows SharePoint 文档库中存储的文档。  
  
 Microsoft 还提供了用于常用商业软件的适配器，包括：  
  
-   用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器  
  
-   用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器  
  
-   用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器  
  
-   用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器  
  
-   用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器  
  
 有关这些适配器的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  
  
 无论使用哪一种适配器来接收数据，通常都必须对该适配器接收到的消息进行处理，然后业务流程才能访问这些消息。 同样，通常需要对业务流程生成的传出消息进行处理，然后适配器才能发送这些消息。  
  
## <a name="processing-messages-pipelines"></a>处理消息： 管道  
 业务流程中涉及的应用程序通过交换各种类型的文档进行通信： 有关示例，采购订单和发票。 如果要使用 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 应用程序来执行业务流程，则该应用程序必须能够正确地处理包含这些文档的消息。 此处理过程可能包含多个步骤，因此将通过消息管道来执行。 传入消息通过接收管道处理，而传出消息则通过发送管道处理。  
  
 例如，即使越来越多的应用程序已设计为可理解 XML 文档，但目前仍有许多（很可能是大多数）应用程序无法理解 XML 文档。 由于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 内部只使用 XML 文档，因此它必须提供一种可实现其他格式与 XML 之间相互转换的方法。 此外，还可能需要其他服务，例如对消息发送方进行身份验证。 为了以模块化且可自定义的方式处理这些任务和其他任务，将分若干个阶段来构造管道，其中每个阶段均包含一个或多个启用 .NET 的组件或组件对象模型 (COM) 组件。 每个组件处理特定的消息处理部分。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]提供地址的最常见的用例的许多标准组件。 如果这些组件无法满足需要，开发人员也可以为接收管道和发送管道创建自定义组件。  
  
 ![](../core/media/understandingbts-05-pipelinereceive.gif "UnderstandingBTS_05_PipelineReceive")  
  
 上图显示了接收管道中的各个阶段以及为每个阶段提供的标准组件。 这些阶段及其关联组件如下：  
  
-   解码：[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]对于这一阶段，MIME/SMIME 解码器提供一个标准的组件。 此组件可以处理 MIME 或 Secure MIME (S/MIME) 格式的消息以及消息中包含的任何附件。 该组件可将这两种类型的消息转换为 XML，还可以对 S/MIME 消息进行解密并验证其数字签名。  
  
-   反汇编： 提供了三个标准组件。 平面文件拆装器组件可将平面文件转换为 XML 文档。 这些文件可以是位置文件，其中每条记录的长度和结构相同；也可以是分隔文件，这些文件使用指定字符来分隔文件中的记录。 第二个标准组件为 XML 拆装器，用于解析已使用 XML 进行说明的传入消息。 第三个标准组件为 BizTalk 框架拆装器，该组件如今已不常使用。 该组件使用 BizTalk 框架定义的可靠消息传送机制来接受所发送的消息， BizTalk 框架是在 BizTalk Server 2000 中实现的 。  
  
-   验证：[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]对于这一阶段中提供的 XML 验证程序组件。 顾名思义，此组件可根据指定的架构或架构组对拆装阶段生成的 XML 文档进行验证，如果文档与任一架构不符，则返回错误。  
  
-   解析方： 对此阶段，参与方解析的唯一标准组件尝试确定此消息的发件人的身份。 如果已对消息进行数字签名，则使用该签名在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的管理数据库中查找 Windows 标识。 （正如稍后部分中将介绍的一样，BizTalk Server 的管理工具也使用此数据库。）如果消息包含 Windows 用户的已验证安全标识符 (SID)，则使用此标识。 如果这两种机制都无法成功，则为消息发送方分配默认的匿名标识。  
  
 ![](../core/media/understandingbts-06-pipelinesend.gif "UnderstandingBTS_06_PipelineSend")  
  
 按照所使用的发送管道的定义，传出消息可能也要经历多个阶段。 上图显示了发送管道的各个阶段和标准组件。 它们分别是：  
  
-   预配置： 提供了没有标准的组件。 不过，可以根据需要在此处插入自定义组件。  
  
-   配置： 并行接收管道中的拆装阶段，此阶段还具有三个标准组件。 平面文件组装器将 XML 消息转换为位置平面文件或分隔平面文件，XML 组装器则支持向传出 XML 消息添加信封以及对其进行其他更改。 第三个组件为 BizTalk 框架组装器，它使用 BizTalk 框架消息传送技术将消息打包以便进行可靠传输。  
  
-   进行编码：[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]对于这一阶段，MIME/SMIME 编码器定义只有一个标准的组件。 此组件以 MIME 或 S/MIME 格式打包传出消息。 如果使用 S/MIME，则还可以对消息进行数字签名和/或加密。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 定义了一些默认管道，其中包括可用于处理以 XML 表示的消息的简单接收/发送对。 开发人员还可以使用管道设计器来创建自定义管道。 运行在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 内的此工具提供了一个图形界面，使用该界面，开发人员可以使用任何所需的操作来拖放组件以创建管道。  
  
## <a name="choosing-messages-subscriptions"></a>选择消息： 订阅  
 在消息已通过适配器和接收管道进行传递后，下一步是确定该消息要传递到的目标。 消息通常以业务流程为目标，但消息也可能直接传递到发送管道，这样就允许将 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 仅用作消息传送系统。 无论在哪种情况下，均使用订阅来实现消息与其目标的匹配。  
  
 接收管道对消息进行处理后，将创建包含消息的各种属性的消息上下文。 业务流程或发送管道可以根据这些属性的值来订阅消息。 例如，业务流程可以创建匹配的"发票"的类型的所有消息或从 QwickBank corporation，收到"发票"的类型的所有消息或收到的 QwickBank corporation 的"发票"的类型的所有消息的订阅提供多个 $10000 的。 但是指定了该值，订阅其订阅服务器中返回匹配订阅定义的条件的那些消息。 接收到的消息可以通过实例化某些业务流程来启动业务流程，也可以激活正在运行的业务流程中的其他步骤。 同样，当业务流程发送消息时，会根据发送管道已建立的订阅将消息与发送管道进行匹配。  
  
-   在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中，也有可能订阅特定的错误情况。 错误消息可以按特定方式进行处理，也可以路由到特定目标，例如 Windows SharePoint Services 文件夹。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server Messaging Engine](../core/the-biztalk-server-messaging-engine.md)   
 [发布和订阅体系结构](../core/publish-and-subscribe-architecture.md)   
 [适配器](../core/adapters.md)   
 [管道](../core/pipelines.md)