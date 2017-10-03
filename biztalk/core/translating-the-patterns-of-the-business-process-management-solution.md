---
title: "翻译模式的业务流程管理解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, patterns
- patterns [process management solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to artifacts
- orchestrations, patterns
- orchestrations, boundaries
ms.assetid: 69f37732-f235-4bbb-bc85-31b4971c95ce
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23603e66e80461baecea88648100442eb9da0166
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="translating-the-patterns-of-the-business-process-management-solution"></a>翻译模式的业务流程管理解决方案
本部分将介绍该解决方案如何将模式关系图转换为 BizTalk Server 项目。  
  
 ![业务流程管理解决方案模式](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
## <a name="connections"></a>Connections  
 连接是解决方案组件之间的消息路径。 最简单的开始位置是服务接口。 使用 BizTalk Server，可以便捷地将业务流程表示为 Web Services。 有关公开作为 web 服务的业务流程的信息，请参阅[如何映射到 Web 服务的业务流程](../core/how-to-map-orchestrations-to-web-services.md)。  
  
 服务与预处理部分之间、预处理部分与流程管理器之间、流程管理器和处理阶段之间存在其他连接。 连接还包括各阶段与后端系统之间、预处理与历史记录数据库和服务系统之间的连接。  
  
> [!NOTE]
>  转换器与 BizTalk 映射相对应。 地图是反过来，管道的部分或**转换**orchestration 形状。  
  
 在确定与流程管理器建立同步连接或异步连接时，需要考虑一些问题。 与信用检查不同，流程（例如在线服务订购）中的订单不太可能迅速完成。 如果与流程管理器建立了异步连接，并且需要与其相关，则管理流程的逻辑将更为复杂。 实际上，此解决方案通过将消息发布到 MessageBox 来使用与流程管理器的异步连接。  
  
 流程管理器与各阶段之间的连接表示节省服务器资源与简化逻辑之间的相似权衡关系。 各阶段的处理时间比流程管理器的处理时间短。 每个阶段需要完成其处理，然后才能继续在下一阶段中进行处理。 但是，由于可能需要修改这些阶段，因此流程管理器不能与这些阶段紧密连接。 在应用程序中，连接可以显示为一个受限制的发布-订阅模型。 流程管理器通过单个专用端口将消息发送到各个阶段， 而这些阶段又会进行筛选以识别其专用的消息。  
  
## <a name="determining-orchestration-boundaries"></a>确定业务流程边界  
 模式可分为三个主要方面： 预处理的消息，管理业务流程和业务流程自身。 预处理由以下操作组成：处理与 Web Services 的连接、将消息转换为相应消息以进行响应、通知服务系统、在历史记录数据库中记录条目以及将消息传输到流程管理器。 在应用程序中，预处理将由单个业务流程进行处理。 管理业务流程将由另一个业务流程进行处理。 要管理的业务流程可以分为若干个适当阶段。 其中每个阶段都与业务流程相对应，从而允许进行添加和删除以表示订单流程中的更改。 有关的订单过程阶段设计的详细信息，请参阅"除以业务流程"[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
## <a name="translating-the-components-into-orchestrations"></a>将组件转换为业务流程  
 第一个业务流程， **OrderBroker**，只需并直接将关系图。 该业务流程主要是用于为流程管理器构造通知消息和订单消息的映射形状。 业务流程形状的完整列表，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。  
  
 流程管理器及其附属程序集的逻辑比较复杂。 有关逻辑信息的进程管理器业务流程、 **OrderManager**，请参阅[过程管理器逻辑](../core/process-manager-logic.md)。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)   
 [设计用于模式： 业务流程管理解决方案](../core/designing-with-patterns-the-business-process-management-solution.md)   
 [业务流程管理解决方案的模式目录](../core/pattern-catalog-for-the-business-process-management-solution.md)