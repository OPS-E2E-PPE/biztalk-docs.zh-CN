---
title: 单一登录： 事件 10515 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e2b884ae52af96ceaae83f8b092ed15b6b12e3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269885"
---
# <a name="single-sign-on-event-10515"></a>单一登录： 事件 10515
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10515|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_POLL_DATABASE|  
|消息正文|丢失与 SSO 数据库的联系。 请检查 SSO 数据库是否可用。|  
  
## <a name="explanation"></a>解释  
 此错误事件表示 SSO 服务已丢失与 SSO 数据库的联系。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   验证 SQL Server (MSSQLSERVER) 服务正在运行。  
  
-   如果在远程服务器上，则验证到 SQL Server 的网络连接是否正常。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)  
  
-   [如何显示的 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)  
  
-   [配置 SSO](../core/configuring-sso.md)  
  
 另请参阅 SQL Server 联机丛书