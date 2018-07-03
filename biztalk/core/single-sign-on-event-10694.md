---
title: 单一登录： 事件 10694 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75faca65-48d9-45f6-b079-2b612ef3de76
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d5bcd178020e6aee2b16e3cd3fbababd6b8498
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981646"
---
# <a name="single-sign-on-event-10694"></a>单一登录： 事件 10694
## <a name="details"></a>详细信息  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  产品名称   |                              企业单一登录                              |
| 产品版本 |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    事件 ID     |                                        10694                                        |
|  事件源   |                                       ENTSSO                                        |
|    组件    |                                         N\A                                         |
|  符号名称  |                         SSO_ERROR_REPLAY_INCORRECT_VERSION                          |
|  消息正文   | 在重播或进度 file.%r 中检测到损坏。<br /><br /> 文件名称： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 已重建与 SSO 数据库的联系，但无法读取重播文件由于损坏问题。 如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
