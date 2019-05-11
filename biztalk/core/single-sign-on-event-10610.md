---
title: 单一登录：Event 10610 | Microsoft Docs
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
ms.openlocfilehash: 451468316420c0653b967a25f233564303a6e1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397726"
---
# <a name="single-sign-on-event-10610"></a>单一登录：事件 10610
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                       企业单一登录                                                       |
| 产品版本 |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    事件 ID     |                                                                 10610                                                                 |
|  事件源   |                                                                ENTSSO                                                                 |
|    组件    |                                                                  不可用                                                                  |
|  符号名称  |                                                      SSO_WARN_CRED_CACHE_FAILED                                                       |
|  消息正文   | 凭据缓存遇到意外的错误，已经关闭。 这可能会影响 performance.%r<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 凭据缓存遇到意外的错误，已经关闭。 虽然这可能会影响性能，它不会影响功能。  
  
## <a name="user-action"></a>用户操作  
 重新启动 SSO 服务在方便的时候。