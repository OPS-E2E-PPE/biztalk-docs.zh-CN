---
title: "在业务流程中使用相关性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3be56c2171205bb49d2ff1f589c77ac309ea188
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-correlations-in-orchestrations"></a>在业务流程中使用相关性
相关是将传入消息与业务流程的相应实例相匹配的过程。 例如，业务流程发出一条消息，然后接收到返回该业务流程的一个或多个响应。 有三种相关消息交换模式：  
  
-   传统握手  
  
-   顺序保护  
  
-   并行保护  
  
 在传统握手模式中，握手出现在业务流程内的消息交换之中，您可以通过在业务流程中定义相关集来实现握手，其中相关集是一个升级属性列表，这些属性具有特定的值，用来将消息路由到特定的业务流程实例。  
  
 例如，如果您的业务流程用于发出采购订单，接收发票以及付款，则您需要确保由发送采购订单的业务流程实例接收相应发票消息，因为系统可能同时处理多个采购订单。 在下例中，采购订单标识号可用作将采购订单消息与发票消息相关联的相关集中的参数。 下面是此示例的流程。  
  
1.  业务流程 A 向业务流程 B 发出采购订单消息。在发出采购订单消息之前，初始化相关集。  
  
2.  在业务流程 B 中处理采购订单，生成并发回发票，第一个接收形状将沿用同一相关集来接收采购订单消息。  
  
3.  处理完采购订单消息后，在将发票消息发回业务流程 A 时，也将沿用同一相关集。  
  
4.  在业务流程 A 的接收从业务流程 B 发回的发票消息的接收形状中，也将沿用同一相关集，以确保根据预定义相关集接收相关发票消息。  
  
 在必须将多个单一项关联在一起才能得出所需结果，而单个项目自身不能完成的情况下，就需要使用顺序保护和并行保护模式。 有关详细信息，请参阅[使用队列方案](../core/working-with-convoy-scenarios.md)。  
  
 除了相关消息交换模式以外，业务流程中还有两种类型的相关：  
  
-   手动相关  
  
-   自动相关  
  
 在手动相关方案中，您手动配置业务流程来初始化并沿用相关集，以将消息与正确的实例相关联。 在自动相关方案中，消息引擎将为您关联消息与实例，例如，在业务流程中设置请求-响应端口或自相关端口时。  
  
 在业务流程不能显式将消息与实例相关联时，必须使用相关，例如，活动接收端口、请求-响应端口或自相关端口。  
  
## <a name="examples-of-using-correlations"></a>使用相关示例  
  
-   [PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)  
  
-   从下载 SDK 示例"关联的消息与业务流程实例" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"并行保护" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [关联集](../core/correlation-sets.md) 
  
-   [相关性类型](../core/correlation-types.md) 
  
-   [如何添加和删除关联集](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [如何配置相关设置](../core/how-to-configure-correlation-sets.md)  
  
-   [如何配置相关类型](../core/how-to-configure-correlation-types.md)  
  
-   [使用队列方案](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a>另请参阅  
 [如何使用自关联 Direct 绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md)