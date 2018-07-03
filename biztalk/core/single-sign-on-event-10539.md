---
title: 单一登录： 事件 10539 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7934b3011af2656f413270b4d249ca4f7f96bae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006270"
---
# <a name="single-sign-on-event-10539"></a>单一登录： 事件 10539
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10539                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                             CO                             |
|  符号名称  |              SSO_WARN_SSO_TICKETS_NOT_ALLOWED              |
|  消息正文   |        SSO 系统没有启用票证。         |

## <a name="explanation"></a>解释  
 此警告事件表示 SSO 票证尚未启用。 允许使用 SSO 票证是 SSO 系统的一个可选功能。 您的 SSO 系统上尚未启用此功能。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

- 请与 SSO 管理员联系以启用 SSO 系统票证。 可使用 SSO 管理工具（GUI 或命令行）完成此操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)  

- [使用 SSO](../core/using-sso.md)
