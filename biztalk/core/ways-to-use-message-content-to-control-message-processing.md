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
ms.openlocfilehash: b0036b9b16faf64d0768d2d5cc7ce1f828cfbffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009358"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a>使用消息内容控制消息处理的方法
有两种类型的属性升级：**可分辨字段**并**属性字段**，后者使用属性架构。 在 BizTalk 编辑器中，这两种类型的属性升级使用来管理**升级属性**对话框中，通过使用可访问该**升级属性**属性**架构**节点。  
  
> [!NOTE]
>  对于可以升级的值有一些限制。 有关详细信息，请参阅中的表[升级属性](../core/promoting-properties.md)。  
  
 您必须基于具体情况，确定要使用的属性升级的类型。 请考虑以下区别**可分辨字段**属性升级和**属性字段**属性升级：  
  
- **可分辨字段**不能参与消息路由，因此它们不显示在筛选器表达式。 它们只能用于业务流程的上下文中，但在发送和接收消息时的系统开销较小。  
  
- **可分辨字段**不具有任何大小限制。 **属性字段**仅限于 255 个字符。  
  
- **可分辨字段**不需要任何单独的项目，而要创建**属性字段**则需要创建和维护属性架构。  
  
  绘制这些注意事项后，您应将节点升级为**属性字段**仅当你想要升级的属性用于消息路由或跟踪。 否则，如果仅要访问从业务流程中升级的属性，您应充分利用这一事实，**可分辨字段**是更廉价、 更轻量、 和更易于使用比**属性字段**。  
  
  通过使用提升的属性**可分辨字段**机制仅可从业务流程中访问，而不能从管道、 端口等访问。 但是，通过使用升级属性**属性字段**，属性架构机制，可从所有这些组件访问。 两者的另一个重要差异是：属性字段值限制为 255 个字符，而可分辨字段值没有这样的限制。  
  
  本部分提供有关这两种属性升级的信息，包括如何使用 BizTalk 编辑器为消息架构建立此类升级属性的有关信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [关于 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)  
  
-   [使用可分辨字段处理实例消息](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [使用属性升级处理实例消息](../core/instance-message-processing-using-property-promotion.md)