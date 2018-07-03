---
title: 配置动态发送端口使用 WCF 适配器上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, send ports
- send ports, WCF services
- dynamic send ports, WCF services
- send ports, dynamic
ms.assetid: 2a7e2cd2-fa2d-45da-bb8e-eb8bab21bfa3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca781dc1d101e3eef0976229b3d1b986c2f4498d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995270"
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a>配置动态发送端口使用 WCF 适配器上下文属性
可以为 WCF 适配器配置动态发送端口。 URI、 操作和绑定可能会确定传入消息上的属性，然后中指定**表达式**形状，如以下 Wcf-nettcp 适配器中所示：  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.SecurityMode)="Transport";  
MessageOut(WCF.TransportClientCredentialType)="Windows";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/netTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-NetTcp";  
```  
  
 下面的代码演示如何指定 WCF 上下文属性中的示例**表达式**WCF 自定义适配器的形状：  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.BindingType)="customBinding";  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.BindingConfiguration)=@"<binding name=""customBinding""><binaryMessageEncoding /><tcpTransport /></binding>";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/customNetTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
 指定 WCF 上下文属性的注意事项如下：  
  
- 有些地址可以映射到多个适配器。 例如，以 http:// 或 https:// 开头的地址可以由 HTTP 适配器处理，也可以由 WCF-BasicHttp、WCF-WsHttp 或 WCF-Custom 适配器处理。 再例如，在上述两个示例代码中，它们都使用了以 net.tcp:// 开头的地址，不过由于第二个示例代码使用了自定义绑定，因而应使用 WCF-Custom 适配器处理该地址。 因此，若要标识正确的适配器，您必须配置可选**Microsoft.XLANGs.BaseTypes.TransportType**字段中**表达式**形状与你想要使用的适配器。  
  
  > [!NOTE]
  >  如果地址以 http:// 或 https:// 开头，并且如果未指定**Microsoft.XLANGs.BaseTypes.TransportType**字段中，默认情况下，BizTalk 引擎将使用 HTTP 适配器。  
  
- **WCF。BindingType**按名称标识的绑定。 该参数可以是下列值之一：  
  
  - basicHttpBinding  
  
  - customBinding  
  
  - netMsmqBinding  
  
  - netNamedPipeBinding  
  
  - netTcpBinding  
  
  - wsFederationHttpBinding  
  
  - wsHttpBinding  
  
    上述列表可以扩展。 例如，您可以向其中自行添加绑定，如 FtpBinding。  
  
- **WCF。BindingConfiguration**指定绑定类型的绑定配置。 它会获取在计算机配置文件中注册的所有绑定。 它还会以 WCF 配置文件的绑定配置中所用的相同格式获取 XML 配置。  
  
- 您可能需要指定其他 WCF 属性。 您可以键入**WCF**在表达式编辑器和 IntelliSense 功能将列出所有可用的上下文属性。 有关 WCF 上下文属性的详细信息，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。  
  
  前面的示例演示如何配置**WCF。操作**通过一个操作。 对于具有多个操作映射的情况，WCF 适配器不支持将多个操作映射与动态发送端口一起使用。 您可以在中设置实际操作**WCF。操作**为在上面显示的上下文属性。  
  
## <a name="see-also"></a>请参阅  
 [指定 SOAP 操作，为 WCF 发送适配器](../core/specifying-soap-actions-for-wcf-send-adapters.md)   
 [如何使用表达式向动态端口赋值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)   
 [端口绑定](../core/port-bindings.md)