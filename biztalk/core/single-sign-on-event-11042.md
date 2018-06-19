---
title: 单一登录： 事件 11042 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da20346fbf2f73ac2ab64db3c9137394aa5bd366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277053"
---
# <a name="single-sign-on-event-11042"></a>单一登录： 事件 11042
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11042|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_ACCESS_DENIED_ACCOUNTS|  
|消息正文|访问被拒绝。<br /><br /> 若要执行此功能，客户端用户必须是以下某一帐户中的成员。%r<br /><br /> SSO Administrators: %1 %r<br /><br /> SSO 关联管理员: %2 %r<br /><br /> Application Administrators: %3 %r<br /><br /> Application Users: %4 %r<br /><br /> 其他数据： %5|  
  
## <a name="explanation"></a>解释  
 若要执行此功能，客户端用户必须是警告中列出的其中一个帐户中的成员。  
  
## <a name="user-action"></a>用户操作  
 若要执行此功能，您必须加入到其中一个帐户。