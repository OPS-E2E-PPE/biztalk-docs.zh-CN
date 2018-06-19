---
title: 单一登录： 事件 10544 |Microsoft 文档
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
ms.openlocfilehash: a1a01cda4272e2851f929c35fd2b767c321a9dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270573"
---
# <a name="single-sign-on-event-10544"></a>单一登录： 事件 10544
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10544|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_WARN_TICKET_EXPIRED|  
|消息正文|票证已过期。%r<br /><br /> 应用程序名称： %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表示应用程序的票证超时已过期。 票证超时可以在系统级别和应用程序级别上指定。 如果在系统级别和应用程序级别上都已指定超时，则将由应用程序级别的超时决定过期时间。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   确定票证在验证之前就过期的原因。  
  
-   确保票证超时值足够长，以便可以从颁发票证之时延续到兑换票证之时。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)