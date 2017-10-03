---
title: "单一登录： 事件 10673 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8068d7ec43cc07dfd76b21dc749ca062226e49f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10673"></a>单一登录： 事件 10673
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10673|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED|  
|消息正文|外部密码更改将造成对多个 Windows 帐户的更改。%r<br /><br /> 这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> Windows 帐户 1: %4 %r<br /><br /> Windows 帐户 2: %5|  
  
## <a name="explanation"></a>解释  
 此信息事件表示，外部密码更改将导致多个 Windows 帐户更改。  
  
## <a name="user-action"></a>用户操作  
  
-   不需要用户进行任何操作。  
  
## <a name="more-info"></a>详细信息
  
-   [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  
  
-   **密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [密码同步](../core/password-synchronization2.md)