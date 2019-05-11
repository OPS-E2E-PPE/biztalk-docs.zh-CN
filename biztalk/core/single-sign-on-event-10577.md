---
title: 单一登录：Event 10577 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4563567a-9ee3-4c32-a202-c2521fd95b6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10d381ccbeb1809fbd3a668bd8d1e38264a3a5fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303389"
---
# <a name="single-sign-on-event-10577"></a>单一登录：事件 10577
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                             企业单一登录                                                                                                             |
| 产品版本 |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    事件 ID     |                                                                                                                       10577                                                                                                                       |
|  事件源   |                                                                                                                      ENTSSO                                                                                                                       |
|    组件    |                                                                                                                        不可用                                                                                                                        |
|  符号名称  |                                                                                                          SSO_INFO_CHANGED_SSO_AFF_ADMIN                                                                                                           |
|  消息正文   | 已更新的 SSO Affiliate Administrators account.%r<br /><br /> 新的 SSO 关联管理员: %1 %r<br /><br /> 旧 SSO 关联管理员: %2 %r<br /><br /> 跟踪 ID: %3 %r<br /><br /> 客户端计算机: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 这是一条信息性消息，也可用于跟踪 SSO 系统中的发生的与安全相关的重要事件。 此消息表明已更新 SSO 关联管理员帐户。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。