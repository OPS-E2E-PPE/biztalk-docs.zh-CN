---
title: 单一登录： 事件 10521 |Microsoft Docs
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
ms.openlocfilehash: 8af1b2ac8d2ac3645db6a6a80146832378aececf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008566"
---
# <a name="single-sign-on-event-10521"></a>单一登录： 事件 10521
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
 当无法从注册表获取主密钥时，会在主密钥服务器上发生此错误事件。 事件日志中可能有相关的错误消息，能够为您提供更多信息。 导致此错误的原因很可能是，当 SSO 服务帐户尝试访问注册表时，发生了权限错误或加密错误。 这可能更改 SSO 服务帐户时。 此主密钥是使用基于 SSO 服务帐户标识的某个密钥进行加密的。 如果更改了该帐户，则不能再对注册表中的现有主密钥进行解密。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 通过先备份主密钥，然后更改 SSO 服务帐户，最后再还原主密钥来更改 SSO 服务帐户。 这样可以还原主密钥，并且应该能够修复此错误。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [主密钥服务器](../core/master-secret-server.md)  

- [管理主密钥](../core/managing-the-master-secret.md)  

- [配置 SSO](../core/configuring-sso.md)  

- [SSO 安全建议](../core/sso-security-recommendations.md)
