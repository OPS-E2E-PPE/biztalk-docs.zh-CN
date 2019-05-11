---
title: 单一登录：Event 11023 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 525c2bd0759aa24c191991e075276bd75233d6d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266537"
---
# <a name="single-sign-on-event-11023"></a>单一登录：事件 11023
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                 企业单一登录                                                                                                                                  |
| 产品版本 |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    事件 ID     |                                                                                                                                           11023                                                                                                                                            |
|  事件源   |                                                                                                                                           ENTSSO                                                                                                                                           |
|    组件    |                                                                                                                                            不可用                                                                                                                                             |
|  符号名称  |                                                                                                                             SSO_WARN_WINDOWS_PASSWORD_DELETED                                                                                                                              |
|  消息正文   | 已删除 SSO 数据库中无效的 Windows 密码以阻止帐户 lockout.%r<br /><br /> 使用 SSO 管理工具设置为此 Windows account.%r 的外部凭据<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3 |
  
## <a name="explanation"></a>解释  
 无效的 Windows 密码已被删除。  
  
## <a name="user-action"></a>用户操作  
 使用 SSO 管理工具来设置此 Windows 帐户的外部凭据。 有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。