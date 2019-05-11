---
title: 顺序保护 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- convoy sets
- correlation sets, sequential receive tasks
ms.assetid: f05ff42c-2236-42a3-8166-19700e0c3d97
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7a928650b04b7f57c29ba3abe2828990bf0a0cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393329"
---
# <a name="sequential-convoys"></a>顺序保护
顺序保护可以使多个单独的消息以实现所需的效果。 顺序保护是一组具有预定义的顺序的相关消息。 尽管消息无需是完全相同，但 BizTalk Server 必须按先后顺序来接收它们。  
  
 例如，假设在线零售公司接收新订单，从直接客户和经销商处在整个一天中的课程。 在下午 2:00 之前接收的所有订单必须都转到单个批处理中的仓库，必须保留的一系列订单的接收顺序。 这样，较早的订单具有优先级，以防从仓库中的存货中转出任何项。 通过组装具有批头部信息的单个文件中的天的所有订单生成此批顺序。 在下午 2:00，一天的所有订单都进入仓库进行处理。 2:00 之后接收的所有订单被都放入新批处理的第二天的处理。  
  
 前面的方案是需要顺序保护处理的传入消息的业务流程的示例。 业务要求指出，所有单个订单都接收到的特定一天下午 2:00 点之前应统一批处理。 这要求设置接收启动一个新的业务流程实例并初始化一个相关的第一个消息。 此时，接收的所有其他订单的消息类型路由到已在运行的业务流程实例。 若要实现此目的，您定位**侦听**形状 (包含**接收**形状和一个**延迟**形状) 内**循环**形状。 达到延迟后, 结束循环。 这允许将未知数量的同一个业务流程中的订单回执。  
  
## <a name="implementing-sequential-convoys"></a>实现顺序保护  
 您可以通过使用实现顺序保护"顺序关联接收"消息传送在 BizTalk Server 中的设计模式。 顺序关联接收是接收的关联到前一个接收。  
  
 将在其中接收的相关集由其他接收初始化的情况下发生保护处理。  
  
 对于接收到需要保护处理的、 具有以下限制：  
  
- 构成特殊接收必须初始化由前一个的顺序保护集的相关集接收。  
  
- 需要顺序保护处理的接收端口必须与初始化保护集的接收端口相同。 不支持跨端口保护。  
  
- 需要保护处理必须与初始化保护接收的消息类型相匹配的接收的消息类型设置，除非接收语句所操作按序的送达端口上。  
  
- 所有接收参与顺序保护中必须遵循所有相关集已初始化 （或后接） 由初始化接收，除非在按序的送达端口上操作。  
  
- 如果顺序保护初始化由激活接收语句，则激活接收不能具有筛选器表达式，除非在按序的送达端口上操作。  
  
- 如果顺序保护初始化由激活接收，则后续接收不能为嵌套的业务流程内。  
  
  有关顺序保护实现的示例，请参阅[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用保护方案](../core/working-with-convoy-scenarios.md)   
 [并行保护](../core/parallel-convoys.md)