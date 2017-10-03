---
title: "单一登录： 事件 10615 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9570290f82821a80d22826f41d4ed669e29f5b4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10615"></a>单一登录： 事件 10615
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10615|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_NO_UPDATE_TICKET_TIMEOUT|  
|消息正文|客户端用户必须是 SSO 管理员帐户的成员才能更改应用程序的票证超时值。%r<br /><br /> 客户端用户: %1 %r<br /><br /> SSO Administrators: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 客户端用户必须是 SSO 管理员帐户的成员才能更改应用程序的票证超时值。  
  
## <a name="user-action"></a>用户操作  
 请系统管理员帮助您找到一个 SSO 管理员帐户成员来进行此更改。