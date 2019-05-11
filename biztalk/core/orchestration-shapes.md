---
title: 业务流程形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ad225737b806991a0633019dcf91b683f726bca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322632"
---
# <a name="orchestration-shapes"></a>业务流程形状
业务流程设计器是一种可视化工具用于创建业务流程。 它提供了多个形状，可以将它们放在设计图面上作为底层操作的可视表示形式，它们可帮助您可以有效地设计和实现业务流程。  
  
 **缺少配置的操作**  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  当业务流程设计器检测到相关联的形状没有完全配置时，将在业务流程设计器中显示完全的配置操作。 如果业务流程中的形状没有完全配置关联的业务流程将不编译。  
  
 下表列出了可用形状，以及每个形状的函数的简要说明。  
  
|形状|形状的名称|用途|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|**调用业务流程**|允许业务流程同步调用另一个业务流程。|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|**调用规则**|可以配置业务规则策略以在您的业务流程中执行。|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|**补偿**|可以调用撤消或补偿发生错误时由业务流程已执行的操作的代码。|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|**构造消息**|使您可以构造一条消息。|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|**决定**|可以在业务流程中有条件地分支。|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|**Delay**|可以根据超时间隔在业务流程中设置延迟。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**表达式**|可以将值分配给变量或进行.NET 调用。|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|**分组**|可以将操作分组为单个可折叠或展开的单元以便于查看。|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|**Listen**|允许业务流程到有条件地根据收到的消息的分支或超时期限过期。|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|**Loop**|允许业务流程以循环播放，直到满足某个条件。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**消息赋值**|可以分配消息值。|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|**并行操作**|允许业务流程执行各自独立的两个或多个操作。|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|**端口**|定义位置和方式传输消息。|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|**Receive**|可以在业务流程中收到一条消息。|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|**角色链接**|可以使用同一个逻辑合作伙伴，可能通过不同的传输或终结点创建的端口进行通信的集合。|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|**范围**|用于事务和异常处理提供了一个框架。|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|**Send**|可以从您的业务流程发送消息。|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|**启动业务流程**|允许业务流程以异步方式调用其他业务流程。|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|**挂起**|挂起业务流程以便能够出现某些错误条件时进行干预的操作。|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|**终止**|使您能够立即结束出现某些错误条件时业务流程的操作。|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|**引发异常**|可以显式引发异常发生错误时。|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|**转换**|可以将字段从现有消息映射到新消息。|