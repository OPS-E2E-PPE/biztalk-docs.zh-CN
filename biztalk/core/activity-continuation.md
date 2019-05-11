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
ms.openlocfilehash: 4a8615dc75802b643783e3c366159180b740521a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361695"
---
# <a name="activity-continuation"></a>活动继续符
（也称为业务活动） 的 BAM 活动可以跨多个的异类应用程序 （例如，管道、 两个业务流程、 业务线应用程序和另一个管道）。 BAM 基础结构可以关联来自多个应用程序的一些帮助开发人员 – 名为的概念事件"*延续*，"这在下图中所示。  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a>应用程序  
 活动的第一部分发生在销售应用程序中，活动的第二部分发生在打包和程序集的应用程序，并最后，发货现已推出配送应用程序。 每个应用程序使用不同的 Id 为当前的工作单位： 采购订单 (PO) 编号、 销售订单数 (SO) 以及发货订单数 (UPS)。 若要将两个不同的应用程序之间的事件相关联，必须：  
  
- 标识继续符，可供这两个应用程序 （例如，正在交换的消息的一部分） 的数据的一个唯一的。  
  
- 在第一个应用程序中调用 EnableContinuation 并传递与当前 ActivityID 一起继续标记。  
  
- 请勿在第二个应用程序中调用 BeginActivity。  
  
- 通过使用继续标记而不 ActivityID 触发第二个应用程序中的所有后续事件。  
  
  下面的代码示例演示如何使用三个应用程序之间的活动继续符：  
  
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
  
 请遵循这些准则在代码中使用活动继续符：  
  
-   当最终用户必须将不同的应用程序的工作视为同一活动的一部分时，仅使用继续符。 每个应用程序使用单独的活动并创建活动关系，如果最终用户视图中有意义的活动的每个应用程序的工作。  
  
-   如果应用程序中的工作单位不具有一对一的关系，您可以使用活动关系而不是继续符，例如，销售订单涉及多次发货存在时。  
  
-   如果以同步方式将数据发送到 BAM （使用 DirectEventStream） 和 ActivityID 传播到所有涉及的组件，则不需要使用继续符。  
  
-   如果以异步方式将数据发送到 BAM (使用 BufferedEventStream 或通过业务流程)，则即使向所有组件传播 ActivityID，必须使用继续符。 在这种情况下，需要通过前缀使用唯一字符串 （例如，应用程序名称） 在每个应用程序中使用 activityid 各不相同。 这是必需的因为不同的应用程序中的数据可能会到达 BAM 的随机顺序，BAM 必须隐藏顺序颠倒的事件，以确保正确的查询和聚合结果。  
  
-   延续任务不需要重新编写您的应用程序交换更多数据。  
  
## <a name="see-also"></a>请参阅  
  
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)   
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)   
 [BAM 端对端（BizTalk Server 示例）](../core/bam-end-to-end-biztalk-server-sample.md)