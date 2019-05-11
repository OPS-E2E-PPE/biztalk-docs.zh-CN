---
title: 单一登录：Event 10544 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 262a57b44143909b40842eddf7b1aba4049ca130
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243502"
---
# <a name="single-sign-on-event-10544"></a>单一登录：事件 10544
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10544                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                             CO                             |
|  符号名称  |                  SSO_WARN_TICKET_EXPIRED                   |
|  消息正文   | 票证已 expired.%r<br /><br /> 应用程序名称： %1 |

## <a name="explanation"></a>解释  
 此警告事件表示应用程序票证超时已过期。 可以在系统级别和应用程序级别指定票证超时。 如果指定了系统级别和应用程序级超时，应用程序级超时用于确定的到期时间。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 确定票证在验证之前过期的原因。  

- 确保票证超时值足够长上, 一次之间的时间兑换颁发票证之时的时间。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [SSO 票证](../core/sso-tickets.md)  

- [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)
