---
title: 使用业务流程中的端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, receiving
- ports, configuring manually
- send ports, messages
- ports, creating
- ports, messages
- creating, ports
- send ports, sending
- ports, operations
- configuring, ports
- ports, deleting
- deleting, ports
- orchestrations, ports
- Port Configuration Wizard [Orchestration Designer]
- ports
- ports, about ports
- ports, configuring
ms.assetid: 968b2d1b-e233-4eb0-8254-9ec6b7642cdf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2204e5bb00cd6614c66f9325f043db131b402fbd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396578"
---
# <a name="using-ports-in-orchestrations"></a>使用业务流程中端口
端口指定如何将消息发送到您的业务流程和从其他业务流程接收消息。 每个端口都具有一个类型、 方向和绑定，它们共同确定通信、 通信模式、 位置或从其发送或接收消息和如何进行通信的方向。  
  
> [!NOTE]
>  没有端口和端口类型之间的区别。 端口是端口类型; 的实例多个不同的端口可能具有相同的端口类型。  
  
 根据这些因素，端口可能会有与它关联的 URI （物理位置）、 传输 （FILE、 HTTP、 SOAP、 SMTP 或 BizTalk 消息队列）、 发送管道来做好 （例如，按其进行组合、 加密、 压缩时，发送一条消息或对它执行一些其他操作） 和接收管道进行处理 （例如，通过拆装、 解密或对其进行解压缩） 准备接收的消息。  
  
 你将端口添加到业务流程相同的方式向 Web 窗体或 Windows 窗体添加控件。 此外可以通过使用业务流程视图窗口来添加端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [通信模式](../core/communication-pattern.md)  
  
-   [通信方向](../core/communication-direction.md)  
  
-   [端口绑定](../core/port-bindings.md)  
  
-   [如何使用业务流程中的端口](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [如何使用端口类型](../core/how-to-work-with-port-types.md)  
  
-   [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [在业务流程中使用直接绑定端口](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a>请参阅  
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)