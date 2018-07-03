---
title: 单一登录： 事件 10655 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bb6a8dd-35e4-40a6-8900-450a9b6de249
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ce0442b02667ce9796d9418dae4b1700dd757d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013006"
---
# <a name="single-sign-on-event-10655"></a>单一登录： 事件 10655
## <a name="details"></a>详细信息  

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
|  产品名称   |                          企业单一登录                           |
| 产品版本 |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]          |
|    事件 ID     |                                    10655                                     |
|  事件源   |                                    ENTSSO                                    |
|    组件    |                                     N\A                                      |
|  符号名称  |                   SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED                   |
|  消息正文   | 密码同步服务器（用于 ping）访问被拒绝。%r<br /><br /> 客户端用户： %1 |

## <a name="explanation"></a>解释  
 此错误事件表明消息发送到 [名称] 服务器但回复受到阻止。 此错误可能由许多不同原因导致，如协议不正确或对服务器没有足够的安全权限。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [密码同步](../core/password-synchronization2.md)
