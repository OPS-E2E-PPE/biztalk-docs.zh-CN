---
title: 单一登录：事件 11071 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43105808e83b06f780736e7168581d3854305439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247483"
---
# <a name="single-sign-on-event-11071"></a>单一登录：事件 11071
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                   企业单一登录                                                                                   |
| 产品版本 |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    事件 ID     |                                                                                             11071                                                                                             |
|  事件源   |                                                                                            ENTSSO                                                                                             |
|    组件    |                                                                                              不可用                                                                                              |
|  符号名称  |                                                                         SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH                                                                          |
|  消息正文   | 已放弃 Windows 密码更改，因为 Windows 密码长度为零 characters.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 客户端用户： %3 |
  
## <a name="explanation"></a>解释  
 Windows 密码更改已被丢弃，因为 Windows 密码长度为零个字符。 提供 Windows 帐户和客户端用户名。  
  
## <a name="user-action"></a>用户操作  
 同样，使用的数量和类型的字符所需的 SSO 系统更改的密码。