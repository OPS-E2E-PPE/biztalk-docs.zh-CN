---
title: 单一登录： 事件 10518 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 274e29f9-1933-4e40-83c0-2e84c6708315
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27b82d7f0a6bbaf02400679add53851867d728c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271309"
---
# <a name="single-sign-on-event-10518"></a>单一登录： 事件 10518
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10518|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_BAD_USER_GROUP|  
|消息正文|用于此应用程序的应用程序用户帐户无效。 如果是本地帐户，请检查服务器上是否存在此帐户。 如果是域帐户，请与域管理员联系。 当帐户有效时，启用应用程序。 如果您不打算在此计算机上使用此应用程序，则可以忽略此消息。<br /><br /> 应用程序名称: %1 %r<br /><br /> Application Users: %2 %r<br /><br /> 无效帐户: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 此警告事件表示应用程序用户组帐户不是有效的 Windows 帐户。 每个关联应用程序都有一个对应的应用程序用户帐户组。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   验证指定的应用程序用户帐户是否存在。  
  
-   使用 SSO 管理实用工具来验证指定的关联应用程序是否配置为使用正确的应用程序用户帐户。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 用户组](../core/sso-user-groups.md)  
  
-   [SSO 关联应用程序](../core/sso-affiliate-applications.md)  
  
-   [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)