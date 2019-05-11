---
title: 单一登录：Event 10513 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec0cb1df806771e3676bcd580be2965498b618a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243397"
---
# <a name="single-sign-on-event-10513"></a>单一登录：事件 10513
## <a name="details"></a>详细信息  

|                 |                                                                                      |
|-----------------|--------------------------------------------------------------------------------------|
|  产品名称   |                              企业单一登录                               |
| 产品版本 |              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    事件 ID     |                                        10513                                         |
|  事件源   |                                        ENTSSO                                        |
|    组件    |                                         N\A                                          |
|  符号名称  |                              SSO_ERROR_DB_FIRST_ACCESS                               |
|  消息正文   | 无法与 SSO 数据库取得联系: %1 %r<br /><br /> %2%r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 服务无法连接到 SSO 数据库启动时。 事件消息包含数据源名称 (DSN) 字符串，该值指示指定的 SQL Server 和数据库名称，以及从 SQL 连接库返回的错误消息。  

 SSO 服务启动时，它将尝试连接到 SSO 数据库使用在注册表中指定的 SQL Server 和 SSO 数据库名称。 SSO 服务将尝试连接 12 倍，等待 5 秒每次失败尝试，总共 1 分钟之间。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 验证 SQL Server (MSSQLSERVER) 服务正在运行。  

- 验证错误消息中指示的数据源名称 (DSN) 字符串正确以及包含正确的 SQL Server 和数据库名称。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)  

- [如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)  

- [配置 SSO](../core/configuring-sso.md)  

- SQL Server 联机丛书
