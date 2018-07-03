---
title: 单一登录： 事件 10683 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a8a769e9cf74a3d0119ca814d7201c1e14e7304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978302"
---
# <a name="single-sign-on-event-10683"></a>单一登录： 事件 10683
## <a name="details"></a>详细信息  

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  产品名称   |                        企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    事件 ID     |                                  10683                                   |
|  事件源   |                                  ENTSSO                                  |
|    组件    |                                   N\A                                    |
|  符号名称  |                   SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD                   |
|  消息正文   | 删除重播文件，因为它太 old.%r<br />重播文件： %1 |

## <a name="explanation"></a>解释  
 此警告事件表明重播文件因太旧而被删除。 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 在这种情况下，密码更改存储在临时的加密文件中，在重新变为可用时重播回 SSO 数据库。 当要将文件重播回 SSO 数据库时，如果检测到文件太旧，则会放弃该文件。 通过 SSO 密码同步系统; 将放弃所有旧密码更改`password sync age`参数确定密码的最大期限更改请求和可以使用命令行工具控制， **ssoconfig – syncAge**或 SSO 管理 MMC。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
