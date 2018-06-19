---
title: 单一登录： 事件 11062 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b695b98e556d9fa23f07ee7af6602bb1ad845eb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276461"
---
# <a name="single-sign-on-event-11062"></a>单一登录： 事件 11062
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11062|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_PASSWORD_FILTER_FAILED|  
|消息正文|密码筛选失败。 将不使用任何密码筛选器。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 密码筛选器字符串: %2 %r<br /><br /> 其他数据: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 未创建筛选器和创建密码筛选器时出错。  
  
## <a name="user-action"></a>用户操作  
 若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。