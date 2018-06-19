---
title: 单一登录： 事件 10573 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39c07ba359c93c4a98211216af1c795340b5801b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270397"
---
# <a name="single-sign-on-event-10573"></a>单一登录： 事件 10573
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10573|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP|  
|消息正文|此 SSO 关联管理员帐户无法用于全局信息更新。%r<br /><br /> SSO 关联管理员: %1 %r<br /><br /> 无效帐户: %2 %r<br /><br /> 错误代码： %3|  
  
## <a name="explanation"></a>解释  
 此 SSO 关联管理员帐户无法用于全局信息更新。  
  
## <a name="user-action"></a>用户操作  
 此警告消息包含 SSO 关联管理员帐户和无效帐户的相关信息。 查看此信息，进行任何必要的更正，然后重试更新。