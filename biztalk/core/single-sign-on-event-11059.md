---
title: 单一登录：Event 11059 | Microsoft Docs
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
ms.openlocfilehash: b851e468db974456fe5f9eca00dc201fdfe1e12d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258771"
---
# <a name="single-sign-on-event-11059"></a>单一登录：事件 11059
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                               企业单一登录                                                                                                               |
| 产品版本 |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    事件 ID     |                                                                                                                         11059                                                                                                                         |
|  事件源   |                                                                                                                        ENTSSO                                                                                                                         |
|    组件    |                                                                                                                          不可用                                                                                                                          |
|  符号名称  |                                                                                                          SSO_INFO_INVALID_USER_NOT_IN_GROUP                                                                                                           |
|  消息正文   | 无法创建映射，因为指定的用户不是应用程序用户 account.%r 的成员<br /><br /> Windows 帐户： %1\\%2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 无法创建映射，因为指定的用户不是应用程序用户帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 与 ENTSSO 管理员如何成为应用程序用户帐户的成员联系。