---
title: 单一登录：Event 10687 | Microsoft Docs
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
ms.openlocfilehash: 77412a149c79e508c03b245cba04a76c87542936
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397393"
---
# <a name="single-sign-on-event-10687"></a>单一登录：事件 10687
## <a name="details"></a>详细信息  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               企业单一登录                                               |
| 产品版本 |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    事件 ID     |                                                         10687                                                         |
|  事件源   |                                                        ENTSSO                                                         |
|    组件    |                                                          N\A                                                          |
|  符号名称  |                                               SSO_INFO_REPLAY_COMPLETE                                                |
|  消息正文   | 重播存储的外部密码更改 completed.%r<br /><br /> 重播文件: %1 %r<br /><br /> 其他数据： %2 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 已完成重播存储的外部密码更改文件。 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
