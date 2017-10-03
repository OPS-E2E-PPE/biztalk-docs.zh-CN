---
title: "使用多个延续 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01a38087-71ee-40b3-a957-6a2653bd6435
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e27a73fae39a55f05650c08397616f3cbe4fa80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-multiple-continuations"></a>使用多个继续符
在有多个活动的环境中使用跟踪配置文件编辑器 (TPE)，您需要知道在哪些情况下跟踪活动，这是为了以正确的顺序映射接收端口、业务流程和发送端口。  
  
 在跟踪配置文件中，TPE 自动计算活动的开始和结束时间。 活动在开始收集数据时开始，在收集完数据后结束。  
  
 大多数情况下，创建单个继续符（如两个业务流程之间的继续符）对开发人员来说很简单。 在存在多个继续符的情况下，使用 TPE 将很复杂。 在存在多个继续符的方案中，业务活动监视 (BAM) 活动跨越多个接收端口、业务流程和发送端口。 为了将 BAM 数据收集在一个记录中，必须在所有 BizTalk Server 计划之间创建继续符。 使用 TPE 用户界面 (UI) 完成这个过程可能很复杂。  
  
 本主题介绍如何在不同的方案中创建单个和多个继续符。  
  
#### <a name="base-scenario-description---multiple-receive-ports-orchestrations-and-send-ports"></a>基本方案描述 - 多个接收端口、业务流程和发送端口  
 该方案由具有多个接收端口 (R)、业务流程 (O) 和发送端口 (S) 的 BizTalk Server 组成。 有一个常规 interchangeID 上下文属性用于链接继续符。 您可以使用任何上下文属性，如 activityID 或其他唯一标识符。 具体内容的选择不在这个方案的论述范围之内。  
  
 此方案不论述从这些端口和业务流程跟踪的具体数据项/里程碑/上下文属性值。 那部分映射是特定于业务逻辑的。 本方案的目的是捕获来自所有端口和业务流程的所有 BAM 数据，在已完成的活动表中将它们存入一行。 业务流程接收和处理消息的不同方式形成了一些有意义的挑战和解决方案。  
  
> [!NOTE]
>  可以将只有一个端口或一个业务流程的方案看作具有多个端口和多个业务流程方案的一种特例。  
  
#### <a name="scenario-solution-1---one-receive-port-and-one-orchestration"></a>解决方案 1 - 一个接收端口和一个业务流程  
 在此方案中，消息只发送到一个接收端口 (R1)，并且仅由一个业务流程 (O1) 处理。  
  
 继续符的创建过程如下：  
  
1.  在跟踪配置文件的文件夹活动树视图中创建一个继续符。  
  
2.  通过单击来选择上下文属性架构**选择事件源**按钮，，然后单击**选择上下文属性**菜单项。  
  
3.  找到**interchangeId 属性**中**上下文属性名称**列表，，然后选择它。  
  
4.  将 interchangeID 从属性架构映射到刚创建的继续符文件夹。  
  
5.  右键单击活动树中新创建的 interchangeID 节点，然后选择映射自哪些端口。  
  
6.  在**选择端口**显示的对话框中选择所有**N**接收端口。  
  
7.  在文件夹活动树中创建 continuationID 文件夹。  
  
8.  通过单击打开每个业务流程**选择事件源**按钮，，然后单击**选择业务流程计划**菜单项。 对每个业务流程，右键单击业务流程中的形状，然后将 interchangeID 上下文属性映射到新创建的 continuationID。  
  
 在具有三个业务流程的部署中，跟踪配置文件如下所示：  
  
 ![键入多个延续方案 1](../core/media/4761d680-7218-4404-a636-06739f70f344.gif "4761d680-7218-4404-a636-06739f70f344")  
  
#### <a name="scenario-solution-2---one-receive-port-and-multiple-orchestrations"></a>解决方案 2 - 一个接收端口和多个业务流程  
 在此方案中，消息只发送到一个接收端口，然后由每个业务流程分别处理。 这发生在消息同时发送到每个业务流程时。  
  
 在这种情况下，我们需要为每个业务流程创建继续符和 continuationID。 用于创建延续的过程将类似于方案解决方案 1 中所述的步骤。 对于三业务流程部署，你生成的跟踪配置文件如下所示：  
  
 ![键入多个延续方案 2](../core/media/3cebd82f-9192-4d52-84c7-584f24e8ecca.gif "3cebd82f-9192-4d52-84c7-584f24e8ecca")  
  
#### <a name="scenario-solution-3---content-based-routing"></a>解决方案 3 - 基于内容的路由  
 此方案定义基于内容的路由 (CBR) 解决方案。 消息只发送到一个接收端口，并且仅由一个发送端口发送。 此路由基于消息中的上下文属性值来执行。 在这种情况下，需要一个继续符。 映射如下所示：  
  
 ![延续 CBR 方案。] (../core/media/4459a73d-515f-4d6d-a68f-b18eee072df8.gif "4459a73d-515f-4d6d-a68f-b18eee072df8")  
  
> [!NOTE]
>  上面的映射还对只发送到一个接收端口并由所有发送端口发送的消息有效。  
  
#### <a name="scenario-solution-4---one-orchestration-multiple-send-ports"></a>解决方案 4 - 一个业务流程，多个发送端口  
 在此方案中，有多个发送。 端口。 由业务流程，也不能由处理规则中，会发送到所有发送端口中恰好有一个处理一条消息。 在这种情况下，需要一个继续符。 映射如下所示：  
  
 ![Coninuation 方案 4](../core/media/3ab10b51-d306-4ad1-acb6-6731e23394ac.gif "3ab10b51-d306-4ad1-acb6-6731e23394ac")  
  
#### <a name="scenario-solution-5---sequential-orchestrations"></a>解决方案 5 - 序列化业务流程  
 在此方案中，消息由每个业务流程一个接一个地按顺序处理，通过继续符传递给下一个业务流程。 映射如下所示：  
  
 ![延续方案 5](../core/media/563cacee-104c-4f8a-9836-da90aecb7487.gif "563cacee-104c-4f8a-9836-da90aecb7487")  
  
### <a name="collecting-data-in-an-asynchronous-environment"></a>在异步环境中收集数据  
 在设置继续符后，BAM 等待数据到来。 但在异步环境中可能接收不到后端进程的响应。  
  
 如果没有收到响应数据，则活动实例无限期等待。 该活动永不结束，活动记录会一直保留在 BAM 主导入数据库的表中。 如果是长期事务，则没有办法断定剩余数据何时到达。 由于数据的到达由业务逻辑或流程决定，因此不会发生使活动标记为完成的超时。 数据可能在当天到达，极端情况下可能是明年。  
  
 该解决方案使用相关活动。  
  
 将您的活动分为两个活动。 将这两个活动相关联，然后将响应关联到原始活动。  
  
 有关相关活动的详细信息，请参阅[活动关系](../core/activity-relationships.md)。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)