---
title: 无法将消息路由到批处理业务流程，因为无法确定编码类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d2ee38d-22c0-4fcf-bb68-b2ef00088c4c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e74a5e8768115af8c70cc54278552d19f7532371
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388642"
---
# <a name="the-message-cannot-be-routed-to-the-batching-orchestration-as-the-encoding-type-could-not-be-determined"></a>无法将消息路由到批处理业务流程，因为无法确定编码类型
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| 产品版本 |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    事件 ID     |                                                                                              -                                                                                              |
|  事件源   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                    |
|    组件    |                                                                                       批处理引擎                                                                                       |
|  符号名称  |                                                                                     UnknownEncodingType                                                                                     |
|  消息正文   | 消息不能路由到批处理业务流程，因为无法确定编码类型。 对于要批处理的消息，编码类型应为 X12 或 EDIFACT。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明未将非 EDI 批处理元素路由到批处理业务流程实例，即使事务集符合批处理的筛选条件也是如此。 无法将事务集路由到批处理业务流程实例，因为 EDI.EncodingType 上下文属性未使用 X12 的值 0 或 EDIFACT 的值 1 升级。 当 BatchMarker 管道组件将批处理元素路由到路由业务流程，但非 EDI 批处理元素未通过映射转换为 EDI 消息时会发生此错误。 因此，路由业务流程无法从 EDI 标头确定编码类型。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保先将非 EDI 消息通过映射转换为 EDI 消息，然后再将该消息路由到路由业务流程。 还必须包含自定义的管道组件（具有 BatchMarker 组件）或自定义的业务流程才能处理非 EDI 批处理元素。 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的“装配批处理的 EDI 交换”。