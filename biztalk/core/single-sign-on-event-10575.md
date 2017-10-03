---
title: "单一登录： 事件 10575 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b21e8826ba1dc77676929a872a6091e3531310
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10575"></a>单一登录： 事件 10575
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10575|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_INFO_CHANGED_SECRET_SERVER|  
|消息正文|已更新密钥服务器名称。%r<br /><br /> 新的密钥服务器: %1 %r<br /><br /> 旧的密钥服务器: %2 %r<br /><br /> 跟踪 ID: %3 %r<br /><br /> 客户端计算机: %4 %r<br /><br /> 客户端用户： %5|  
  
## <a name="explanation"></a>解释  
 这是信息性消息，可以用于跟踪 SSO 系统中发生的与安全有关的重要事件。 此消息表明密钥服务器名称已经更新。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。