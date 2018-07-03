---
title: 单一登录： 事件 10662 |Microsoft Docs
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
ms.openlocfilehash: f33d106f7c272f74f99ef537e5083d9bdb015ecb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984702"
---
# <a name="single-sign-on-event-10662"></a>单一登录： 事件 10662
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             企业单一登录                                                                             |
| 产品版本 |                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    事件 ID     |                                                                                       10662                                                                                       |
|  事件源   |                                                                                      ENTSSO                                                                                       |
|    组件    |                                                                                        N\A                                                                                        |
|  符号名称  |                                                                     SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED                                                                     |
|  消息正文   | 从 PCNS 中收到 Windows 密码更改。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 其他数据: %3 %r<br /><br /> 客户端用户： %4 |

## <a name="explanation"></a>解释  
 此信息事件表示，从密码更改通知服务收到 Windows 密码更改。  

## <a name="user-action"></a>用户操作  

-   不需要用户进行任何操作。  

## <a name="more-info"></a>详细信息

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  

- **密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
