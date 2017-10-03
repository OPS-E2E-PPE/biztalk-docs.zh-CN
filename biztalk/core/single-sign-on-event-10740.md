---
title: "单一登录： 事件 10740 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928760bebef1119207ee6a3021cd39c22ceacad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10740"></a>单一登录： 事件 10740
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10740|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_INVALID_WINDOWS_USER|  
|消息正文|此 Windows 帐户不能用于应用程序更新。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 错误代码： %3|  
  
## <a name="explanation"></a>解释  
 此警告事件表明，该 Windows 帐户（在事件消息中指定）不能用于应用程序更新。 为主机组应用程序更改 Windows 帐户时可能发生这种情况。 主机组应用程序用于从外部系统到 Windows 系统的单一登录。 这些应用程序可将一组外部用户映射到单个 Windows 帐户。 该应用程序的“应用程序用户”字段中定义了所映射到的 Windows 帐户。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   检查您所使用的 Windows 帐户是否有效。  
  
-   重新创建具有正确 Windows 帐户属性的 Windows 帐户。  
  
 有关详细信息，请参阅下列资源：  
  
-   [密码同步](../core/password-synchronization2.md)