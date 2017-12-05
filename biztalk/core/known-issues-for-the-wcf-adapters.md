---
title: "适用于这些 WCF 适配器的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 423c6021-5fb7-48c9-9319-11e7a18c775c
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c296dfb2ca1f05a2f403aa31a73b67934fb23a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-for-the-wcf-adapters"></a>WCF 适配器的已知的问题
本主题介绍 BizTalk Server 附带的 WCF 适配器的已知的问题。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-receive-adapters"></a>在入站 SOAP 封送处理中失败的消息不会在 WCF 接收适配器中挂起  
 在消息到达 WCF 接收适配器时，WCF 适配器将从传入的 SOAP 消息创建 BizTalk 消息，然后将 BizTalk 消息传递到由终结点管理器管理的传输代理。 如果创建 BizTalk 消息时该适配器无法读取 SOAP 信封和正文，则消息不会挂起，因为该适配器使用快速、非缓存的只进读取器来访问 SOAP 消息。  
  
 您应该检查事件日志中的失败消息。 例如，可以使用正文路径表达式上**消息**WCF 适配器传输属性对话框中的选项卡来指定如何通过 WCF 适配器传入 SOAP 消息创建入站的 BizTalk 消息正文。 当传入的 SOAP 消息的正文无效路径表达式提供上**消息**选项卡上，则适配器将失败，创建 BizTalk 消息和无法挂起传入的消息。 有关如何使用正文路径表达式上**消息**选项卡上，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
 下图显示**消息**在其，您可以指定如何创建从传入的 SOAP 消息的入站的 BizTalk 消息的选项卡。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-send-adapters"></a>在入站 SOAP 封送处理中失败的消息不会在 WCF 发送适配器中挂起  
 要求-响应 WCF 发送端口可以接收 WCF 消息作为响应消息。 当消息到达 WCF 发送适配器时，WCF 适配器将从传入的 SOAP 消息创建 BizTalk 消息，然后将 BizTalk 消息传递到由终结点管理器管理的传输代理。 如果创建 BizTalk 消息时该适配器无法读取 SOAP 信封和正文，则消息不会挂起，因为该适配器使用快速、非缓存的只进读取器来访问 SOAP 消息。  
  
 您应该检查事件日志中的失败消息。 例如，可以使用 XPath 表达式上**消息**WCF 适配器传输属性对话框中的选项卡来指定如何通过 WCF 适配器传入 SOAP 消息创建入站的 BizTalk 消息正文。 当将无效的 XPath 表达式为传入的 SOAP 消息提供上**消息**选项卡上，则适配器将失败，创建 BizTalk 消息和无法挂起传入的消息。 有关如何使用 XPath 表达式上**消息**选项卡上，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
 下图显示**消息**作为示例的 WCF NetNamedPipe 发送适配器的选项卡。  
  
 ![在 WCF 消息选项卡发送适配器](../core/media/54623ccf-49a9-4b6a-9487-da0d94bab64d.gif "54623ccf-49a9-4b6a-9487-da0d94bab64d")  
  
## <a name="messages-can-be-lost-when-using-onewaybindingelement-in-a-two-way-transport-with-custom-binding-in-non-transactional-wcf-receive-locations"></a>如果在非事务性 WCF 接收位置将双向传输中的 OneWayBindingElement 用于自定义绑定，则消息可能会丢失  
 在双向通信中，WCF 适配器将发送回响应，直到消息已保存在 MessageBox 数据库中。 但是，使用**OneWayBindingElement**调度到 WCF 适配器收到的消息之前立即生成 dummy 响应。 因此，如果配置自定义绑定用于**OneWayBindingElement**中非事务性的双向传输协议通道堆栈中接收位置、 消息可能会丢失，因为 WCF 适配器处理接收方式单向消息。  
  
## <a name="default-values-of-the-readerquotas-attributes-in-the-wcf-custom-and-wcf-customisolated-transport-properties-dialog-boxes-are-used-when-constructing-the-bindings"></a>构造绑定时，将使用“WCF-Custom 传输属性”和“WCF-CustomIsolated 传输属性”对话框中 ReaderQuotas 属性的默认值  
 中的 WCF 自定义和 WCF CustomIsolated 传输属性对话框框中， **ReaderQuotas**属性值将显示为零。 然而，构造绑定时，将使用以下值：  
  
|Attribute|Description|值|  
|---------------|-----------------|-----------|  
|maxArrayLength|正整数，指定允许的最大数组长度。|16384|  
|maxBytesPerRead|正整数，指定允许每次读取时返回的最大字节数。|4096|  
|maxDepth|正整数，指定每次读取的最大嵌套节点深度。|32|  
|maxNameTableCharCount|正整数，指定表名称中允许的最大字符数。|16384|  
|maxStringContentLength|正整数，指定 XML 元素内容中允许的最大字符数。|8192|  
  
