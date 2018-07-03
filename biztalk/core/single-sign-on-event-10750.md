---
title: 单一登录： 事件 10750 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28526c6695cbf8f9c29e99621d6cb2f852fa7021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984366"
---
# <a name="single-sign-on-event-10750"></a>单一登录： 事件 10750
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                    企业单一登录                                                                                                                     |
| 产品版本 |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    事件 ID     |                                                                                                                              10750                                                                                                                               |
|  事件源   |                                                                                                                              ENTSSO                                                                                                                              |
|    组件    |                                                                                                                               N\A                                                                                                                                |
|  符号名称  |                                                                                                                SSO_ERROR_PS_WRONG_USER_NAME_TYPE                                                                                                                 |
|  消息正文   | PasswordChangeNotify： 不正确的用户名称类型。 唯一接受的值是 USER_NAME_TYPE_NT4。<br /><br /> 在 Active Directory.%r 中错误地配置目标<br /><br /> 用户名称类型: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示密码同步接收到了来自密码更改通知服务 (PCNS) 的密码更改，但密码更改的格式错误。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查 PCNS 配置。 PCNS 只能在域控制器上运行。  

- 在 Active Directory 中将用户名称类型配置为 USER_NAME_TYPE_NT4。  

  有关详细信息，请参阅下列资源：  

- 请参阅 Active Directory 文档，了解有关如何指定用户名称类型的信息。  

- [密码同步](../core/password-synchronization2.md)
