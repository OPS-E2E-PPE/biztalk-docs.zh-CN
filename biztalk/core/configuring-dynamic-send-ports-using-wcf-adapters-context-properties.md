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
ms.openlocfilehash: 956c66ae42d2c0239a8ca6f8b84dd8e11685ed08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356100"
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a>配置动态发送端口使用 WCF 适配器上下文属性
可以配置用于 WCF 适配器的动态发送端口。 URI、 操作和绑定可能会确定传入消息上的属性，然后中指定**表达式**形状，如以下 Wcf-nettcp 适配器中所示：  
  
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
  
 指定 WCF 上下文属性时的注意事项如下所示：  
  
- 有可以映射到多个适配器的地址。 例如，通过 HTTP 适配器和 Wcf-basichttp、 Wcf-wshttp 或 Wcf-custom 适配器，则可以处理以 http:// 或 https:// 开头的地址。 有关其他示例，在上面的示例代码中，这两个地址开始使用 net.tcp://，但由于第二个示例代码使用自定义绑定，应使用 Wcf-custom 适配器处理该地址。 因此，若要标识正确的适配器，您必须配置可选**Microsoft.XLANGs.BaseTypes.TransportType**字段中**表达式**形状与你想要使用的适配器。  
  
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
  
    可以扩展上面的列表。 例如，可以如 FtpBinding 向其添加您自己的绑定。  
  
- **WCF。BindingConfiguration**指定绑定类型的绑定配置。 需要在计算机配置文件中注册任何绑定。 它还将在与 WCF 配置文件中的绑定配置中使用相同的格式中使用 XML 配置。  
  
- 您可能需要指定其他 WCF 属性。 您可以键入**WCF**在表达式编辑器和 IntelliSense 功能将列出所有可用的上下文属性。 有关 WCF 上下文属性的详细信息，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。  
  
  前面的示例演示如何配置**WCF。操作**通过一个操作。 为多个操作映射的情况，WCF 适配器不支持使用多个操作映射与动态发送端口。 您可以在中设置实际操作**WCF。操作**为在上面显示的上下文属性。  
  
## <a name="see-also"></a>请参阅  
 [指定 SOAP 操作，为 WCF 发送适配器](../core/specifying-soap-actions-for-wcf-send-adapters.md)   
 [如何使用表达式向动态端口赋值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)   
 [端口绑定](../core/port-bindings.md)