---
title: 单一登录： 事件 10603 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738d2939f4178fdfaa115b8dfcc2273935c37b85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270389"
---
# <a name="single-sign-on-event-10603"></a>单一登录： 事件 10603
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10603|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_DB_ACCESS|  
|消息正文|无法访问 SSO 数据库。 如果此情况继续存在，SSO 服务将脱机。%r<br /><br /> %1.%r<br /><br /> SQL 错误代码： %2|  
  
## <a name="explanation"></a>解释  
 SSO 数据库不可用。  
  
## <a name="user-action"></a>用户操作  
 检查包含在警告中的 SQL 错误代码。 错误代码中可能会提供一些指导信息。 如果没有，请联系 Microsoft 产品支持服务。