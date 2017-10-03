---
title: "延续任务，并 ContinuationID 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa8956721d4a44b51b8d2c7776560aaa878f864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="continuation-and-continuationid-nodes"></a>继续符和 ContinuationID 节点
继续符为 BAM 基础结构提供有关以下信息的指导：  
  
-   事件应按何种顺序发生  
  
-   对与事件项关联的唯一 ID 中的任何更改进行处理的方法  
  
 换种方式来说明此点，继续符定义如何向活动传输参与者之间的这些信息。 当以下情况出现时，将发生传输：  
  
-   当活动正在进行时，ActivityID 发生变化。 例如，您有两个相关的消息，即采购订单号和销售订单号。 每个消息都有分配给它的唯一编号，例如，采购订单号的唯一编号为 123456，销售订单号的唯一编号为 987654。 您想使用继续符让采购订单和销售订单的唯一标识符相等，以便事件可以关联到公用活动，而不用管哪个唯一标识符与传入事件相关联。  
  
-   从一个运行时环境转换到另一个运行时环境。 例如，在必须提供 BizTalk Server 消息管道，然后将调用一个业务流程和业务流程，然后将控件传递到的应用程序发送传送通知，采购订单的应用程序方案中你有两个环境转换： 从消息传递到管道业务流程和从消息管道业务流程。  
  
 在选择要用于您的继续符的属性的一个重要一点是：必须从同一上下文映射这些属性。  
  
 例如，如果您具有属性 Message.InterchangeID 和 servicecontext.InterchangeID，则可能您可以使用 InterchangeID 来创建您的继续符。 如果这些消息来自不同的上下文，则您将不能使用 InterchangeID（或其他属性）来可靠地创建继续符。  
  
## <a name="working-with-continuation-nodes"></a>使用继续符节点  
 延续节点包含数据的项，指示一个唯一的实例 ID，也称为*继续标记*。 通过使用继续符，开发人员可以链接到使用 ContinuationID 节点的其他活动。  
  
 使用继续符和 ContinuationID 节点的基本情况有以下三种：  
  
-   业务流程到业务流程  
  
-   业务流程到 BizTalk 解决方案  
  
-   BizTalk 解决方案到业务流程  
  
 在业务流程到业务流程的情况中，TPE 必须定义继续符节点和 ContinuationID 节点，并且这两个节点必须具有相同的名称以便 BAM 可以关联活动。  
  
 在业务流程到 BizTalk 解决方案的情况中，您需要使用 TPE 定义继续符节点，并且开发人员需要创建一个用 BAM API 来处理该继续符的目标部分的解决方案。  
  
 在 BizTalk 解决方案到业务流程的情况中，开发人员需要使用 BAM API 提供继续符对的起点，然后您需要使用 TPE 定义 ContinuationID 节点。  
  
> [!NOTE]
>  双向端口可在两个方向上进行操作，这意味着要侦听传过这种端口的数据，可能需要启用继续符，具体情况取决于 BizTalk 解决方案的行为。 例如，如果活动在两个方向上为 BizTalk Server 消息处理端口的激活过程记录“PortEndTime”（例如，如果项名称为“MessageReceived”和“MessageSent”，这两项的顺序为此处的先后顺序），您需要在它们之间创建一个继续符。 如果有多个事件流分配到 BAM 活动中，并且每个实现接触点有不同的事件流（例如，BTS 消息传入、BTS 消息传出、业务流程、自定义应用程序以及 Web Services），则必须使用继续符。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建一个延续任务](../core/how-to-create-a-continuation.md)   
 [键入活动视图节点](../core/tpe-activity-view-nodes.md)