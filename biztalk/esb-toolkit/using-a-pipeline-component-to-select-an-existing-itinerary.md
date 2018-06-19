---
title: 使用管道组件来选择现有路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a733da2348de13120ce37a205b77d2e8194c7790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295885"
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a>使用管道组件来选择现有路线
## <a name="esb-itinerary-selector-pipeline-component"></a>ESB 路线的选择器管道组件  
 使用泛型路线上-渐变提交的消息将会提交没有路线标头。 若要解决适当路线，并将其附加到传入的消息，在负载增加必须提供一种机制，可以将配置为从中央存储库访问路线。  
  
 ESB 路线选择器管道组件使用的解析程序连接字符串，结合专用解析程序解析 （默认情况下，SQL Server） 存储在一个中心存储库服务器端路线的内容。  
  
 当 WCF 上-渐变结合路线静态冲突解决程序中使用 ESB 路线选择器管道组件时，从消息上下文检索的名称和版本 （如在 SOAP 标头中表示），客户端请求路线和用于选择相应的路线。  
  
 默认情况下，ESB 路线选择器管道组件驻留在以下管道：  
  
-   ItinerarySelectReceive  
  
-   ItinerarySelectReceivePassthrough  
  
-   ItinerarySelectReceiveXml  
  
-   ItinerarySelectSendReceive  
  
 以下各节描述了每个组件执行的步骤。  
  
## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a>ESB 路线的选择器管道组件处理步骤  
 ESB 路线选择器管道组件执行以下步骤：  
  
-   正在提交方提交邮件以进行处理。 路线选择器组件使用指定为属性连接字符串，由开发人员，配置的冲突解决程序来确定并从路线存储，基于消息内容或上下文中选择相应的路线。  
  
-   它验证路线，并设置要预设默认值，如果它们处于 null 路线; 的特定属性例如：  
  
    -   如果服务计数等于或大于 1，组件会引发异常。  
  
    -   该组件设置使用的服务计数，标识符的值的路线根特性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。  
  
    -   组件验证服务，设置标识符，设置当前服务实例 （使服务能够处理下一步），并验证任何关联的解析程序。  
  
    -   该组件设置的 Microsoft BizTalk Server 段的路线使用以下属性：  
  
        -   **correlationToken**  
  
        -   **reqRespTransmitPipelineID**  
  
        -   **interchangeId**  
  
        -   **receiveInstanceId**  
  
        -   **epmRRCorrelationToken**  
  
    -   组件将写入使用系统 Properties.xsd 架构中定义的属性下表中列出的 BizTalk 消息上下文属性的修改后的路线。  
  
        |属性|  
        |----------------|  
        |**名称 = ItineraryHeader**|  
        |**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**|  
  
    -   组件提升下使用系统 Properties.xsd 架构中定义的值的表中列出的四个 BizTalk 上下文属性。  
  
        |属性|值|  
        |--------------|-----------|  
        |**ServiceName**|定义在路线中的当前服务实例的名称。|  
        |**ServiceType**|设置为**Orchestration**或**消息传送**。|  
        |**IsRequestResponse**|设置为**True**或**False**。|  
        |**ServiceState**|设置为**挂起**。|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB 调度程序管道组件过程步骤  
 ESB 调度程序管道组件执行以下步骤：  
  
-   它管理的类型的任何路线步骤执行**消息**并提升路线。 位置识别并执行逻辑在消息处理周期，可能是根据其位置 ESB 调度程序组件**接收入站**，**发送传输**，**发送入站**，或**接收出站**。 ESB 调度程序管道组件调用路线 ESB Esb.config 文件中指定的消息传递服务。 默认情况下，此组件用于路由和转换的配置属性是与以下服务：  
  
    -   **Microsoft.Practices.ESB.Services.Transform**。 此服务执行对入站消息的负载的 BizTalk 映射。 服务验证转换要求，并更新包含文档的规范名称和消息类型的 BizTalk 上下文属性。 这是转换服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。  
  
    -   **Microsoft.Practices.ESB.Services.Routing。** 此服务使用的解析程序和适配器提供程序框架设置相应的终结点路由信息。 这是路由服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。