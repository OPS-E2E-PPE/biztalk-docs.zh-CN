---
title: 单一登录：Event 10668 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f9930c9c9f07c95ddc39ae1806fc6ba41e50a2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397529"
---
# <a name="single-sign-on-event-10668"></a>单一登录：事件 10668
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                   企业单一登录                                                                                                                                                   |
| 产品版本 |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    事件 ID     |                                                                                                                                                             10668                                                                                                                                                             |
|  事件源   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    组件    |                                                                                                                                                              N\A                                                                                                                                                              |
|  符号名称  |                                                                                                                                               SSO_WARN_NO_OLD_WINDOWS_PASSWORD                                                                                                                                                |
|  消息正文   | 不能更改 Windows 密码，因为此帐户的旧 Windows 密码不是 SSO database.%r 中可用<br /><br /> 使用 SSO 管理工具设置为此 Windows account.%r 的外部凭据<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3 |

## <a name="explanation"></a>解释  
 此警告事件表示密码同步不能更改 Windows 密码，因为此帐户的旧 Windows 密码不在 SSO 数据库中可用。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

-   确定哪些应用程序分配给此适配器 （事件日志消息中的名称），然后使用 SSO 管理工具来设置此 Windows 帐户的外部凭据。 必须在所有这些应用程序设置 （适用于给定的 Windows 帐户） 的外部密码。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
