---
title: "单一登录： 事件 11051 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe767818-f74e-415c-9287-5b7cc46e358a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a58ee5a4fd842dd292179cea0f7461a5ab0517
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11051"></a>单一登录： 事件 11051
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11051|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_SSO_ADMIN_NOT_GROUP|  
|消息正文|SSO Administrators 帐户包含一个或多个个人 （非组） 帐户。 如果已经从 Active Directory 或本地计算机删除这些个人帐户，则必须立即从 SSO 系统中删除这些帐户，否则它们会成为安全隐患。%r<br /><br /> SSO Administrators: %1 %r<br /><br /> 个人帐户： %2|  
  
## <a name="explanation"></a>解释  
 从 Active Directory 或本地计算机上删除个人帐户并不会自动从 SSO 系统删除该帐户。 这意味着如果从本地计算机删除帐户 USER1，然后另一个不同用户（例如新的员工）使用相同的名称加入到系统，则 SSO 系统会将原来 USER1 所具有的安全权限都授予新的 USER1。 这会形成安全隐患。  
  
## <a name="user-action"></a>用户操作  
 在从 Active Directory 或本地计算机中删除个人帐户之前，无需进行操作。 如果发生上述删除操作，则必须尽快从 SSO 系统删除该个人帐户。