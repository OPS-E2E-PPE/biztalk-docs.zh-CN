---
title: "使用管道组件读取一条路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bceec4df732247be043e006b52c7abbfbf6a6b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a>使用管道组件读取一条路线
在接收管道到达的消息可以包含在其定义其处理要求 （客户端路线） 的 SOAP 标头的元数据。 图 1 说明 ESB 路线和 ESB 调度程序管道组件的用法。  
  
 ![管道组件读取](../esb-toolkit/media/ch4-pipelinecomponentread.gif "第四章第 4 PipelineComponentRead")  
  
 **图 1**  
  
 **ESB 路线管道组件的示例**  
  
 ESB 路线管道组件可以用于捕获从消息的元数据作为可以定义 ESB 由应用处理的上下文属性。  
  
 以下各节描述了每个组件执行的步骤。  
  
## <a name="esb-itinerary-pipeline-component-process-steps"></a>ESB 路线管道组件过程步骤  
 在图 1 所示示例中，ESB 路线管道组件执行以下步骤：  
  
-   读取路线 SOAP 标头。 正在提交方的时他或她将消息提交将填充的 SOAP 标头设置路线。 BizTalk 消息上下文属性的一系列表示 SOAP 标头;这些属性因所使用的 Web 服务适配器的类型而异。 以下是相关的 Web 服务适配器：  
  
    -   **WCF 适配器。** 此适配器分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。  
  
        |属性|  
        |----------------|  
        |**名称 = 路线**|  
        |**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**|  
  
        > [!NOTE]
        >  默认情况下，Windows Communication Foundation (WCF) 适配器所使用的作为 BizTalk 上下文的名为的 ItineraryDescription.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称**名称**自变量，它作为 BizTalk 上下文使用的架构的目标命名空间和**Namespace**自变量。  
  
    -   **SOAP 适配器。** 此适配器分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。  
  
        |属性|  
        |----------------|  
        |**名称 = 路线**|  
        |**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**|  
  
        > [!NOTE]
        >  默认情况下，SOAP 适配器所使用的作为 BizTalk 上下文的名为的 Itinerary.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称**名称**自变量，并使用作为 SOAP 头的命名空间BizTalk 上下文**Namespace**自变量。  
  
-   它会从消息上下文中删除原始路线值。  
  
-   它验证路线，并设置要预设默认值，如果它们处于 null 路线; 的特定属性例如：  
  
    -   如果服务计数等于或大于 1，组件会引发异常。  
  
    -   该组件设置使用的服务计数，标识符的值的路线根特性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。  
  
    -   组件验证服务，设置标识符，设置当前服务实例 （使服务能够处理下一步），并验证任何关联的解析程序。  
  
    -   该组件设置使用以下属性路线 BizTalk 段：  
  
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
        |**ServiceType**|设置为**Orchestration**或**消息传送**|  
        |**IsRequestResponse**|设置为**True**或**False**|  
        |**ServiceState**|设置为**挂起**|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB 调度程序管道组件过程步骤  
 在图 1 所示示例中，ESB 调度程序管道组件执行以下步骤：  
  
-   它管理的类型的任何路线步骤执行**消息**并提升路线。 位置识别并执行逻辑在消息处理周期，可能是根据其位置 ESB 调度程序组件**接收入站，发送传输**，**发送入站**，或**接收出站**。 ESB 调度程序管道组件调用路线 ESB Esb.config 文件中指定的消息传递服务。 默认情况下，此组件用于路由和转换的配置属性是与以下服务：  
  
    -   **Microsoft.Practices.ESB.Services.Transform。** 此服务执行对入站消息的负载的 BizTalk 映射。 服务验证转换要求，并更新包含文档的规范名称和消息类型的 BizTalk 上下文属性。 这是转换服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。  
  
    -   **Microsoft.Practices.ESB.Services.Routing。**此服务使用的解析程序和适配器提供程序框架设置相应的终结点路由信息。 这是路由服务的名称，因为它将出现在 ESB 调度程序管道组件的相应属性，ESB 调度程序就会执行此服务。