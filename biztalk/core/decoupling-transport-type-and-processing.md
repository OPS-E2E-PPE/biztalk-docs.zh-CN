---
title: 分离传输类型和处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transport types, decoupling processing
- processing, decoupling transport types
- transport types
- transport types, service solutions
- service solution tutorial, MQSeries adapters
- processing, service solutions
- service solution tutorial, decoupling transport type and processing
- correlations, MQSeries adapters
- MQSeries adapters, correlations
- MQSeries adapters, service solutions
ms.assetid: 0b2c733a-e2c7-42ff-a733-f712fde38f7e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b14522c6bbf9393bc22f632c4db5eeb5e4a22a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238597"
---
# <a name="decoupling-transport-type-and-processing"></a>分离传输类型和处理
在面向服务的解决方案中，业务处理与传输和接收消息的具体细节之间通常存在明显的界线。 这样，您可以单独更改解决方案的业务流程或消息传送部分。  
  
 但是，面向服务的解决方案在一处违反了此设计原则。 本部分将描述这种情况，并提供可用的替代方案以及所选的结构。  
  
## <a name="correlation-and-the-mqseries-adapter"></a>相关和 MQSeries 适配器  
 若要使用 MQSeries 适配器，则不能使用标准的 BizTalk Server 相关标识符。 这是因为相关标识符将转到具有自己的系统相关标识符的 IBM 后端系统。 相反，你必须使用**MQSeries.MQMD_CorrelId**和**MQSeries.MQMD_MsgID**属性。 使用这些属性可能会将特定于传输的信息放入业务流程中，即，放入业务程序中。  
  
 处理此依存关系的一种方法是使用 BizTalk Server 相关标识符，并使用自定义管道组件翻译 MQSeries 的相关标识符。 这会增加该方案的复杂性。 此外，如果传输发生更改，则必须相应地更改两个管道组件。 最终，BizTalk Server 相关标识符将重新指定依存关系（在管道组件中），而不是解析 MQSeries 标识符。  
  
 另一种办法是将特定于 MQSeries 的相关处理分别放置在单独的业务流程中，并调用该业务流程。 这将保持业务流程的独立性。 但这也将导致在业务流程之间存在编译时依存关系。 若要修改传输，则两个业务流程都需要进行重新编译（例如，从解决方案的存根版本更改为解决方案的适配器版本）。 同时，调用也会增加解决方案的响应时间。  
  
 在增加了复杂性和性能可能降低的情况下，直接在业务流程中使用 MQSeries 相关似乎是最简单的办法。  
  
 有关适配器和在业务流程中的相关性的详细信息，请参阅[MQSCorrelationSetOrchestration （BizTalk Server 示例）](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>另请参阅  
 [服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [MQSCorrelationSetOrchestration （BizTalk Server 示例）](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)