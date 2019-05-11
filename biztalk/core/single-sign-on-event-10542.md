---
title: 单一登录：Event 10542 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493937fbcf9eb04ccfe59881c56f12e4b3851f11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243432"
---
# <a name="single-sign-on-event-10542"></a>单一登录：事件 10542
## <a name="details"></a>详细信息  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                          企业单一登录                                          |
| 产品版本 |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    事件 ID     |                                                    10542                                                    |
|  事件源   |                                                   ENTSSO                                                    |
|    组件    |                                                     CO                                                      |
|  符号名称  |                                       SSO_WARN_APP_TICKETS_VALIDATED                                        |
|  消息正文   | 不能为此应用程序未经 validated.%r 兑换票证<br /><br /> 应用程序名称： %1 |

## <a name="explanation"></a>解释  
 此警告事件表示，不能应用程序票证兑换未经验证。 当应用程序票证兑换之后它们可以进行验证或不进行验证。 验证可以提高安全性，通过比较 BizTalk 消息中的用户的名称与颁发票证的用户的名称。 如果名称不同时验证失败。 当 BizTalk 消息流经的不受信任的主机时，BizTalk 消息中的用户的名称更改为不受信任的主机。 验证可确保 BizTalk 消息仅已流经受信任的主机。 此消息尤其意味着系统级别的应用程序 （由于 SSO 系统选项设置），需要验证但已由调用方提供任何验证信息。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 如果使用 BizTalk Server，请确保，您的消息只流经受受信任的主机。 这将减少与消息中的数据被篡改的风险。  

- 如果你的方案允许，将关闭此应用程序的验证。 验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [SSO 票证](../core/sso-tickets.md)  

- [如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)
