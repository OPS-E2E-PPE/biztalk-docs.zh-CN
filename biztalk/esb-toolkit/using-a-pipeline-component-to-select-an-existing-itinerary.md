---
title: 使用管道组件来选择现有路线 |Microsoft Docs
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
ms.openlocfilehash: 9e705bb1c048e4ef84e8783226f7980dc868c2d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396487"
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a>使用管道组件来选择现有路线
## <a name="esb-itinerary-selector-pipeline-component"></a>ESB 路线选择器管道组件  
 使用泛型路线接入提交的消息没有路线标头提交。 若要解决相应路线，并将其附加到传入消息，在负载增加必须提供一种机制，可以配置为从一个中央存储库访问路线。  

 ESB 路线选择器管道组件使用与专用的冲突解决程序，结合使用冲突解决程序连接字符串，若要解决服务器端路线 （默认情况下，SQL Server） 存储在中央存储库中的内容。  

 ESB 路线选择器管道组件中 WCF 接入与路线静态冲突解决程序一起使用时，消息上下文中检索名称和版本 （如 SOAP 标头中所示），客户端请求路线和用于选择相应的路线。  

 默认情况下，ESB 路线选择器管道组件驻留在以下管道：  

- ItinerarySelectReceive  

- ItinerarySelectReceivePassthrough  

- ItinerarySelectReceiveXml  

- ItinerarySelectSendReceive  

  以下部分介绍每个组件执行的步骤。  

## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a>ESB 路线选择器管道组件处理步骤  
 ESB 路线选择器管道组件执行以下步骤：  

- 提交的参与方将提交邮件以进行处理。 路线选择器组件使用指定为属性连接字符串，在开发人员配置的冲突解决程序确定，并从路线存储，基于消息内容或上下文中选择相应的路线。  

- 它验证路线并设置特定属性来预设的默认值，如果它们处于 null 路线;例如：  

  - 如果服务计数小于 1，组件会引发异常。  

  - 该组件设置使用的服务计数，该标识符的值的路线根属性 (**Uuid**)、 开始时间 (**BeginTime**)，以及是否这是单向还是双向的请求 (**IsRequestResponse**)。  

  - 该组件验证服务，设置的标识符，设置当前服务实例 （服务才能处理下一步），并验证任何关联的冲突解决程序。  

  - 该组件设置的 Microsoft BizTalk Server 段的路线使用以下属性：  

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
    |**ServiceType**|设置为**业务流程**或**消息传送**。|  
    |**IsRequestResponse**|设置为 **，则返回 True**或**False**。|  
    |**ServiceState**|设置为**挂起**。|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a>ESB 调度程序管道组件处理步骤  
 ESB 调度程序管道组件执行以下步骤：  

-   它管理的类型的任何路线步骤执行**Messaging** ，并将提升路线。 ESB 调度程序组件是位置感知，执行消息传送处理周期，可能是根据其位置的逻辑**接收的入站**，**发送传输**，**发送入站**，或**接收出站**。 ESB 调度程序管道组件调用 ESB 路线消息传递服务 Esb.config 文件中指定。 默认情况下，此组件用于路由和转换的配置属性相关联与以下服务：  

    -   **Microsoft.Practices.ESB.Services.Transform**. 此服务执行针对入站消息的负载的 BizTalk 映射。 服务验证转换要求并更新包含该文档规范名称和消息类型的 BizTalk 上下文属性。 ESB 调度程序管道组件的相应属性中所示，这是转换服务的名称，ESB 调度程序就会执行此服务。  

    -   **Microsoft.Practices.ESB.Services.Routing.** 此服务使用的冲突解决程序和适配器提供程序框架设置相应的终结点路由信息。 ESB 调度程序管道组件的相应属性中所示，这是路由服务的名称，ESB 调度程序就会执行此服务。