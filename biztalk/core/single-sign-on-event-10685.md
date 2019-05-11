---
title: 单一登录：Event 10685 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f73b44e334c60a59211b59a46f5c9a2dacffa8ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397401"
---
# <a name="single-sign-on-event-10685"></a>单一登录：事件 10685
## <a name="details"></a>详细信息  

|                 |                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------|
|  产品名称   |                                      企业单一登录                                       |
| 产品版本 |                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                      |
|    事件 ID     |                                                10685                                                 |
|  事件源   |                                                ENTSSO                                                |
|    组件    |                                                 N\A                                                  |
|  符号名称  |                                     SSO_WARN_REPLAY_CANNOT_OPEN                                      |
|  消息正文   | 无法打开重播文件或进度 file.%r<br /><br /> 文件名称: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表明 SSO 已重建与 SSO 数据库的联系，但无法打开重播或进度文件。 如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示距离通过 SSO 能够读取与 SSO 数据库的重播文件中用例联系人愉悦再次通过播放重播文件。  

## <a name="user-action"></a>用户操作  
 若要解决此警告事件，请执行以下操作：  

- 应检查相关事件，以确定为何 SSO 无法与 SSO 数据库联系的系统和应用程序事件日志。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
