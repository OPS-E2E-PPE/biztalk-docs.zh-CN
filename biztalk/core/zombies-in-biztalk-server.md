---
title: 在 BizTalk Server 中的僵停 |Microsoft Docs
description: BizTalk Server 中的僵停消息的常见原因
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
ms.openlocfilehash: cc41a06c15738c63812ddd9320c7ebbfe9c52d7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320803"
---
# <a name="zombies-in-biztalk-server"></a>在 BizTalk Server 中的僵停

## <a name="what-is-a-zombie"></a>什么是僵停？  
  
-   僵停消息是一条消息，已从 messagebox 路由到正在运行的业务流程，而只是"航班"业务流程结束的时间。 "正在"处理状态消息是已经路由到服务实例和这样是发往的服务实例的 messagebox 队列中的消息。 由于消息不再可供订阅业务流程实例，将消息挂起，并 ServiceInstance/State 值标记为"已挂起 （不可恢复）"。  
  
-   僵停服务实例是处于"正在处理"状态消息从 messagebox 路由到业务流程的实例时已完成的业务流程的实例。 业务流程实例已经结束，因为它不能使用"正在"处理状态消息因此挂起和 ServiceInstance/State 值标记为"已挂起 （不可恢复）"。  
  
## <a name="typical-causes"></a>典型的原因
僵停的匹配项通常属于以下类别之一：  
  
1. **终止控制消息**– 业务流程引擎允许使用控制消息来取消特定业务流程实例中所有当前正在运行的工作。 由于控制消息会立即停止正在运行的业务流程，则僵停实例是意料之中的。 工作流的许多相关设计倾向于使用此机制，以及其他一些设计。  
  
2. **并行侦听接收**-在此方案中的服务实例等待 n 个消息 1 和收到某些消息时它会执行一些任务，并终止。 如果并行分支上收到消息就像正在终止服务实例，将创建僵停。  
  
3. **使用非确定性终结点的顺序保护**– 在此方案中，主业务流程计划被设计为处理特定类型的以满足某种系统设计要求的所有消息。 这些设计要求可能包括按序的送达、 资源分配器和批处理。 对于此方案中，往往会是定义一段与一个分支具有 receive 和其他包含延迟形状后, 跟某种构造，这会设置一些变量，用以指示 while 循环构造围绕侦听的循环应停止。 这是不确定的因为可以触发延迟，但仍无法传递消息。 此类不确定性终结点是僵。  
  
   僵停服务实例挂起时，生成以下错误消息：  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 可以使用[BizTalk 终止符](https://www.microsoft.com/download/details.aspx?id=2846)来帮助删除僵停。  
  
## <a name="see-also"></a>请参阅  
 **删除挂起的服务实例** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]