---
title: 单一登录：Event 10543 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8a3b284910ea5555085a5617a2d2922d0231f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243386"
---
# <a name="single-sign-on-event-10543"></a>单一登录：事件 10543
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                               企业单一登录                                                                |
| 产品版本 |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    事件 ID     |                                                                         10543                                                                          |
|  事件源   |                                                                         ENTSSO                                                                         |
|    组件    |                                                                           CO                                                                           |
|  符号名称  |                                                           SSO_WARN_ORIGINAL_TICKET_VALIDATED                                                           |
|  消息正文   | 需要验证所颁发票证。 它无法兑换此应用程序未经 validated.%r<br /><br /> 应用程序名称： %1 |

## <a name="explanation"></a>解释  
 此警告事件指示需要验证发布应用程序票证。 未经验证，不能兑换票证。 票证验证是在每个关联应用程序。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 如果使用企业单一登录，请确保您的消息只通过受信任的主机流动。 这将减少与消息中的数据被篡改的风险。  

- 如果你的方案允许，将关闭此应用程序的验证。 验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [SSO 票证](../core/sso-tickets.md)  

- [如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)
