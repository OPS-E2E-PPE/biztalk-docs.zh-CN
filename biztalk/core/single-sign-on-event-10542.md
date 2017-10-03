---
title: "单一登录： 事件 10542 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebcf97a9de014d0651c9f239c1ae6e846925f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10542"></a>单一登录： 事件 10542
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10542|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_WARN_APP_TICKETS_VALIDATED|  
|消息正文|由于未经过验证，因此无法兑换此应用程序的票证。%r<br /><br /> 应用程序名称： %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表示，应用程序票证在不经过验证的情况下无法进行兑换。 应用程序票证兑换后，它们可能经过了验证也可能未经过验证。 验证过程会提高安全性，因为会将发出票证的用户的名称与 BizTalk 消息中用户的名称进行比较。 如果名称不相同，则验证失败。 当 BizTalk 消息在不受信任的主机中传输时，BizTalk 消息中用户的名称会更改为该不受信任主机的名称。 验证过程确保了 BizTalk 消息只能在受信任的主机中传输。 此消息特别指出，由于 SSO 系统选项设置原因，需要在应用程序系统级别进行验证，但是呼叫者并未提供任何验证信息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   如果您使用的是 BizTalk Server，请确保您的消息只在受信任的主机之间传输。 这将降低在消息中篡改数据的风险。  
  
-   如果情况允许，请针对此应用程序关闭验证。 验证是一个管理选项，可以针对整个系统、或只针对此特定的应用程序关闭该选项。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)