---
title: "单一登录： 事件 10674 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d239353276657e85c7fbdcfa634c3c1268723724
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10674"></a>单一登录： 事件 10674
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10674|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED|  
|消息正文|外部密码更改将导致多个 Windows 帐户更改。%r<br /><br /> 此操作已被阻止，因为此外部系统的适配器配置为不允许映射冲突。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> Windows 帐户 1: %4 %r<br /><br /> Windows 帐户 2: %5|  
  
## <a name="explanation"></a>解释  
 此警告事件表示，外部密码更改将导致多个 Windows 帐户更改。 已阻止此更改，因为适配器配置不允许进行此项更改。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   如果预期并且允许映射冲突，请使用 SSO 管理工具来配置**允许映射冲突**密码同步适配器属性。  
  
## <a name="more-info"></a>详细信息
  
-   **密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [密码同步](../core/password-synchronization2.md)