## <a name="the-wcf-receive-locations-may-be-disabled-if-you-change-the-wcf-adapter-type-and-keep-the-same-address"></a>如果更改 WCF 适配器类型并保持相同的地址，则可能会禁用 WCF 接收位置  
 如果更改适配器类型 — 例如，将从 WCF NetTcp WCF 适配器类型更改为使用 NetTcp 绑定的 WCF 自定义，并保留相同的地址，接收位置可能由于缓存问题在终结点管理器中禁用。 若要解决此问题，您可以执行以下操作之一：  
  
-   重新启动 BTSNTSvc 服务。  
  
-   将 URI 更改为其他地址并保存，然后将 URI 改回原始地址并再次保存。  
  
## <a name="the-wcf-action-set-in-the-orchestration-does-not-override-the-action-setting-in-the-static-send-port"></a>业务流程中设置的 WCF 操作不会重写静态发送端口中的操作设置  
 如果你设置**WCF。操作**业务流程中的上下文属性，您需要离开**操作**字段保留为空白在 WCF 适配器传输属性对话框中。 如果你还在静态发送端口中，指定操作**WCF。操作**静态发送端口中设置的值时将替代在业务流程中设置的上下文属性。  
  
## <a name="propagating-a-fault-message-is-not-supported-in-the-transactional-send"></a>事务性发送中不支持传播错误消息  
 **传播错误消息**请求-响应发送端口中的选项允许你传送失败对订阅应用程序的出站处理的消息。 但是，如果**启用事务**同时传输的属性对话框中选中复选框和则中止此事务或不在错误响应到达时到适配器可用，你将无法传播错误消息转换为任何订阅的应用程序  
  
## <a name="the-msmq-cluster-resource-group-needs-to-be-restarted-before-restarting-the-biztalk-host-cluster-resource-group-during-the-cluster-failover"></a>在群集故障转移期间，需要先重新启动 MSMQ 群集资源组，然后再重新启动 BizTalk 主机群集资源组  
 在故障转移群集方案中，如果发生故障转移，则需要先重新启动 MSMQ 群集资源组，然后再重新启动 BizTalk 主机群集资源组。 如果没有这样做，则可能会禁用 MSMQ 接收位置。 若要解决此问题，您可以使 BizTalk 主机群集资源组依赖于 MSMQ 群集资源组，以确保 MSMQ 群集资源组在 BizTalk 主机群集资源组之前启动。 或者，您可以重新启动 BizTalk 主机群集资源组来解决此问题。  
  
## <a name="you-receive-an-error-when-sending-messages-to-a-wcf-service-that-uses-wsfederationhttpbinding-in-the-endpoint"></a>将消息发送到在终结点中使用 wsFederationHttpBinding 的 WCF 服务时收到错误  
 您会收到类似如下的错误：  
  
```  
The adapter failed to transmit message going to send port "MySendPort" with URL "http://localohost/MywsFedHttp". It will be retransmitted after the retry interval specified for this Send Port. Details:"The channel is configured to use interactive initializer 'System.ServiceModel.Security.InfocardInteractiveChannelInitializer', but the channel was Opened without calling DisplayInitializationUI.  Call DisplayInitializationUI before calling Open or other methods on this channel.".  
```  
  
 这种行为是默认设置。 WCF 适配器不能将消息发送到使用 WCF 服务**wsFederationHttpBinding**其终结点中。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-enable-you-to-select-message-types-or-port-types-from-the-wsdl"></a>使用 BizTalk WCF 服务使用向导不能从 WSDL 选择消息类型或端口类型  
 导入 WCF 服务时，使用 BizTalk WCF 服务使用向导不能从 WSDL 选择消息类型或端口类型。 若要消除此限制，您可以使用以下代码获取架构，然后将所需架构添加到 BizTalk 项目：  
  
```  
svcutil.exe /t:metadata http://service/metadataendpoint  
```  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-the-combination-of-one-way-and-request-response-operations"></a>BizTalk WCF 服务使用向导不允许单向操作和请求响应操作组合  
 BizTalk WCF 服务使用向导不允许导入具有单向操作和请求响应操作组合的端口类型。 若要解决此问题，您可以使用 ServiceModel 元数据实用工具生成端口类型。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-you-to-set-certificate-credentials-when-retrieving-the-wsdl"></a>BizTalk WCF 服务使用向导不允许在检索 WSDL 时设置证书凭据  
 BizTalk WCF 服务使用向导不允许在检索 WSDL 时设置证书凭据。 若要解决此问题，可以使用 ServiceModel 元数据实用工具生成的 WSDL，并从你想要使用的证书凭据的 WCF 服务的 XSD 文件在 svcutil.exe.config 文件中，设置和将其导入 BizTalk WCF 服务使用向导通过选择**元数据文件 （WSDL 和 XSD）**选项**元数据源**页。  
  
