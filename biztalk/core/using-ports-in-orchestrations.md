---
title: "使用在业务流程中的端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f48c1c070e3a3a3e7ebe7e86618a4fd9ebc90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-ports-in-orchestrations"></a>使用在业务流程中的端口
端口指定了业务流程与其他业务程序之间收发消息的方式。 每个端口都具有类型、方向和绑定，它们共同确定通信方向、通信模式、消息的源位置或目标位置、以及进行通信的方式。  
  
> [!NOTE]
>  端口与端口类型之间存在差别。 端口是端口类型的实例，多个不同的端口可以具有相同的端口类型。  
  
 根据这些因素的不同，端口可能与 URI（物理位置）、传输（FILE、HTTP、SOAP、SMTP 或 BizTalk 消息队列）、用于准备消息以进行发送的发送管道（例如，通过对消息进行组装、加密、压缩或执行其他某些操作）或用于准备接收的消息以进行处理的接收管道（例如，通过对消息进行拆装、解密或解压缩）相关联。  
  
 向业务流程添加端口的方式与向 Web 窗体或 Windows 窗体添加控件的方式相同。 还可以使用“业务流程视图”窗口来添加端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [通信模式](../core/communication-pattern.md)  
  
-   [通信方向](../core/communication-direction.md)  
  
-   [端口绑定](../core/port-bindings.md)  
  
-   [如何使用在业务流程中的端口](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [如何使用端口类型](../core/how-to-work-with-port-types.md)  
  
-   [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [使用在业务流程中的直接绑定端口](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a>另请参阅  
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)