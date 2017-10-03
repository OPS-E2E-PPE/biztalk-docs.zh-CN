---
title: "单一登录： 事件 10613 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7230a0d6400a7265ef9f3cedb6bb47cc23aade
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10613"></a>单一登录： 事件 10613
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10613|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_RPC_CALLBACK|  
|消息正文|SSO 服务器访问被拒绝。%r<br /><br /> 客户端用户: %1 %r<br /><br /> RPC 调用信息: %2: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 从客户端到 SSO 服务器的调用已作出，但未被接受。 这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请注意此消息中的信息和事件日志中的任何相关信息并与 Microsoft 产品支持服务联系。