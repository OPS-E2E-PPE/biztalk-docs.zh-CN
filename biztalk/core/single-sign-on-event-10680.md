---
title: 单一登录：Event 10680 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a8b734006a8ec0181a3307386a32d8d249eaa25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397434"
---
# <a name="single-sign-on-event-10680"></a>单一登录：事件 10680
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                        企业单一登录                                                                                                                                        |
| 产品版本 |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    事件 ID     |                                                                                                                                                  10680                                                                                                                                                  |
|  事件源   |                                                                                                                                                 ENTSSO                                                                                                                                                  |
|    组件    |                                                                                                                                                   N\A                                                                                                                                                   |
|  符号名称  |                                                                                                                                      SSO_WARN_PS_GET_CREDS_FAILED                                                                                                                                       |
|  消息正文   | 密码未更改外部帐户由于无法从 SSO database.%r 获得现有外部凭据<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此警告事件表示，密码未更改外部帐户由于无法从 SSO 数据库获得现有外部凭据。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

-   验证外部凭据。  

-   外部凭据不是有效，请使用 SSO 管理工具设置此外部帐户的外部凭据。 必须在所有关联应用程序中设置 （适用于给定的帐户的外部密码。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
