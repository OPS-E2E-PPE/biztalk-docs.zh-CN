---
title: 使用管道组件读取路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 153f99e68e2c2457db44998b6c955c02af73a6c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396497"
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a>使用管道组件读取路线
在接收管道中的消息可以包含其定义其处理要求 （客户端的路线） 的 SOAP 标头中的元数据。 图 1 说明了使用 ESB 路线和 ESB 调度程序管道组件。  

 ![管道组件读取](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")  

 **图 1**  

 **ESB 路线管道组件的示例**  

 ESB 路线管道组件可用于为上下文属性，可以定义应用的 ESB 处理捕获的元数据的一条消息。  

 以下部分介绍每个组件执行的步骤。  

## <a name="esb-itinerary-pipeline-component-process-steps"></a>ESB 路线管道组件处理步骤  
 在图 1 所示示例中，ESB 路线管道组件执行以下步骤：  

- 它会读取路线 SOAP 标头。 提交的参与方的时他或她将消息提交将填充 SOAP 标头来设置路线。 BizTalk 消息上下文属性的一系列表示 SOAP 标头;这些属性会有所不同，具体取决于所使用的 Web 服务适配器类型。 以下是相关的 Web 服务适配器：  

  - **WCF 适配器。** 此适配器将分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。  


    |                                  属性                                  |
    |------------------------------------------------------------------------------|
    |                             **名称 = 路线**                             |
    | **Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary** |

    > [!NOTE]
    >  默认情况下，Windows Communication Foundation (WCF) 适配器使用名为的 ItineraryDescription.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称作为 BizTalk 上下文**名称**参数，并作为 BizTalk 上下文使用的架构的目标命名空间**Namespace**参数。  

  - **SOAP 适配器。** 此适配器将分析 SOAP 标头，并填充下表中列出的 BizTalk 消息上下文属性。  


    |                              属性                              |
    |----------------------------------------------------------------------|
    |                         **名称 = 路线**                         |
    | **Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** |

    > [!NOTE]
    >  默认情况下，SOAP 适配器使用名为的 Itinerary.xsd （此架构用于生成 ESB 路线 SOAP 标头） 的架构的根名称作为 BizTalk 上下文**名称**参数，并使用作为 SOAP 标头的命名空间BizTalk 上下文**Namespace**参数。  

- 它从消息上下文中删除原始的路线值。  

- 它验证路线并设置特定属性来预设的默认值，如果它们处于 null 路线;例如：  

  - 如果服务计数小于 1，组件会引发异常。  

  - 该组件设置使用的服务计数，该标识符的值的路线根属性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。  

  - 该组件验证服务，设置的标识符，设置当前服务实例 （服务才能处理下一步），并验证任何关联的冲突解决程序。  

  - 该组件设置 BizTalk 段的路线使用以下属性：  

    -   **correlationToken**  

    -   **reqRespTransmitPipelineID**  

    -   **interchangeId**  

    -   **receiveInstanceId**  

    -   **epmRRCorrelationToken**  

  - 该组件将修改后的旅行计划写入到下使用系统 Properties.xsd 架构中定义的属性的表中列出的 BizTalk 消息上下文属性。  


    |                                           属性                                           |
    |------------------------------------------------------------------------------------------------|
    |                                   **名称 = ItineraryHeader**                                   |
    | **Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties** |


  - 组件会升级系统 Properties.xsd 架构中定义的值使用下表中列出的四个 BizTalk 上下文属性。  

    |属性|ReplTest1|  
    |--------------|-----------|  
    |**ServiceName**|在路线中定义的当前服务实例的名称。|  
    |**ServiceType**|设置为**业务流程**或**消息传送**|  
    |**IsRequestResponse**|设置为 **，则返回 True**或**False**|  
    |**ServiceState**|设置为**挂起**|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB 调度程序管道组件处理步骤  
 在图 1 所示示例中，ESB 调度程序管道组件执行以下步骤：  

- 它管理的类型的任何路线步骤执行**Messaging** ，并将提升路线。 ESB 调度程序组件是位置感知，执行消息传送处理周期，可能是根据其位置的逻辑**接收的入站、 发送传输**，**发送入站**，或**接收出站**。 ESB 调度程序管道组件调用 ESB 路线消息传递服务 Esb.config 文件中指定。 默认情况下，此组件用于路由和转换的配置属性相关联与以下服务：  

  - **Microsoft.Practices.ESB.Services.Transform.** 此服务执行针对入站消息的负载的 BizTalk 映射。 服务验证转换要求并更新包含该文档规范名称和消息类型的 BizTalk 上下文属性。 ESB 调度程序管道组件的相应属性中所示，这是转换服务的名称，ESB 调度程序就会执行此服务。  

  - <strong>Microsoft.Practices.ESB.Services.Routing。</strong>此服务使用的冲突解决程序和适配器提供程序框架设置相应的终结点路由信息。 ESB 调度程序管道组件的相应属性中所示，这是路由服务的名称，ESB 调度程序就会执行此服务。
