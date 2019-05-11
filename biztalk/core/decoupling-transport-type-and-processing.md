---
title: 分离传输类型和处理 |Microsoft Docs
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
ms.openlocfilehash: 23a65f525664d44a53760e5cb905e4db10f0f8a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352469"
---
# <a name="decoupling-transport-type-and-processing"></a>分离传输类型和处理
在面向服务解决方案中，清除行通常存在业务处理和传输和接收消息的具体情况之间。 这使您可以独立地更改业务流程或消息传送解决方案的一部分。  
  
 面向服务的解决方案违反了此设计原则在一个位置。 本部分介绍这种情况，可能替代方案，并将所选的结构。  
  
## <a name="correlation-and-the-mqseries-adapter"></a>相关和 MQSeries 适配器  
 若要使用 MQSeries 适配器，不能使用标准 BizTalk Server 相关标识符。 这是因为相关标识符将转到具有其自己系统相关标识符的 IBM 后端系统。 相反，必须使用**MQSeries.MQMD_CorrelId**并**MQSeries.MQMD_MsgID**属性。 在业务流程和，因此，业务流程中，可能会使用这些属性将特定于传输的信息。  
  
 处理此依存关系的一种方法是使用 BizTalk Server 相关标识符并使用自定义管道组件翻译 mqseries 相关标识符。 这会增加复杂性的方案。 此外，如果传输发生更改，则必须更改两个管道组件。 而且，从根本上讲，它重新定位到的依赖关系 （在管道组件中） 而不是解析它。  
  
 另一个选项是隔离到单独的业务流程处理的特定于 MQSeries 的相关并调用该业务流程。 这样可以保持业务流程的独立性。 但是，它引入了在业务流程之间的编译时依赖项。 若要修改传输需要进行重新编译这两个业务流程 （为，例如，在从转存根 （stub） 到解决方案的适配器版本）。 调用也会增加解决方案的响应时间。  
  
 给定增加了复杂性和性能可能降低的它看起来最简单的方法直接在业务流程中使用 MQSeries 相关。  
  
 有关适配器和业务流程中的相关详细信息，请参阅[MQSCorrelationSetOrchestration （BizTalk Server 示例）](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>请参阅  
 [面向服务的实现重点推荐的解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [MQSCorrelationSetOrchestration（BizTalk Server 示例）](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)