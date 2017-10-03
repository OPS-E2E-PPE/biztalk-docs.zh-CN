---
title: "单一登录： 事件 10731 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10960489638aa565a11ecc32c70fc3a8fc6d477b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10731"></a>单一登录： 事件 10731
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10731|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_INVALID_USER_NOT_IN_GROUP|  
|消息正文|无法创建映射，因为指定的用户不是“应用程序用户”帐户的成员。%r<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> Application Users: %4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 此警告事件表明由于指定的用户不是应用程序用户帐户的成员而无法创建映射。  
  
 每个关联应用程序都具有应用程序用户的组帐户。 此帐户的成员可以在关联应用程序中验证其凭据并且可以在关联应用程序中管理其凭据映射。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   将指定的用户添加到指定的关联应用程序的应用程序用户的组。  
  
 有关详细信息，请参阅下列资源：  
  
-   [SSO 用户组](../core/sso-user-groups.md)  
  
-   [SSO 关联应用程序](../core/sso-affiliate-applications.md)