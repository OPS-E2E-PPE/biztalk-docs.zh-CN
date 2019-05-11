---
title: 使用多个继续符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01a38087-71ee-40b3-a957-6a2653bd6435
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a9f333606143e53d5797d7bae506c770cb08b56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396771"
---
# <a name="using-multiple-continuations"></a>使用多个继续符
在其中有多个活动的环境中使用跟踪配置文件编辑器 (TPE) 要求您了解在该活动正在跟踪以将接收端口，业务流程、 映射和中适当的发送端口的方案序列。  
  
 在跟踪配置文件，TPE 评估的开头和结尾的活动自动。 在活动开始时收集数据的第一条并结束时收集的最后一项工作。  
  
 在大多数情况下创建单个继续符，如两个业务流程之间的继续符为开发人员是一个简单的过程。 TPE 将很复杂性是在多个继续符的情况下。 多个继续符方案是其中的业务活动监视 (BAM) 活动跨越多个接收端口，业务流程和发送端口。 为了收集一条记录中的 BAM 数据，必须创建所有 BizTalk Server 计划之间的继续符。 此过程可能很复杂时通过 TPE 用户界面 (UI) 完成。  
  
 本主题介绍如何创建单个和多个不同的方案中的继续符。  
  
#### <a name="base-scenario-description---multiple-receive-ports-orchestrations-and-send-ports"></a>基本方案描述-多个接收端口、 业务流程和发送端口  
 该方案由具有多个接收端口 (R) 业务流程 (O) 的 BizTalk 服务器和发送端口 (S)。 没有用于链接继续符的常规 interchangeID 上下文属性。 可以使用任何上下文属性，如 activityID 或其他唯一标识符。 所选的特定内容的方案的讨论无关。  
  
 有关方案的目的，未指定数据项/里程碑/上下文的属性的值的被跟踪从这些端口和业务流程的讨论。 该部分映射是特定于业务逻辑。 目标是捕获来自所有端口和已完成的活动表中的单个行中的业务流程的所有 BAM 数据。 在其中一条消息可以接收和处理业务流程的不同方式提供了一些有趣的挑战和解决方案。  
  
> [!NOTE]
>  一个端口或一个业务流程的方案可被视为一种特殊情况的多个端口和许多业务流程方案。  
  
#### <a name="scenario-solution-1---one-receive-port-and-one-orchestration"></a>解决方案 1-一个接收端口和一个业务流程  
 在此方案中，只发送到一个接收端口 (R1) 和由一个业务流程 (O1) 处理消息。  
  
 若要创建延续任务的过程是按如下所示：  
  
1. 跟踪配置文件的文件夹活动树视图中创建一个继续符。  
  
2. 通过单击来选择上下文属性架构**选择事件源**按钮，，然后单击**选择上下文属性**菜单项。  
  
3. 找到**interchangeId 属性**中**上下文属性名称**列表，并选择它。  
  
4. 从属性架构中，将 interchangeID 映射到刚创建的继续符文件夹。  
  
5. 右键单击活动树中的新创建的 interchangeID 节点，然后选择映射自哪些端口。  
  
6. 在中**选择端口**将显示的对话框中选择所有**N**接收端口。  
  
7. 在文件夹活动树中创建 continuationID 文件夹。  
  
8. 通过单击打开每个业务流程**选择事件源**按钮，，然后单击**选择业务流程计划**菜单项。 从每个业务流程，右键单击形状在业务流程，，然后将 interchangeID 上下文属性映射到新创建的 continuationID。  
  
   在部署具有三个业务流程中，跟踪配置文件将类似于此：  
  
   ![TPE 多继续符方案 1](../core/media/4761d680-7218-4404-a636-06739f70f344.gif "4761d680-7218-4404-a636-06739f70f344")  
  
#### <a name="scenario-solution-2---one-receive-port-and-multiple-orchestrations"></a>解决方案 2-一个接收端口和多个业务流程  
 在此方案中，一条消息只发送到一个接收端口，并由每个业务流程处理。 当消息同时发送到每个业务流程，将发生这种情况。  
  
 在这种情况下，我们需要继续符和 continuationID 用于每个业务流程。 创建继续符的过程将类似于解决方案 1 中所述的步骤。 对于三个业务流程部署，产生的跟踪配置文件如下所示：  
  
 ![TPE 多继续符方案 2](../core/media/3cebd82f-9192-4d52-84c7-584f24e8ecca.gif "3cebd82f-9192-4d52-84c7-584f24e8ecca")  
  
#### <a name="scenario-solution-3---content-based-routing"></a>方案解决方案 3-内容基于路由  
 此方案中定义的基于内容的路由 (CBR) 解决方案。 一条消息只发送到一个接收端口和发送到发送端口之一。 此路由基于消息中的上下文属性值。 在这种情况下，我们需要一个延续。 映射如下所示：  
  
 ![连续 CBR 方案。](../core/media/4459a73d-515f-4d6d-a68f-b18eee072df8.gif "4459a73d-515f-4d6d-a68f-b18eee072df8")  
  
> [!NOTE]
>  上面的映射也是有效的消息只发送到一个接收端口和发送到所有发送端口。  
  
#### <a name="scenario-solution-4---one-orchestration-multiple-send-ports"></a>方案解决方案 4-一个业务流程，多个发送端口  
 在此方案中，有多个发送。 端口。 由一个业务流程，它由处理规则，并发送到所有发送端口处理消息。 在这种情况下，我们需要一个延续。 映射如下所示：  
  
 ![Coninuation Scenario 4](../core/media/3ab10b51-d306-4ad1-acb6-6731e23394ac.gif "3ab10b51-d306-4ad1-acb6-6731e23394ac")  
  
#### <a name="scenario-solution-5---sequential-orchestrations"></a>解决方案 5-序列化业务流程  
 在此方案中，处理的序列中的每个业务流程，一一，并通过继续符传递给下一个业务流程的消息。 映射如下所示：  
  
 ![Continuation scenario 5](../core/media/563cacee-104c-4f8a-9836-da90aecb7487.gif "563cacee-104c-4f8a-9836-da90aecb7487")  
  
### <a name="collecting-data-in-an-asynchronous-environment"></a>在异步环境中收集数据  
 当设置延续任务时，BAM 等待数据到来。 在异步环境中可能会不从后端进程收到响应。  
  
 如果未收到响应数据，活动实例无限期等待。 该活动将永远不会完成并记录会一直保留在 BAM 主导入数据库中的表中。 长时间运行的事务，这种情况，请考虑在没有办法断定剩余数据将到达时。 没有超时，因为数据到达时将取决于业务逻辑或流程，在其后使活动标记为已完成。 数据无法到达同一天，或在极端情况下下, 一年。  
  
 解决方案是使用相关的活动。  
  
 将您的活动分为两个活动。 相关的两个活动，并将响应关联到原始活动。  
  
 有关相关活动的详细信息，请参阅[活动关系](../core/activity-relationships.md)。  
  
## <a name="see-also"></a>请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)