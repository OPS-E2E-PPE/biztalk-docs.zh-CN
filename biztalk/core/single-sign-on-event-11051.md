---
title: 单一登录：事件 11051 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe767818-f74e-415c-9287-5b7cc46e358a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4375b2a018fa649ef795e425e83078ac3add5cef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400922"
---
# <a name="single-sign-on-event-11051"></a>单一登录：事件 11051
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                          企业单一登录                                                                                                                                                           |
| 产品版本 |                                                                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                          |
|    事件 ID     |                                                                                                                                                                    11051                                                                                                                                                                     |
|  事件源   |                                                                                                                                                                    ENTSSO                                                                                                                                                                    |
|    组件    |                                                                                                                                                                     不可用                                                                                                                                                                      |
|  符号名称  |                                                                                                                                                         SSO_WARN_SSO_ADMIN_NOT_GROUP                                                                                                                                                         |
|  消息正文   | SSO Administrators 帐户包含一个或多个个人 （非组） 帐户。 如果从 Active Directory 或本地计算机删除了这些个人帐户则必须立即删除从 SSO 系统或它们将造成安全 risk.%r<br /><br /> SSO Administrators: %1 %r<br /><br /> 个人帐户： %2 |
  
## <a name="explanation"></a>解释  
 从 Active Directory 或本地计算机上删除个人帐户不会自动删除该帐户从 SSO 系统。 这意味着，如果 USER1 本地已删除的帐户，然后选择其他用户 （例如，新的员工） 使用相同的名称将系统加入，SSO 系统将授予新的 USER1 将原来 USER1 所具有的所有安全权限。 这会带来安全风险。  
  
## <a name="user-action"></a>用户操作  
 从 Active Directory 或本地计算机中删除个人帐户之前，不不需要任何操作。 此时，必须尽可能快地删除从 SSO 系统的单个帐户。