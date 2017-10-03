---
title: "单一登录： 事件 11043 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc211e4726c68a16f860dd0431a234765e80b76a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11043"></a>单一登录： 事件 11043
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11043|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_PS_ADAPTER_REPORTED_FAILURE|  
|消息正文|尝试更改外部密码时，密码同步适配器报告失败。 未在 SSO 数据库中更新外部密码。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> 错误消息: %4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 ENTSSO 向密码同步适配器发送密码更改时，必须成功更改外部密码，然后 ENTSSO 才能在 SSO 数据库中进行相应更新。 在这种情况下，不会发生这种错误。  
  
## <a name="user-action"></a>用户操作  
 注意警告消息中的信息，并咨询系统管理员。