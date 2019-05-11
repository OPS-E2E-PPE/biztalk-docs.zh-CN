---
title: 单一登录：Event 10762 | Microsoft Docs
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
ms.openlocfilehash: b26f196e2431f0229ac28b9d8f2718b551a58b1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396653"
---
# <a name="single-sign-on-event-10762"></a>单一登录：事件 10762
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                   企业单一登录                                                    |
| 产品版本 |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    事件 ID     |                                                             10762                                                              |
|  事件源   |                                                             ENTSSO                                                             |
|    组件    |                                                              不可用                                                               |
|  符号名称  |                                                     ENTSSO_E_WRONG_THREAD                                                      |
|  消息正文   | 已对错误的线程调用 SSO 客户端组件。 它当前已锁定到一个线程，因为它具有一个事务。 |
  
## <a name="explanation"></a>解释  
 当它们不具有事务组件只能是多线程。 此组件有一个事务，因此它锁定到一个线程。  
  
## <a name="user-action"></a>用户操作  
 配置你的应用程序，以便它将不会调用 SSO 客户端组件在多个线程上使用事务时。