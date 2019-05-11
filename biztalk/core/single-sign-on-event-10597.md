---
title: 单一登录：Event 10597 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c57db8f-f7e4-4745-89b6-3112a3b2e1be
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a65e16c4575b1eee29fd920ab55a3bf76bf87197
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397831"
---
# <a name="single-sign-on-event-10597"></a>单一登录：事件 10597
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                   |
| 产品版本 |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            10597                                                                                             |
|  事件源   |                                                                                            ENTSSO                                                                                            |
|    组件    |                                                                                             不可用                                                                                              |
|  符号名称  |                                                                             SSO_WARN_CALLER_NOT_IN_NEW_SSO_ADMIN                                                                             |
|  消息正文   | 客户端用户必须是新 SSO 管理员帐户的成员，才能更改 SSO Administrators 帐户 name.%r<br /><br /> 客户端用户: %1 %r<br /><br /> 新的 SSO Administrators: %2 |
  
## <a name="explanation"></a>解释  
 客户端用户必须是新 SSO 管理员帐户的成员，才能更改 SSO 管理员帐户名。  
  
## <a name="user-action"></a>用户操作  
 必须是新 SSO 管理员帐户的成员，才能更改 SSO 管理员帐户名。