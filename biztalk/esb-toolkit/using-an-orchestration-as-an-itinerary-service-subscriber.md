---
title: 将业务流程用作路线服务订阅方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd787ec23e09bc420939d33c25005dd611f5fd38
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009558"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a>将业务流程用作路线服务订阅方
业务流程也可用作路线服务。 若要参与路线时，必须首先设计业务流程作为直接绑定;若要执行此操作，请使用类似于前一个主题中的发送端口的筛选器订阅[发送端口用作路线服务订阅方](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)。 图 1 显示了合适的业务流程，可以提取满足以下条件的任何消息筛选器表达式的一个示例：  

- **ServiceName = Microsoft.Practices.ESB.Services.Transform**  

- **ServiceState = 挂起**  

- **ServiceType = 业务流程**  

  ![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-业务流程")  

  **图 1**  

  **将参与作为订阅者路线的业务流程的示例筛选表达式**  

  ESB 管道中的验证步骤消息到达时在 Microsoft BizTalk Server 中通过 ESB 接入点，将筛选器属性的属性值写入到 BizTalk 上下文属性的传入消息;这将它们升级到消息上下文。 路线服务始终设置**ServiceName**属性当前处于活动状态的服务来处理接下来，并使用名称服务**ServiceState**属性值为**挂起**。 对于订阅，则必须设置至少第三个以下属性：  

- **ServiceName。** 这是服务的名称，存储在 ESB 路线中，可以是任何名称。 路线使用此名称来标识要执行的服务。  

- **ServiceState。** 这是当前的路线服务步骤，若要执行的状态。 当前服务步骤 （适用于处理下一步） 将始终具有值**挂起**、 任一 ESB 路线管道组件设置，ESB 路线选择器管道组件或代码的调用**提前**路线 API 方法。  

- **服务类型。** 此属性定义的服务，以指明是否源自从业务流程或消息传送子系统在 BizTalk 中的类型。  

- **IsRequestResponse。** 此可选属性必须具有相同的值**IsRequestResponse**服务属性。
