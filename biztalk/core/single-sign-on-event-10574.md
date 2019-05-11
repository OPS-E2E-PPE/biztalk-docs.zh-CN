---
title: 单一登录：Event 10574 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f2a5aa-3a19-4d7c-9257-89f1567a3c2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae5f0ecae1e9c3016817d1627ad0bfba75ef7ba4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398718"
---
# <a name="single-sign-on-event-10574"></a>单一登录：事件 10574
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                        企业单一登录                                                                         |
| 产品版本 |                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                        |
|    事件 ID     |                                                                                  10574                                                                                   |
|  事件源   |                                                                                  ENTSSO                                                                                  |
|    组件    |                                                                                   不可用                                                                                    |
|  符号名称  |                                                                     SSO_WARN_INVALID_SSO_ADMIN_GROUP                                                                     |
|  消息正文   | SSO Administrators 帐户对于全局信息 update.%r 无效<br /><br /> SSO Administrators: %1 %r<br /><br /> 无效帐户: %2 %r<br /><br /> 错误代码： %3 |
  
## <a name="explanation"></a>解释  
 SSO Administrators 帐户无效，不能用于全局信息更新。  
  
## <a name="user-action"></a>用户操作  
 此警告消息包含有关 SSO 管理员帐户和无效帐户的信息。 查看此信息，进行任何必要的更正，并重试该更新。