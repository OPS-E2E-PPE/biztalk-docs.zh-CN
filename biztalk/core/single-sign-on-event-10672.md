---
title: 单一登录：Event 10672 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2422c7d-51bc-4f12-8830-193d71d2bce9
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 443c0bce458775f73c397cb0f1b1038665f328ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397500"
---
# <a name="single-sign-on-event-10672"></a>单一登录：事件 10672
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                                           企业单一登录                                                                                                                                                                                            |
| 产品版本 |                                                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                           |
|    事件 ID     |                                                                                                                                                                                                     10672                                                                                                                                                                                                      |
|  事件源   |                                                                                                                                                                                                     ENTSSO                                                                                                                                                                                                     |
|    组件    |                                                                                                                                                                                                      N\A                                                                                                                                                                                                       |
|  符号名称  |                                                                                                                                                                                 SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED                                                                                                                                                                                 |
|  消息正文   | Windows 密码更改将对同一外部 system.%r 导致对多个帐户的更改<br /><br /> 这已被阻止，因为此外部系统的适配器配置为不允许映射 conflicts.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户 1: %4 %r<br /><br /> 外部帐户 2: %5 |

## <a name="explanation"></a>解释  
 此警告事件表示，Windows 密码更改可能会造成对多个帐户的更改同一外部系统上。 已阻止此更改，因为适配器配置不允许它。  

## <a name="user-action"></a>用户操作  

-   使用 SSO 管理工具来配置**允许映射冲突**密码同步适配器的属性。  

## <a name="more-info"></a>详细信息

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [密码同步](../core/password-synchronization2.md)
