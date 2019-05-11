---
title: 单一登录：Event 10681 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f6edaf7f524984365ffcca35ead803fa0693c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397419"
---
# <a name="single-sign-on-event-10681"></a>单一登录：事件 10681
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                              企业单一登录                                                                                               |
| 产品版本 |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    事件 ID     |                                                                                                        10681                                                                                                         |
|  事件源   |                                                                                                        ENTSSO                                                                                                        |
|    组件    |                                                                                                         N\A                                                                                                          |
|  符号名称  |                                                                                         SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE                                                                                          |
|  消息正文   | 外部密码更改。 Windows 密码未更改，因为一个或多个外部帐户更改 failed.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3 |

## <a name="explanation"></a>解释  
 此警告事件表示，Windows 密码未更改，因为一个或多个外部帐户更改失败。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

-   检查关联的事件的系统和应用程序事件日志。  

-   验证使用 SSO 管理工具的适配器配置。  

-   验证外部系统。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
