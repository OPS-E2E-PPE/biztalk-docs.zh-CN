---
title: 创建自定义路线服务使用 BizTalk 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa36acc84358a8e91a0b9daaa4370270fb5860b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988534"
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a>创建自定义路线服务使用 BizTalk 业务流程
是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持使用业务流程路线步骤执行。 可以为基于应用的功能需求，其中可能包括以下 Microsoft BizTalk Server 业务流程来实现自定义路线服务：  
  
- 多个服务调用 (如所示[安装和运行分散-集中示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))  
  
- 协议中介和消息相关 (例如，HTTP MQSeries)  
  
- 复杂的路由决策基于消息收集从外部数据源  
  
- 业务处理逻辑  
  
  使用 BizTalk Server 业务流程实现的每个路线服务负责以下：  
  
- 异常和错误处理使用 ESB 异常处理框架或可选的自定义异常处理程序支持重新提交 （单向路线）  
  
- 前移路线和发布通过 BizTalk Server 的出站消息，以便可以执行下一步的路线服务步骤  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a>若要创建使用 BizTalk Server 业务流程的自定义路线服务  
  
1. 创建包含新的业务流程; 的新 BizTalk Server 项目例如，MyCustomeItineraryService.odx。  
  
2. 添加对以下程序集的引用：  
  
   -   **Microsoft.Practices.ESB.Itinerary**  
  
   -   **Microsoft.Practices.ESB.Itinerary.Schemas**  
  
   -   **Microsoft.Practices.ESB.ExceptionHandling**  
  
   -   **Microsoft.Practices.ESB.ExceptionHandling.Faults**  
  
3. 定义逻辑直接绑定接收端口和激活的接收形状在业务流程中。  
  
4. 定义订阅筛选器，以便该业务流程执行激活业务流程从消息路线上下文**MyCustomItineraryService**步骤。 下面的代码显示了合适的筛选器的示例。  
  
   ```csharp  
   (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
       == "MyCustomItineraryService")   
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
       == "Orchestration")  
   ```  
  
5. 定义类型的业务流程**Microsoft.Practices.ESB.Itinerary.ItineraryStep**。 在下面的代码所示，添加到填充此变量的业务流程的表达式活动。  
  
   ```csharp  
   // Retrieve the current itinerary step.  
   itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
   step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
   itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
   step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
   ```  
  
6. 将自定义实现添加到创建的出站消息的下一步的路线步骤; 路线例如，OutboundMsg。  
  
7. 请继续学习路线使用下面的表达式活动，将使用从入站消息的消息上下文。  
  
   ```csharp  
   OutboundMessage(*) = InboundMessage(*);   
   itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
   ```  
  
8. 通过用于激活的下一步的路线服务的直接绑定发送端口发送的出站消息的已更新的路线。  
  
   有关实现使用 BizTalk Server 业务流程的自定义路线服务的详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)和[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。