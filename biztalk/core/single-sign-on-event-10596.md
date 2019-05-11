---
title: 单一登录：Event 10596 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f093968363a0c67d48e8e50e4bd0d44c45d9491a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397839"
---
# <a name="single-sign-on-event-10596"></a>单一登录：事件 10596
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                         企业单一登录                                                                                                          |
| 产品版本 |                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    事件 ID     |                                                                                                                   10596                                                                                                                    |
|  事件源   |                                                                                                                   ENTSSO                                                                                                                   |
|    组件    |                                                                                                                    不可用                                                                                                                     |
|  符号名称  |                                                                                                     SSO_WARN_TICKET_USER_NOT_IN_GROUP                                                                                                      |
|  消息正文   | 无法兑换票证，因为要为其颁发票证的用户不是应用程序用户 account.%r 的成员<br /><br /> 应用程序名称: %1 %r<br /><br /> 有关颁发票证: %2 %r<br /><br /> 应用程序用户： %3 |
  
## <a name="explanation"></a>解释  
 无法兑换票证，因为要为其颁发票证的用户不是应用程序用户帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 是 Application Users 帐户的成员的用户将票证重新颁发。