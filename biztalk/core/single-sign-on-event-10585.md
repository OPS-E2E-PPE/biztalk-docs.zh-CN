---
title: 单一登录：Event 10585 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfca6095e57936df056558e84ec0ed8ecdb8b002
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530944"
---
# <a name="single-sign-on-event-10585"></a>单一登录：事件 10585
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                 企业单一登录                                                                                 |
| 产品版本 |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    事件 ID     |                                                                                           10585                                                                                           |
|  事件源   |                                                                                          ENTSSO                                                                                           |
|    组件    |                                                                                            不可用                                                                                            |
|  符号名称  |                                                                             SSO_WARN_EXPIRED_TICKET_REDEEMED                                                                              |
|  消息正文   | 票证将兑换票证超时期限已过。 这允许，因为 application.%r 禁用票证超时值<br /><br /> 应用程序名称： %1 |
  
## <a name="explanation"></a>解释  
 可以启用或禁用票证超时值。 在这种情况下将兑换票证即使其超时期限已过，因为已禁用超时。  
  
## <a name="user-action"></a>用户操作  
 如果应禁用超时，不不需要任何用户操作。 但是，如果您没有意识到此特定应用程序已禁用其超时，则应检查应用程序立即以确保你想要允许它。