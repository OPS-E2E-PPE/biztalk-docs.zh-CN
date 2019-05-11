---
title: 单一登录：Event 10662 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed63088692545e73c5804b5c0f60d59fd36f6f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397600"
---
# <a name="single-sign-on-event-10662"></a>单一登录：事件 10662
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             企业单一登录                                                                             |
| 产品版本 |                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    事件 ID     |                                                                                       10662                                                                                       |
|  事件源   |                                                                                      ENTSSO                                                                                       |
|    组件    |                                                                                        N\A                                                                                        |
|  符号名称  |                                                                     SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED                                                                     |
|  消息正文   | Windows 密码更改已从 PCNS.%r 中收到<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 其他数据: %3 %r<br /><br /> 客户端用户： %4 |

## <a name="explanation"></a>解释  
 此信息事件表明，从密码更改通知服务收到 Windows 密码更改。  

## <a name="user-action"></a>用户操作  

-   不不需要任何用户操作。  

## <a name="more-info"></a>详细信息

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
