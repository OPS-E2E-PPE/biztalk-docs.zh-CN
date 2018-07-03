---
title: 单一登录： 事件 10699 |Microsoft Docs
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
ms.openlocfilehash: 3802f04d2adf7d95a6ff10ae208acabbc1acf8ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983366"
---
# <a name="single-sign-on-event-10699"></a>单一登录： 事件 10699
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                       企业单一登录                                                                                                       |
| 产品版本 |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    事件 ID     |                                                                                                                 10699                                                                                                                 |
|  事件源   |                                                                                                                ENTSSO                                                                                                                 |
|    组件    |                                                                                                                  N\A                                                                                                                  |
|  符号名称  |                                                                                           SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY                                                                                           |
|  消息正文   | 从适配器（从重播文件）接收到一个外部密码更改。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 记录号： %5 |

## <a name="explanation"></a>解释  
 此信息性事件表示，从适配器接收到一个外部密码更改，此项更改记录在一个重播文件中。 SSO 正在重播来自重播文件的已存储外部密码更改。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
