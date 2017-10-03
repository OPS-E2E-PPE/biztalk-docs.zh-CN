---
title: "单一登录： 事件 10677 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876048e9c86cf908be9eda121340ec60354803c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10677"></a>单一登录： 事件 10677
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10677|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_NO_EXISTING_PASSWORD|  
|消息正文|外部密码更改。 无法验证旧密码，因为没有可用于此外部帐户的现有凭据。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4|  
  
## <a name="explanation"></a>解释  
 此警告事件表示由于旧密码没有现有凭据，因此外部密码更改无法完成。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   确定分配到此适配器（事件日志消息中的名称）的应用程序，然后使用 SSO 管理工具设置此外部帐户的外部凭据。 必须在所有这些应用程序中设置外部密码（对于给定帐户）。  
  
## <a name="more-info"></a>详细信息
  
-   [密码同步](../core/password-synchronization2.md)  
  
-   **密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]