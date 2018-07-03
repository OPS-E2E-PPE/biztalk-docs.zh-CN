---
title: 单一登录： 事件 10545 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a21543359b9a0d59aba3071874b6b01210118a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969126"
---
# <a name="single-sign-on-event-10545"></a>单一登录： 事件 10545
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10545                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                             CO                             |
|  符号名称  |             SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED             |
|  消息正文   |        SSO 系统没有启用票证。         |

## <a name="explanation"></a>解释  
 此警告事件表示没有为 SSO 系统启动票证。 如果在系统级别上禁用了票证功能，则也不能在关联应用程序级别上使用此功能。 就可以启用在系统级别票证和关联应用程序级别禁用它。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

- 启用 SSO 系统级别的票证。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [SSO 票证](../core/sso-tickets.md)  

- [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)
