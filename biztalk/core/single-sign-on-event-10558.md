---
title: 单一登录： 事件 10558 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2ee5c21bdf90e6aedcdbe2ac83e0e51a7f48f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270797"
---
# <a name="single-sign-on-event-10558"></a>单一登录： 事件 10558
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10558|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_USER_OWN_MAPPINGS|  
|消息正文|应用程序用户只能控制自己的映射。%r<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 客户端用户： %4|  
  
## <a name="explanation"></a>解释  
 应用程序用户尝试控制其他用户的映射。 不允许这样做。  
  
## <a name="user-action"></a>用户操作  
 映射只能由特定映射的应用程序用户来控制。