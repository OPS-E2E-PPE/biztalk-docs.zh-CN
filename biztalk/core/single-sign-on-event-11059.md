---
title: 单一登录： 事件 11059 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac5b6ce7-8819-4b9d-85f7-f5dfaf940487
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a22b2a68acc6cd4be3d5cf854a4d965d897e302
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965774"
---
# <a name="single-sign-on-event-11059"></a>单一登录： 事件 11059
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                               企业单一登录                                                                                                               |
| 产品版本 |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    事件 ID     |                                                                                                                         11059                                                                                                                         |
|  事件源   |                                                                                                                        ENTSSO                                                                                                                         |
|    组件    |                                                                                                                          N/A                                                                                                                          |
|  符号名称  |                                                                                                          SSO_INFO_INVALID_USER_NOT_IN_GROUP                                                                                                           |
|  消息正文   | 无法创建映射，因为指定的用户不是“应用程序用户”帐户的成员。%r<br /><br /> Windows 帐户： %1\\%2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 无法创建映射，因为指定的用户不是“应用程序用户”帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 请与 ENTSSO 管理员联系，了解成为“应用程序用户”帐户成员的相关信息。