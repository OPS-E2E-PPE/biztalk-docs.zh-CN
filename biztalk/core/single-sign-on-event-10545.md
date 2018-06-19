---
title: 单一登录： 事件 10545 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64cb10ceef5827f9c0b0aab5d9810db061af8a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270645"
---
# <a name="single-sign-on-event-10545"></a>单一登录： 事件 10545
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10545|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED|  
|消息正文|SSO 系统没有启用票证。|  
  
## <a name="explanation"></a>解释  
 此警告事件表示没有为 SSO 系统启动票证。 如果在系统级别上禁用了票证功能，则也不能在关联应用程序级别上使用此功能。 它可启用在系统级别的票证和 Affiliate 应用程序级别禁用它。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   启用 SSO 系统级别的票证。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)