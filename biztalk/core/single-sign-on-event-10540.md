---
title: "单一登录： 事件 10540 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec48afebfa36411594c28908a233409311e32df9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10540"></a>单一登录： 事件 10540
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10540|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_WARN_APP_TICKETS_NOT_ALLOWED|  
|消息正文|此应用程序未启用票证。%r<br /><br /> 应用程序名称： %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表示，此应用程序未启用票证功能。 使用 SSO 票证是每个 SSO 应用程序的可选功能。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   与应用程序管理员联系，为此 SSO 应用程序启用票证。 可使用 SSO 管理工具（GUI 或命令行）完成此操作。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)