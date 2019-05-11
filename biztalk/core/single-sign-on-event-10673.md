---
title: 单一登录：Event 10673 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d6481684fdb53aed156703a52e472c3fe1f06d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397498"
---
# <a name="single-sign-on-event-10673"></a>单一登录：事件 10673
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                        企业单一登录                                                                                                                                                                         |
| 产品版本 |                                                                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    事件 ID     |                                                                                                                                                                                  10673                                                                                                                                                                                   |
|  事件源   |                                                                                                                                                                                  ENTSSO                                                                                                                                                                                  |
|    组件    |                                                                                                                                                                                   N\A                                                                                                                                                                                    |
|  符号名称  |                                                                                                                                                                SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                 |
|  消息正文   | 外部密码更改将导致对多个 Windows account.%r 的更改<br /><br /> 这允许，因为此外部系统的适配器配置为允许映射 conflicts.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> Windows 帐户 1: %4 %r<br /><br /> Windows 帐户 2: %5 |

## <a name="explanation"></a>解释  
 此信息事件表明外部密码更改将导致对多个 Windows 帐户的更改。  

## <a name="user-action"></a>用户操作  

-   不不需要任何用户操作。  

## <a name="more-info"></a>详细信息

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [密码同步](../core/password-synchronization2.md)
