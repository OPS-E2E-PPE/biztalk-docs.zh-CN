---
title: "单一登录： 事件 10762 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 487fbeb0f077950605432861a9118eacd93f2c89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10762"></a>单一登录： 事件 10762
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10762|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_WRONG_THREAD|  
|消息正文|已在错误的线程上调用了 SSO 客户端组件。 由于此组件具有一个事务，因此当前被锁定到一个线程。|  
  
## <a name="explanation"></a>解释  
 如果组件不具有事务，则只能为多线程。 此组件具有一个事务，因此被锁定到一个线程。  
  
## <a name="user-action"></a>用户操作  
 配置您的应用程序以便使用事务时将不调用多个线程上的 SSO 客户端组件。