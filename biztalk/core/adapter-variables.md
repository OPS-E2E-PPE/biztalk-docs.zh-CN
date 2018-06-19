---
title: 适配器变量 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aeda96bc-5141-4c42-8a29-b0a28bc47aa4
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ecb644aa2eb341ca0d6012194095be6afbe88e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233877"
---
# <a name="adapter-variables"></a>适配器变量
任何自定义适配器都有大量变量需要处理。 赋给这些变量的值将影响适配器实现的自定义逻辑。 特定于传输或特定于应用程序的配置属性还有助于支持您的解决方案。 下表列出了这些常见变量。 您必须确定是否要在您的自定义适配器中支持每个变量。  
  
 对于每个选项，您的适配器必须实现特定的接口。 下表列出了各个变量选项以及有关链接，这些链接提供与编写适配器代码来支持的您的设计决策有关的详细信息。  
  
|适配器变量|Description|  
|----------------------|-----------------|  
|通信方向|**接收。** 接收适配器侦听传入消息的特定于协议的地址。 在收到某一消息时，接收适配器将该消息移交给消息引擎，消息引擎将该消息经过接收管道传递，最终保存在 MessageBox 数据库中。<br /><br /> **发送。** 在消息引擎需要将某一消息发送到特定终结点时，会将该消息传递到发送管道。 发送适配器接受来自发送管道的消息，并将该消息发送到发送端口。|  
|适配器宿主|**在过程。** 创建和承载于 BizTalk 服务进程，BTSNTSvc.exe 进程内适配器。 如果主机是 64 位进程的名为 BTSNTSvc64.exe。 为简单起见，我们将不介绍在本部分中再次 64 位进程。<br /><br /> 这意味着，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]创建和管理适配器的生存期、 传输代理并用其进行初始化，服务适配器请求，并终止服务关闭时适配器。<br /><br /> 对于进程内适配器，请[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到适配器在运行时，包括处理程序中，提供了配置信息也发送端口和接收位置配置。 此外，配置服务时段如方面由处理 the Messaging Engine 以便适配器不需要确保接收位置或发送端口是在服务窗口之外。<br /><br /> 请注意，所有发送适配器进程内适配器并且必须在 BTSNTSvc.exe 进程中运行。<br /><br /> **隔离。** 在不是一个独立主机中创建该适配器属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时。 独立的一个示例是适配器的 HTTP 接收适配器，在进程空间的 Internet 信息服务 (IIS) 中运行。<br /><br /> IIS 进程模型是这样，IIS 管理的 ASP.NET 应用程序和 ISAPI 扩展的生存期。 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法管理的生存期的适配器，该适配器简称为独立的适配器。<br /><br /> 因为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不管理独立适配器的实例化，所以，适配器必须创建自己的传输代理，并需要自己完成传输代理注册。<br /><br /> 请注意，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构消除了不必要的进程间通信。 由于独立的适配器和 BizTalk 堆栈是在同一进程中，没有进程间通信适配器调用 the Messaging Engine 时。 仅进程间通信是消息引擎和数据库，这是不可避免地之间。<br /><br /> COM + 应用程序不能驻留在未托管代码中编写发送适配器。|  
|消息交换模式|**单向。** 消息是传入或传出。<br /><br /> **请求-响应**（双向）**。** 请求-响应适配器始终是接收适配器。 请求-响应接收适配器从客户端接收请求消息和将消息提交至[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序处理完请求消息中，它将响应消息发送回适配器。  然后，该适配器传输回客户端的响应消息。<br /><br /> **请求作出响应**（双向）**。** 请求作出响应适配器始终为发送适配器。 请求-响应发送适配器发送的请求消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到目标，等待响应消息，，然后将响应消息提交回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。|  
|发送端口绑定|**动态发送端口和接收位置。** 发送的 URI 变量端口或接收位置使用在动态在运行时确定绑定。<br /><br /> **静态发送端口和接收位置。** 发送的 URI 变量端口或接收位置是静态的在运行时之前配置。|  
|与异步发送适配器同步发送|**同步发送适配器。** 执行时发送操作，the Messaging Engine 阻止传输代理线程，直到它已发送消息的批处理，并返回。 消息传输，重试，挂起，或到下一步操作在移动操作完成后，传输代理处理消息删除。<br /><br /> **异步发送适配器。** 异步发送适配器不阻止传输代理线程，但而是在执行发送操作时使用单独的线程。 与不同的是同步的适配器，此适配器必须实现所有删除和重试逻辑，然后重试。传输代理并不处理逻辑。<br /><br /> 将异步消息发送的适配器允许更好[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]比发送同步消息的性能。 这是因为线程花费大量时间等待入站或出站操作完成。 因为消息引擎与 CPU 高度相关，所以，阻止消息引擎线程将会降低适配器的性能。<br /><br /> 使用异步传输强烈建议，并提高性能。|  
|异步接收适配器|所有接收适配器是异步的。 这意味着当适配器提交新消息到 BizTalk Messaging Engine 它不会等待在返回之前完全处理它们。|  
|事务支持|**事务的适配器。** 事务支持发送和接收的消息。 在发送端，仅异步成批的发送适配器支持事务。<br /><br /> **非事务性适配器。** 适配器，不会接收或发送消息的显式事务的作用域内。 许多适配器是非事务性的因为它们正在送入到或从系统，如 Windows 文件系统中，不支持事务。|  
|与批处理不受支持的批处理支持发送适配器发送适配器|**批处理支持适配器。** 发送适配器可以处理的操作批中的消息。<br /><br /> 所有适配器可以收集所有提交的可用消息，然后提交到 MessageBox 数据库在一次，从而减少了必要的数据库更新的数目。 在某些情况下，这意味着批处理的长度是之一。 同样，发送适配器收集的所有可用于发送消息，提取，以及在一次然后将它们发送到其目标。<br /><br /> 一般情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将一批视为数据库更新的工作的工作单元。 在同一个批处理，适配器可以提交单向、 请求-响应和请求作出响应消息;挂起消息;删除消息;一条消息会重试传输; 的请求或消息被移动到备份传输的请求。 只要有可能，应使用批处理的传输。<br /><br /> 发送和接收可成批归入适配器，但仅成批异步发送适配器支持事务。<br /><br /> **批处理不受支持的适配器。** 每个消息无需对服务器的独立调用。|  
|批处理支持接收适配器|所有接收适配器支持批处理。|  
|动态与静态设计时适配器配置|**动态适配器的设计时。** 为适配器以便支持动态设计时配置，必须开发自定义用户界面 (UI) 用于添加适配器元数据向导。 此接口允许用户选择要添加到 BizTalk 项目的架构，并通过 Web 服务描述语言 (WSDL) 文件返回其服务说明。 适配器提供用于获取架构的自定义 UI。 通过添加适配器元数据向导导入服务，它将端口类型、 消息类型和业务流程添加到 BizTalk 项目除了架构。<br /><br /> 有关详细信息，请参阅[静态设计时适配器配置](../core/static-design-time-adapter-configuration.md)。<br /><br /> **静态适配器的设计时。** 若要支持设计时的静态配置的适配器您执行标准接口，以允许添加适配器元数据向导以选择要添加到 BizTalk 项目的架构。 BizTalk 适配器框架将为适配器提供 UI。<br /><br /> 有关修改示例文件适配器的信息，请参阅[动态设计时适配器配置](../core/dynamic-design-time-adapter-configuration.md)。|  
|与应用程序适配器的传输适配器|**传输适配器。** 传输适配器支持特定协议，并且不使用架构。 九个十二本机适配器，是传输适配器： MSMQ、 MQ 系列、 文件、 FTP、 HTTP、 SMTP、 POP3 和 SOAP。<br /><br /> **应用程序适配器。** 应用程序适配器使用数据架构将数据发送到指定的应用程序。 两个是应用程序适配器的本机适配器：[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]和 SQL。|  
  
 有关在您的自定义适配器代码中实现的接口的信息，请使用下表中的链接，了解您计划创建的适配器的类型。 在某些情况下，您必须结合使用列出的接口，用列出的接口满足一个要求，用其他页上列出的接口满足另一个要求。  
  
|变量|有关详细信息，请参阅：|  
|--------------|--------------------------|  
|**发送适配器**|[实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)|  
|同步|[发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md)|  
|异步|[异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md)|  
|批处理支持的同步|[同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)|  
|异步批处理支持|[异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)|  
|事务异步批处理的支持|[事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)|  
|请求作出响应|[适配器发送的请求作出响应的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)|  
|**接收适配器**|[实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)|  
|Regular|[进程内的接口接收适配器](../core/interfaces-for-an-in-process-receive-adapter.md)|  
|隔离|[一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)|  
|批处理支持|[批处理支持的接口接收适配器](../core/interfaces-for-a-batch-supported-receive-adapter.md)|  
|批处理支持的事务|[批处理支持为一个事务性接口接收适配器](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)|  
|同步请求-响应适配器|[接口同步请求-响应接收适配器](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)|  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义适配器](../core/developing-custom-adapters.md)   
 [使用适配器](../core/using-adapters.md)   
 [适配器样本-开发](../core/adapter-samples-development.md)