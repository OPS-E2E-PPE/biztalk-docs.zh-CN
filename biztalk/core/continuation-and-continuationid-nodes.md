---
title: 继续符和 ContinuationID 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- Continuation nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- BAM, correlating activities
- activities, linking
- activities, continuation tokens
- ContinuationID nodes [Tracking Profile Editor]
ms.assetid: aa050660-66f7-4084-b6bf-b9319ce625af
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0cd305241b04bbbb7a09a8cf716820978594e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354594"
---
# <a name="continuation-and-continuationid-nodes"></a>继续符和 ContinuationID 节点
延续任务提供指导到 BAM 基础结构有关的以下信息：  
  
- 事件预期发生的顺序  
  
- 一种方法来处理任何更改的项对与事件相关联的唯一 ID  
  
  若要表明此另一种方法，继续符定义活动的参与者之间的此信息传输。 在以下情况下会发生传输：  
  
- 没有在活动开始的时间和结束之间的 ActivityID 的更改。 例如，你有采购订单号和销售订单号相关的两个消息。 每个都有分配给它，如 123456 采购订单号和销售订单编号为 987654 的唯一编号。 将使用延续来使唯一标识符相等的采购订单和销售订单，以便事件可以关联到公用活动，而不考虑的唯一标识符是与传入事件相关联。  
  
- 可以从一个运行时环境转换到另一个。 例如，在必须提供给 BizTalk Server 消息传送管道，然后调用业务流程和业务流程，然后将控制权传递给发送发货通知的应用程序，采购订单的应用程序方案中有两个环境转换： 从消息传送管道转换业务流程和从业务流程传递到消息传送管道。  
  
  选择要用于您的继续符某一属性时要记住的重要一点是，必须将属性映射的同一上下文中。  
  
  例如，如果您具有属性 Message.InterchangeID 和 servicecontext。它可能显示您可以使用 InterchangeID 来创建您的继续符的 InterchangeID。 如果这些消息来自不同的上下文不能使用 InterchangeID （或其他属性） 来可靠地创建继续符。  
  
## <a name="working-with-continuation-nodes"></a>使用继续符节点  
 继续符节点包含指示唯一实例 ID，也称为的数据项*继续标记*。 通过使用继续标记，开发人员可以链接到使用 ContinuationID 节点的其他活动。  
  
 有三种基本方案中的继续符和 ContinuationID 节点可用：  
  
- 业务流程到业务流程  
  
- 业务流程到 BizTalk 解决方案  
  
- BizTalk 解决方案到业务流程  
  
  在业务流程中情况中，TPE 必须定义继续符节点和 ContinuationID 节点，并且节点必须具有相同的名称以便 BAM 可以关联活动。  
  
  在业务流程到 BizTalk 解决方案的情况，您将使用 TPE 定义继续符节点和开发人员创建的解决方案，使用 BAM API 来处理的目标部分的延续任务...  
  
  在 BizTalk 解决方案到业务流程中，开发人员使用 BAM API 提供继续符对的起点，并使用 TPE 定义 ContinuationID 节点。  
  
> [!NOTE]
>  双向端口可以运行在任一方向，这意味着，数据会通过端口侦听可以具体取决于 BizTalk 解决方案的行为，需要启用继续符。 例如，如果活动记录"PortEndTime"激活的 BizTalk Server 消息传送端口，在任一方向 （如果项名称，例如，"MessageReceived"和"MessageSent"按此顺序），您需要创建它们之间的继续符。 延续是必需的任何时间超过一个事件流分配到 BAM 活动中，并且有不同的事件流，每个实现接触点 （如 BTS 消息传入、 BTS 消息传出、 业务流程、 自定义应用程序和 Web 服务）。  
  
## <a name="see-also"></a>请参阅  
 [如何创建一个继续符](../core/how-to-create-a-continuation.md)   
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)