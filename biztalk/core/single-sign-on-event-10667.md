---
title: 单一登录：Event 10667 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74bbe7e6-af21-434c-9a62-3c3b13ca3307
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5115d7d521a0e19d1b48f5c1bf1f9f1f5937e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397549"
---
# <a name="single-sign-on-event-10667"></a>单一登录：事件 10667
## <a name="details"></a>详细信息  

|                 |                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        企业单一登录                                                        |
| 产品版本 |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    事件 ID     |                                                                  10667                                                                  |
|  事件源   |                                                                 ENTSSO                                                                  |
|    组件    |                                                                   N\A                                                                   |
|  符号名称  |                                          SSO_INFO_SUPPRESSED_DUPLICATE_WINDOWS_PASSWORD_CHANGE                                          |
|  消息正文   | 禁止显示重复的 Windows 密码 change.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 已取消重复的 Windows 密码更改。  

## <a name="user-action"></a>用户操作  

-   不不需要任何用户操作。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
