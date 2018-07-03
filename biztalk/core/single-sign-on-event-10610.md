---
title: 单一登录： 事件 10610 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c90855c1f136dc8204afe718ea4456c834ab667
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024403"
---
# <a name="single-sign-on-event-10610"></a>单一登录： 事件 10610
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                       企业单一登录                                                       |
| 产品版本 |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    事件 ID     |                                                                 10610                                                                 |
|  事件源   |                                                                ENTSSO                                                                 |
|    组件    |                                                                  N/A                                                                  |
|  符号名称  |                                                      SSO_WARN_CRED_CACHE_FAILED                                                       |
|  消息正文   | 凭据缓存遇到意外错误并已关闭。 这可能会影响 performance.%r<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 凭据缓存遇到意外错误并已关闭。 尽管这可能会影响性能，但对功能运转没有影响。  
  
## <a name="user-action"></a>用户操作  
 在方便的时候重新启动 SSO 服务。