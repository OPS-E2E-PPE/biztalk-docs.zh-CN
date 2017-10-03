---
title: "为路线服务的订阅服务器使用一个业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f496884d0aed8d5f351f681ca8cfe59e05684240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a>为路线服务的订阅服务器使用一个业务流程
业务流程还可以充当路线的服务。 若要参与路线，必须首先设计为直接绑定; 业务流程若要执行此操作，使用类似于在上一主题中，发送端口的筛选器订阅[为路线服务的订阅服务器使用发送端口](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)。 图 1 显示合适的业务流程，以拾取满足下列条件的任何消息筛选器表达式的示例：  
  
-   **ServiceName = Microsoft.Practices.ESB.Services.Transform**  
  
-   **ServiceState = 挂起**  
  
-   **ServiceType = 业务流程**  
  
 ![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "第四章第 4 业务流程")  
  
 **图 1**  
  
 **适用于将参与作为订阅服务器路线业务流程的示例筛选器表达式**  
  
 当消息到达时通过 ESB 入口 Microsoft BizTalk Server 中时，则 ESB 管道中的验证步骤将筛选器属性的属性值写入的传入消息中; BizTalk 上下文属性这将它们升级到消息上下文。 路线服务始终设置**ServiceName**处理接下来，并与服务的名称的当前处于活动状态服务的属性**ServiceState**属性值**挂起**。 对于订阅，你必须设置至少第一个三个以下属性：  
  
-   **ServiceName。** 这是服务的名称，因为存储在 ESB 路线，并可以是任何名称。 路线使用此名称来标识要执行的服务。  
  
-   **ServiceState。** 这是当前的路线服务步骤，若要执行的状态。 当前服务步骤 （适用于处理下一步） 将始终具有值**挂起**、 任一 ESB 路线管道组件设置，ESB 路线选择器管道组件，或代码调用**高级**路线 API 方法。  
  
-   **ServiceType。** 此属性定义的服务，，该值指示是否来自业务流程或 BizTalk 中的消息传递子系统的类型。  
  
-   **IsRequestResponse。** 此可选属性必须具有相同的值**IsRequestResponse**服务属性。