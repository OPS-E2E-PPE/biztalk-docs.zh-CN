---
title: 错误处理 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Messaging Engine, errors
- errors, Messaging Engine
- errors, messages
- messages, errors
ms.assetid: ebc889cc-eeac-483c-baf3-407a218f6d14
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4763941600b6e38909f56ee27ec82c8bfb1f246f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348239"
---
# <a name="error-handling"></a>错误处理
消息通过 BizTalk Server 消息传送子系统如下所示的路径包含多个处理和传输的点。 在该路径的每个点，可以在 BizTalk Server 基础结构和应用程序提供的元素，如自定义管道组件和业务流程中出现故障。  
  
 本节以及其中包含在讨论已知阶段的处理和通过 BizTalk Server 配置和应用程序提供的元素，如业务流程如何解决这些失败模式的典型失败模式。 失败的影响包括消息、 诊断捕获和记录，以及操作注意事项的处置。  
  
 一条消息失败时发生的事件包括依赖于失败的位置和失败的消息路由和可恢复交换处理的状态。 下表总结了管道和订阅失败的失败行为及恢复位置。  
  
|失败类型|失败的消息路由|可恢复交换处理|失败行为|恢复位置|  
|------------------|----------------------------|----------------------------------------|----------------------|---------------------|  
|管道|禁用|禁用|消息在管道前被挂起|在管道前。|  
|管道|禁用|Enabled|消息在管道后被挂起|在管道前。 有关可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
|管道|Enabled|禁用|消息已发布与升级的错误报告相关的消息上下文属性|不会挂起消息。 有关路由失败消息的详细信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。|  
|管道|Enabled|Enabled|消息已发布与升级的错误报告相关的消息上下文属性。|不会挂起消息。|  
|订阅|禁用|禁用|消息在管道前被挂起。 创建路由故障报告。|消息将在管道前恢复。 路由故障报告是不可恢复。|  
|订阅|禁用|Enabled|消息在管道后被挂起。 创建路由故障报告。|消息将在管道前恢复。 路由故障报告是不可恢复。 有关可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
|订阅|Enabled|禁用|消息已发布与升级的错误报告相关的消息上下文属性。 创建路由故障报告。|不会挂起消息。 路由故障报告是不可恢复。 有关路由失败消息的详细信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。|  
|订阅|Enabled|Enabled|消息已发布与升级的错误报告相关的消息上下文属性。 创建路由故障报告。|不会挂起消息。 路由故障报告是不可恢复。|  
  
 其中许多枚举模式对应于特定的 BizTalk Server 功能，旨在解决失败模式，例如可恢复交换处理和错误报告的失败。 其他失败模式涉及 BizTalk Server 如何传送到应用程序元素的失败信息，以及接下来如何应用程序元素，如自定义管道组件、 适配器和业务流程失败信息传送给 BizTalk Server.  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用失败的消息路由](../core/using-failed-message-routing.md)  
  
-   [如何为失败消息启用路由功能](../core/how-to-enable-routing-for-failed-messages.md)  
  
-   [使用确认](../core/using-acknowledgments.md)  
  
## <a name="see-also"></a>请参阅  
 [可恢复交换处理](../core/recoverable-interchange-processing.md)   
 [消息失败的类型](../core/types-of-message-failures.md)