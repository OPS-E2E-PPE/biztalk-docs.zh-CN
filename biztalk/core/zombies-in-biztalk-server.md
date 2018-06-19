---
title: BizTalk Server 中的僵尸 |Microsoft 文档
description: 僵停在 BizTalk Server 中的消息的常见原因
ms.custom: ''
ms.date: 03/23/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c684891-e984-442f-b5fd-de5f7cf32b44
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9764522d2ff5265b6f28f2f125cb33b2982a7605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290541"
---
# <a name="zombies-in-biztalk-server"></a>BizTalk Server 中的僵停

## <a name="what-is-a-zombie"></a>什么是僵停？  
  
-   僵停消息是指这样的消息：从 messagebox 路由到一个正在运行的业务流程，但在该业务流程结束时仍处于“正在处理”状态。 “正在处理”的消息是已经路由到服务实例的消息，因此它位于以该服务实例为目标的 messagebox 队列中。 由于该消息不能再被订阅业务流程实例所处理，因此该消息将被挂起，其 ServiceInstance/State 值标记为“已挂起（不可恢复）”。  
  
-   僵停服务实例是指这样一种业务流程实例：消息已从 messagebox 路由到该业务流程实例，而该业务流程实例完成时消息处于“正在处理”状态。 由于该业务流程实例已结束，不能再处理“正在处理”中的消息，因此该业务流程将被挂起，其 ServiceInstance/State 值标记为“已挂起（不可恢复）”。  
  
## <a name="typical-causes"></a>典型的原因
僵停通常发生在以下几种情况下：  
  
1.  **终止控件消息**– 业务流程引擎允许使用的控制消息取消的特定业务流程实例中的所有当前正在运行的工作。 由于控制消息会立即停止正在运行的业务流程，因此出现僵停实例是意料之中的。 一些与工作流相关的设计和其他一些设计倾向于使用此机制。  
  
2.  **并行侦听接收**– 在此方案中的服务实例将等待 1 n 消息并在收到某些消息时，它还执行一些操作并终止。 如果服务实例终止时并行分支上收到消息，则会产生僵停。  
  
3.  **与非确定性的终结点的顺序保护**– 在此方案中，主业务流程计划旨在处理的特定类型的所有消息，以便满足某种类型的系统的设计要求。 这些设计要求可能包括按序送达、资源分配器和批处理。 对于这种方案，通常定义一个围绕侦听的 while 循环，其中一个分支包含接收形状，而另一个分支包含延迟形状，后跟某种构造，构造中设置一些变量，用以指明该 while 循环的结束条件。 此机制具有不确定性，因为可以触发延迟，但仍然能够传送消息。 类似这样的不确定性终结点都有可能造成僵停。  
  
 当挂起僵停服务实例时，将生成以下的错误消息：  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 你可以使用[BizTalk 终止符](https://www.microsoft.com/download/details.aspx?id=2846)有助于删除僵尸。  
  
## <a name="see-also"></a>另请参阅  
 **删除挂起的服务实例**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]