---
title: 使用模式进行设计： 业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [process management solutions], examples
- patterns [process management solutions], designing
- examples, programming patterns
- designing, programming patterns
ms.assetid: 0583f4a4-01db-4d5b-a1f5-1694c1ddbd30
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3477ff868c6a5f07d6a600e35c1dea4b3d6cf9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530932"
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a>使用模式进行设计： 业务流程管理解决方案
业务流程管理解决方案显示了一种方法来构造流程管理器中的 BizTalk 应用程序。 该解决方案使用一个组件来选择和控制订单处理中的阶段序列。 该解决方案首先获取订单-这可能会为新的服务、 更改或取消服务 — 记录，并处理在传递之前该订单进行确认。 处理由处理订单的一个或多个阶段组成。 最后，该解决方案返回最终响应向原始订单请求。  
  
 设计完善的流程管理解决方案，可增加或减少而无需重新构造的应用程序的其余部分的过程中的各个阶段。 此解决方案中采用的方法允许这一点。 订单处理拆分为分散、 独立的阶段。 所有阶段都从同一个端口读取和使用筛选器来确定哪些消息要供其处理。 此予以详细介绍在以下部分中，"模式。"  
  
 此解决方案还通过接受输入 Web 服务，尽管也可以使用此解决方案通过 FTP 连接使用非服务接口。 此工具将模拟应用程序可能会使用批处理系统中的方式。  
  
## <a name="patterns"></a>模式  
 下图显示在业务流程管理解决方案中的前面部分所述的模式的简化的版本。  
  
 ![业务流程管理解决方案模式](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
 该解决方案包含以下部分： 服务接口、 FTP 通道、 各种转换器、 流程管理器和两个处理阶段。 预处理部分中的四个转换器创建回服务接口中，将生成一个项历史记录或跟踪数据库中并在服务系统中生成一个条目的确认消息。 第四个转换器可创建流程管理器所需的消息。 进程管理器又控制处理阶段。  
  
 在多个进程管理器实现中，管理器会跟踪处理状态。 此实现中，如图所示，此进行了修改。 在此解决方案中，进程管理器消息以指示应接着处理消息的处理阶段中设置的标志。 然后，每个阶段都使用筛选器以确定是否应处理特定消息。  
  
 使用此方法，流程管理器无需维护任何路由信息。 该管理器和各个阶段之间的所有消息都使用相同的端口。 若要添加某一阶段，只需添加发送和接收正确的端口和正确的阶段编号的筛选器上的组件。 你不必更改任何流程管理器本身。  
  
 请注意还有许多未表达出关系图。 处理阶段可能 — 和，实际上，做 — 与后端进程进行通信。 解决方案还可以收集进程中的多个点的历史信息。 这样一来，最重要的是，进程管理器的逻辑未指定。 此外，未指定使用同步或异步连接。 将以下各节中讨论这些内容。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)   
 [转换业务流程管理解决方案的模式](../core/translating-the-patterns-of-the-business-process-management-solution.md)