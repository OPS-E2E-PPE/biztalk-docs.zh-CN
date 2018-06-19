---
title: 单一登录： 事件 10714 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba63ab9197dcf9629f03f3d6c96f064345aaa46e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271373"
---
# <a name="single-sign-on-event-10714"></a>单一登录： 事件 10714
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10714|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED|  
|消息正文|重试过期，丢弃通知。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器： %2|  
  
## <a name="explanation"></a>解释  
 此警告事件表明密码同步通知重试已过期，并已丢弃通知。  
  
 将密码更改（从 Windows 到外部系统）传送到密码同步适配器时，密码同步适配器确认已经成功处理了密码更改。 如果在指定时间段内未发生密码更改，或者如果在更改期间发生了其他问题，则密码更改将再次传送到密码同步适配器。 只能在有限次数（最大重试次数）内完成此操作，然后将丢弃密码更改通知。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   检查有相关事件的系统和应用程序事件日志。  
  
 有关详细信息，请参阅下列资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)