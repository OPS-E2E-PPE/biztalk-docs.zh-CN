---
title: "如何使用到控件的消息内容消息处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73d356496d07bb2227aa514ee68f2a2a51e2291b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a>使用消息内容控制消息处理的方法
有两种类型的属性提升：**可分辨字段**和**属性字段**，后者将使用属性架构。 在 BizTalk 编辑器中，你通过进行管理这两种类型的属性提升**升级属性**对话框中，这是可访问通过使用**升级属性**属性**架构**节点。  
  
> [!NOTE]
>  对于可以升级的值有一些限制。 有关详细信息，请参阅中的表[提升属性](../core/promoting-properties.md)。  
  
 您必须基于具体情况，确定要使用的属性升级的类型。 请考虑以下区别**可分辨字段**属性提升和**属性字段**属性提升：  
  
-   **可分辨字段**不能参与邮件路由，因此它们不会出现在筛选表达式中。 它们只能用于业务流程的上下文中，但在发送和接收消息时的系统开销较小。  
  
-   **可分辨字段**不具有任何大小限制。 **属性字段**限于 255 个字符。  
  
-   **可分辨字段**不需要任何单独的项目，而要创建**属性字段**需要的创建和维护属性架构。  
  
 绘制这些注意事项时，你应升级节点**属性字段**仅当你想要使用提升的属性路由或跟踪消息。 否则，如果你仅要访问从你的业务流程内提升的属性，你应充分利用这一事实，**可分辨字段**是更廉价、 更轻量，和更简单易用的比**属性字段**。  
  
 通过使用提升的属性**可分辨字段**机制仅可从业务流程内访问，而不能从管道、 端口和等等访问。 另一方面，属性提升通过**属性字段**，从所有这些组件可访问属性架构机制。 两者的另一个重要差异是：属性字段值限制为 255 个字符，而可分辨字段值没有这样的限制。  
  
 本部分提供有关这两种属性升级的信息，包括如何使用 BizTalk 编辑器为消息架构建立此类升级属性的有关信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [有关 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)  
  
-   [实例消息处理使用可分辨字段](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [使用属性提升实例消息处理](../core/instance-message-processing-using-property-promotion.md)