---
title: "单一登录： 事件 10709 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a28807d9307ba1217e5b48e24facfe36711536f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10709"></a>单一登录： 事件 10709
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10709|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_PS_PCNS_ACCESS_DENIED|  
|消息正文|仅接受来自访问域中域控制器上 PCNS 的 Windows 密码更改。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 访问域: %3 %r<br /><br /> 访问 Sid: %4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 此警告事件表明，收到来自 ENTSSO 服务器域外某个服务器上密码更改通知服务 (PCNS) 的一个 Windows 密码更改。 仅接受来自 ENTSSO 服务器所在域中的域控制器的 Windows 密码更改。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   将同一域中的 ENTSSO 服务器配置为 PCNS。  
  
 有关详细信息，请参阅下列资源：  
  
-   [密码同步](../core/password-synchronization2.md)