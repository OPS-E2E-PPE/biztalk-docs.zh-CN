---
title: 处理详细信息中的说明 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d867737599369ad8ff07780080b16f5ce0f6f2fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005574"
---
# <a name="processing-instructions-in-detail"></a>在详细信息的处理指令
本主题介绍的格式和系统 Properties.xsd 属性架构，用于定义路线处理所需的多个上下文属性的结构。 这些属性将升级时接收并处理通过 BizTalk Server 管道; 一条消息由于它们是升级的属性，它们都可以访问 BizTalk Server 组件。 系统 Properties.xsd 属性架构中定义以下属性：  
  
- **ItineraryHeader。** 此属性包含所有路线信息和路线服务通过一系列的路线步骤要调用的列表。 路线 API 在内部使用此属性。  
  
- **ServiceName。** 此属性包含要处理的当前路线服务的名称。  
  
- **ServiceState。** 此属性包含当前的路线服务的状态：**挂起**，**完成**，或**Active**。 所有服务都订阅包含行程步骤**ServiceState**的值**挂起**。  
  
- **服务类型。** 此属性定义路线步骤的类型 (**Messaging**或**业务流程**)。  
  
- **IsRequestResponse。** 此属性定义的消息类型 (单向或请求-响应)。  
  
  路线服务中有两种，具体取决于值执行路线步骤**ServiceType**属性：  
  
- 路线的管道组件执行所有路线步骤**ServiceType**的属性**消息传送**。 开发人员可以扩展此过程使用的自定义管道和路线 API。  
  
- 当**ServiceType**属性是**业务流程**，由对路线上下文属性的订阅激活业务流程执行路线的步骤。  
  
  当路线服务处理行程步骤时，此服务负责提前路线和调度的消息的新的路线上下文以进行进一步处理使用发布的订阅的 BizTalk Server 功能。 路线服务具有完全控制权限的消息上下文中路线，并可以转到相应的步骤基于其内部逻辑和消息内容。  
  
  路线的处理机制支持单个路线中的消息传送和业务流程路线步骤的组合。 开发人员还可以定义自定义路线服务和配置自定义路线的步骤。  
  
  关于路线的详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。  
  
  有关自定义路线服务和自定义路线步骤的详细信息，请参阅[创建自定义路线服务](../esb-toolkit/creating-a-custom-itinerary-service.md)。