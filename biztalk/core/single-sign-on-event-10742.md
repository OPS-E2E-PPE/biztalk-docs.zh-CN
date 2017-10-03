---
title: "单一登录： 事件 10742 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb3acb03e60d1d7a7e705ac8b36aa5157616f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10742"></a>单一登录： 事件 10742
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10742|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_NO_UPDATE_ADAPTER|  
|消息正文|若要更新适配器，客户端用户必须是 SSO 管理员帐户或应用程序管理员帐户的成员。%r<br /><br /> 客户端用户: %1 %r<br /><br /> SSO Administrators: %2 %r<br /><br /> Application Administrators: %3 %r<br /><br /> 适配器: %4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 此警告事件表示进行了更新指定适配器的尝试，但是无法完成，因为所使用的用户帐户不是 SSO 管理员帐户或应用程序管理员帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   将用户帐户添加到 SSO 管理员帐户或应用程序管理员帐户。  
  
-   重试更新。  
  
 有关详细信息，请参阅下列资源：  
  
-   [如何管理密码同步](../core/how-to-administer-password-synchronization.md)