---
title: 单一登录：Event 10717 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47ff4ceb707d1cbd353f88c9335d226a9a0158d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397170"
---
# <a name="single-sign-on-event-10717"></a>单一登录：事件 10717
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                            企业单一登录                                                             |
| 产品版本 |                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                            |
|    事件 ID     |                                                                      10717                                                                       |
|  事件源   |                                                                      ENTSSO                                                                      |
|    组件    |                                                                       N\A                                                                        |
|  符号名称  |                                                         SSO_ERROR_NEW_REPLAY_DIR_FAILED                                                          |
|  消息正文   | 无法创建重播文件 directory.%r<br /><br /> 客户端用户: %1 %r<br /><br /> 重播文件目录: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示无法创建重播文件目录。  

 SSO 服务从密码同步适配器接收密码更改，则这些模块存储在 SSO 数据库中。 如果 SSO 数据库暂时不可用，密码更改存储在本地重播文件中。 重播文件存储在重播文件目录。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查重播文件目录，如果不存在，尝试手动与 SSO 服务使用相同的服务帐户创建它。 如果无法创建重播文件目录使用与 SSO 服务相同的帐户，则检查该帐户的权限。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
