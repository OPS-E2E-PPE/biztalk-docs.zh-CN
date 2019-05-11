---
title: 用于 WCF 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 423c6021-5fb7-48c9-9319-11e7a18c775c
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05951b5bfd2f586cdaf88bc11bdf12f505ef15b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330735"
---
# <a name="known-issues-for-the-wcf-adapters"></a>WCF 适配器的已知的问题
本主题介绍 BizTalk Server 附带的 WCF 适配器的已知的问题。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-receive-adapters"></a>在入站 SOAP 封送处理中的失败 WCF 中不会挂起消息接收适配器  
 当消息到达 WCF 接收适配器，WCF 适配器从传入 SOAP 消息创建 BizTalk 消息，然后将 BizTalk 消息传递到由终结点管理器管理的传输代理。 如果适配器无法创建 BizTalk 消息时读取 SOAP 信封和正文，则消息未挂起，因为适配器使用快速、 非缓存和只进读取器来访问 SOAP 消息。  
  
 应检查失败的消息在事件日志。 例如，可以在使用的正文路径表达式**消息**WCF 适配器传输属性对话框中，指定如何通过 WCF 适配器传入的 SOAP 消息创建入站的 BizTalk 消息正文中的选项卡。 当传入的 SOAP 消息的无效的正文路径表达式上提供了为**消息**选项卡上，则适配器无法创建 BizTalk 消息且无法挂起传入消息。 详细了解如何在使用的正文路径表达式**消息**选项卡上，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
 下图显示**消息**选项卡可以在其中指定如何从传入 SOAP 消息创建入站的 BizTalk 消息。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-send-adapters"></a>在 WCF 发送适配器不挂起入站 SOAP 封送处理中失败的消息  
 要求-响应 WCF 发送端口可以接收 WCF 消息作为响应消息。 当消息到达 WCF 发送适配器，WCF 适配器从传入 SOAP 消息创建 BizTalk 消息，然后将 BizTalk 消息传递到由终结点管理器管理的传输代理。 如果适配器无法创建 BizTalk 消息时读取 SOAP 信封和正文，则消息未挂起，因为适配器使用快速、 非缓存和只进读取器来访问 SOAP 消息。  
  
 应检查失败的消息在事件日志。 例如，可以使用 XPath 表达式上**消息**WCF 适配器传输属性对话框中，指定如何通过 WCF 适配器传入的 SOAP 消息创建入站的 BizTalk 消息正文中的选项卡。 当传入的 SOAP 消息的 XPath 表达式无效上提供了为**消息**选项卡上，则适配器无法创建 BizTalk 消息且无法挂起传入消息。 有关如何在使用 XPath 表达式的详细信息**消息**选项卡上，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
 下图显示**消息**Wcf-netnamedpipe 发送适配器作为示例的选项卡。  
  
 ![WCF 中的消息选项卡发送适配器](../core/media/54623ccf-49a9-4b6a-9487-da0d94bab64d.gif "54623ccf-49a9-4b6a-9487-da0d94bab64d")  
  
## <a name="messages-can-be-lost-when-using-onewaybindingelement-in-a-two-way-transport-with-custom-binding-in-non-transactional-wcf-receive-locations"></a>消息可能会丢失时 OneWayBindingElement 将双向传输中使用自定义绑定中非事务性 WCF 接收位置  
 在双向通信中，WCF 适配器将发送响应，直到在 MessageBox 数据库中保存的消息。 但是，使用**OneWayBindingElement**调度到 WCF 适配器收到的消息之前生成虚拟响应。 因此，如果配置自定义绑定与**OneWayBindingElement**在非事务性的双向传输通道堆栈中接收位置，因为 WCF 适配器处理接收到消息可能会丢失以单向形式的消息。  
  
## <a name="default-values-of-the-readerquotas-attributes-in-the-wcf-custom-and-wcf-customisolated-transport-properties-dialog-boxes-are-used-when-constructing-the-bindings"></a>默认构造绑定时，将使用 Wcf-custom 和 Wcf-customisolated 传输属性对话框中 ReaderQuotas 属性的值  
 在 Wcf-custom 和 Wcf-customisolated 传输属性对话框中， **ReaderQuotas**属性值显示为零。 但是，当构造绑定，使用以下值：  
  
|特性|Description|ReplTest1|  
|---------------|-----------------|-----------|  
|maxArrayLength|一个正整数，指定最大允许的数组长度。|16384|  
|maxBytesPerRead|每次读取返回一个正整数，指定的最大允许字节数。|4096|  
|maxDepth|一个正整数，指定每次读取的最大嵌套的节点深度。|32|  
|maxNameTableCharCount|一个正整数，指定表名称中允许的最大字符数。|16384|  
|maxStringContentLength|一个正整数，指定 XML 元素内容中允许的最大字符数。|8192|  
  
