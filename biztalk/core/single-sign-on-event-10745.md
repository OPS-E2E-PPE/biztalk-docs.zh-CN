---
title: "单一登录： 事件 10745 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe734562b9d8b3564a08f3f5196d53996bf40ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10745"></a>单一登录： 事件 10745
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10745|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_ADAPTER_OFFLINE|  
|消息正文|适配器处于脱机状态。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 错误消息: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 此错误事件表示指定的适配器处于脱机状态。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   检查相关错误的系统和应用程序事件日志。  
  
-   检查外部适配器是否存在错误。  
  
 有关详细信息，请参阅下列资源：  
  
-   [如何管理密码同步](../core/how-to-administer-password-synchronization.md)