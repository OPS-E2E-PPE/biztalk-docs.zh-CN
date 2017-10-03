---
title: "中的顺序处理阶段处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a8eae6b814af36d0ea07065726ca66518984703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-order-processing-stages"></a>在订单处理阶段中处理
业务流程管理解决方案包括两个阶段， **CableOrder1**和**CableOrder2**业务流程，执行处理操作的顺序。 有关如何订单过程已划分为阶段的详细信息，请参阅[处理阶段数](../core/number-of-processing-stages.md)。  
  
 这两个处理阶段开始时它们接收订单消息，同时使用到的状态消息回复**OrderManager**业务流程后它们已启动。 同样，一条消息回到这两个发送**OrderManager**指示阶段是否完成或终止，出现错误。 有关详细信息之间的连接**OrderManager**业务流程和处理阶段中，请参阅[反直接合作伙伴绑定](../core/inverse-direct-partner-binding.md)。  
  
 这两种处理阶段使用自助关联，动态端口，以将信息发送回**OrderManger**。 通过动态端口，业务流程可将端口地址从消息复制到发送端口。  
  
 所有处理阶段接收的顺序消息都是在中创建的规范化的规范顺序消息**OrderBroker**。  
  
> [!NOTE]
>  由于**CableOrder1**和**CableOrder2**业务流程，你可能想要阅读此部分与 Microsoft Visual Studio 中打开的业务流程。  
  
## <a name="the-cableorder1-orchestration"></a>CableOrder1 业务流程  
 **CableOrder1**时接收顺序消息时，业务流程将启动。 然后将消息中的答复地址复制到阶段完成端口。 接下来，构造一条确认消息，并将其发送的响应**BeginStagePort**端口，，然后将路由信息保存在本地变量。  
  
 此业务流程接着获取 SSO 的配置信息。 有关如何解决方案使用 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。  
  
 然后，业务流程创建的实例**OrderHandler**对象，以便与后端进程通信、 检查消息的有效性，将分析该消息，确定服务类型中，并要采取的操作。 具体取决于要执行的操作，它调用的顺序操作业务流程中的一个**激活**，**更改**，或**取消**并将传递**OrderHandler**业务流程的对象。  
  
 **CableOrder1**业务流程，然后将为中断，发送到设备组并等待的消息以了解签。 如果业务流程收到功能组发回的消息，则会继续进行处理。 否则，业务流程将在出现中断时引发中断异常。  
  
 业务流程完成方法是构造一条完成消息并将其通过发送**StageCompletion**端口。  
  
## <a name="the-cableorder2-orchestration"></a>CableOrder2 业务流程  
 CableOrder2 业务流程执行相同 CableOrder1 业务流程的路由的信息，SSO 配置信息，以启动步骤并创建的实例**OrderHandler**对象。  
  
 业务流程然后检查中断和传递**OrderHandler**对的调用中的对象**完成**业务流程。 接下来，业务流程创建订单状态消息、 更新订单历史记录，并将发送一条完成消息通过**StageCompletion**端口。  
  
## <a name="see-also"></a>另请参阅  
 [版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md)   
 [在业务流程管理解决方案中进行处理](../core/processing-in-the-business-process-management-solution.md)