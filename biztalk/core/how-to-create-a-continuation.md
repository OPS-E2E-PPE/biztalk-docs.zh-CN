---
title: 如何创建一个继续符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0cf558ec136cf25bece9c899cad13e1c9d75f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340095"
---
# <a name="how-to-create-a-continuation"></a>如何创建一个继续符
创建继续符可以指示一个或多个业务流程中的业务事件通过构造连接的活动相关。  
  
> [!IMPORTANT]
>  如果该活动将包含 BAM 继续符，更新跟踪配置文件可能会影响正在进行中的活动实例。 具体而言，如果跟踪配置文件更新指定的已记录某个活动项的数据的下游拦截，就可以将覆盖原始值。 从本质上讲，任何单个事件流不会受跟踪配置文件更新，因为每个流对象绑定到活动/流开始时就已存在的配置文件的特定版本的应用程序。  但是，由于延续关联多个事件流的方式，流尚未开始更新配置文件的时间会选取更新，从而导致可能覆盖数据的情况中的更改。  
  
> [!NOTE]
>  您可以与不处理消息的业务流程创建继续符。 可以通过在业务流程之间执行调用中传递参数并使用 BAM Api 来处理继续符处理消息的业务流程，你可以获取相同的功能。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须部署 BAM 活动定义和将连接到的业务流程。  
  
### <a name="to-create-a-continuation"></a>若要创建一个继续符  
  
1.  打开现有的跟踪配置文件或创建跟踪配置文件。 有关创建跟踪配置文件的信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  识别*继续标记、* 这是一种可供这两个活动的唯一信息。 例如，如果**CreditHistory**活动从发送一条消息来激活**LoanProcess**中的活动**EquityLoan**业务流程、 的 SSN 字段消息可以用作一个继续标记，因为它是普遍适用于这两个活动。  
  
3.  右键单击该活动，然后选择**新的延续**来创建继续符 (CreditHistory)。 命名您刚创建的继续符节点。  
  
4.  从业务流程调度视图中，选择在步骤 2 中，例如 SSN （在此情况下从发送操作） 中选择的继续标记，并将其放到在步骤 3 中创建的继续符节点。  
  
5.  右键单击该活动，然后选择**新建 ContinuationID**创建继续符 ID 节点。 其使用步骤 3 中选择的名称命名，并将其放在包含 （在此情况下，从接收操作的 SSN） 相应数据项的节点。  
  
6.  上**文件**菜单上，单击**另存为**保存跟踪配置文件作为.btt 文件到 BizTalk 管理数据库，以避免覆盖任何现有的.btt 文件。  
  
## <a name="see-also"></a>请参阅  
 [继续符和 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)