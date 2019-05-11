---
title: 单一登录：Event 10728 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c7469a60ba0143f3e6674f5b140a452eebfe63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394338"
---
# <a name="single-sign-on-event-10728"></a>单一登录：事件 10728
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                     企业单一登录                                                                                                                     |
| 产品版本 |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    事件 ID     |                                                                                                                               10728                                                                                                                               |
|  事件源   |                                                                                                                              ENTSSO                                                                                                                               |
|    组件    |                                                                                                                                N\A                                                                                                                                |
|  符号名称  |                                                                                                                         SSO_ERROR_VERSION                                                                                                                         |
|  消息正文   | 此版本的 SSO 服务器不兼容与 SSO 数据库。 请升级你主 server.%r<br /><br /> SQL Server 名称: %1 %r<br /><br /> SSO 数据库名称: %2 %r<br /><br /> SSO 数据库版本: %3 %r<br /><br /> 所需的版本： %4 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 服务器版本是比 （最初创建的版本） 更新 SSO 数据库。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 升级 SSO 主密钥服务器以匹配此 SSO 服务器的当前版本。 这将升级到最新版本的 SSO 数据库。  

  有关详细信息，请参阅下列资源：  

- [管理主密钥](../core/managing-the-master-secret.md)
