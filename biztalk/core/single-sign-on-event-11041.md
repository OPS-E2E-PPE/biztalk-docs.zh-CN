---
title: 单一登录： 事件 11041 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 186aefc4-fbb0-4f79-baa0-a9f4a7abd71a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 004945467fcbc1a3fc4dd6ed5c2b8ef07b8bb9bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982238"
---
# <a name="single-sign-on-event-11041"></a>单一登录： 事件 11041
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                   |
| 产品版本 |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            11041                                                                                             |
|  事件源   |                                                                                            ENTSSO                                                                                            |
|    组件    |                                                                                             N/A                                                                                              |
|  符号名称  |                                                                                    SSO_WARN_LOCAL_ACCOUNT                                                                                    |
|  消息正文   | SSO 服务在本地帐户下运行。 不建议这样做，否则会限制 SSO 的功能。 有关详细信息，请参阅您的文档。%r<br /><br /> SSO 服务帐户： %1 |
  
## <a name="explanation"></a>解释  
 SSO 服务在本地帐户下运行。 不建议这样做，否则会限制 SSO 的功能。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。