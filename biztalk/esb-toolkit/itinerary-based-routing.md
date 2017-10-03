---
title: "基于路线的路由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fbfe8877202a2f691bd30fd2b56fc3032240ee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing"></a>基于路线的路由
核心功能之一[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是基于路线的路由的设置，简化了企业级消息传送应用程序开发并减少成本来维护大量的静态发送端口和接收位置。  
  
 一条路线组成的服务执行的列表 （其中可以包含路由、 转换和自定义服务） 和解决执行其中每个服务所需的元数据所需的配置信息。 例如，一个阶段的路线可能路由服务;与此服务关联的解决方案说明可能指示该服务可以执行特定的目标终结点将路由到的有关信息的通用、 描述、 发现和集成 (UDDI) 或业务规则引擎 (BRE) 查找消息。  
  
 路线可以附加到入站消息中，通过以下方式：  
  
-   客户端提交的消息不包含任何与路线相关的数据。 接收管道解析，检索，并附加相应路线基于消息内容或上下文。  
  
-   客户端提交的消息可以包含定义路线引用数据，其中包含路线的名称和版本，以及业务活动监视 (BAM) 跟踪的唯一标识符的 SOAP 标头。 接收管道评估此信息，并从 ESBItineraryDb 数据库中检索相应的路线。  
  
-   客户端提交条消息可以具有一个路线 SOAP 标头，其中包含路线的整个内容。 此设计不建议，并且应仅用于测试目的使用。  
  
 为入站消息解决路线后，接收管道将提升为消息的上下文，从而使可用于访问由订阅此消息的任何 Microsoft BizTalk Server 组件的属性的路线数据。 BizTalk Server 组件可以获取当前路线步骤的详细信息，完成所需的处理，和/或使路线前进到下一步的步骤。 这样将导致下一个服务中路线来处理该消息，根据发布-订阅功能的 BizTalk Server。  
  
 有关 ESB 动态解决机制、 转换、 路线处理和消息创建的信息，请参阅[主要方案和开发任务](../esb-toolkit/key-scenarios-and-development-tasks.md)。