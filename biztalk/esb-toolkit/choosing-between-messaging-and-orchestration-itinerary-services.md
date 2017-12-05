---
title: "选择消息传送和业务流程路线服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 694f929a-c830-4906-8e97-4fbd50e70133
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98f48cc93e973b7170c854590359029a60ebf57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="choosing-between-messaging-and-orchestration-itinerary-services"></a>选择消息传送和业务流程路线服务
可以配置路线服务的消息传递子系统或 BizTalk Server 业务流程子系统中出现。 这些 ESB 路线的消息传递服务配置为处理该消息，并且可能在 BizTalk Server 管道中使用 （入口或出口） 执行。 此选项允许开发人员定义完全在其中在管道中的服务将执行。 当然，配置为在业务流程子系统处理服务将执行 BizTalk 业务流程中。  
  
## <a name="esb-itinerary-messaging-services"></a>ESB 路线的消息传递服务  
 在 BizTalk Server 管道中正在处理一条消息，当使用 ESB 路线的消息传递服务减少了消息延迟。 通过在管道中使用单个实现连续服务，它是可以转换多个时间的一条消息并将消息路由到其终结点，与仅单个暂留到消息框数据库。 此外，基于消息的处理消除处理业务流程的其他资源成本。 通常情况下，基于消息的处理资源消耗小，并提供比基于业务流程的处理的处理速度。 在管道，ESB 调度程序和 ESB 调度程序反汇编管道提供的组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]充当消息拦截器并执行基于消息的路线服务、 是否是路由、 转换或自定义服务。 有关配置这些组件的详细信息，请参阅[ESB 调度程序组件](../esb-toolkit/the-esb-dispatcher-component.md)和[ESB 调度程序反汇编组件](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB 路线业务流程服务  
 如果之间或之后业务流程，必须进行动态路由，请对路线服务使用基于业务流程的处理。 默认情况下，基于业务流程的服务作为 XML 文档中接收消息。 路由业务流程使用解析程序管理器尝试解决在路线中标识的终结点。 适配器管理器使用从解析程序管理器的响应来将终结点详细信息提升到消息上下文中，并将消息发布到消息框数据库使用直接绑定逻辑端口。 此时，正则 BizTalk 路由出现，且使用消息的提升的属性配置动态发送端口。  
  
 包含的路线服务业务流程提供创建自定义基于业务流程的路线服务的很好的起点。 有关创建自定义路线服务的详细信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。