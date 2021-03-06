---
title: 单一登录：Event 10743 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10ec09fac8f7b555cb189e032b94bf0c8f8da839
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278024"
---
# <a name="single-sign-on-event-10743"></a>单一登录：事件 10743
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                   企业单一登录                                                                    |
| 产品版本 |                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    事件 ID     |                                                                             10743                                                                              |
|  事件源   |                                                                             ENTSSO                                                                             |
|    组件    |                                                                              N\A                                                                               |
|  符号名称  |                                                                    SSO_ERROR_REPLAY_STOPPED                                                                    |
|  消息正文   | 由于 errors.%r 已停止重播存储的外部密码更改<br /><br /> 重播文件: %1 %r<br /><br /> 其他数据: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示该重播存储的外部密码更改由于错误已停止。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
