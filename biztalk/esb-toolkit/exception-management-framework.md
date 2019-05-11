---
title: 异常管理框架 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b5aebc0-2467-4f48-a385-056507ed1c1e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ed120355d2e1623c22f717252dc632526a641d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268788"
---
# <a name="exception-management-framework"></a>异常管理框架
ESB 异常管理框架提供用于管理 BizTalk Server 环境中可能发生的所有异常的统一面向消息的错误生成机制。 ESB 异常管理框架可以接收通过异常发布服务，除了消息从 BizTalk Server 失败消息路由机制发布的异常消息。  
  
 该框架提供了一个 API 的错误消息创建、 发布和管理从业务流程进程，复制首次随 BizTalk Server 2006 的 BizTalk Server 失败的消息路由功能。 此外，该框架提供用于规范化丰富，将业务活动监视 (BAM) 跟踪和发布最终输出到显示异常管理数据库和 reporting ESB 中应用的所有异常工具管理门户。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下管道组件支持 ESB 异常管理框架：  
  
- <strong>异常故障处理器管道组件。</strong>此组件是作为带关闭斜坡 ESB 异常相关联的管道的一部分。 此关闭 ramp 订阅所有 ESB 生成错误消息，以及由 BizTalk Server 失败消息路由机制生成的异常。 组件路由错误消息到 ESB 异常管理 ESB 管理门户中数据库，或可以将它配置为路由到另一个位置。 管道组件还使其更加丰富的所有错误消息和异常的元数据，并将其规范化为通用格式。  
  
- <strong>BAM 跟踪管道组件。</strong>此组件会截获，并记录 BizTalk Server BAM 子系统中的异常信息，并以独占方式由异常管理框架中的异常故障处理器管道。 提供与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是一个示例，演示如何使用 BAM 作为可选跟踪设施异常信息。  
  
  异常管理框架有关的详细信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。