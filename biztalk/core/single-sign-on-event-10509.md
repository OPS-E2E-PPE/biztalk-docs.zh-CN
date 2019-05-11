---
title: 单一登录：Event 10509 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2911358dd326c5fa7f2673567f53805edb898de0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243416"
---
# <a name="single-sign-on-event-10509"></a>单一登录：事件 10509
## <a name="details"></a>详细信息  

|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10509                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              N\A                               |
|  符号名称  |                 SSO_INFO_SERVICE_REMOVE_FAILED                 |
|  消息正文   | 未能删除 SSO service.%r<br /><br /> 错误代码： %1 |

## <a name="explanation"></a>解释  
 此事件表示无法卸载 ENTSSO 服务。 在手动卸载的企业单一登录，才会发生此事件。  

## <a name="user-action"></a>用户操作  
 若要解决此事件，请执行以下操作：  

- 检查应用程序和系统事件日志中的 ENTSSO 或其他服务的相关错误。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [安装 SSO](../core/installing-sso.md)  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
