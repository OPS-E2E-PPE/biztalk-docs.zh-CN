---
title: 单一登录：事件 10731 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 630267c28a4db6b570be4c6efe73218e45f15b2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267517"
---
# <a name="single-sign-on-event-10731"></a>单一登录：事件 10731
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                         企业单一登录                                                                                                                         |
| 产品版本 |                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                         |
|    事件 ID     |                                                                                                                                   10731                                                                                                                                   |
|  事件源   |                                                                                                                                  ENTSSO                                                                                                                                   |
|    组件    |                                                                                                                                    N\A                                                                                                                                    |
|  符号名称  |                                                                                                                    SSO_WARN_INVALID_USER_NOT_IN_GROUP                                                                                                                     |
|  消息正文   | 无法创建映射，因为指定的用户不是应用程序用户 account.%r 的成员<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此警告事件表示，因为指定的用户不是应用程序用户帐户的成员可能不会创建一个映射。  

 为每个关联应用程序存在的应用程序用户组帐户。 此帐户的成员可以验证其凭据的关联应用程序中，并且可以管理其凭据映射的关联应用程序中。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 将指定的用户添加到指定的关联应用程序的应用程序用户的组。  

  有关详细信息，请参阅下列资源：  

- [SSO 用户组](../core/sso-user-groups.md)  

- [SSO 关联应用程序](../core/sso-affiliate-applications.md)
