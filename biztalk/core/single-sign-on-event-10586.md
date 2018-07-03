---
title: 单一登录： 事件 10586 |Microsoft Docs
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
ms.openlocfilehash: 2b353c5d9fb569da7bcc35927e31ce5c3e68ae11
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978867"
---
# <a name="single-sign-on-event-10586"></a>单一登录： 事件 10586
## <a name="details"></a>详细信息  
  
|                 |                                                             |
|-----------------|-------------------------------------------------------------|
|  产品名称   |                  企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]  |
|    事件 ID     |                            10586                            |
|  事件源   |                           ENTSSO                            |
|    组件    |                             N/A                             |
|  符号名称  |                   SSO_WARN_CRED_CACHE_OFF                   |
|  消息正文   | 此 SSO 服务器已禁用凭据缓存。 |
  
## <a name="explanation"></a>解释  
 已禁用凭据缓存；而通常情况下是启用凭据缓存的。 只有系统管理员可以启用或禁用凭据缓存。 禁用凭据缓存有时将导致 ENTSSO 系统出现更多当前凭据，虽然这会降低性能。  
  
## <a name="user-action"></a>用户操作  
 若要重新启用凭据缓存，请参阅中的关联应用程序属性表[SSO 关联应用程序](../core/sso-affiliate-applications.md)。