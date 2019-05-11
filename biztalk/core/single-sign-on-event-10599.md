---
title: 单一登录：Event 10599 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd671aa5-b243-4081-9a4e-87103be9a1d7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 263d2b0b50e43b485e60a56ebd74e0164dab8b0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397812"
---
# <a name="single-sign-on-event-10599"></a>单一登录：事件 10599
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             企业单一登录                                                                              |
| 产品版本 |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    事件 ID     |                                                                                       10599                                                                                        |
|  事件源   |                                                                                       ENTSSO                                                                                       |
|    组件    |                                                                                        不可用                                                                                         |
|  符号名称  |                                                                              SSO_WARN_ENTSSO_IS_ADMIN                                                                              |
|  消息正文   | SSO 服务正在本地管理员帐户。 出于安全原因，这不被建议。 请参阅 details.%r 文档<br /><br /> SSO 服务帐户： %1 |
  
## <a name="explanation"></a>解释  
 指定的 SSO 服务正在本地管理员帐户。 出于安全原因，这不被建议。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。