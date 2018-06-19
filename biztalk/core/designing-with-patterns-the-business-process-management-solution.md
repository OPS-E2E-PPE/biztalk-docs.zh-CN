---
title: 设计用于模式： 业务流程管理解决方案 |Microsoft 文档
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
ms.openlocfilehash: 91da8c63fc46ee90696e257bfd6142b5088af305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239661"
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a>设计用于模式： 业务流程管理解决方案
业务流程管理解决方案为您展示了一种在 BizTalk 应用程序中构造流程管理器的方法。 该解决方案使用组件来选择和控制订单处理中的阶段序列。 该解决方案首先获取订单（该订单可能是申请新的服务、申请变化或申请取消服务），然后记录该订单，并在传递订单以进行处理之前对该订单进行确认。 处理过程由一个或多个订单处理阶段组成。 最后，该解决方案向原始订单请求返回最终响应。  
  
 通过设计完善的流程管理解决方案，您可以增减流程中的各个阶段，而无需重新构造其余的应用程序。 在此解决方案中采用的方法正是这样。 将订单处理拆分为分散、独立的阶段。 所有阶段都从同一端口进行读取，并使用筛选器确定要供其处理的消息。 在下一部分“模式”中将对此予以详细介绍。  
  
 尽管您可以通过 FTP 连接将非服务接口用于此解决方案。但此解决方案还可通过 Web Services 接受输入， 此工具将模拟应用程序在批处理系统中的可能用法。  
  
## <a name="patterns"></a>模式  
 下图显示了业务流程管理解决方案（如前一部分中所示）中简化版本的模式。  
  
 ![业务流程管理解决方案模式](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
 解决方案包含以下部分： 服务接口、 FTP 通道、 各种转换器、 进程管理器中，和两个处理阶段。 预处理部分中的四个转换器可创建返回服务接口的确认消息，在历史记录或跟踪数据库中生成条目，并在服务系统中生成条目。 第四个转换器可创建流程管理器所需的消息。 而该流程管理器又控制处理阶段。  
  
 在许多流程管理器实施方式中，该管理器可跟踪处理状态。 如图所示，该实施方式对此进行了修改。 在此解决方案中，流程管理器在消息中设置了一个标志，以指示应接着处理消息的处理阶段。 然后，每个阶段都使用筛选器确定是否应处理特定消息。  
  
 使用此方法，流程管理器将无需维护任何路由信息。 管理器和各个阶段之间的所有消息都使用同一端口。 若要添加阶段，则只需添加一个组件，该组件在恰当的端口上进行发送和接收操作并筛选正确的阶段编号。 而无需更改任何流程管理器本身的项。  
  
 请注意，在图表中还有许多未表达出来的内容。 实际上，处理阶段可能与后台进程进行通信。 该解决方案还可以收集进程中多个点的历史信息。 可能最重要的是，未指定流程管理器的逻辑。 此外，未指定使用同步连接还是异步连接。 在后面几部分中将讨论这些内容。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)   
 [翻译模式的业务流程管理解决方案](../core/translating-the-patterns-of-the-business-process-management-solution.md)