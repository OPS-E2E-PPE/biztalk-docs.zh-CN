---
title: 单一登录：Event 10678 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c8acb17f22b9b7fbf3faeaa918aa2fc0a7fd68e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397461"
---
# <a name="single-sign-on-event-10678"></a>单一登录：事件 10678
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                    企业单一登录                                                                                                                    |
| 产品版本 |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    事件 ID     |                                                                                                                              10678                                                                                                                              |
|  事件源   |                                                                                                                             ENTSSO                                                                                                                              |
|    组件    |                                                                                                                               N\A                                                                                                                               |
|  符号名称  |                                                                                                                   SSO_WARN_PASSWORD_MISMATCH                                                                                                                    |
|  消息正文   | 外部密码更改。 适配器提供旧密码与外部 account.%r 的现有密码不匹配<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |

## <a name="explanation"></a>解释  
 此警告事件表明适配器提供旧密码与外部帐户的现有密码不匹配。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

-   确定哪些应用程序分配给此适配器 （事件日志消息中的名称），然后使用 SSO 管理工具设置此外部帐户的外部凭据。 必须在所有这些应用程序设置 （适用于给定的帐户的外部密码。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
