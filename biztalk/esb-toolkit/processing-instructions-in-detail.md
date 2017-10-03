---
title: "处理详细信息中的说明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532721c347189f2e3d4db9e57b2afc3aa45b76db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-instructions-in-detail"></a>在详细信息中的处理指令
本主题介绍的格式和定义所需的路线处理的多个上下文属性的系统 Properties.xsd 属性架构结构。 这些属性提升接收和处理通过一条消息时[!INCLUDE[prague](../includes/prague-md.md)]管道; 因为它们是提升的属性，它们都 BizTalk Server 组件访问。 系统 Properties.xsd 属性架构中定义以下属性：  
  
-   **ItineraryHeader。** 此属性包含所有路线的信息和通过一系列路线步骤要调用的路线服务的列表。 路线 API 内部使用此属性。  
  
-   **ServiceName。** 此属性包含要处理的当前路线服务的名称。  
  
-   **ServiceState。** 此属性包含当前路线服务的状态：**挂起**，**完成**，或**Active**。 所有服务都订阅包含一个路线步骤**ServiceState**值**挂起**。  
  
-   **ServiceType。** 此属性定义的路线步骤的类型 (**消息**或**Orchestration**)。  
  
-   **IsRequestResponse。** 此属性定义的消息传递的类型 (单向或请求-响应)。  
  
 路线服务中通过两种方式，具体取决于的值执行路线步骤**ServiceType**属性：  
  
-   路线管道组件执行所有路线步骤**ServiceType**属性**消息**。 开发人员可以扩展此过程，使用自定义管道和路线 API。  
  
-   当**ServiceType**属性是**Orchestration**，业务流程，通过路线上下文属性的订阅激活执行路线的步骤。  
  
 当路线服务处理路线步骤时，此服务负责前移路线和使用发布的进一步处理的新路线上下文将消息调度的订阅的 BizTalk Server 的功能。 路线服务的消息上下文中路线的完全控制，因此可以转到相应的步骤基于其内部的逻辑和消息内容。  
  
 路线处理机制支持消息传送和业务流程路线中的步骤单个路线的组合。 开发人员还可以定义自定义路线服务和配置自定义路线的步骤。  
  
 有关路线的详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。  
  
 有关自定义路线服务和自定义路线步骤的详细信息，请参阅[创建自定义路线服务](../esb-toolkit/creating-a-custom-itinerary-service.md)。