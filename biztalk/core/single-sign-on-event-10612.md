---
title: 单一登录：Event 10612 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b73a601e883f651b5333224c557a1344d32943c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397714"
---
# <a name="single-sign-on-event-10612"></a>单一登录：事件 10612
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                            企业单一登录                                                                                                                            |
| 产品版本 |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    事件 ID     |                                                                                                                                      10612                                                                                                                                      |
|  事件源   |                                                                                                                                     ENTSSO                                                                                                                                      |
|    组件    |                                                                                                                                       不可用                                                                                                                                       |
|  符号名称  |                                                                                                                          SSO_WARN_TRANSACTION_TIMEOUT                                                                                                                           |
|  消息正文   | 事务超时时间超出了此操作的建议最大值。 请参阅 details.%r 文档<br /><br /> 事务 ID: %1 %r<br /><br /> 事务超时： %2 分钟 （零表示无限超时） %r<br /><br /> 建议最大值： %3 分钟 |
  
## <a name="explanation"></a>解释  
 事务已进入系统具有过大超时值。 如果 ENTSSO 系统轮询 SSO 数据库时锁定由长时间运行事务时，系统最终会处于脱机状态。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。