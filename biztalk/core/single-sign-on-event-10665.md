---
title: 单一登录：Event 10665 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47cd0f957ba835df7f7463a8ee9c33f7b4503eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397560"
---
# <a name="single-sign-on-event-10665"></a>单一登录：事件 10665
## <a name="details"></a>详细信息  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               企业单一登录                                                |
| 产品版本 |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    事件 ID     |                                                         10665                                                          |
|  事件源   |                                                         ENTSSO                                                         |
|    组件    |                                                          N\A                                                           |
|  符号名称  |                                                 SSO_WARN_NO_PROPERTIES                                                 |
|  消息正文   | 读取密码同步适配器属性时出错。 使用 defaults.%r<br /><br /> 适配器: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表明时读取默认密码同步适配器属性时出错。 每个密码同步适配器都有与之关联的配置属性。 这些属性存储在 SSO 配置存储区中，并创建密码同步适配器时由 SSO 命令行工具或 SSO 管理 MMC 创建。  可能会缺少某些属性如果密码同步适配器创建了任何其他方法，则可以发出此错误。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

-   验证密码同步适配器属性。  

-   重新创建密码同步适配器  

## <a name="more-info"></a>详细信息

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [密码同步](../core/password-synchronization2.md)
