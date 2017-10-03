---
title: "单一登录： 事件 10851 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdd719c77dc77fb626f97460ed92bd74ab6da812
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10851"></a>单一登录： 事件 10851
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10851|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC|  
|消息正文|应用程序无法分配到密码同步适配器，因为其已设置“直接密码同步”标志。|  
  
## <a name="explanation"></a>解释  
 应用程序无法使用直接密码同步和密码同步适配器。  
  
## <a name="user-action"></a>用户操作  
 检查您的应用程序并决定其是否应具有直接密码同步。如果应该，则保留标记设置，并且不要尝试将应用程序分配到密码同步适配器。 如果不应该，则关闭标志并根据需要将应用程序分配到密码同步适配器。