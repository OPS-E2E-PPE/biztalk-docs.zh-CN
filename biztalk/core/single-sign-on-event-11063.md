---
title: 单一登录：事件 11063 |Microsoft Docs
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
ms.openlocfilehash: a5971a2ace4307128d094a6b88c4928616173694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258680"
---
# <a name="single-sign-on-event-11063"></a>单一登录：事件 11063
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           11063                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |          SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED          |
|  消息正文   |      密码同步服务器 （用于 MIIS) 访问 denied.%r      |
  
## <a name="explanation"></a>解释  
 MIIS 回拨访问已被拒绝。 此错误最可能原因是未能使用 Kerberos 身份验证之间的 ENTSSO 系统和 MIIS。  
  
## <a name="user-action"></a>用户操作  
 确认您的 ENTSSO 系统使用 Kerberos 身份验证。 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。