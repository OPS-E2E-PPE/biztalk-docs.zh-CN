---
title: ESB Web 服务 |Microsoft 文档
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
ms.openlocfilehash: 94e6f59770e14e14ed9599d0c26bae187f340e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294373"
---
# <a name="esb-web-services"></a>ESB Web 服务
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含以下 Web 服务：  
  
-   **路线上负载增加 Web 服务。** 这些服务接受外部消息并将其提交处理的消息。 一条路线的内容包含描述要执行哪些服务的元数据和处理说明。 路由服务定义到应将消息路由，而转换服务指定应如何转换消息的终结点。 这些服务支持单向和双向 （请求-响应） 处理;提供了 ASMX 和 Windows Communication Foundation (WCF) 实现。 路线上负载增加 Web 服务不是消息 – 特定类型，因此它们接受任何消息类型。  
  
-   **解析程序 Web 服务。** 此服务允许外部应用程序调用 Microsoft ESB 冲突解决程序框架，以查找 ESB 终结点基于解析冲突解决程序 Framework 支持的机制。 服务还提供 ASMX 和 WCF 的实现。  
  
-   **转换 Web 服务。** 此服务允许执行 Microsoft BizTalk Server 映射而无需消息框持久性，扩展的功能的 BizTalk Server 映射到不基于 BizTalk Server 的应用程序的执行开销。 服务提供 ASMX 和 WCF 的实现。  
  
-   **异常处理 Web 服务。** 此服务接受来自外部源的异常消息和使用错误处理器管道的路由将规范化、 跟踪和将异常消息发布到 ESB 管理门户。 服务提供 ASMX 和 WCF 的实现。  
  
-   **UDDI Web 服务。** 此服务，应用程序和用户，可以查找基于服务名称、 业务提供程序或业务类别的终结点; 它还允许应用程序和用户操作的业务提供程序，而服务，，类别存储在UDDI 存储库。 这是由 ESB 管理门户和第三方提供程序使用的公钥基础结构服务。  
  
-   **BizTalk 操作 Web 服务。** 基于此 ASMX 的服务公开有关 BizTalk Server 主机、 业务流程、 应用程序和状态，启用用户和来轻松地查询的应用程序和主机的状态，而不考虑计算机中的位置的第三方信息BizTalk Server 组中。 查询可以包括消息状态和流、 状态更改、 当前服务实例，和消息详细信息。 此外可以更新服务接收位置。 这是由 ESB 管理门户和第三方提供程序使用的公钥基础结构服务。  
  
 有关作为的一部分提供的 Web 服务的详细信息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。