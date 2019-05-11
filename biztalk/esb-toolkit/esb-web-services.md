---
title: ESB Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c122ecdd-344a-4f76-9c73-bf692d479c09
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08cc136f26133ab760e1c2f0bc099d06d583416a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262037"
---
# <a name="esb-web-services"></a>ESB Web 服务
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含以下 Web 服务：  
  
- <strong>路线接入点 Web 服务。</strong>这些服务接受外部消息并提交以进行处理的消息。 路线的内容包含描述要执行哪些服务的元数据和处理说明。 路由服务定义到应将消息路由，而转换服务指定应如何转换消息的终结点。 这些服务支持单向和双向 （请求-响应） 处理;提供了 ASMX 和 Windows Communication Foundation (WCF) 实现。 路线接入点 Web 服务不是特定于类型 – 消息，因此它们接受任何消息类型。  
  
- <strong>解析程序 Web 服务。</strong>此服务允许外部应用程序调用 Microsoft ESB 解析程序框架来查找 ESB 的终结点冲突解决程序框架支持的解决机制。 该服务还提供了 ASMX 和 WCF 的实现。  
  
- <strong>转换 Web 服务。</strong>此服务允许执行的 Microsoft BizTalk Server 映射无需使用的消息框暂留，扩展映射执行不基于 BizTalk Server 的应用程序的 BizTalk Server 的功能。 该服务加强了 ASMX 和 WCF 的实现。  
  
- <strong>异常处理 Web 服务。</strong>此服务接受来自外部源的异常消息，并使用故障处理器管道的路由将规范化、 跟踪和将异常消息发布到 ESB 管理门户。 该服务加强了 ASMX 和 WCF 的实现。  
  
- <strong>UDDI Web 服务。</strong>此服务后，应用程序和用户，若要查找的终结点的服务名称、 业务提供程序或业务类别; 它还允许应用程序和用户操作的业务提供程序，服务，，类别存储中UDDI 存储库。 这是供 ESB 管理门户和第三方提供商的基础结构服务。  
  
- <strong>BizTalk 操作 Web 服务。</strong>基于此 ASMX 的服务公开有关 BizTalk Server 主机、 业务流程、 应用程序和状态，启用用户和应用程序和主机的状态，而不考虑计算机中的位置轻松查询的第三方信息BizTalk Server 组中。 查询可以包括消息状态和流、 状态更改、 当前服务实例和消息的详细信息。 此外可以更新服务接收位置。 这是供 ESB 管理门户和第三方提供商的基础结构服务。  
  
  有关作为的一部分提供的 Web 服务的详细信息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。