---
title: 单一登录：Event 10715 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72bb7740ee9c0edb1c5e3c35304c9e9633bb89f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397201"
---
# <a name="single-sign-on-event-10715"></a>单一登录：事件 10715
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                            企业单一登录                                                                                             |
| 产品版本 |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                            |
|    事件 ID     |                                                                                                      10715                                                                                                       |
|  事件源   |                                                                                                      ENTSSO                                                                                                      |
|    组件    |                                                                                                       N\A                                                                                                        |
|  符号名称  |                                                                                            SSO_WARN_NO_CREATE_ADAPTER                                                                                            |
|  消息正文   | 客户端用户必须是 SSO 管理员帐户的成员才能创建 adapters.%r<br /><br /> 客户端用户: %1 %r<br /><br /> SSO Administrators: %2 %r<br /><br /> 适配器: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示客户端用户必须是 SSO 管理员帐户的成员才能创建适配器。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 登录所用帐户所属的 SSO 管理员组。  

  有关详细信息，请参阅下列资源：  

- [SSO 用户组](../core/sso-user-groups.md)
