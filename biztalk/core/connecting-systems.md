---
title: 连接系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c4895e5-7272-415f-a0de-905256fa0a43
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 949627c621dcedc26be98a175eae890193f61ac4
ms.sourcegitcommit: bab8f4abca27edc45f9f4601ada6f3fc6a2b87cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2019
ms.locfileid: "67189088"
---
# <a name="connecting-systems"></a>连接系统
有效的不同计算机上的不同软件之间的消息交换是绝对必需的集成。 考虑到现有通信方式多种多样，BizTalk Server 必须支持各种协议和消息格式。 按下文所述，该引擎的重要部分专门介绍实现此通信。 要记住，一个重要事实，但该引擎内部只使用 XML 文档。 在任何格式一条消息到达时，必须转换为 XML 文档是收到。 同样，如果文档的收件人不能接受该文档为 XML，则引擎将其转换为目标所需的格式。  
  
## <a name="sending-and-receiving-messages-adapters"></a>发送和接收消息：适配器  
 BizTalk Server 必须与各种其他软件进行通信，因为它依赖适配器来实现此类。 适配器是一种通信机制，例如特定的协议的实现。 开发人员确定要在给定情况下使用的适配器。 它们可能会选择 BizTalk Server 提供，例如，内置适配器之一或使用为诸如 Windows SharePoint Services 之类的常用产品创建的适配器或甚至可以创建自定义适配器。 在每个这种情况下，适配器是基于名为适配器框架的标准结构。 此框架提供一种方式来创建和运行适配器的支持，并且它还支持相同的工具用于管理所有适配器类型。  
  
 Microsoft BizTalk Server 包含以下本地适配器：  
  
- 文件适配器： 支持读取和写入到文件中的 Windows 文件系统。 由于业务流程中所涉及的应用程序通常可以访问相同的文件系统，本地或网络中，通过文件交换消息可以是一个方便的选项。  
  
- FTP 适配器： 支持发送和接收文件传输协议 (FTP) 服务器与 BizTalk Server 之间的信息。  
  
- HTTP 适配器： 支持发送和接收使用 HTTP 的信息。 BizTalk Server 公开一个或多个 Url，以便其他应用程序以将数据发送到它，并且它可以使用此适配器将数据发送到其他 Url。  
  
- MSMQ 适配器： 支持发送和接收消息使用 Microsoft 消息队列 (MSMQ)。  
  
- WebSphere MQ 适配器： 支持发送和接收消息使用 IBM 的 WebSphere MQ （以前称为 MQSeries）。  
  
- POP3 适配器： 支持接收电子邮件及其附件使用邮局协议 (POP3) 的第三版。  
  
- SMTP 适配器： 支持使用 SMTP 发送消息。 标准电子邮件地址用于标识参与方。  
  
- SOAP 适配器： 支持发送和接收 Web 服务请求，以使 BizTalk Server 要连接到 Web 服务。  
  
- WCF 适配器： 支持发送和接收使用 Windows Communication Foundation 的信息。  
  
- Windows SharePoint Services (WSS) 适配器： 支持访问和发布在 Microsoft Windows SharePoint 文档库中存储的文档。  
  
  适配器用于常用商业软件也是 Microsoft 提供的其中包括：  
  
- Microsoft BizTalk Adapter for JD Edwards OneWorld  
  
- Microsoft BizTalk Adapter for JD Edwards EnterpriseOne  
  
- Microsoft BizTalk Adapter for PeopleSoft Enterprise  
  
- Microsoft BizTalk Adapter for TIBCO Rendezvous  
  
- 用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器  
  
  有关与这些适配器相关的详细信息，请参阅[BizTalk Server 中的适配器](../core/adapters-in-biztalk-server.md)。  
  
  无论适配器用于接收数据，它们可以访问由业务流程之前，通常必须处理它接收的消息。 同样，传出消息生成的业务流程通常需要通过适配器发送前处理。  
  
## <a name="processing-messages-pipelines"></a>处理消息：管道  
 业务流程中涉及的应用程序通过交换各种文档进行通信： 例如，采购订单和发票。 BizTalk Server 应用程序执行业务流程，它必须能够正确处理包含这些文档的消息。 此处理过程可能涉及到多个步骤，并因此通过消息管道来执行。 处理传入消息时由接收管道，而传出消息通过发送管道。  
  
 例如，即使更多应用程序已设计为可理解 XML 文档，很多，很可能是大多数目前 — 不能。 由于 BizTalk Server 内部只使用 XML 文档，它必须提供一种方法，以其他格式与 XML 之间相互转换。 其他服务也可能是必需的例如进行身份验证消息的发件人。 若要处理这些任务和其他任务的模块化且可自定义方式，来构造管道，通过一定数量的阶段，其中每个包含一个或多个。NET 启用或组件对象模型 (COM) 组件。 每个组件处理特定消息处理的部分。 BizTalk Server 提供了几个标准组件，用于解决最常见的情况。 如果这些无法满足需要，开发人员还可以创建自定义两个组件接收和发送管道。  
  
 ![](../core/media/understandingbts-05-pipelinereceive.gif "UnderstandingBTS_05_PipelineReceive")  
  
 如上图所示的接收管道，以及为每个提供的标准组件中的阶段。 这些阶段和及其关联的组件是：  
  
