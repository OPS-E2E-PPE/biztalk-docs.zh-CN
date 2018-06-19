---
title: 相关性类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, correlation types
- correlation types, correlation sets
- correlation types
- validating, correlation types
- correlation types, about correlation types
- correlation types, validating
ms.assetid: 1aa5ca5c-c37d-4091-9f5d-331a6b202d4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3da5fad8cb4edc1d6a528f481616b4f10efb71d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237773"
---
# <a name="correlation-types"></a>相关类型
每个关联集取决于**相关类型**，即只需属性的列表。 这些属性可能在消息本身中找到的数据属性或上下文属性，用于描述系统或无关的数据正在消息中传达的消息的详细信息。  
  
 在多个关联集，可以使用相关类型。 如果你需要在不同的值中相关类型的属性关联，则必须创建新的关联集-每个关联集可以只能初始化一次。  
  
 你可以升级属性架构声明的某些属性在消息中的都可以访问与你的业务流程中的属性。 有关详细信息，请参阅[提升属性](../core/promoting-properties.md)。  
  
> [!CAUTION]
>  未设置系统定义属性**BTS。CorrelationToken**每条消息与该键相关联。 这可由引擎按关联消息，并将其设置可能会导致您丢失消息的业务流程。  
  
## <a name="validating-message-correlation-on-send-actions"></a>验证上发送操作的消息相关  
 你可以验证将从您的业务流程发送一条消息的属性以确保它反映中其关联集的属性。 默认情况下，此验证处于禁用状态。 有关如何启用它的信息，请参阅[业务流程引擎的运行时验证](../core/runtime-validation-for-the-orchestration-engine.md)。