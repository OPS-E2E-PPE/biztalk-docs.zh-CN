---
title: 单一登录：Event 10557 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5cd5be8005a1ce13c1ad5f13c580e6e72353b9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398839"
---
# <a name="single-sign-on-event-10557"></a>单一登录：事件 10557
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                        企业单一登录                                                                                         |
| 产品版本 |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    事件 ID     |                                                                                                  10557                                                                                                   |
|  事件源   |                                                                                                  ENTSSO                                                                                                  |
|    组件    |                                                                                                   不可用                                                                                                    |
|  符号名称  |                                                                                   SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS                                                                                   |
|  消息正文   | 不允许应用程序用户控制的组 applications.%r 映射<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 客户端用户： %4 |
  
## <a name="explanation"></a>解释  
 应用程序用户没有足够的特权创建或控制组应用程序的映射。  
  
## <a name="user-action"></a>用户操作  
 必须由应用程序管理员执行此活动。