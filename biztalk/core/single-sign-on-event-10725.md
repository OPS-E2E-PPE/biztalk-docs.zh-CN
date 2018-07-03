---
title: 单一登录： 事件 10725 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89218d73-bda0-4e98-a578-cd244af79041
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 206173f45d6702290eef7cd8e203c2439ce44cc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016135"
---
# <a name="single-sign-on-event-10725"></a>单一登录： 事件 10725
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                        企业单一登录                                                                                        |
| 产品版本 |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    事件 ID     |                                                                                                  10725                                                                                                  |
|  事件源   |                                                                                                 ENTSSO                                                                                                  |
|    组件    |                                                                                                   N\A                                                                                                   |
|  符号名称  |                                                                                       SSO_ERROR_REPLAY_SECURITY_3                                                                                       |
|  消息正文   | 重播文件目录的安全性与重播或进度文件的安全性不匹配。%r<br /><br /> 文件名称: %1 %r<br /><br /> 文件安全性: %2 %r<br /><br /> 目录安全性： %3 |

## <a name="explanation"></a>解释  
 此错误事件表明重播文件目录的安全性与重播或进度文件的安全性不匹配。  

 重播文件存储在重播文件目录中。 默认情况下，SSO 服务帐户用来创建重播文件和重播文件目录。 创建之后，SSO 会验证是否未对重播文件和重播文件目录的安全配置进行更改。 如果重播文件目录是使用其他帐户创建的，则当密码同步尝试在该目录中创建重播文件时，可能会返回此错误。 强烈建议用户不要更改重播文件和重播文件目录的任何安全配置。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查用于创建重播文件目录的帐户。 如果目录为空，请再次尝试运行密码同步。 可能需要使用与 SSO 服务相同的服务帐户来重新创建目录。 如果无法使用与 SSO 服务相同的帐户重新创建重播文件目录，则检查该帐户的权限。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