## <a name="the-wcf-receive-locations-may-be-disabled-if-you-change-the-wcf-adapter-type-and-keep-the-same-address"></a>WCF 接收位置可能会禁用，如果更改 WCF 适配器类型并保持相同的地址  
 如果更改适配器类型 — 例如，将 WCF 适配器类型从 Wcf-nettcp 更改为带 NetTcp 绑定的 WCF 自定义 — 并保持相同的地址，可能会由于缓存问题在终结点管理器中禁用接收位置。 若要解决此问题，可以执行以下任一操作：  
  
-   重新启动 BTSNTSvc 服务。  
  
-   将 URI 更改为不同的地址并保存它，然后更改回原始地址 URI 并再次保存。  
  
## <a name="the-wcf-action-set-in-the-orchestration-does-not-override-the-action-setting-in-the-static-send-port"></a>在业务流程中设置的 WCF 操作不重写静态发送端口中的操作设置  
 如果您设置**WCF。操作**业务流程中的上下文属性，您需要将**操作**字段留空，WCF 适配器传输属性对话框中的。 如果还在静态发送端口中指定的操作**WCF。操作**在静态发送端口设置的值将重写业务流程中设置的上下文属性。  
  
## <a name="propagating-a-fault-message-is-not-supported-in-the-transactional-send"></a>在事务性发送中不支持传播错误消息  
 **传播错误消息**要求响应发送端口中的选项可以将路由到某个订阅应用程序出站处理失败的消息。 但是，如果**启用事务**还在传输属性对话框中选中复选框和该事务被中止或无法使用错误响应到达适配器时，你将无法传播将错误消息为任何订阅应用程序  
  
## <a name="the-msmq-cluster-resource-group-needs-to-be-restarted-before-restarting-the-biztalk-host-cluster-resource-group-during-the-cluster-failover"></a>需要在群集故障转移期间重新启动 BizTalk 主机群集资源组之前重新启动 MSMQ 群集资源组  
 在故障转移群集方案中，当故障转移发生时，MSMQ 群集资源组需要重新启动 BizTalk 主机群集资源组之前，必须重新启动。 如果您不能执行此操作，与 MSMQ 接收位置可能被禁用。 若要解决此问题，可以使 BizTalk 主机群集资源组依赖于 MSMQ 群集资源组，以确保 BizTalk 主机群集资源组之前启动 MSMQ 群集资源组。 或者，可以重新启动 BizTalk 主机群集资源组，若要解决此问题。  
  
## <a name="you-receive-an-error-when-sending-messages-to-a-wcf-service-that-uses-wsfederationhttpbinding-in-the-endpoint"></a>将消息发送到终结点中使用 wsFederationHttpBinding 的 WCF 服务时收到错误  
 收到如下错误：  
  
```  
The adapter failed to transmit message going to send port "MySendPort" with URL "http://localohost/MywsFedHttp". It will be retransmitted after the retry interval specified for this Send Port. Details:"The channel is configured to use interactive initializer 'System.ServiceModel.Security.InfocardInteractiveChannelInitializer', but the channel was Opened without calling DisplayInitializationUI.  Call DisplayInitializationUI before calling Open or other methods on this channel.".  
```  
  
 这种行为是默认设置。 WCF 适配器不能将消息发送到正在使用的 WCF 服务**wsFederationHttpBinding**中其终结点。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-enable-you-to-select-message-types-or-port-types-from-the-wsdl"></a>BizTalk WCF 服务使用向导不会启用从 WSDL 选择消息类型或端口类型  
 BizTalk WCF 服务使用向导不允许导入 WCF 服务时从 WSDL 选择消息类型或端口类型。 若要解决此限制，可以使用下面的代码来获取架构，然后将所需的架构添加到 BizTalk 项目：  
  
```  
svcutil.exe /t:metadata http://service/metadataendpoint  
```  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-the-combination-of-one-way-and-request-response-operations"></a>BizTalk WCF 服务使用向导不允许组合的单向和请求-响应操作  
 BizTalk WCF 服务使用向导不允许您导入具有单向端口类型和请求-响应操作。 若要解决此问题，可以使用 Servicemodel 元数据实用工具生成端口类型。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-you-to-set-certificate-credentials-when-retrieving-the-wsdl"></a>BizTalk WCF 服务使用向导不允许您检索 WSDL 时设置证书凭据  
 BizTalk WCF 服务使用向导不允许您检索 WSDL 时设置证书凭据。 若要解决此问题，可以使用 ServiceModel Metadata Utility Tool 生成的 WSDL，并从你想要使用的证书凭据的 WCF 服务的 XSD 文件在 svcutil.exe.config 文件中，设置并将其导入 BizTalk WCF 服务通过选择使用向导**元数据文件 （WSDL 和 XSD）** 选项**元数据来源**页。  
  
