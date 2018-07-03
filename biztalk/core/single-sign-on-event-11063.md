---
title: 单一登录： 事件 11063 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c84f91de-221d-43c4-8d23-3d1b7fd29cf7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a653b8c5cf27925c65d8922a5a561855fdb6a4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975566"
---
# <a name="single-sign-on-event-11063"></a>单一登录： 事件 11063
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           11063                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |          SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED          |
|  消息正文   |      拒绝访问密码同步服务器（适用于 MIIS）。%r      |
  
## <a name="explanation"></a>解释  
 MIIS 回拨访问已经拒绝。 发生此错误最可能的原因是在 ENTSSO 系统和 MIIS 间使用 Kerberos 身份验证失败。  
  
## <a name="user-action"></a>用户操作  
 确认您的 ENTSSO 系统使用 Kerberos 身份验证。 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。