## <a name="wcf-adapters-do-not-support-one-way-operations"></a>WCF 适配器不支持单向操作  
 你将收到错误消息类似于以下使用 WCF 服务发布与 WCF 适配器 （除了对于 WCF NetMsmq 收到适配器） 时如果**IsOneWay**属性设置为**true**在客户端。 这是因为**System.ServiceModel.OperationContractAttribute.IsOneWay**发布具有 WCF 适配器 （用于与 WCF NetMsmq 发布服务接收适配器时除外） 的 WCF 服务的属性设置为**false**甚至为单向接收位置。  
  
```  
The channel received an unexpected input message while closing. Your Channel.Close() calls are not synchronized.  
```  
  
 使用与指定的 WCF 服务时，将收到错误消息类似于以下**IsOneWay**属性设置为**true**。 从发送的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起，并可恢复。  
  
```  
The request operation at net.tcp://localhost:8088/MyService/tcp did not receive a reply within timeout 00:01:00.  
```  
  
## <a name="a-memory-leak-may-occur-when-sending-messages-to-non-transactional-msmq-queues-using-wcf-netmsmq-binding"></a>在使用 WCF-NetMsmq 绑定将消息发送到非事务性 MSMQ 队列时，可能发生内存泄漏  
 在使用 WCF-NetMsmq 绑定将消息发送到非事务性 MSMQ 队列时，BizTalk NT 服务中可能发生内存泄漏。 在使用 WCF-NetMsmq 传输将消息发送到非事务性 MSMQ 队列，或者通过将 netMsmqBinding 与 WCF-Custom 传输一起使用，将消息发送到非事务性 MSMQ 队列时，可能发生这种问题。  
  
 若要解决此问题，必须安装.NET Framework 3.0 修补程序 KB 文中所述 936512 在[http://go.microsoft.com/fwlink/?LinkId=92962](http://go.microsoft.com/fwlink/?LinkId=92962)。 该修补程序不要求重新启动系统，但需要重新启动承载使用 WCF-NetMsmq 绑定的发送端口的 BizTalk NT 服务。  
  
## <a name="you-may-receive-exception-when-communicating-with-apache-web-servers-using-wcf-basichttp-adapter"></a>如果使用 WCF-BasicHttp 适配器与 Apache Web 服务器进行通信，则可能会发生异常  
 如果将 WCF-BasicHttp 适配器与传输安全性一起使用来与 Apache Web 服务器进行通信，则可能会发生类似如下的异常：  
  
```  
System.Net.WebException: The underlying connection was closed: An unexpected error occurred on a send.  
System.IO.IOException: Unable to write data to the transport connection: An established connection was aborted by the software in your host machine. System.Net.Sockets.SocketException: An established connection was aborted by the software in your host machine  
```  
  
 若要解决此问题，您需要使用 WCF-Custom 适配器（而非 WCF-BasicHttp 适配器）与 Apache Web 服务器进行通信，如下所示：  
  
1.  创建发送端口和设置的传输类型为**WCF 自定义**。  
  
2.  在**WCF 自定义传输属性**对话框中，在**绑定**选项卡上，选择**customBinding**从**绑定类型**下拉列表。  
  
3.  下**CustomeBindingElement**，右键单击**httpTransport**，然后单击**删除扩展**。  
  
4.  右键单击**CustomeBindingElement**，然后单击**将扩展添加**。  
  
5.  在**选择绑定元素扩展**对话框中，选择**httpTransport** ，然后单击**确定**。  
  
6.  单击**httpTransport**，然后在**配置**窗格中，设置的值**keepAliveEnabled**到**False**。  
  
7.  单击**textMessageEncoding**，然后在**配置**窗格中，设置的值**messageVersion**到`Soap11WSAddressing10`。  
  
8.  可以根据需要配置其他属性。  
  
## <a name="biztalk-server-does-not-work-with-wcf-clients-that-using-clientviabehavior-for-multiple-hop-conversations"></a>BizTalk Server 无法将使用 ClientViaBehavior 的 WCF 客户端用于多跃点会话  
 当直接网络目标不是消息的预期处理器，且调用应用程序无需了解最终目标时，WCF 客户端会使用 ClientViaBehavior 启用多跃点会话。 如果指定 ClientViaBehavior 并将“收件人”地址设置为远程服务（其中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将充当桥梁），您将收到类似如下内容的错误消息：  
  
```  
The message with To 'net.tcp://localhost:5555/test.svc' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher. Check that the sender and receiver's EndpointAddresses agree  
```