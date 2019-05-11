---
title: 单一登录：事件 11040 |Microsoft Docs
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
ms.openlocfilehash: a071aa4959aaf8668a0713221904a1a612d0a417
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401010"
---
# <a name="single-sign-on-event-11040"></a>单一登录：事件 11040
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                  企业单一登录                                                                  |
| 产品版本 |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    事件 ID     |                                                                            11040                                                                            |
|  事件源   |                                                                           ENTSSO                                                                            |
|    组件    |                                                                             不可用                                                                             |
|  符号名称  |                                                                  SSO_WARN_NETWORK_SERVICE                                                                   |
|  消息正文   | SSO 服务正在网络服务帐户。 有一些特殊注意事项为此帐户。 请参阅有关 details.%r 文档 |
  
## <a name="explanation"></a>解释  
 SSO 服务正在网络服务帐户。 有一些特殊注意事项为此帐户。 例如，重新启动后需要，则添加网络服务帐户。 此外下一项网络服务, 运行帐户会限制您只能在非常有限的情况中运行。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。