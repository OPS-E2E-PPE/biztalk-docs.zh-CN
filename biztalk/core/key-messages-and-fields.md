---
title: "关键消息和字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 77db0706-dfdc-48b0-8ca4-bae7ab2d7641
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 524b5f361495d9509809a9229362d28a18712239
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-messages-and-fields"></a>关键信息和字段
本部分简要介绍重要信息和字段由**OrderBroker**和**OrderManager**业务流程。 应用程序中的消息的完整列表，请参阅[业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)。  
  
## <a name="order-messages"></a>订单消息  
 顺序从消息**OrderBroker**多个部分的消息。 其中一部分包含路由信息，另一部分包含订单信息。 定义路由消息部分的 .NET 类将其所有字段都定义为可分辨字段，这样业务流程就可以使用消息属性的方式来访问所有类成员。 这些类还包括路由类中的升级字段，以便消息可以路由。 所有升级字段也是可分辨字段，这样就可以使用较简单的符号对其进行编程和引用。  
  
 有关使用.NET 类来定义消息的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
## <a name="identifying-orders"></a>标识订单  
 解决方案使用路由信息中的三个字段来标识订单。 这三种的两个标识顺序： 订单标识符 (**OrderID**) 和客户标识符 (**CustomerID**)。 尽管这两个字段可以标识订单，但可能存在订单的多个实例。 例如，客户可能本来订购了一个全新的标准电缆安装，但是随后又打电话来将订单更改为全新的高级电缆安装。 原始订单不太可能在更新的订单到达之前完成。 这样就创建了订单的两个实例。  
  
 来区分的订单的实例，该解决方案使用唯一的订单序列号 (**SeqNum**)。 三个字段**OrderID**， **CustomerID**，和**SeqNum**唯一标识订单的实例。  
  
 最后，因为此解决方案使用递增的数字为**SeqNum**，解决方案可以从原始顺序区分更新-更新具有更高**SeqNum**。  
  
> [!NOTE]
>  解决方案依赖于创建顺序请求分配到升序值的系统**SeqNum**。 请参阅输入的 web 服务中的 ASP 页面背后的代码**CSRMainForm.aspx.cs**，并将请求转换为订单时，映射**CSR_OrderRequest_To_Order.btm**字段的名称涉及到。  
  
## <a name="status"></a>状态  
 **OrderBroker**， **OrderManager**，并用其附属业务流程顺序消息路由部分中的两个字段来跟踪状态：**状态**，和**阶段**。 **状态**字段跟踪订单的状态。 下表描述的值**状态**字段。  
  
|值|设置位置|Description|  
|-----------|---------------|-----------------|  
|ACCEPTED|OrderBroker|订单可以继续进入 OrderManager。|  
|COMPLETED|OrderManager|整个订单处理完成，没有出现任何错误。|  
|ERROR|OrderManager|在订单中检测到错误。|  
|ORDERMANAGER 异常|OrderManager|处理订单时在 OrderManager 中出现异常。|  
|STAGE_n_COMPLETED|OrderManager|指示阶段 n（其中 n 是一个数字）已完成，没有出现任何错误。|  
|STARTED|OrderManager|订单处理已开始。|  
|TERMINATED|OrderManager|订单处理由于取消被停止。|  
  
## <a name="stage"></a>阶段  
 **OrderManager**使用**阶段**字段中的路由的部分，以指示消息的处理阶段。 在筛选器中使用该字段来确定处理消息的附属业务流程。 **OrderManager**最初设置**阶段**为一 (1)。 当顺序终止或完成之后， **OrderManager**设置**阶段**到了业务流程变量的值**停止**。  
  
## <a name="requesttype"></a>RequestType  
 **OrderManager**还使用**RequestType**字段的订单消息。 如果该字段的值为 TERMINATE，则将终止订单。 业务流程将忽略所有其他值**RequestType**字段，并依赖于识别订单更新并将重复项的顺序序列号。 否则为**OrderBroker**设置**RequestType**字段的值的**状态**字段中来自供应商或客户服务系统的消息。  
  
## <a name="ordertypecode-ordertype-and-serviceclass"></a>OrderTypeCode、OrderType 和 ServiceClass  
 顺序的类型在为**OrderTypeCode**字段的订单消息。 **OrderBroker**将其值设置为中的值**OrdTypeCode**字段来自客户服务系统或供应商系统消息中。 下表显示的可能值**OrderTypeCode**:  
  
|值|Description|  
|-----------|-----------------|  
|NS|全新的标准电缆安装。|  
|ND|全新的高级电缆安装。|  
|XS|取消标准电缆安装。|  
|XD|取消高级电缆安装。|  
|CS|更改标准电缆安装。|  
|CD|更改高级电缆安装。|  
|UNKNOWN|未知。|  
  
 更高版本，**验证**业务流程使用业务规则引擎来将这些值翻译成两个单独的字段， **OrderType**和**服务类**。 **验证**业务流程由第一个订单处理阶段， **CableOrder1**。  
  
 下表提供的值**OrderType**:  
  
|OrderTypeCode 值|OrderType 值|  
|--------------------------|---------------------|  
|NS，ND|激活|  
|XS，XD|取消|  
|CS，CD|更改|  
|无效组合。|无效|  
  
 值**服务类**是对应的单个字母， **S**标准，或**D**为豪华。  
  
## <a name="additional-identifiers"></a>其他标识符  
 解决方案还对每个订单使用一个标识符。 此标识符， **RequestId**，需要在所有订单是唯一的。 输入 Web Services 会自动为其分配一个 GUID。 通过成批输入提交的消息必须包括该字段的值。 该字段是**RequestID**顺序架构中。 **OrderBroker**，但是，使用**CSR_OrderRequest**架构处理订单。 该字段显示为**ReqId**此架构中，并且是可分辨的属性。  
  
 此解决方案使用**RequestId**以形成 BAM 跟踪系统中使用的活动标识符。  
  
## <a name="see-also"></a>另请参阅  
 [过程管理器逻辑](../core/process-manager-logic.md)   
 [顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)   
 [构造在用户代码中的消息](../core/constructing-messages-in-user-code.md)   
 [业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)