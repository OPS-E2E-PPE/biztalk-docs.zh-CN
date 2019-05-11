---
title: 单一登录：Event 10517 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9febc85f554b8736d75c9315a37214c8a81ca16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279804"
---
# <a name="single-sign-on-event-10517"></a>单一登录：事件 10517
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                  企业单一登录                                                                                                                                                  |
| 产品版本 |                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                  |
|    事件 ID     |                                                                                                                                                            10517                                                                                                                                                            |
|  事件源   |                                                                                                                                                           ENTSSO                                                                                                                                                            |
|    组件    |                                                                                                                                                             N\A                                                                                                                                                             |
|  符号名称  |                                                                                                                                                   SSO_ERROR_BAD_SSO_ADMIN                                                                                                                                                   |
|  消息正文   | SSO 管理员帐户不是有效的。 如果它是本地帐户检查服务器上是否存在此帐户。 如果是域帐户与域管理员联系。 当帐户 valid.%r 时启用 SSO<br /><br /> SSO Administrators: %1 %r<br /><br /> 无效帐户: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 管理员帐户指定为企业单一登录不是有效的 Windows 帐户。 运行企业单一登录服务的服务帐户必须是此帐户的成员。 SSO 管理员帐户可以是 Windows 组帐户或个人帐户。 SSO 管理员帐户也可以是域或本地组帐户。 如果使用个人帐户，则无法更改此帐户到另一个个人帐户。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 验证 SSO 管理员帐户存在。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [SSO 用户组](../core/sso-user-groups.md)
