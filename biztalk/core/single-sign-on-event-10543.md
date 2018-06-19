---
title: 单一登录： 事件 10543 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9bf30640bf61f9c88de3fedbb5727be7a715aa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269997"
---
# <a name="single-sign-on-event-10543"></a>单一登录： 事件 10543
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10543|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_WARN_ORIGINAL_TICKET_VALIDATED|  
|消息正文|需要验证之后发出票证。 此应用程序在不经过验证的情况下无法兑换票证。%r<br /><br /> 应用程序名称： %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表明应用程序票证需要经过验证之后才能发出。 票证未经验证不能兑换。 票证的验证基于每个关联应用程序。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   如果您使用的是企业单一登录，请确保您的消息只通过受信任主机传输。 这将降低在消息中篡改数据的风险。  
  
-   如果情况允许，请针对此应用程序关闭验证。 验证是一个管理选项，可以针对整个系统、或只针对此特定的应用程序关闭该选项。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)