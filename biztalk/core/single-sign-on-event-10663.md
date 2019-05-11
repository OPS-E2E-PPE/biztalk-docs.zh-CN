---
title: 单一登录：Event 10663 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85223ded-1226-4dce-affc-46142157d18d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa139a865dd15f6b7f5ac234b4b1fec56d342e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397577"
---
# <a name="single-sign-on-event-10663"></a>单一登录：事件 10663
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                              企业单一登录                                                                                               |
| 产品版本 |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    事件 ID     |                                                                                                        10663                                                                                                         |
|  事件源   |                                                                                                        ENTSSO                                                                                                        |
|    组件    |                                                                                                         N\A                                                                                                          |
|  符号名称  |                                                                                      SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED                                                                                      |
|  消息正文   | 从 adapter.%r 接收到外部密码更改。<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 客户端计算机： %5 |

## <a name="explanation"></a>解释  
 此信息事件表明从适配器接收到外部密码更改。  

## <a name="user-action"></a>用户操作  

-   不不需要任何用户操作。  

## <a name="more-info"></a>详细信息

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
