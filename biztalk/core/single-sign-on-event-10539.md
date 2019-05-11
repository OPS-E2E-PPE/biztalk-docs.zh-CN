---
title: 单一登录：Event 10539 | Microsoft Docs
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
ms.openlocfilehash: cbae36ca6e261fab1b7ae4e691f64da2bf9ba718
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392922"
---
# <a name="single-sign-on-event-10539"></a>单一登录：事件 10539
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10539                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                             CO                             |
|  符号名称  |              SSO_WARN_SSO_TICKETS_NOT_ALLOWED              |
|  消息正文   |        SSO 系统未启用票证。         |

## <a name="explanation"></a>解释  
 此警告事件表明未启用使用 SSO 票证。 允许使用 SSO 票证是 SSO 系统的一项可选功能。 尚未在 SSO 系统上启用此功能。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 与 SSO 管理员联系以启用 SSO 系统票证。 这可以使用 SSO 管理工具 （GUI 或命令行）。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)  

- [使用 SSO](../core/using-sso.md)
