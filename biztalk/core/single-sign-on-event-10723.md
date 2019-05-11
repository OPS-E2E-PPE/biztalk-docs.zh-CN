---
title: 单一登录：Event 10723 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00536f3e-26d6-4e19-a98f-e687bb1b6611
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b520bac32b3a50fa87432a51afb2e77ef24e8059
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397152"
---
# <a name="single-sign-on-event-10723"></a>单一登录：事件 10723
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                        企业单一登录                                                                                        |
| 产品版本 |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    事件 ID     |                                                                                                  10723                                                                                                  |
|  事件源   |                                                                                                 ENTSSO                                                                                                  |
|    组件    |                                                                                                   N\A                                                                                                   |
|  符号名称  |                                                                                       SSO_ERROR_REPLAY_SECURITY_1                                                                                       |
|  消息正文   | 重播文件目录的安全性与重播或进度 file.%r 的安全性不匹配<br /><br /> 文件名称: %1 %r<br /><br /> 文件安全性: %2 %r<br /><br /> 目录安全性： %3 |

## <a name="explanation"></a>解释  
 此错误事件表明重播文件目录的安全性与重播或进度文件的安全性不匹配。  

 重播文件存储在重播文件目录。 默认情况下，SSO 服务帐户用于创建重播文件和重播文件目录。 没有进行了更改的安全配置的重播文件和重播文件目录创建以来，SSO 会验证。 如果在不同帐户创建重播文件目录时，密码同步尝试在该目录中创建重播文件时，可以返回此错误。 强烈建议用户不要更改重播文件和重播文件目录的任何安全配置。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查用来创建重播文件目录的帐户。 如果该目录为空，则尝试再次运行密码同步。 可能需要重新创建使用与 SSO 服务相同的服务帐户的目录。 如果无法重新创建重播文件目录使用与 SSO 服务相同的帐户，检查该帐户的权限。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
