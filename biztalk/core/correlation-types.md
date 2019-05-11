---
title: 相关类型 |Microsoft Docs
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
ms.openlocfilehash: eea1801632fbeea4eb598f3973923d2436e1d813
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390218"
---
# <a name="correlation-types"></a>相关类型
每个相关集基于**相关类型**，即只需的属性列表。 这些属性可能是数据属性，可在消息本身或上下文属性，描述系统或与消息中所传达的数据无关的消息的详细信息。  
  
 在多个相关集，可以使用相关类型。 如果你需要对相关类型中的属性的不同值相关联，则必须创建新的相关集，可以一次初始化每个相关集。  
  
 你可以升级属性架构声明一条消息中的某些属性是可以访问您的业务流程中的属性。 有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
> [!CAUTION]
>  未设置系统定义的属性**BTS。CorrelationToken**每条消息与该键相关联。 这由关联消息，该引擎使用，并将其设置可能会导致您丢失消息的业务流程。  
  
## <a name="validating-message-correlation-on-send-actions"></a>验证对发送操作消息相关性  
 你可以验证将从您的业务流程发送消息的属性以确保它反映了其相关集中的属性。 默认情况下，此验证已禁用。 有关如何启用它的信息，请参阅[业务流程引擎的运行时验证](../core/runtime-validation-for-the-orchestration-engine.md)。