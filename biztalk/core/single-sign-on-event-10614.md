---
title: 单一登录： 事件 10614 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1f9cd21-3f4b-446f-a4c7-15266973adf1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66d317e63a66ac05d454a6a5a2612aeaae9244b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270213"
---
# <a name="single-sign-on-event-10614"></a>单一登录： 事件 10614
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10614|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_INVALID_TICKET_TIMEOUT|  
|消息正文|票证超时值对全局信息更新无效。%r<br /><br /> 票证超时： %1 分钟 %r<br /><br /> 最小票证超时： 1 分钟 %r<br /><br /> 最大票证超时： %2 分钟 %r<br /><br /> 错误代码： %3|  
  
## <a name="explanation"></a>解释  
 指定的票证超时值无效。  
  
## <a name="user-action"></a>用户操作  
 使用警告消息中提供的信息修正此值。