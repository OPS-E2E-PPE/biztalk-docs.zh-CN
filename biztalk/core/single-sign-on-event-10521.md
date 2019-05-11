---
title: 单一登录：Event 10521 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb36c1306736fed435099c46254ee34d0079a1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394347"
---
# <a name="single-sign-on-event-10521"></a>单一登录：事件 10521
## <a name="details"></a>详细信息  

|                 |                                                                       |
|-----------------|-----------------------------------------------------------------------|
|  产品名称   |                       企业单一登录                       |
| 产品版本 |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    事件 ID     |                                 10521                                 |
|  事件源   |                                ENTSSO                                 |
|    组件    |                                  N\A                                  |
|  符号名称  |                     SSO_ERROR_SECRETS_NOT_LOADED                      |
|  消息正文   | 无法从主密钥服务器的注册表加载密钥。 |

## <a name="explanation"></a>解释  
 无法从注册表获取主密钥时，则将发生此错误事件在主密钥服务器上。 在详细信息在事件日志中可能有相关的错误消息。 最可能的原因是发生了权限的错误或加密错误时 SSO 服务帐户尝试访问注册表。 这可能更改 SSO 服务帐户时。 使用基于 SSO 服务帐户的标识的密钥进行加密主密钥。 如果更改了该帐户，也无法再解密在注册表中的现有主密钥。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- SSO 服务帐户更改通过备份主密钥，然后更改 SSO 服务帐户，然后将还原主密钥。 这可以还原主密钥，应修复此错误。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [主密钥服务器](../core/master-secret-server.md)  

- [管理主密钥](../core/managing-the-master-secret.md)  

- [配置 SSO](../core/configuring-sso.md)  

- [SSO 安全建议](../core/sso-security-recommendations.md)
