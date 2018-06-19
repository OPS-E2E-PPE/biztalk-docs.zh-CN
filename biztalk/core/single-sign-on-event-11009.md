---
title: 单一登录： 事件 11009 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99308e7a9e709cff5c0e1e15963eeb4769c00f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278597"
---
# <a name="single-sign-on-event-11009"></a>单一登录： 事件 11009
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11009|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_NOT_SSO_ADMIN|  
|消息正文|客户端用户不是 SSO 管理员帐户的成员。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2\\%3 %r<br /><br /> SSO Administrators: %4|  
  
## <a name="explanation"></a>解释  
 客户端用户不是 SSO 管理员帐户的成员。 只有当审核级别设置为高时，才会出现此警告。  
  
## <a name="user-action"></a>用户操作  
 若要修复此情形，您必须使客户端用户成为 SSO 管理员帐户的成员。 若要阻止以后出现此警告，您可以降低审核级别。