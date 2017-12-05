---
title: "异常管理框架 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b5aebc0-2467-4f48-a385-056507ed1c1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4d4d19caebb667e822b15b937d9045a26493a57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="exception-management-framework"></a>异常管理框架
ESB 异常管理框架提供了用于管理在 BizTalk Server 环境中可能发生的所有异常的统一面向消息的错误生成机制。 ESB 异常管理框架可以接收发布通过异常发布服务，除了从 BizTalk Server 失败消息路由机制的消息的异常消息。  
  
 框架将为错误消息创建、 发布和管理从业务流程，复制与 BizTalk Server 2006 年首次引入的 BizTalk Server 失败的消息路由功能提供一个 API。 此外，框架提供了用于规范化所有异常，丰富关于，将应用业务活动监视 (BAM) 跟踪和发布到异常管理数据库，用于显示的最终输出和报告中 ESB 工具管理门户。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下支持 ESB 异常管理框架的管道组件：  
  
-   **异常错误处理器管道组件。**此组件是使用关闭提升 ESB 异常相关联的管道的一部分包括。 此关闭提升订阅所有 ESB 生成错误消息，除了由路由机制在 BizTalk Server 失败消息生成的异常。 组件路由错误消息到 ESB 异常管理 ESB 管理门户数据库，或可以将它配置为路由到另一个位置。 管道组件还使其更加丰富的所有错误消息和元数据异常，并对它们进行规范化到一种通用格式。  
  
-   **BAM 跟踪管道组件。**此组件会截获，并记录异常信息内的 BizTalk Server BAM 子系统和以独占方式使用异常管理框架内的异常错误处理器管道。 提供与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是一个示例，演示如何使用 BAM 作为可选跟踪设施有关异常信息。  
  
 有关异常管理框架的详细信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。