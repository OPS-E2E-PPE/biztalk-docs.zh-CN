---
title: 单一登录： 事件 10567 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f29c8d9-3da2-4de7-b61f-8c586382b68f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb6f57bed2f386363d3ae4d92b4e300061056826
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270029"
---
# <a name="single-sign-on-event-10567"></a>单一登录： 事件 10567
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10567|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_INVALID_APP_USER_GROUP|  
|消息正文|该 Application Users 帐户对于应用程序 update.%r 无效<br /><br /> 应用程序名称: %1 %r<br /><br /> Application Users: %2 %r<br /><br /> 无效帐户: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 您尝试更新的应用程序用户帐户无效或不存在。  
  
## <a name="user-action"></a>用户操作  
 检查帐户的名称是否正确。