- 解码：为此阶段，即 MIME/SMIME 解码器，BizTalk Server 提供一个标准组件。 此组件可以处理消息并在 MIME 或 Secure MIME (S/MIME) 中包含的任何附件设置格式。 该组件将这两种类型的消息转换成 XML，并还可以解密 S/MIME 消息，并验证其数字签名。  
  
- 反汇编：提供了三个标准组件。 平面文件拆装器组件将平面文件转换 XML 文档。 这些文件可以是位置，其中每条记录的相同的长度和结构，或带分隔符，使用指定的字符用于分隔文件中的记录。 第二个标准组件，XML 拆装器将分析已使用 XML 描述的传入消息。 第三个标准组件，其中一个已不常使用今天，是 BizTalk 框架拆装器。 它接受使用由 BizTalk 框架在 BizTalk Server 2000 中实现定义的可靠消息传递机制发送消息。  
  
- 验证：BizTalk Server 为此阶段提供 XML 验证器组件。 顾名思义，此组件验证由对指定的架构或架构，如果文档不符合这些架构之一，则返回错误组的拆装阶段生成的 XML 文档。  
  
- 解析参与方： 此阶段，参与方解析的唯一标准组件尝试确定此消息的发件人的标识。 如果已对消息进行数字签名，签名用于查找 BizTalk Server 中的管理数据库中的 Windows 标识。 （如下文所述，使用此数据库还由 BizTalk Server 管理工具。）如果该消息还包含 Windows 用户的已经过身份验证的安全标识符 (SID)，则使用此标识。 如果成功这两种机制，消息的发件人分配默认的匿名标识。  
  
  ![](../core/media/understandingbts-06-pipelinesend.gif "UnderstandingBTS_06_PipelineSend")  
  
  传出消息可能也要经历多个阶段定义的发送管道中使用。 上图显示了阶段和发送管道的标准组件。 它们分别是：  
  
- 预组装：不提供了任何标准组件。 相反，可以根据需要在此处插入自定义组件。  
  
- 组合：并行接收管道中的拆装阶段，此阶段还具有三个标准组件。 平面文件组装器将 XML 消息转换到的位置或分隔平面文件和 XML 组装器支持添加信封以及对传出 XML 消息进行其他更改。 第三个选项，BizTalk 框架组装器，包使用 BizTalk 框架消息传送技术的可靠传输的消息。  
  
- 进行编码：BizTalk Server 定义为此阶段，即 MIME/SMIME 编码器只能有一个标准组件。 此组件打包传出消息中 MIME 或 S/MIME 格式。 如果使用 S/MIME，则该消息可以还会进行数字签名和/或加密。  
  
  BizTalk Server 定义了一些默认管道，其中包括可用于处理已经以 XML 表示的消息的简单接收/发送对。 开发人员还可以创建自定义管道使用管道设计器。 此工具，它在内部运行[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，提供一个图形界面，开发人员可以拖放组件以使用任何所需行为创建管道。  
  
## <a name="choosing-messages-subscriptions"></a>选择消息：订阅  
 一条消息已通过适配器和接收管道后下, 一步是确定它应在哪里。 一条消息通常以业务流程中，目标但还可以直接转到发送管道，从而将 BizTalk Server 要用作纯粹的消息传送系统的消息。 在任一情况下，完成此匹配的消息与其目标使用的订阅。  
  
 一条消息由接收管道处理时，消息上下文被创建包含消息的各种属性。 业务流程或发送管道可以基于这些属性的值的消息订阅。 例如，业务流程可能会创建与类型"发票"的所有消息或从 QwickBank 公司接收到"发票"类型的所有消息或从 QwickBank 公司接收到"发票"类型的所有消息匹配的订阅是用于超过 10,000 美元。 但指定了它，则订阅其订阅服务器中返回与订阅定义的条件匹配的那些消息。 收到的消息可能会通过实例化某些业务流程启动业务流程或也可以激活另一个步骤中已运行业务流程。 同样，当业务流程发送一条消息，则该消息匹配到基于订阅的发送管道管道已建立的。  
  
-   在 BizTalk Server 中，也很有可能订阅特定错误条件。 可以按特定方式处理或路由到特定目标，例如 Windows SharePoint Services 文件夹一条错误消息。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 消息引擎](../core/the-biztalk-server-messaging-engine.md)   
 [发布和订阅体系结构](../core/publish-and-subscribe-architecture.md)   
 [适配器](../core/adapters.md)   
 [管道](../core/pipelines.md)
