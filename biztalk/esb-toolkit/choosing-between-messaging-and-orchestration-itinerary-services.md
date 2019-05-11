---
title: 选择消息传送和业务流程路线服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 694f929a-c830-4906-8e97-4fbd50e70133
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856542d5cb44a352f91cea5f64c56febb0059670
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302279"
---
# <a name="choosing-between-messaging-and-orchestration-itinerary-services"></a>选择消息传送和业务流程路线服务
路线服务可以配置为在消息传送子系统或 BizTalk Server 业务流程子系统中出现。 这些 ESB 路线消息传递服务配置为处理该消息，并且会在 BizTalk Server 管道 （接入点或关闭接入点） 中执行。 此选项允许开发人员定义完全在管道中该服务将执行位置。 正常情况下，将 BizTalk 业务流程中执行服务配置为在业务流程子系统中的过程。  
  
## <a name="esb-itinerary-messaging-services"></a>ESB 路线消息传递服务  
 在 BizTalk Server 管道中处理一条消息，则使用 ESB 路线消息传递服务可以减少消息延迟。 通过在单个管道中实现连续服务，则可以转换多个时间的消息并将消息路由到其终结点具有一个持久化到 Messagebox 数据库。 此外，基于消息的处理消除了业务流程处理的其他资源成本。 通常情况下，基于消息的处理资源消耗小，并提供比基于业务流程的处理更快的处理。 ESB 调度程序和 ESB 调度程序反汇编中的管道，管道组件提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]充当消息拦截器，并执行基于消息传送的路线服务、 它是路由、 转换或自定义服务。 有关配置这些组件的详细信息，请参阅[ESB 调度程序组件](../esb-toolkit/the-esb-dispatcher-component.md)并[ESB 调度程序反汇编组件](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB 路线的业务流程服务  
 如果之间或业务流程进程之后，必须进行动态路由，则使用路线服务基于业务流程的处理。 默认情况下，基于业务流程的服务收到的消息为 XML 文档。 路由业务流程使用冲突解决程序管理器来尝试解决在路线中确定的终结点。 适配器管理器使用响应从解析程序管理器来将终结点详细信息升级到消息上下文，并将消息发布到 Messagebox 数据库使用直接绑定逻辑端口。 此时，正则 BizTalk 路由会发生，并且使用消息的升级的属性配置动态发送端口。  
  
 包括的路线服务业务流程创建自定义基于业务流程的路线服务提供很好的起点。 有关创建自定义路线服务的详细信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。