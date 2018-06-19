---
title: 单一登录： 事件 10585 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b4781628121edad8904130e546038698de03161
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271517"
---
# <a name="single-sign-on-event-10585"></a>单一登录： 事件 10585
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10585|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_EXPIRED_TICKET_REDEEMED|  
|消息正文|票证超时期限过后将兑换票证。 允许此操作是因为已禁用了此应用程序的票证超时。%r<br /><br /> 应用程序名称： %1|  
  
## <a name="explanation"></a>解释  
 可以启用也可以禁用票证超时。 在这种情况下将兑换票证（尽管票证超时期限已过），因为已禁用超时。  
  
## <a name="user-action"></a>用户操作  
 如果应禁用超时，则不需要任何用户操作。 但是，如果您不知道此特定应用程序已禁用了超时，请立即检查应用程序以确保您希望允许超时。