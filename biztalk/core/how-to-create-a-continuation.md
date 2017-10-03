---
title: "如何创建一个延续任务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63983b290f0f4d7dff544cd2faea45f6cf46adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-continuation"></a>如何创建一个延续任务
创建继续符可以指示一个或多个业务流程中的哪些业务活动是通过构造连接的活动来关联的。  
  
> [!IMPORTANT]
>  如果活动中包含 BAM 继续符，则更新跟踪配置文件可能会影响正在进行的活动实例。 具体而言，如果在更新跟踪配置文件时指定在下游对已记录的某个活动项进行数据侦听，则原始值可能会被覆盖。 从本质而言，任何单个事件流将不会受跟踪配置文件更新的应用程序的影响，因为每个流对象是与活动/流开始时处于就绪状态的特定版本的配置文件相联系。  但是，使用继续符就意味着将多个事件流相关联，在更新配置文件时还尚未开始的流将提取更新中所做的更改，从而导致上述可能出现的覆盖数据的情况。  
  
> [!NOTE]
>  你可以使用不处理消息的业务流程创建延续。 通过将参数传递到业务流程间的执行调用中，然后使用 BAM API 来处理继续符，可以获得与处理消息的业务流程相同的功能。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须已部署 BAM 活动定义和要连接到的业务流程。  
  
### <a name="to-create-a-continuation"></a>创建继续符  
  
1.  打开现有跟踪配置文件，或者创建一个跟踪配置文件。 有关创建跟踪配置文件的信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  标识*继续标记、*这是一种可供这两个活动的唯一信息。 例如，如果**CreditHistory**活动从发送消息激活**LoanProcess**中的活动**EquityLoan**业务流程、 的 SSN 字段消息可以用作继续标记，因为它是这两个活动共有的。  
  
3.  右键单击该活动，然后选择**新的延续**若要创建一个延续任务 (CreditHistory)。 命名您刚创建的继续符节点。  
  
4.  从“业务流程调度”视图中，选择在步骤 2 中选择的继续符，例如 SSN（本例中为“发送”操作的 SSN），然后将它放到在步骤 3 中创建的继续符节点中。  
  
5.  右键单击该活动，然后选择**新 ContinuationID**以创建一个延续 ID 节点。 使用在步骤 3 中选择的名称命名该节点，然后将其放到包含相应数据项的节点（本例中为接收操作的 SSN）中。  
  
6.  上**文件**菜单上，单击**另存为**以将跟踪配置文件另存为.btt 文件到 BizTalk 管理数据库和避免覆盖任何现有的.btt 文件。  
  
## <a name="see-also"></a>另请参阅  
 [延续任务，并 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)