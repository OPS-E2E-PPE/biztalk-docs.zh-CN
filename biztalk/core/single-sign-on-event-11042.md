---
title: 单一登录： 事件 11042 |Microsoft Docs
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
ms.openlocfilehash: 109678e68c3624cec11c4c9f235063288f342f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985686"
---
# <a name="single-sign-on-event-11042"></a>单一登录： 事件 11042
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                   企业单一登录                                                                                                                                                   |
| 产品版本 |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    事件 ID     |                                                                                                                                                             11042                                                                                                                                                             |
|  事件源   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    组件    |                                                                                                                                                              N/A                                                                                                                                                              |
|  符号名称  |                                                                                                                                                SSO_WARN_ACCESS_DENIED_ACCOUNTS                                                                                                                                                |
|  消息正文   | 访问被拒绝。<br /><br /> 若要执行此功能，客户端用户必须是以下某一帐户中的成员。%r<br /><br /> SSO Administrators: %1 %r<br /><br /> SSO 关联管理员: %2 %r<br /><br /> 应用程序管理员: %3 %r<br /><br /> 应用程序用户: %4 %r<br /><br /> 其他数据： %5 |
  
## <a name="explanation"></a>解释  
 若要执行此功能，客户端用户必须是警告中列出的其中一个帐户中的成员。  
  
## <a name="user-action"></a>用户操作  
 若要执行此功能，您必须加入到其中一个帐户。