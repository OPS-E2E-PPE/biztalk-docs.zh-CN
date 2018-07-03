---
title: 单一登录： 事件 10762 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 905c59062f8f4af397872f3f7d4434a67b19842e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996006"
---
# <a name="single-sign-on-event-10762"></a>单一登录： 事件 10762
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                   企业单一登录                                                    |
| 产品版本 |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    事件 ID     |                                                             10762                                                              |
|  事件源   |                                                             ENTSSO                                                             |
|    组件    |                                                              N/A                                                               |
|  符号名称  |                                                     ENTSSO_E_WRONG_THREAD                                                      |
|  消息正文   | 已在错误的线程上调用了 SSO 客户端组件。 由于此组件具有一个事务，因此当前被锁定到一个线程。 |
  
## <a name="explanation"></a>解释  
 如果组件不具有事务，则只能为多线程。 此组件具有一个事务，因此被锁定到一个线程。  
  
## <a name="user-action"></a>用户操作  
 配置您的应用程序以便使用事务时将不调用多个线程上的 SSO 客户端组件。