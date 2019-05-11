---
title: 单一登录：Event 10711 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a656e0bc079c2fb11a2cef59e86e914087259cef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397235"
---
# <a name="single-sign-on-event-10711"></a>单一登录：事件 10711
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                             企业单一登录                                                                                                             |
| 产品版本 |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    事件 ID     |                                                                                                                       10711                                                                                                                       |
|  事件源   |                                                                                                                      ENTSSO                                                                                                                       |
|    组件    |                                                                                                                        N\A                                                                                                                        |
|  符号名称  |                                                                                                         SSO_WARN_PS_MISSING_INITIAL_CREDS                                                                                                         |
|  消息正文   | 外部密码更改。 此映射某些缺少的外部凭据字段已设置为默认 values.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示外部密码更改已收到凭据丢失。 这些字段使用了默认值。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 如有必要，设置要匹配的凭据。  

  有关详细信息，请参阅下列资源：  

- [SSO 关联应用程序](../core/sso-affiliate-applications.md)  

- [密码同步](../core/password-synchronization2.md)
