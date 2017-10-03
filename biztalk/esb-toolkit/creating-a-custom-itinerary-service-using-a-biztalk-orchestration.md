---
title: "创建自定义路线服务使用 BizTalk 业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723c0bc93192267f404d42e7fe859bb37ea59895
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a>创建自定义路线服务使用 BizTalk 业务流程
是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持使用业务流程的路线步骤执行。 可以按根据功能要求，其中可能包括以下 Microsoft BizTalk Server 业务流程来实现自定义的路线服务：  
  
-   多个服务调用 (如所示：[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))  
  
-   协议中介和消息关联 (例如，HTTP MQSeries)  
  
-   复杂的路由决策基于消息扩充从外部数据源  
  
-   业务处理逻辑  
  
 使用 BizTalk Server 业务流程来实现的每个路线服务负责以下：  
  
-   异常和错误处理使用 ESB 异常处理的框架或支持重新提交 （单向路线） 的可选的自定义异常处理程序  
  
-   前移路线和发布通过 BizTalk 服务器的出站消息，供执行下一步路线服务的步骤  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a>若要创建自定义路线服务使用 BizTalk Server 业务流程  
  
1.  创建包含新的业务流程; 新的 BizTalk Server 项目例如，MyCustomeItineraryService.odx。  
  
2.  添加对以下程序集引用：  
  
    -   **Microsoft.Practices.ESB.Itinerary**  
  
    -   **Microsoft.Practices.ESB.Itinerary.Schemas**  
  
    -   **Microsoft.Practices.ESB.ExceptionHandling**  
  
    -   **Microsoft.Practices.ESB.ExceptionHandling.Faults**  
  
3.  定义逻辑的直接绑定接收端口和激活的接收形状中业务流程。  
  
4.  定义订阅筛选器来激活消息路线上下文从业务流程，以便业务流程执行**MyCustomItineraryService**步骤。 下面的代码演示了合适的筛选器的示例。  
  
    ```csharp  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
        == "MyCustomItineraryService")   
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
        == "Orchestration")  
    ```  
  
5.  定义类型的业务流程**Microsoft.Practices.ESB.Itinerary.ItineraryStep**。 下面的代码中所示，请将表达式活动添加到填充此变量，业务流程。  
  
    ```csharp  
    // Retrieve the current itinerary step.  
    itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
    step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
    itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
    step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
    ```  
  
6.  将自定义实现添加到创建出站消息有关的下一步的路线步骤; 路线例如，OutboundMsg。  
  
7.  前进路线使用使用从入站消息的消息上下文的以下表达式活动。  
  
    ```csharp  
    OutboundMessage(*) = InboundMessage(*);   
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
8.  通过直接绑定发送端口来激活下一步路线服务发送更新路线的出站消息。  
  
 有关实现自定义路线服务使用 BizTalk Server 业务流程的详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)和[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。