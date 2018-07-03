---
title: 单一登录： 事件 10599 |Microsoft Docs
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
ms.openlocfilehash: 326b94be9c05be6645a21b10f3ea302cf63be8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015678"
---
# <a name="single-sign-on-event-10599"></a>单一登录： 事件 10599
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             企业单一登录                                                                              |
| 产品版本 |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    事件 ID     |                                                                                       10599                                                                                        |
|  事件源   |                                                                                       ENTSSO                                                                                       |
|    组件    |                                                                                        N/A                                                                                         |
|  符号名称  |                                                                              SSO_WARN_ENTSSO_IS_ADMIN                                                                              |
|  消息正文   | SSO 服务在本地管理员帐户下运行。 出于安全原因，这不被建议。 有关详细信息，请参阅文档。%r<br /><br /> SSO 服务帐户： %1 |
  
## <a name="explanation"></a>解释  
 指定的 SSO 服务在本地管理员帐户下运行。 出于安全原因，这不被建议。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。