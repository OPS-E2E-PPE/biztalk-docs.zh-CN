---
title: 单一登录：Event 10671 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f3b434cc328b9356e3f5a7db380c92366c210c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397514"
---
# <a name="single-sign-on-event-10671"></a>单一登录：事件 10671
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                                  企业单一登录                                                                                                                                                                                  |
| 产品版本 |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    事件 ID     |                                                                                                                                                                                            10671                                                                                                                                                                                            |
|  事件源   |                                                                                                                                                                                           ENTSSO                                                                                                                                                                                            |
|    组件    |                                                                                                                                                                                             N\A                                                                                                                                                                                             |
|  符号名称  |                                                                                                                                                                         SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                          |
|  消息正文   | Windows 密码更改将导致对同一外部 system.%r 上的多个帐户的更改<br /><br /> 这允许，因为此外部系统的适配器配置为允许映射 conflicts.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户 1: %4 %r<br /><br /> 外部帐户 2: %5 |

## <a name="explanation"></a>解释  
 此信息事件表明 Windows 密码更改将会对多个帐户的更改导致同一外部系统上。  

## <a name="user-action"></a>用户操作  

-   不不需要任何用户操作。  

## <a name="more-info"></a>详细信息

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [密码同步](../core/password-synchronization2.md)
