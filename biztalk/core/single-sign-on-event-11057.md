---
title: "单一登录： 事件 11057 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca69661d1421433c44472e0572c5d4d4bf76a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11057"></a>单一登录： 事件 11057
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11057|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS|  
|消息正文|直接密码更改。 已将此映射的某些缺少的外部凭据字段设置为默认值。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 应用程序名称: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户： %4|  
  
## <a name="explanation"></a>解释  
 尽管可以使用直接密码同步来更改密码，但此功能只支持一个外部凭据字段。 在这种情况下 ENTSSO 系统遇到多个外部凭据字段，并已将这些字段设置为默认 （空白） 值。  
  
## <a name="user-action"></a>用户操作  
 不需要用户进行任何操作。