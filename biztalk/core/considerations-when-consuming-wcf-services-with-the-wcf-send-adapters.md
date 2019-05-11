---
title: 发送适配器使用 WCF 与 WCF 服务时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- best practices, WCF services
- WCF services, best practices
- consuming, best practices
- WCF services, consuming
ms.assetid: 8bbcfd99-3495-458d-bd7a-6d170a29dde2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab74cc71cf083ac8f6dd33a75cd7fe3be3fb00d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390384"
---
# <a name="considerations-when-consuming-wcf-services-with-the-wcf-send-adapters"></a>发送适配器使用 WCF 与 WCF 服务时的注意事项
本主题提供使用 WCF 适配器使用 WCF 服务时应考虑的信息。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-solicit-messages"></a>在发送作为要求消息的非 XML 内容时使用"模板-内容由模板指定"选项  
 使用 WCF 适配器**正文--BizTalk 响应消息正文**（默认值） 选项不允许发送字符数据和位图图像等非 XML 消息。 可以使用**模板-由模板指定的内容**WCF 适配器能够发送非 XML 消息的选项。 有关如何使用模板的详细信息，请参阅[注意事项时发布 WCF 服务与 WCF 接收适配器](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-ports-always-ignore-the-proxy-if-the-service-address-begins-with-httplocalhost"></a>Wcf-basichttp: Wcf-basichttp 和 Wcf-wshttp 发送端口始终忽略代理，如果服务地址以开始 http://localhost  
 Wcf-basichttp: Wcf-basichttp 和 Wcf-wshttp 发送端口始终忽略代理，如果服务地址以开头 http://localhost是否配置了代理的上**代理**发送端口的选项卡或**代理**选项卡发送处理程序。 如果希望客户端通过代理服务器时在同一台计算机上的服务通信，应使用主机名称 （而非 localhost）。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-adapters-suspend-the-messages-if-the-proxy-setting-is-not-correctly-configured"></a>Wcf-basichttp: Wcf-basichttp 和 Wcf-wshttp 发送适配器将挂起消息，如果未正确配置代理设置  
 可以指定的代理设置为 Wcf-basichttp 和 Wcf-wshttp 发送适配器**代理**发送端口的选项卡或**代理**的发送处理程序的选项卡。 如果未正确配置此代理设置，WCF 适配器将挂起消息，并在事件日志中收到的"There was no endpoint listening that 可以接受消息"错误消息。  
  
## <a name="setting-up-the-permissions-for-a-wcf-send-port-with-the-wcf-netmsmq-adapter"></a>设置权限的 wcf 发送端口使用 Wcf-netmsmq 适配器  
 当带有 Wcf-netmsmq 适配器的 WCF 发送端口向 netmsmqbinding 发布的 WCF 服务发送消息时，它解决了到目标队列，这是由服务的队列管理器管理的队列消息。 在客户端上的队列管理器将消息发送至传输 （或传出） 队列。 传输队列是客户端队列管理器中，用于存储传输到目标队列的消息队列。  
  
 服务的队列管理器接受定址到目标队列拥有并存储消息的消息。 然后，服务可进行请求以便读取来自目标队列，队列管理器将消息传递给该服务。 出于此原因，承载发送端口的 BizTalk 主机实例的服务帐户应具有在传输队列的写权限。  
  
## <a name="use-an-empty-xpath-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>使用 XPath 空表达式接收字符数据的 SOAP 消息的 SOAP Body 元素内容中  
 要求-响应 WCF 发送端口可以接收 WCF 消息作为响应消息。 若要从传入响应消息的 soap 内容中有字符数据创建 BizTalk 消息**正文**元素，如以下示例所示，您应该保留**XPath 表达式**文本框在空**消息**WCF 适配器传输属性对话框中的选项卡。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 如果选择**信封**或**正文**选项，该适配器不会创建 BizTalk 消息，从传入消息。 消息未挂起，因为在入站 SOAP 封送处理中失败的消息不会挂起。 有关如何在使用 XPath 表达式的详细信息**消息**选项卡上，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
> [!NOTE]
>  通过配置 btsntsvc.exe.config 文件来，可以在 Windows SDK 中使用的 TraceViewer 工具 (SvcTraceViewer.exe)。 有关 Windows SDK 的详细信息，请参阅"什么是 Windows SDK 中的新增功能"处[ http://go.microsoft.com/fwlink/?LinkId=75219 ](http://go.microsoft.com/fwlink/?LinkId=75219)。 有关 TraceViewer 工具的详细信息，请参阅"TraceViewer 工具 (SvcTraceViewer.exe)"在[ http://go.microsoft.com/fwlink/?LinkId=75218 ](http://go.microsoft.com/fwlink/?LinkId=75218)。  
  
## <a name="biztalk-server-does-not-use-multi-part-message-types-and-root-elements-describing-custom-soap-headers"></a>BizTalk Server 不使用多部分消息类型和描述自定义 SOAP 标头的根元素  
 如果您运行 BizTalk WCF 服务针对元数据在其中定义了自定义 SOAP 标头，该向导使用向导将生成在生成的架构来表示自定义 SOAP 标头根元素。 该向导还为自定义 SOAP 标头的业务流程中创建多部分消息类型。 BizTalk Server。 但是，BizTalk Server 不使用多部分消息类型和根元素处理自定义 SOAP 标头。  
  
 若要访问自定义 SOAP 标头，应使用**InboundHeaders**属性。 有关接收自定义 SOAP 标头的详细信息，请参阅[SOAP 标头发布 WCF 服务与](../core/soap-headers-with-published-wcf-services.md)。 若要使用自定义 SOAP 标头，应使用**OutboundCustomHeaders**属性。 有关发送自定义 SOAP 标头的详细信息，请参阅[SOAP 标头与使用 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)。  
  
## <a name="create-separate-host-instances-for-send-ports-that-use-different-proxy-addresses-andor-proxy-credentials"></a>创建单独的主机实例使用不同代理地址和/或代理凭据的发送端口  
 若要获得最佳性能为 WCF 发送适配器，我们建议创建单独的主机实例使用不同代理地址和/或代理凭据的发送端口。 这样可避免对代理设置的争用。  
  
## <a name="see-also"></a>请参阅  
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)