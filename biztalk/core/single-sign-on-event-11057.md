---
title: 单一登录：Event 11057 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff6e7a5c811c983ebe9f48fc6cdd85ed79f3ee16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400868"
---
# <a name="single-sign-on-event-11057"></a>单一登录：事件 11057
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                企业单一登录                                                                                                                |
| 产品版本 |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    事件 ID     |                                                                                                                          11057                                                                                                                          |
|  事件源   |                                                                                                                         ENTSSO                                                                                                                          |
|    组件    |                                                                                                                           不可用                                                                                                                           |
|  符号名称  |                                                                                                        SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS                                                                                                         |
|  消息正文   | 直接密码更改。 此映射某些缺少的外部凭据字段已设置为默认 values.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 应用程序名称: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户： %4 |
  
## <a name="explanation"></a>解释  
 无法更改使用直接密码同步的密码时，此功能仅支持一个外部凭据字段。 在这种情况下 ENTSSO 系统遇到了多个外部凭据字段中，并且已将这些字段设置为默认 （空） 值。  
  
## <a name="user-action"></a>用户操作  
 不不需要任何用户操作。