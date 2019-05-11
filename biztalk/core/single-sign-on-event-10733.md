---
title: 单一登录：Event 10733 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3f67e18a9388e5f055d760d6223e2034ad6ea0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291798"
---
# <a name="single-sign-on-event-10733"></a>单一登录：事件 10733
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                  企业单一登录                                                                  |
| 产品版本 |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    事件 ID     |                                                                            10733                                                                            |
|  事件源   |                                                                           ENTSSO                                                                            |
|    组件    |                                                                             N\A                                                                             |
|  符号名称  |                                                              SSO_WARN_PS_SET_WINDOWS_PASSWORD                                                               |
|  消息正文   | 更新 SSO database.%r 中的 Windows 密码失败<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户： %2\\%3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示密码同步未能更新 SSO 数据库中指定的 Windows 帐户密码。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 检查系统和应用程序事件日志中的关联错误。  

- 验证指定帐户的密码为有效的 Windows 密码。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
