---
title: 单一登录： 事件 11057 |Microsoft Docs
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
ms.openlocfilehash: 0bce17e6659867d8bcf8c39408ec24d8e79052aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967654"
---
# <a name="single-sign-on-event-11057"></a>单一登录： 事件 11057
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                企业单一登录                                                                                                                |
| 产品版本 |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    事件 ID     |                                                                                                                          11057                                                                                                                          |
|  事件源   |                                                                                                                         ENTSSO                                                                                                                          |
|    组件    |                                                                                                                           N/A                                                                                                                           |
|  符号名称  |                                                                                                        SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS                                                                                                         |
|  消息正文   | 直接密码更改。 已将此映射的某些缺少的外部凭据字段设置为默认值。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 应用程序名称: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户： %4 |
  
## <a name="explanation"></a>解释  
 尽管可以使用直接密码同步来更改密码，但此功能只支持一个外部凭据字段。 在这种情况下 ENTSSO 系统遇到了多个外部凭据字段中，并且已将这些字段设置为默认 （空） 值。  
  
## <a name="user-action"></a>用户操作  
 不需要用户进行任何操作。