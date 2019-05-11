---
title: 主要消息和字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 77db0706-dfdc-48b0-8ca4-bae7ab2d7641
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f97e13b50dd0ccce127ae862972cd0448c4d56a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329487"
---
# <a name="key-messages-and-fields"></a>主要消息和字段
本部分简要介绍主要消息和字段由处理**OrderBroker**并**OrderManager**业务流程。 在应用程序中的消息的完整列表，请参阅[业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)。  
  
## <a name="order-messages"></a>订单消息  
 订单消息从**OrderBroker**是多部分消息。 一部分包含路由信息;另一个部件，订单信息。 .NET 类定义的路由的消息部分进行的所有字段可分辨字段以便业务流程可以有权访问的所有消息属性作为类成员。 这些类还包括升级的字段中的路由类，以便消息可以路由。 所有升级字段也是可分辨的字段，以便他们可以针对进行编程和使用较简单的符号引用。  
  
 有关使用.NET 类来定义消息的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
## <a name="identifying-orders"></a>标识订单  
 该解决方案使用路由信息中的三个字段来标识订单。 这三个字段，两个用于标识订单： 订单标识符 (**OrderID**) 和客户标识符 (**CustomerID**)。 但是，尽管这两个字段标识订单，但可以有多个订单的实例。 例如，客户可能本来的新的标准电缆安装，然后更高版本调用以将顺序更改为新的高级电缆安装。 不太可能，将更新的订单到达之前完成的原始顺序。 这将创建两个实例的顺序。  
  
 为了区分订单的实例，该解决方案使用唯一的订单序列号 (**SeqNum**)。 三个字段**OrderID**， **CustomerID**，并**SeqNum**唯一地标识订单实例。  
  
 最后，由于解决方案使用的递增的数字**SeqNum**，该解决方案可以区分出更新的原始顺序-更新具有更高**SeqNum**。  
  
> [!NOTE]
>  解决方案依赖于系统创建订单请求，以便分配到递增的值**SeqNum**。 请参阅输入的 web 服务，ASP 页后面的代码**CSRMainForm.aspx.cs**，并将请求转换为订单，映射**若要**的字段的名称所涉及。  
  
## <a name="status"></a>“登录属性”  
 **OrderBroker**， **OrderManager**，及其附属业务流程使用订单消息路由部分中的两个字段来跟踪状态：**状态**，并**阶段**。 **状态**字段用于跟踪订单的状态。 下表描述了的值**状态**字段。  
  
|ReplTest1|在其中设置|Description|  
|-----------|---------------|-----------------|  
|接受|OrderBroker|订单可以继续进入 OrderManager。|  
|已完成|OrderManager|整个订单处理完成后不会出错。|  
|error|OrderManager|在订单中检测到的错误。|  
|ORDERMANAGER 异常|OrderManager|处理订单时在订单管理器中发生异常。|  
|STAGE_n_COMPLETED|OrderManager|指示阶段 n，其中 n 是一个数字，完成，没有错误。|  
|STARTED|OrderManager|订单处理已开始。|  
|终止|OrderManager|订单处理由于取消被停止。|  
  
## <a name="stage"></a>阶段  
 **OrderManager**使用**阶段**字段以指示消息的处理阶段在路由部分中。 在确定的附属业务流程处理消息的筛选器中使用该字段。 **OrderManager**最初设置**阶段**为一 (1)。 当订单终止或完成时， **OrderManager**设置**阶段**业务流程变量的值**停止**。  
  
## <a name="requesttype"></a>RequestType  
 **OrderManager**还使用**RequestType**订单消息的字段。 如果字段的值为 TERMINATE，顺序是终止。 业务流程将忽略所有其他值的**RequestType**字段并依赖于订单序列号来识别订单更新和重复项。 否则为**OrderBroker**设置**RequestType**的值字段**状态**字段中来自供应商或客户服务系统的消息。  
  
## <a name="ordertypecode-ordertype-and-serviceclass"></a>OrderTypeCode、 OrderType 和 ServiceClass  
 订单的类型位于**OrderTypeCode**订单消息的字段。 **OrderBroker**将其设置为中的值**OrdTypeCode**字段中来自客户服务系统或供应商系统的消息。 下表显示了可能的值为**OrderTypeCode**:  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|NS|新的标准电缆安装。|  
|ND|新的高级电缆安装。|  
|XS|取消标准电缆安装。|  
|XD|取消高级电缆安装。|  
|CS|更改标准电缆安装。|  
|CD|更改高级电缆安装。|  
|UNKNOWN|未知。|  
  
 更高版本， **Validate**业务流程使用业务规则引擎来转换为两个单独的字段，这些值**OrderType**并**ServiceClass**。 **Validate**由第一个订单处理阶段中，调用业务流程**CableOrder1**。  
  
 下表提供的值**OrderType**:  
  
|OrderTypeCode 值|OrderType 值|  
|--------------------------|---------------------|  
|NS ND|激活|  
|XS XD|取消|  
|CS CD|更改|  
|无效组合。|INVALID|  
  
 值**ServiceClass**是相应的单个字母**S**标准，或**D**为高级。  
  
## <a name="additional-identifiers"></a>其他标识符  
 该解决方案还将用于每个订单的标识符。 此标识符**RequestId**，需要的所有订单之间保持唯一。 输入的 web 服务会自动向其分配一个 GUID。 通过成批输入提交消息必须包含字段的值。 该字段是**RequestID**订单架构中。 **OrderBroker**，但是，使用**CSR_OrderRequest**架构来处理订单。 该字段显示为**ReqId**此架构中，为可分辨的属性。  
  
 该解决方案使用**RequestId**若要在 BAM 跟踪系统中使用的活动标识符。  
  
## <a name="see-also"></a>请参阅  
 [进程管理器逻辑](../core/process-manager-logic.md)   
 [通过进程管理器的订单流](../core/order-flow-through-the-process-manager.md)   
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)   
 [业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)