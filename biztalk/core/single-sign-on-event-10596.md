---
title: "单一登录： 事件 10596 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051fdf627edc3f560a8d02026207dc2fe5bb3533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10596"></a>单一登录： 事件 10596
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10596|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_TICKET_USER_NOT_IN_GROUP|  
|消息正文|无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 票证的发布日期: %2 %r<br /><br /> Application Users: %3|  
  
## <a name="explanation"></a>解释  
 无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 将票证重新颁发给属于应用程序用户帐户成员的用户。