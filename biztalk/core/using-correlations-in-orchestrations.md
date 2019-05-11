---
title: 业务流程中使用相关性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b16c54f4c49a1a81ea412c5b980ba23e60e8290
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401620"
---
# <a name="using-correlations-in-orchestrations"></a>业务流程中使用的相关性
相关是将传入消息与业务流程的相应实例相匹配的过程。 例如，业务流程发出一条消息并接收响应或响应回同一业务流程。 有三种相关的消息交换模式：  
  
- 传统握手  
  
- 顺序保护  
  
- 并行保护  
  
  在传统握手模式中，握手出现在业务流程或业务流程之间的消息交换，并可以通过在其中相关集是一系列业务流程中定义相关集来实现握手升级具有将消息路由到特定的业务流程实例使用的特定值的属性。  
  
  如果您的业务流程，用于发出采购订单、 接收发票和付款，则需要以确保通过从发送相应的采购订单的业务流程实例接收的发票消息由于可能会同时处理的采购订单号。 在此示例中，采购订单标识号可用作相关集进行关联的采购订单消息和发票消息中的参数。 下面是此示例中的方案流  
  
1. 业务流程 A 采购订单消息发送到业务流程 b。在发送前查看采购订单消息，初始化相关集。  
  
2. 在业务流程 B，在其中处理采购订单，生成并发回发票，第一个的接收形状将沿用同一相关集，以接收采购订单消息。  
  
3. 处理后的采购订单消息，将发票消息发送回业务流程 A 时，也将沿用同一相关集。  
  
4. 在从业务流程 B，接收发票消息的接收形状在业务流程 A，沿用同一相关集是还以确保接收相关的发票消息基于预定义的相关集。  
  
   顺序保护和并行保护模式中存在全球多个单一项必须为关联在一起才能实现类似无法完成的单个项本身的任何时间。 有关详细信息，请参阅[使用保护方案](../core/working-with-convoy-scenarios.md)。  
  
   除了相关的消息交换模式，有两种类型的业务流程中的相关性：  
  
- 手动相关  
  
- 自动关联  
  
  在手动相关方案中，手动配置业务流程来初始化并沿用相关集，以将消息与正确的实例相关联。 在自动相关方案中，消息引擎将关联消息与实例，例如，如果您的业务流程中设置了请求-响应端口或自相关端口。  
  
  每当您的业务流程不具有将消息与实例相关联的一种显式方法，例如激活接收，请求-响应端口或自相关端口时，必须使用相关。  
  
## <a name="examples-of-using-correlations"></a>使用相关示例  
  
-   [PartyResolution（BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)  
  
-   从下载 SDK 示例"关联消息与业务流程实例" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"并行保护" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [相关集](../core/correlation-sets.md) 
  
-   [相关类型](../core/correlation-types.md) 
  
-   [如何添加和删除相关集](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [如何配置相关集](../core/how-to-configure-correlation-sets.md)  
  
-   [如何配置相关类型](../core/how-to-configure-correlation-types.md)  
  
-   [使用保护方案](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a>请参阅  
 [如何使用自相关直接绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md)