## <a name="wcf-adapters-do-not-support-one-way-operations"></a>WCF 适配器不支持单向操作  
 你将收到错误消息如下所示通过 WCF 适配器 （Wcf-netmsmq 接收适配器） 除外使用 WCF 服务发布时如果**IsOneWay**属性设置为**true**客户端。 这是因为**System.ServiceModel.OperationContractAttribute.IsOneWay**通过 WCF 适配器 （Wcf-netmsmq 使用发布的服务接收适配器除外） 发布的 WCF 服务的属性设置为**false**甚至对于单向接收位置。  
  
```  
The channel received an unexpected input message while closing. Your Channel.Close() calls are not synchronized.  
```  
  
 使用指定的 WCF 服务时，将收到错误消息如下所示**IsOneWay**属性设置为**true**。 从发送的邮件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起且可恢复。  
  
```  
The request operation at net.tcp://localhost:8088/MyService/tcp did not receive a reply within timeout 00:01:00.  
```  
  
## <a name="a-memory-leak-may-occur-when-sending-messages-to-non-transactional-msmq-queues-using-wcf-netmsmq-binding"></a>将消息发送到使用 Wcf-netmsmq 绑定的非事务性 MSMQ 队列时，可能会发生内存泄漏  
 将消息发送到使用 Wcf-netmsmq 绑定的非事务性 MSMQ 队列时，BizTalk NT 服务中可能发生内存泄漏。 这可能会发生或将消息发送到非事务性 MSMQ 队列使用 netMsmqBinding 与 Wcf-custom 传输时将消息发送到非事务性 MSMQ 队列使用 Wcf-netmsmq 传输。  
  
 若要解决此问题，必须安装.NET Framework 3.0 修补程序知识库文章 936512 在中所述[ http://go.microsoft.com/fwlink/?LinkId=92962 ](http://go.microsoft.com/fwlink/?LinkId=92962)。 此修补程序不需要重新启动系统，但需要重新启动 BizTalk NT 服务的宿主的发送端口，使用 Wcf-netmsmq 绑定。  
  
## <a name="you-may-receive-exception-when-communicating-with-apache-web-servers-using-wcf-basichttp-adapter"></a>与 Apache Web 服务器使用 Wcf-basichttp 适配器进行通信时，可能会收到异常  
 使用时 Wcf-basichttp 适配器使用传输安全性与 Apache Web 服务器，通信可能会收到类似于以下各项的异常：  
  
```  
System.Net.WebException: The underlying connection was closed: An unexpected error occurred on a send.  
System.IO.IOException: Unable to write data to the transport connection: An established connection was aborted by the software in your host machine. System.Net.Sockets.SocketException: An established connection was aborted by the software in your host machine  
```  
  
 若要解决此问题，需要使用而不是 WCF BasicHttp 适配器的 WCF 自定义适配器与如下所示的 Apache Web 服务器进行通信：  
  
1.  创建发送端口并将传输类型设置为**WCF 自定义**。  
  
2.  在中**Wcf-custom 传输属性**对话框中，在**绑定**选项卡上，选择**customBinding**从**绑定类型**下拉列表。  
  
3.  下**CustomeBindingElement**，右键单击**httpTransport**，然后单击**删除扩展**。  
  
4.  右键单击**CustomeBindingElement**，然后单击**将扩展添加**。  
  
5.  在中**选择绑定元素扩展**对话框中，选择**httpTransport** ，然后单击**确定**。  
  
6.  单击**httpTransport**，然后在**配置**窗格中，设置的值**keepAliveEnabled**到**False**。  
  
7.  单击**textMessageEncoding**，然后在**配置**窗格中，设置的值**messageVersion**到`Soap11WSAddressing10`。  
  
8.  您可能需要根据需要配置其他属性。  
  
## <a name="biztalk-server-does-not-work-with-wcf-clients-that-using-clientviabehavior-for-multiple-hop-conversations"></a>BizTalk Server 并不适用于 WCF 客户端使用 ClientViaBehavior 的多跃点会话  
 WCF 客户端使用 ClientViaBehavior，当直接网络目标不是要调用的应用程序不需要知道最终目标时，启用多跃点对话的消息的预期的处理器时。 如果指定 ClientViaBehavior 并将收件人地址设置为远程服务其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将充当中介，您将收到错误消息如下所示：  
  
```  
The message with To 'net.tcp://localhost:5555/test.svc' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher. Check that the sender and receiver's EndpointAddresses agree  
```