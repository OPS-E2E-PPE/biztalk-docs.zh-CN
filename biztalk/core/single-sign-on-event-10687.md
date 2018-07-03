---
title: 单一登录： 事件 10687 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e928e779d8b2d22a20cc502fb65fd321fb99668c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976470"
---
# <a name="single-sign-on-event-10687"></a>单一登录： 事件 10687
## <a name="details"></a>详细信息  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               企业单一登录                                               |
| 产品版本 |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    事件 ID     |                                                         10687                                                         |
|  事件源   |                                                        ENTSSO                                                         |
|    组件    |                                                          N\A                                                          |
|  符号名称  |                                               SSO_INFO_REPLAY_COMPLETE                                                |
|  消息正文   | 重播存储的外部密码更改已完成。%r<br /><br /> 重播文件: %1 %r<br /><br /> 其他数据： %2 |

## <a name="explanation"></a>解释  
 此信息事件表示 SSO 已完成重播存储的外部密码更改文件。 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
