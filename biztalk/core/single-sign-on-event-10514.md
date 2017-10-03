---
title: "单一登录： 事件 10514 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b527841-a2e2-44c7-a9cb-6e9a8eea2fba
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40077ead4157b4cc6c91a2c44b4a19569d76ebc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10514"></a>单一登录： 事件 10514
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10514|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_DB_ACCESS|  
|消息正文|尝试访问 SSO 数据库时出错。%r<br /><br /> 函数: %1 %r<br /><br /> 文件: %2 %r<br /><br /> %3.%r<br /><br /> SQL 错误代码: %4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 此错误事件表示尝试访问 SSO 数据库时接收到来自 SQL Server 的错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   验证 SQL Server (MSSQLSERVER) 服务正在运行。  
  
-   检查使用的事件和错误消息中心的 SQL Server 错误代码[http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869)。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)  
  
-   [如何显示的 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)  
  
 另请参阅 SQL Server 联机丛书。