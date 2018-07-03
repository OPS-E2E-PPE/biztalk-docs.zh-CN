---
title: 单一登录： 事件 11054 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59dc801d-fc78-4561-8a26-9d815c86d842
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0225123b40abd32280a240daf1d3c072dc4d969a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999430"
---
# <a name="single-sign-on-event-11054"></a>单一登录： 事件 11054
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                           企业单一登录                                                                                                                                                                           |
| 产品版本 |                                                                                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                           |
|    事件 ID     |                                                                                                                                                                                     11054                                                                                                                                                                                     |
|  事件源   |                                                                                                                                                                                    ENTSSO                                                                                                                                                                                     |
|    组件    |                                                                                                                                                                                      N/A                                                                                                                                                                                      |
|  符号名称  |                                                                                                                                                                         SSO_WARN_APP_USERS_NOT_GROUP                                                                                                                                                                          |
|  消息正文   | 应用程序用户帐户包含一个或多个个人（不是组）帐户。 如果已经从 Active Directory 或本地计算机删除这些个人帐户，则必须立即从 SSO 系统中删除这些帐户，否则它们会成为安全隐患。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 应用程序用户: %2 %r<br /><br /> 个人帐户： %3 |
  
## <a name="explanation"></a>解释  
 从 Active Directory 或本地计算机上删除个人帐户并不会自动从 SSO 系统删除该帐户。 这意味着如果从本地计算机删除帐户 USER1，然后另一个不同用户（例如新的员工）使用相同的名称加入到系统，则 SSO 系统会将原来 USER1 所具有的安全权限都授予新的 USER1。 这会形成安全隐患。  
  
 作为最佳实践，建议 SSO 管理员帐户使用 Active Directory 组帐户，而非个人帐户。  
  
## <a name="user-action"></a>用户操作  
 在从 Active Directory 或本地计算机中删除个人帐户之前，无需进行操作。 如果发生上述删除操作，则必须尽快从 SSO 系统删除该个人帐户。