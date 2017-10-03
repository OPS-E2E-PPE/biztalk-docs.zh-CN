---
title: "使用 WCF 服务和 WCF 时的注意事项发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- best practices, WCF services
- WCF services, best practices
- consuming, best practices
- WCF services, consuming
ms.assetid: 8bbcfd99-3495-458d-bd7a-6d170a29dde2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2bb1e512b8a13c3d91b87bbfc410c3d21f334fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-consuming-wcf-services-with-the-wcf-send-adapters"></a>通过 WCF 发送适配器使用 WCF 服务时的注意事项
本主题介绍了在通过 WCF 适配器使用 WCF 服务时的注意事项。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-solicit-messages"></a>在发送作为要求消息的非 XML 内容时，使用“模板 - 由模板指定的内容”选项  
 使用 WCF 适配器**正文--BizTalk 响应消息正文**（默认值） 选项不允许进行发送非 XML 消息，例如字符数据和位图图像。 你可以使用**模板--由模板指定内容**发送非 XML 消息的 WCF 适配器的选项。 有关如何使用模板的详细信息，请参阅[注意事项发布 WCF 服务时使用 WCF 接收适配器](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-ports-always-ignore-the-proxy-if-the-service-address-begins-with-httplocalhost"></a>如果服务地址以 http://localhost 开头，则 WCF-BasicHttp 和 WCF-WSHttp 发送端口将始终忽略代理  
 WCF BasicHttp 和 WCF WSHttp 发送端口总是忽略代理，如果服务地址以 http://localhost 是否配置了代理的上**代理**发送端口的选项卡或**代理**选项卡发送处理程序。 如果希望客户端通过代理与同一计算机上的服务进行对话，则应当使用主机名（而非 localhost）。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-adapters-suspend-the-messages-if-the-proxy-setting-is-not-correctly-configured"></a>如果未正确配置代理设置，则 WCF-BasicHttp 和 WCF-WSHttp 发送适配器将挂起消息  
 你可以指定的代理设置为 WCF BasicHttp 和 WCF WSHttp 发送适配器**代理**发送端口的选项卡或**代理**发送处理程序的选项卡。 如果未正确配置代理设置，则 WCF 适配器将挂起消息，而事件日志中会收到错误消息“There was no endpoint listening that could accept the message”。  
  
## <a name="setting-up-the-permissions-for-a-wcf-send-port-with-the-wcf-netmsmq-adapter"></a>为使用 WCF-NetMsmq 适配器的 WCF 发送端口设置权限  
 当采用 WCF-NetMsmq 适配器的 WCF 发送端口向 NetMsmqBinding 发布的 WCF 服务发送消息时，它会将消息发送到由服务的队列管理器管理的目标队列。 客户端上的队列管理器会将该消息发送到传输（或传出）队列。 传输队列是客户端队列管理器上的一个队列，用来存储要传输到目标队列的消息。  
  
 服务的队列管理器接受发送到它所拥有的目标队列的消息，并存储这些消息。 然后，服务会请求从目标队列读取消息，而队列管理器会将这些消息传送给该服务。 因此，用来承载发送端口的 BizTalk 主机实例的服务帐户应当具有写入传输队列的权限。  
  
## <a name="use-an-empty-xpath-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>使用空的 XPath 表达式接收其 SOAP Body 元素内容中带有字符数据的 SOAP 消息  
 要求-响应 WCF 发送端口可以接收 WCF 消息作为响应消息。 若要从传入的响应消息的 SOAP 内容中的字符数据与创建 BizTalk 消息**正文**元素，如以下示例所示，您应该保留**XPath 表达式**文本框中在空**消息**WCF 适配器传输属性对话框中的选项卡。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 如果你选择**信封**或**正文**选项，该适配器不创建 BizTalk 消息，从传入消息。 该消息不会挂起，因为在入站 SOAP 封送处理中失败的消息不会挂起。 有关如何使用 XPath 表达式上**消息**选项卡上，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
> [!NOTE]
>  可以通过配置 BTSNTSvc.exe.config 文件来使用 Windows SDK 中的 TraceViewer 工具 (SvcTraceViewer.exe)。 有关 Windows SDK 的详细信息，请参阅"什么是 Windows SDK 中的新增功能"网址[http://go.microsoft.com/fwlink/?LinkId=75219](http://go.microsoft.com/fwlink/?LinkId=75219)。 有关 TraceViewer 工具的详细信息，请参阅"TraceViewer 工具 (SvcTraceViewer.exe)"在[http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)。  
  
## <a name="biztalk-server-does-not-use-multi-part-message-types-and-root-elements-describing-custom-soap-headers"></a>BizTalk Server 不使用用来描述自定义 SOAP 标头的多部分消息类型和根元素  
 如果在元数据中定义了自定义 SOAP 标头，则根据该元数据运行 BizTalk WCF 服务使用向导时，该向导将在生成的架构中生成根元素以表示该自定义 SOAP 标头。 该向导还会在业务流程中为自定义 SOAP 标头创建多部分消息类型。 BizTalk Server。 然而，BizTalk Server 不使用多部分消息类型和根元素来处理自定义 SOAP 标头。  
  
 若要访问自定义 SOAP 标头，应使用**InboundHeaders**属性。 关于接收自定义 SOAP 标头的详细信息，请参阅[发布 WCF 服务使用的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)。 若要使用自定义 SOAP 标头，应使用**OutboundCustomHeaders**属性。 有关发送自定义 SOAP 标头的详细信息，请参阅[与使用 WCF 服务的 SOAP 标头](../core/soap-headers-with-consumed-wcf-services.md)。  
  
## <a name="create-separate-host-instances-for-send-ports-that-use-different-proxy-addresses-andor-proxy-credentials"></a>为使用不同代理地址和/或代理凭据的发送端口创建单独的主机实例  
 为了使 WCF 发送适配器获得最佳性能，建议您为使用不同代理地址和/或代理凭据的发送端口创建单独的主机实例。 这样可避免对代理设置的争用。  
  
## <a name="see-also"></a>另请参阅  
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)