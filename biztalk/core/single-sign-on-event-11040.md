---
title: 单一登录： 事件 11040 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eefc6c65e07b430851606ce7779aad3771776a83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019067"
---
# <a name="single-sign-on-event-11040"></a>单一登录： 事件 11040
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                  企业单一登录                                                                  |
| 产品版本 |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    事件 ID     |                                                                            11040                                                                            |
|  事件源   |                                                                           ENTSSO                                                                            |
|    组件    |                                                                             N/A                                                                             |
|  符号名称  |                                                                  SSO_WARN_NETWORK_SERVICE                                                                   |
|  消息正文   | SSO 服务在网络服务帐户下运行。 此帐户有一些特殊的注意事项。 有关详细信息，请参阅您的文档。%r |
  
## <a name="explanation"></a>解释  
 SSO 服务在网络服务帐户下运行。 此帐户有一些特殊的注意事项。 例如，添加网络服务帐户后需要重新启动。 同时，在网络服务帐户下运行会限制您只能在非常有限的情况下运行。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。