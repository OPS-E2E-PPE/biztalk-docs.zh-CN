---
title: "错误处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Messaging Engine, errors
- errors, Messaging Engine
- errors, messages
- messages, errors
ms.assetid: ebc889cc-eeac-483c-baf3-407a218f6d14
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cbf0d898f7af193220cf8f1c24e809aefa1b782
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-handling"></a>错误处理
消息通过 BizTalk Server 消息传送子系统时所遵循的路径包含多个处理点和传输点。 在该路径上的每个点，BizTalk Server 基础结构和应用程序提供的元素（例如自定义管道组件和业务流程）中都有可能出现失败。  
  
 本节以及其中涉及的章节将讨论处理的已知阶段的典型失败模式，以及如何通过 BizTalk Server 配置和应用程序提供的元素（例如业务流程）来解决这些失败模式。 失败的影响包括消息的处理、捕获和记录的诊断以及操作注意事项。  
  
 消息失败时所发生的事件与失败位置、失败消息路由的状态以及可恢复的交换处理的状态相关。 下表简要列出了管道失败和订阅失败的失败行为及恢复位置。  
  
|故障类型|失败消息路由|可恢复的交换处理|失败行为|恢复位置|  
|------------------|----------------------------|----------------------------------------|----------------------|---------------------|  
|管道|禁用|禁用|消息在管道前被挂起|在管道前。|  
|管道|禁用|已启用|消息在管道后被挂起|在管道前。 有关可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
|管道|已启用|禁用|消息已发布，而且升级了与错误报告相关的消息上下文属性|消息未被挂起。 有关路由失败消息的详细信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。|  
|管道|已启用|已启用|消息已发布，而且升级了与错误报告相关的消息上下文属性。|消息未被挂起。|  
|订阅|禁用|禁用|消息在管道前被挂起。 创建了路由故障报告。|消息将在管道前恢复。 路由故障报告不可恢复。|  
|订阅|禁用|已启用|消息在管道后被挂起。 创建了路由故障报告。|消息将在管道前恢复。 路由故障报告不可恢复。 有关可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
|订阅|已启用|禁用|消息已发布，而且升级了与错误报告相关的消息上下文属性。 创建了路由故障报告。|消息未被挂起。 路由故障报告不可恢复。 有关路由失败消息的详细信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。|  
|订阅|已启用|已启用|消息已发布，而且升级了与错误报告相关的消息上下文属性。 创建了路由故障报告。|消息未被挂起。 路由故障报告不可恢复。|  
  
 在这些列举的失败模式中，许多都对应于旨在解决失败模式的 BizTalk Server 的特定功能，例如可恢复的交换处理和错误报告。 其他失败模式涉及 BizTalk Server 如何将失败信息传送给应用程序元素，以及应用程序元素（例如自定义管道组件、适配器和业务流程）接下来如何将失败信息传送给 BizTalk Server。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用失败的邮件路由](../core/using-failed-message-routing.md)  
  
-   [如何允许路由失败消息](../core/how-to-enable-routing-for-failed-messages.md)  
  
-   [使用确认](../core/using-acknowledgments.md)  
  
## <a name="see-also"></a>另请参阅  
 [可恢复的交换处理](../core/recoverable-interchange-processing.md)   
 [类型的消息失败](../core/types-of-message-failures.md)