---
title: 单一登录： 事件 10577 |Microsoft Docs
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
ms.openlocfilehash: 769576430df7ac3ce7ec0ec31a3e7b3eea03968c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003054"
---
# <a name="single-sign-on-event-10577"></a>单一登录： 事件 10577
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                             企业单一登录                                                                                                             |
| 产品版本 |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    事件 ID     |                                                                                                                       10577                                                                                                                       |
|  事件源   |                                                                                                                      ENTSSO                                                                                                                       |
|    组件    |                                                                                                                        N/A                                                                                                                        |
|  符号名称  |                                                                                                          SSO_INFO_CHANGED_SSO_AFF_ADMIN                                                                                                           |
|  消息正文   | 已更新 SSO 关联管理员帐户。%r<br /><br /> 新的 SSO 关联管理员: %1 %r<br /><br /> 旧 SSO 关联管理员: %2 %r<br /><br /> 跟踪 ID: %3 %r<br /><br /> 客户端计算机: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 这是信息性消息，可以用于跟踪 SSO 系统中发生的与安全有关的重要事件。 此消息表明 SSO 关联应用程序帐户已更新。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。