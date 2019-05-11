---
title: 单一登录：Event 10750 | Microsoft Docs
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
ms.openlocfilehash: 951a22f0b8ea5c346486d8cd2ea0882aaa2b0f05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307925"
---
# <a name="single-sign-on-event-10750"></a>单一登录：事件 10750
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                    企业单一登录                                                                                                                     |
| 产品版本 |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    事件 ID     |                                                                                                                              10750                                                                                                                               |
|  事件源   |                                                                                                                              ENTSSO                                                                                                                              |
|    组件    |                                                                                                                               N\A                                                                                                                                |
|  符号名称  |                                                                                                                SSO_ERROR_PS_WRONG_USER_NAME_TYPE                                                                                                                 |
|  消息正文   | PasswordChangeNotify:不正确的用户名称类型。 唯一接受的值是 USER_NAME_TYPE_NT4。<br /><br /> 在 Active Directory.%r 中错误地配置目标<br /><br /> 用户名称类型: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示密码同步接收密码更改从密码更改通知服务 (PCNS)，但密码更改的格式不正确。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查 PCNS 配置。 PCNS 只能在域控制器可以运行。  

- 在 Active Directory 中配置为 USER_NAME_TYPE_NT4 用户名称类型。  

  有关详细信息，请参阅下列资源：  

- 请参阅有关如何指定用户名称类型的信息的 Active Directory 文档。  

- [密码同步](../core/password-synchronization2.md)
