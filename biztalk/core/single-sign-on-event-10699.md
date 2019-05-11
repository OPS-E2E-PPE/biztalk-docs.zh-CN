---
title: 单一登录：Event 10699 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2cd62c4d952b9375b5d9255efc2f46add36dbb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397292"
---
# <a name="single-sign-on-event-10699"></a>单一登录：事件 10699
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                       企业单一登录                                                                                                       |
| 产品版本 |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    事件 ID     |                                                                                                                 10699                                                                                                                 |
|  事件源   |                                                                                                                ENTSSO                                                                                                                 |
|    组件    |                                                                                                                  N\A                                                                                                                  |
|  符号名称  |                                                                                           SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY                                                                                           |
|  消息正文   | 从适配器 （从重播 file).%r 收到外部密码更改<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 记录号： %5 |

## <a name="explanation"></a>解释  
 此信息事件表明从已记录到重播文件适配器接收到外部密码更改。 SSO 正在重播来自重播文件的存储的外部密码更改。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
