---
title: 单一登录：Event 10573 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37199e0b619f6d9f9d5a37ef1a6b4eb53c6f5712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398724"
---
# <a name="single-sign-on-event-10573"></a>单一登录：事件 10573
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                   |
| 产品版本 |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            10573                                                                                             |
|  事件源   |                                                                                            ENTSSO                                                                                            |
|    组件    |                                                                                             不可用                                                                                              |
|  符号名称  |                                                                             SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP                                                                             |
|  消息正文   | SSO Affiliate Administrators 帐户对于全局信息 update.%r 无效<br /><br /> SSO 关联管理员: %1 %r<br /><br /> 无效帐户: %2 %r<br /><br /> 错误代码： %3 |
  
## <a name="explanation"></a>解释  
 SSO Affiliate Administrators 帐户无效，不能用于全局信息更新。  
  
## <a name="user-action"></a>用户操作  
 此警告消息包含有关 SSO 关联管理员帐户和无效帐户的信息。 查看此信息，进行任何必要的更正，并重试该更新。