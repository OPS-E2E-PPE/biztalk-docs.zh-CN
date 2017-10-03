---
title: "顺序保护 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- convoy sets
- correlation sets, sequential receive tasks
ms.assetid: f05ff42c-2236-42a3-8166-19700e0c3d97
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329d0f56d9f092cd146a900c42ed48d5206a6393
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sequential-convoys"></a>顺序保护
顺序保护可以使多个单独的消息结合在一起，以取得所需的效果。 顺序保护是一组具有预定义顺序的相关消息。 虽然这些消息不必完全相同，但 BizTalk Server 必须按顺序接收它们。  
  
 例如，假设一家在线零售公司一整天都从直接客户和经销商处接收新订单。 在下午 2:00 之前接收的所有订单都必须作为单独一批进入仓库，并且订单的接收顺序必须保留。 这就使得在仓库中的任何商品脱销的情况下，较早的订单具有优先权。 通过将一天的所有订单整理到一个具有批头部信息的文件中，您可以生成此批顺序。 在下午 2:00，一天的所有订单都进入仓库进行处理。 在下午 2:00 以后接收的所有订单将放到一个新批中，以备第二天进行处理。  
  
 上述方案举例说明了需要对传入消息进行顺序保护处理的业务流程。 业务要求指出，在特定一天的下午 2:00 之前接收的所有单个订单都应共同组成一批。 这就需要接收的第一条消息启动新的业务流程实例并初始化相关集。 同时，接收的该消息类型的所有其他订单都路由到已经运行的业务流程实例。 若要实现此目的，您可以定位**侦听**形状 (包含**接收**形状和**延迟**形状) 内**循环**形状。 达到延迟后，循环将结束。 这就允许在同一业务流程中接收无数个订单。  
  
## <a name="implementing-sequential-convoys"></a>实现顺序保护  
 您可以使用 BizTalk Server 中的“顺序关联接收”消息传送设计模式来实现顺序保护。 顺序关联接收是与以前的接收相关联的接收。  
  
 某个接收的相关集由其他接收初始化时将发生保护处理。  
  
 对于需要保护处理的接收，有下列限制：  
  
-   构成特殊接收的顺序保护集的相关集必须由前一个接收初始化。  
  
-   需要顺序保护处理的接收的端口必须与初始化保护集的接收的端口相同。 不支持跨端口保护。  
  
-   需要保护处理的接收的消息类型必须与初始化保护集的接收的消息类型匹配，除非接收语句所操作的是按序送达端口。  
  
-   参与顺序保护的所有接收都必须沿用由初始化接收所初始化（或跟随）的所有相关集，除非在按序送达端口上操作。  
  
-   如果顺序保护由激活接收语句初始化，则激活接收不能具有筛选器表达式，除非在按序送达端口上操作。  
  
-   如果顺序保护由激活接收初始化，则后续接收不能位于嵌套的业务流程中。  
  
 有关顺序保护实现的示例，请参阅[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用队列方案](../core/working-with-convoy-scenarios.md)   
 [并行的保护](../core/parallel-convoys.md)