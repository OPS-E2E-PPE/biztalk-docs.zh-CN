---
title: 单一登录：事件 11042 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bef9cdffc7e1b11409491ad27bb195d40c639518
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400986"
---
# <a name="single-sign-on-event-11042"></a>单一登录：事件 11042
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                   企业单一登录                                                                                                                                                   |
| 产品版本 |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    事件 ID     |                                                                                                                                                             11042                                                                                                                                                             |
|  事件源   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    组件    |                                                                                                                                                              不可用                                                                                                                                                              |
|  符号名称  |                                                                                                                                                SSO_WARN_ACCESS_DENIED_ACCOUNTS                                                                                                                                                |
|  消息正文   | 访问被拒绝。<br /><br /> 客户端用户必须是以下帐户之一的成员才能执行此 function.%r<br /><br /> SSO Administrators: %1 %r<br /><br /> SSO 关联管理员: %2 %r<br /><br /> 应用程序管理员: %3 %r<br /><br /> 应用程序用户: %4 %r<br /><br /> 其他数据： %5 |
  
## <a name="explanation"></a>解释  
 客户端用户必须是一个警告来执行此功能中列出的帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 您必须加入一个帐户来执行此功能。