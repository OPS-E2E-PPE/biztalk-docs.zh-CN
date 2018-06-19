---
title: 单一登录： 事件 10681 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0f1b6c27f3e77220d4615da1c0b5bb343344de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272037"
---
# <a name="single-sign-on-event-10681"></a>单一登录： 事件 10681
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10681|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE|  
|消息正文|外部密码更改。 Windows 密码未更改，因为一个或多个外部帐户更改失败。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3|  
  
## <a name="explanation"></a>解释  
 此警告事件表明，因为一个或多个外部帐户更改失败导致 Windows 密码未更改。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   检查系统和应用程序事件日志，了解相关事件。  
  
-   使用 SSO 管理工具验证适配器配置。  
  
-   验证外部系统。  
  
## <a name="more-info"></a>详细信息
  
-   [密码同步](../core/password-synchronization2.md)  
  
-   **密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]