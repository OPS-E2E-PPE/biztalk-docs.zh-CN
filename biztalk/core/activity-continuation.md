---
title: 活动继续符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- activities [BAM], code samples
- activities [BAM], continuation tokens
- continuations, activities [BAM]
- code samples, activities [BAM]
ms.assetid: 47d91ae6-77c1-4efb-940f-a7b3a325e5bd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91eadd02e3b0a8792b9b27ea6c913b847b534456
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981990"
---
# <a name="activity-continuation"></a>活动继续符
BAM 活动（也称为业务活动）可涉及多个异类应用程序（例如，一个管道、两个业务流程、一个行业应用程序以及另一个管道）。 BAM 基础结构可以关联来自多个应用程序的一些帮助开发人员 – 名为的概念事件"*延续*，"这在下图中所示。  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a>应用程序  
 活动的第一部分发生在销售应用程序中，活动的第二部分发生在打包和程序集应用程序中，最后，发货流程在发货应用程序中。 每个应用程序使用不同的 Id 为当前的工作单位： 采购订单 (PO) 编号、 销售订单数 (SO) 以及发货订单数 (UPS)。 若要关联两个不同应用程序间的事件，必须执行以下操作：  
  
- 标识继续符，继续符是两个应用程序都可用的唯一数据片断（例如，正在交换的消息部分）。  
  
- 在第一个应用程序中调用 EnableContinuation，然后将继续符与当前 ActivityID 一起传递。  
  
- 不要在第二个应用程序中调用 BeginActivity。  
  
- 使用继续符而不是 ActivityID 在第二个应用程序中触发所有后续事件。  
  
  以下代码示例阐释了如何在三个应用程序之间使用活动继续符：  
  
  **采购订单应用程序**  
  
```  
string oID="PO#123";  
string soID="SO#265";  
es.BeginActivity("PurchaseOrder",poID);  
es.UpdateActivity("PurchaseOrder",poID,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
"CustomerCity","Seattle");  
es.EnableContinuation(  
   "PurchaseOrder",poId,soID);  
es.EndActivity("PurchaseOrder",poID);  
```  
  
 **执行应用程序**  
  
```  
string soID="SO#265";  
string upsID="UPS#97892";  
es.UpdateActivity("PurchaseOrder",soID,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","ProductA");  
es.EnableContinuation(  
   "PurchaseOrder",soID,upsID);  
es.EndActivity("PurchaseOrder",soID);  
```  
  
 **发货应用程序**  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 在代码中使用活动继续符时请遵循以下准则：  
  
-   仅当最终用户必须将不同应用程序的工作视为同一活动的组成部分时才使用继续符。 如果最终用户将每个应用程序中的工作视为有意义的活动，请在每个应用程序中使用单独的活动，并创建活动关系。  
  
-   如果各应用程序中的工作单位不是一对一的关系，则可使用活动关系而不是继续符，例如，当一个销售订单涉及多次发货时。  
  
-   如果向 BAM 同步发送数据（使用 DirectEventStream），并且向所有涉及的组件传播 ActivityID，则不需要使用继续符。  
  
-   如果向 BAM 异步发送数据（使用 BufferedEventStream 或通过业务流程），即使向所有组件传播 ActivityID，也必须使用继续符。 在这种情况下，需要将唯一字符串（例如，应用程序名）作为 ActivityID 的前缀，使每个应用程序中的 ActivityID 各不相同。 这很有必要，因为来自不同应用程序的数据到达 BAM 的顺序可能是随机的，BAM 必须隐藏顺序颠倒的事件以确保得到正确的查询和聚合结果。  
  
-   使用继续符无需在交换更多数据的时候重写应用程序。  
  
## <a name="see-also"></a>请参阅  
  
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)   
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)   
 [BAM 端对端（BizTalk Server 示例）](../core/bam-end-to-end-biztalk-server-sample.md)