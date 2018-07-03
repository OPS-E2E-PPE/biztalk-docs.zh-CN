---
title: 端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, warnings
- ports, bindings
- bindings, Web ports
- bindings, design time
- Web ports, port bindings
- bindings, ports
- bindings, direct
- bindings, warnings
- bindings, deployment
- bindings, dynamic
ms.assetid: b61c725a-0082-42d3-b88a-533583161734
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74e60db9b3a5994ff04f13fe2f242792cf2dcc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972534"
---
# <a name="port-bindings"></a>端口绑定
端口绑定是用于确定发送或接收消息的位置及方式的配置信息。 根据绑定类型的不同，端口绑定可能是指物理位置、管道或其他业务流程。  
  
 对于接收消息的端口，存在三种类型的端口绑定：  
  
- 立即指定  
  
- 以后指定  
  
- 直接  
  
  对于发送消息的端口，存在四种类型的端口绑定：  
  
- 立即指定  
  
- 以后指定  
  
- 直接  
  
- Dynamic  
  
## <a name="binding-at-deployment-time"></a>在部署时进行绑定  
 您可以将端口绑定至接收位置或发送端口。 如果您不具备所有指定的物理位置所需的信息，则可以选择**以后指定**端口绑定选项，在业务流程设计器中，并且您只需指定描述该端口的端口类型。 在已经部署应用程序后，您可以通过使用 BizTalk Server 管理控制台指定与位置有关的信息，或者可以通过编程方式配置位置信息。  
  
## <a name="binding-at-design-time"></a>在设计时进行绑定  
 可以选择**立即指定**端口绑定业务流程设计器中的选项以在设计时指定的传输和管道。 在为接收消息指定端口时，在下拉列表中只提供 HTTP、SOAP 和 FILE 传输。 在为发送消息指定端口时，在下拉列表中只提供 HTTP、FILE 和 SMTP 传输。 如果您事先知道所传输消息的源或目标，此选项将非常有用。  
  
## <a name="direct-binding"></a>直接绑定  
 直接绑定端口是您的业务流程中的逻辑单向或双向端口，并不显式绑定到任何物理端口。 直接绑定端口允许您在服务中具有不同的通信模式。 若要实现直接绑定，请选择**直接**端口在业务流程设计器在设计时的绑定选项。  
  
 直接绑定端口有三种类型：  
  
- MessageBox 直接绑定端口  
  
- 自相关直接绑定端口  
  
- 合作伙伴业务流程直接绑定端口  
  
  有关如何使用直接绑定端口的详细信息，请参阅[使用直接绑定端口在业务流程中](../core/working-with-direct-bound-ports-in-orchestrations.md)。  
  
> [!NOTE]
>  使用直接绑定时，您无法在一个请求响应端口和两个单向端口之间交换消息。  
  
> [!NOTE]
>  直接绑定不符合 Web Services 的业务流程工程语言 (BPEL4WS) 标准。 如果您需要符合 BPEL4WS，请使用其他类型的绑定。  
  
## <a name="dynamic-binding"></a>动态绑定  
 如果直到运行时才知道通信的目标，则可以对发送端口使用动态绑定。 位置，例如，可从传入消息上的属性确定，然后中指定**表达式**形状，如下面的代码中所示：  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 有关如何将值动态分配到端口的信息，请参阅[如何向动态端口分配值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)。  
  
## <a name="web-ports"></a>Web 端口  
 如果项目包含对 Web Services 的引用，则业务流程设计器将检测该引用并使相应的 Web 端口类型可用。 若要创建某一 Web 端口，只需将某一端口添加到您的业务流程，然后向它分配某一现有 Web 端口类型。 有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何使用端口类型](../core/how-to-work-with-port-types.md)   
 [通信模式](../core/communication-pattern.md)   
 [通信方向](../core/communication-direction.md)   
 [使用业务流程中端口](../core/using-ports-in-orchestrations.md)   
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [使用 Web 服务](../core/consuming-web-services.md)