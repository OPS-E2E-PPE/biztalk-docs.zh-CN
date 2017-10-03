---
title: "业务流程形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer]
- Loop shape [Orchestration Designer]
- Throw Exception shape [Orchestration Designer]
- Expression shape [Orchestration Designer]
- Decide shape [Orchestration Designer]
- Receive shape [Orchestration Designer]
- Compensate shape [Orchestration Designer]
- orchestrations, shapes
- Suspend shape [Orchestration Designer]
- Send shape [Orchestration Designer]
- Group shape [Orchestration Designer]
- Listen shape [Orchestration Designer]
- shapes, about shapes
- Construct Message shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer]
- Call Rules shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer]
- Transform shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Role Link shape [Orchestration Designer]
- Call Orchestration shape [Orchestration Designer]
- Port shape [Orchestration Designer]
- shapes
- Scope shape [Orchestration Designer]
- Terminate shape [Orchestration Designer]
- Orchestration Designer, shapes
- Insufficient Configuration Smart Tag [Orchestration Designer]
ms.assetid: a1d03baa-a267-499d-94fc-700b3e959458
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181656208b757c595feb9d19ee786fe91f1b78f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-shapes"></a>业务流程形状
业务流程设计器是用于创建业务流程的可视工具。 它提供了一些形状，可放在设计图面上作为底层操作的可视表示形式，这些形状可以帮助你有效地设计和实施业务流程。  
  
 **缺少配置操作**  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  当业务流程设计器检测到相关联的形状没有完全配置时，“不完全的配置操作”就会显示在业务流程设计器中。 如果业务流程中的形状没有完全配置，则关联的业务流程将不进行编译。  
  
 下表列出了可用形状，并提供了每个形状的功能的简要说明。  
  
|形状|形状名称|用途|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|**调用业务流程**|允许业务流程同步调用其他业务流程。|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|**调用规则**|允许你配置要在业务流程中执行的业务规则策略。|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|**补偿**|允许你调用代码以在发生错误时对业务流程已执行的操作进行撤消或补偿。|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|**构造消息**|允许构造消息。|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|**决定**|允许你在业务流程中有条件地进行分支。|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|**延迟**|允许你根据超时间隔在业务流程中设置延迟。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**表达式**|允许你将值赋给变量或进行 .NET 调用。|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|**分组**|允许你将操作分组为单个可折叠或展开的单元，以便于查看。|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|**侦听**|允许业务流程根据收到的消息或超时到期情况有条件地进行分支。|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|**循环**|允许业务流程在满足条件之前进行循环。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**消息赋值**|允许分配消息值。|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|**并行操作**|允许业务流程相互独立地执行两个或更多操作。|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|**端口**|定义传输消息的位置和方式。|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|**接收**|允许你在业务流程中接收消息。|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|**角色链接**|允许你创建一个端口集合，以与同一个逻辑合作伙伴进行通信（可能通过不同的传输或端点）。|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|**范围**|为事务和异常处理提供框架。|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|**发送**|允许你从业务流程发送消息。|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|**启动业务流程**|允许业务流程异步调用其他业务流程。|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|**挂起**|挂起业务流程的操作，以便在出现某个错误条件时可以进行干预。|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|**终止**|允许你在出现某个错误条件时立即结束业务流程的操作。|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|**引发异常**|允许你在错误事件中显式引发异常。|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|**转换**|允许你将字段从现有消息映射到新消息。|