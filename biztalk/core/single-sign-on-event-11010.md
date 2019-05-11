---
title: 单一登录：Event 11010 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2bc9357644c48a7b17acc38582d8b386dd28e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306529"
---
# <a name="single-sign-on-event-11010"></a>单一登录：事件 11010
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                企业单一登录                                                                                |
| 产品版本 |                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    事件 ID     |                                                                                          11010                                                                                          |
|  事件源   |                                                                                         ENTSSO                                                                                          |
|    组件    |                                                                                           不可用                                                                                           |
|  符号名称  |                                                                               SSO_WARN_NOT_SSO_AFF_ADMIN                                                                                |
|  消息正文   | 客户端用户不是 SSO Affiliate Administrators account.%r 的成员<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2\\%3 %r<br /><br /> SSO 关联管理员： %4 |
  
## <a name="explanation"></a>解释  
 客户端用户不是 SSO Affiliate Administrators 帐户的成员。 审核级别设置为高时，才会显示此警告。  
  
## <a name="user-action"></a>用户操作  
 若要纠正这种情况，您必须使客户端用户的 SSO Affiliate Administrators 帐户的成员。 若要停止在将来出现此警告消息，则可以降低审核级别。