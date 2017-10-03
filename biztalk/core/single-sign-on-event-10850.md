---
title: "单一登录： 事件 10850 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e9bef6d104b8da3c41d295005a7a274a1d2610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10850"></a>单一登录： 事件 10850
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10850|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE|  
|消息正文|不能创建已指定“已启用”标志的应用程序。|  
  
## <a name="explanation"></a>解释  
 启用应用程序前，需要先创建该应用程序，并为其每个字段（如，用户 ID 和密码）输入字段信息。 不能创建已设置“已启用”字段的应用程序。  
  
## <a name="user-action"></a>用户操作  
 使用创建应用程序 API 或新建关联应用程序向导再次创建该应用程序。 应用程序创建完成并填充字段后，启用该应用程序。