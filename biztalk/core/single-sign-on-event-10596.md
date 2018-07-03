---
title: 单一登录： 事件 10596 |Microsoft Docs
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
ms.openlocfilehash: 3a1e565ca3b96663e0ece5a2cf68c02d3258ac5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008790"
---
# <a name="single-sign-on-event-10596"></a>单一登录： 事件 10596
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                         企业单一登录                                                                                                          |
| 产品版本 |                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    事件 ID     |                                                                                                                   10596                                                                                                                    |
|  事件源   |                                                                                                                   ENTSSO                                                                                                                   |
|    组件    |                                                                                                                    N/A                                                                                                                     |
|  符号名称  |                                                                                                     SSO_WARN_TICKET_USER_NOT_IN_GROUP                                                                                                      |
|  消息正文   | 无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 有关颁发票证: %2 %r<br /><br /> 应用程序用户： %3 |
  
## <a name="explanation"></a>解释  
 无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。  
  
## <a name="user-action"></a>用户操作  
 将票证重新颁发给属于应用程序用户帐户成员的用户。