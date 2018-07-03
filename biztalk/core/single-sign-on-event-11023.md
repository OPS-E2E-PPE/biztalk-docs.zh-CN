---
title: 单一登录： 事件 11023 |Microsoft Docs
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
ms.openlocfilehash: cecf9536babaf2510444abade571149c5fc0e0a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991534"
---
# <a name="single-sign-on-event-11023"></a>单一登录： 事件 11023
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                 企业单一登录                                                                                                                                  |
| 产品版本 |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    事件 ID     |                                                                                                                                           11023                                                                                                                                            |
|  事件源   |                                                                                                                                           ENTSSO                                                                                                                                           |
|    组件    |                                                                                                                                            N/A                                                                                                                                             |
|  符号名称  |                                                                                                                             SSO_WARN_WINDOWS_PASSWORD_DELETED                                                                                                                              |
|  消息正文   | 已删除 SSO 数据库中无效的 Windows 密码以阻止帐户锁定。%r<br /><br /> 请使用 SSO 管理工具为此 Windows 帐户设置外部凭据。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3 |
  
## <a name="explanation"></a>解释  
 已删除无效的 Windows 密码。  
  
## <a name="user-action"></a>用户操作  
 使用 SSO 管理工具为此 Windows 帐户设置外部凭据。 有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。