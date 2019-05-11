---
title: 单一登录：Event 10540 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd18184dbf06934600231a6bbb75abdc1709f5ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243407"
---
# <a name="single-sign-on-event-10540"></a>单一登录：事件 10540
## <a name="details"></a>详细信息  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  产品名称   |                            企业单一登录                             |
| 产品版本 |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    事件 ID     |                                      10540                                       |
|  事件源   |                                      ENTSSO                                      |
|    组件    |                                        CO                                        |
|  符号名称  |                         SSO_WARN_APP_TICKETS_NOT_ALLOWED                         |
|  消息正文   | Application.%r 未启用票证<br /><br /> 应用程序名称： %1 |

## <a name="explanation"></a>解释  
 此警告事件表示票证功能尚未启用此应用程序。 使用 SSO 票证是每个 SSO 应用程序的可选功能。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 请联系你的应用程序管理员以启用对此 SSO 应用程序的票证。 这可以使用 SSO 管理工具 （GUI 或命令行）。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [SSO 票证](../core/sso-tickets.md)  

- [如何列出关联应用程序的属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)
