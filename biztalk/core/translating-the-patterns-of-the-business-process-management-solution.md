---
title: 将业务流程管理解决方案的模式转换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, patterns
- patterns [process management solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to artifacts
- orchestrations, patterns
- orchestrations, boundaries
ms.assetid: 69f37732-f235-4bbb-bc85-31b4971c95ce
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e9c850e7e73d95decc7eb610a575d8fd2135aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243514"
---
# <a name="translating-the-patterns-of-the-business-process-management-solution"></a>转换业务流程管理解决方案的模式
本部分介绍如何在解决方案模式关系图将转换为 BizTalk Server 项目。  
  
 ![业务流程管理解决方案模式](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
## <a name="connections"></a>连接  
 连接是解决方案组件之间的消息路径。 开始的最简单位置是服务接口。 BizTalk Server，可以轻松地将业务流程作为 Web 服务。 有关将业务流程作为 web 服务公开的信息，请参阅[如何映射到 Web 服务的业务流程](../core/how-to-map-orchestrations-to-web-services.md)。  
  
 服务与预处理部分之间、 预处理部分与流程管理器之间和进程管理器和处理阶段之间存在其他连接。 连接还包括各阶段与后端系统之间和预处理和历史记录数据库和服务的系统之间。  
  
> [!NOTE]
>  转换器与 BizTalk 映射相对应。 映射是反过来，管道的部分或**转换**业务流程形状。  
  
 建立到流程管理器的连接，同步或异步的决定需要考虑一些问题。 与信用检查，如在线服务订购过程中的订单不太可能迅速完成。 如果与流程管理器的连接是异步的并且需要与其相关的管理流程的逻辑更复杂。 实际上，此解决方案使用与流程管理器通过将消息发布到 MessageBox 的异步连接。  
  
 进程管理器和阶段之间的连接表示节省服务器资源与简化逻辑之间的相似权衡。 阶段具有较短的处理时间比流程管理器。 每个阶段需要完成其处理，然后继续下一阶段中进行处理。 但是，因为我们可能想要修改这些阶段，进程管理器不能是紧密耦合到各个阶段。 在应用程序，如有限发布-订阅模型，可以描述的连接。 进程管理器将消息发送到通过单个、 专用端口的阶段。 阶段，又会进行筛选以识别其专用的消息。  
  
## <a name="determining-orchestration-boundaries"></a>确定业务流程边界  
 模式可分为三个主要区域： 预处理消息、 管理业务流程和业务流程本身。 预处理包含处理与 web 服务的连接、 将消息转换为的响应消息，通知服务系统、 历史记录数据库中写入项和消息传输到流程管理器。 在应用程序，由单个业务流程处理预处理。 管理业务流程由另一个业务流程处理。 管理业务流程将划分成适当阶段。 每个阶段对应于业务流程以允许进行添加和删除以表示订单流程中的更改。 订单处理阶段设计的详细信息，请参阅"划分业务流程"中[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
## <a name="translating-the-components-into-orchestrations"></a>将组件转换为业务流程  
 第一个业务流程**OrderBroker**，简单直接地转换关系图。 该业务流程将主要用于为流程管理器构造通知消息和订单消息的映射形状。 业务流程形状的完整列表，请参阅[业务流程形状](../core/orchestration-shapes.md)。  
  
 进程管理器和其附属程序集的逻辑是有些复杂。 有关逻辑的进程管理器业务流程**OrderManager**，请参阅[进程管理器逻辑](../core/process-manager-logic.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)   
 [使用模式进行设计： 业务流程管理解决方案](../core/designing-with-patterns-the-business-process-management-solution.md)   
 [业务流程管理解决方案中的模式目录](../core/pattern-catalog-for-the-business-process-management-solution.md)