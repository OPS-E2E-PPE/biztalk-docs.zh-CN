---
title: 单一登录： 事件 10586 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 124ed0a722d0da0f21722f3b337c8bb938068b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270709"
---
# <a name="single-sign-on-event-10586"></a>单一登录： 事件 10586
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10586|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_CRED_CACHE_OFF|  
|消息正文|此 SSO 服务器已禁用凭据缓存。|  
  
## <a name="explanation"></a>解释  
 已禁用凭据缓存；而通常情况下是启用凭据缓存的。 只有系统管理员可以启用或禁用凭据缓存。 禁用凭据缓存有时将导致 ENTSSO 系统出现更多当前凭据，虽然这会降低性能。  
  
## <a name="user-action"></a>用户操作  
 若要重新启用凭据缓存，请参阅中的 Afflilate 应用程序属性表[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。