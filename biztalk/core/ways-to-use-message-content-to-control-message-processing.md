---
title: 如何使用消息内容控制消息处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7791957dba89fab54813212fce3ecbd2c39fe19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393624"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a>使用消息内容控制消息处理的方法
有两种类型的属性升级：**可分辨字段**并**属性字段**，后者使用属性架构。 在 BizTalk 编辑器中，这两种类型的属性升级使用来管理**升级属性**对话框中，通过使用可访问该**升级属性**属性**架构**节点。  
  
> [!NOTE]
>  有一些限制，您可以将升级的值。 有关详细信息，请参阅中的表[升级属性](../core/promoting-properties.md)。  
  
 您必须决定哪种类型的属性升级为使用基于你的方案的详细信息。 请考虑以下区别**可分辨字段**属性升级和**属性字段**属性升级：  
  
- **可分辨字段**不能参与消息路由，因此它们不显示在筛选器表达式。 它们只是业务流程的上下文中可用，但它们具有更少的开销时发送和接收消息。  
  
- **可分辨字段**不具有任何大小限制。 **属性字段**仅限于 255 个字符。  
  
- **可分辨字段**不需要任何单独的项目，而要创建**属性字段**则需要创建和维护属性架构。  
  
  绘制这些注意事项后，您应将节点升级为**属性字段**仅当你想要升级的属性用于消息路由或跟踪。 否则，如果仅要访问从业务流程中升级的属性，您应充分利用这一事实，**可分辨字段**是更廉价、 更轻量、 和更易于使用比**属性字段**。  
  
  通过使用提升的属性**可分辨字段**机制仅可从业务流程中访问，而不能从管道、 端口等访问。 但是，通过使用升级属性**属性字段**，属性架构机制，可从所有这些组件访问。 另一个重要区别是属性字段值限制为 255 个字符，并且可分辨的字段的值有没有此类限制。  
  
  本部分提供有关这两种类型的属性升级，包括有关如何建立此类信息如何通过使用 BizTalk 编辑器中升级为消息架构的属性的信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [关于 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)  
  
-   [使用可分辨字段处理实例消息](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [使用属性升级处理实例消息](../core/instance-message-processing-using-property-promotion.md)