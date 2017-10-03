---
title: "单一登录： 事件 10807 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e269b22bc8ea2fec013123d515ac04bd3f60d46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10807"></a>单一登录： 事件 10807
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10807|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS|  
|消息正文|未确认的通知太多。|  
  
## <a name="explanation"></a>解释  
 每次发送密码更改通知时都会收到一条确认消息。 这样就超出了未确认通知的限制。  
  
## <a name="user-action"></a>用户操作  
 检查密码同步适配器。