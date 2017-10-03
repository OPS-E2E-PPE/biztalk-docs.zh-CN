---
title: "单一登录： 事件 10749 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 864c887cb6c115a2f766f9c06cbaa292fdbeace2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10749"></a>单一登录： 事件 10749
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10749|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_PS_CLIENT_PING|  
|消息正文|无法联系目标 SSO 服务器。<br /><br /> 请检查 SSO 服务是否正在该服务器上运行，以及是否能够连接到该服务。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> SSO 服务器名: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 此警告事件表示 SSO 密码同步不能联系指定的目标 SSO 服务器。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   使用 ENTSSO 服务器管理单元检查服务器。  
  
-   启动企业单一登录服务（如果该服务未运行）。  
  
-   检查到 SSO 服务器的网络连接是否正常。  
  
-   检查目标 SSO 服务器上的防火墙。  
  
 有关详细信息，请参阅下列资源：  
  
-   [如何使用服务器管理单元](../core/how-to-use-the-servers-snap-in.md)