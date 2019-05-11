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
ms.openlocfilehash: c39dbaa807c68d5964dde973ab12c6fc91f7805c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394883"
---
# <a name="port-bindings"></a>端口绑定
端口绑定是确定在何处以及如何将发送或接收消息的配置信息。 根据其类型，端口绑定可能指物理位置、 管道或其他业务流程。  
  
 有三种类型的接收消息的端口的端口绑定：  
  
- 立即指定  
  
- 以后指定  
  
- 直接  
  
  有四种类型的发送消息的端口的端口绑定：  
  
- 立即指定  
  
- 以后指定  
  
- 直接  
  
- 动态  
  
## <a name="binding-at-deployment-time"></a>在部署时进行绑定  
 可以将端口绑定到接收位置或发送端口。 如果您不具备所有指定的物理位置所需的信息，则可以选择**以后指定**端口绑定选项，在业务流程设计器中，并且您只需指定描述该端口的端口类型。 部署应用程序后，你可以使用 BizTalk Server 管理控制台中，指定与位置有关的信息，或可以以编程方式配置位置信息。  
  
## <a name="binding-at-design-time"></a>在设计时绑定  
 可以选择**立即指定**端口绑定业务流程设计器中的选项以在设计时指定的传输和管道。 指定此端口来接收消息，仅 HTTP、 SOAP 和文件传输时，可从下拉列表。 指定用于将消息发送端口，仅 HTTP、 FILE 和 SMTP 传输时，可从下拉列表。 此选项非常有用，如果您事先知道源或目标的传输的消息。  
  
## <a name="direct-binding"></a>直接绑定  
 直接绑定的端口是您不显式绑定到任何物理端口的业务流程中的逻辑单向或双向端口。 直接绑定的端口允许您具有在服务中的不同通信模式。 若要实现直接绑定，请选择**直接**端口在业务流程设计器在设计时的绑定选项。  
  
 有三种类型的直接绑定端口：  
  
- MessageBox 直接绑定的端口  
  
- 自相关直接绑定的端口  
  
- 合作伙伴业务流程直接绑定的端口  
  
  有关如何使用直接绑定端口的详细信息，请参阅[使用直接绑定端口在业务流程中](../core/working-with-direct-bound-ports-in-orchestrations.md)。  
  
> [!NOTE]
>  在使用直接绑定时，您不能交换一个请求-响应端口和两个单向端口之间的消息。  
  
> [!NOTE]
>  直接绑定不符合的 Web 服务 (BPEL4WS) 业务流程工程语言标准。 如果需要符合 bpel4ws 规范，请使用其他类型的绑定。  
  
## <a name="dynamic-binding"></a>动态绑定  
 如果你将无法知道直到运行时通信的目标，可以为发送端口使用动态绑定。 位置，例如，可从传入消息上的属性确定，然后中指定**表达式**形状，如下面的代码中所示：  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 有关如何将值动态分配到端口的信息，请参阅[如何向动态端口分配值](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)。  
  
## <a name="web-ports"></a>Web 端口  
 如果你的项目包含对 Web 服务的引用，业务流程设计器会将其检测并会将提供相应的 Web 端口类型。 若要创建 Web 端口，只需将端口添加到您的业务流程中，并将其分配现有 Web 端口类型。 有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何使用端口类型](../core/how-to-work-with-port-types.md)   
 [通信模式](../core/communication-pattern.md)   
 [通信方向](../core/communication-direction.md)   
 [使用业务流程中端口](../core/using-ports-in-orchestrations.md)   
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [使用 Web 服务](../core/consuming-web-services.md)