---
title: "单一登录： 事件 10513 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1be7ae463dbb1ee9651f69f231614cc11db5f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10513"></a>单一登录： 事件 10513
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10513|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_DB_FIRST_ACCESS|  
|消息正文|无法与 SSO 数据库取得联系: %1 %r<br /><br /> %2%r<br /><br /> 错误代码： %3|  
  
## <a name="explanation"></a>解释  
 此错误事件表明，SSO 服务在启动时无法连接到 SSO 数据库。 事件消息包含数据源名称 (DSN) 字符串（表明指定的 SQL Server 和数据库名称），以及从 SQL 连接库返回的错误消息。  
  
 当 SSO 服务启动时，它将尝试使用在注册表中指定的 SQL Server 和 SSO 数据库名称连接到 SSO 数据库。 SSO 服务将尝试进行 12 次连接，每次尝试失败后再等待 5 秒钟重试，总共 1 分钟。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   验证 SQL Server (MSSQLSERVER) 服务是否正在运行。  
  
-   验证错误消息中显示的数据源名称 (DSN) 字符串是否正确，以及是否包含正确的 SQL Server 和数据库名称。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)  
  
-   [如何显示的 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)  
  
-   [配置 SSO](../core/configuring-sso.md)  
  
-   SQL Server 联机丛书