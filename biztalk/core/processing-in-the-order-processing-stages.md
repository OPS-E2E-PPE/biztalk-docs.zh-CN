---
title: 在订单处理阶段中处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cf62be2b8a4e11ce7a6acc5b9807207aea89d00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299858"
---
# <a name="processing-in-the-order-processing-stages"></a>在订单处理阶段中处理
该业务流程管理解决方案包含两个阶段**CableOrder1**并**CableOrder2**执行订单处理操作的业务流程。 有关如何订单流程已分为若干阶段的详细信息，请参阅[处理阶段数](../core/number-of-processing-stages.md)。  
  
 这两个处理阶段开始时收到订单消息和状态消息作为答复**OrderManager**业务流程在开始之后。 同样，这两个将发送一条消息回**OrderManager**以指示是否在阶段已完成或终止，出现错误。 有关详细信息之间的连接**OrderManager**业务流程和处理阶段中，请参阅[反转直接合作伙伴绑定](../core/inverse-direct-partner-binding.md)。  
  
 这两种处理阶段使用自相关，动态端口，以将信息发送回**OrderManger**。 通过动态端口，业务流程从消息将发送端口将复制的端口地址。  
  
 所有处理阶段接收的订单消息都是在创建的标准化、 规范化订单消息**OrderBroker**。  
  
> [!NOTE]
>  由于的长度**CableOrder1**并**CableOrder2**业务流程，你可能想要阅读此部分在 Microsoft Visual Studio 中打开该业务流程。  
  
## <a name="the-cableorder1-orchestration"></a>CableOrder1 业务流程  
 **CableOrder1**业务流程将启动时收到订单消息。 它然后回复地址将从消息复制到阶段完成端口。 接下来，它构造一个确认消息并将其作为响应发送**BeginStagePort**端口，，然后将路由信息保存在本地变量。  
  
 接下来，业务流程从 SSO 获取配置信息。 有关该解决方案如何使用 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。  
  
 该业务流程将创建的实例**OrderHandler**对象与后端进程进行通信、 检查消息的有效性、 分析消息、 确定服务类型和要采取的操作。 具体取决于要执行的操作，它将调用一个订单操作业务流程**激活**，**更改**，或**取消**，并将传递**OrderHandler**向业务流程的对象。  
  
 **CableOrder1**业务流程将检查中断，将消息发送到的功能组和等待听到备份。 如果业务流程获取一条消息返回功能组，它将继续处理。 否则，如果存在中断，业务流程将引发中断异常。  
  
 在业务流程完成构建一条完成消息并将其通过发送**StageCompletion**端口。  
  
## <a name="the-cableorder2-orchestration"></a>CableOrder2 业务流程  
 CableOrder2 业务流程执行相同 CableOrder1 业务流程的路由的信息，SSO 配置信息，以启动步骤并创建的实例**OrderHandler**对象。  
  
 业务流程接着检查中断，并传递**OrderHandler**调用中的对象**完成**业务流程。 接下来，该业务流程创建一个订单状态消息，更新订单历史记录，并发送完成消息通过**StageCompletion**端口。  
  
## <a name="see-also"></a>请参阅  
 [版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md)   
 [在业务流程管理解决方案中处理](../core/processing-in-the-business-process-management-solution.md)