---
title: "用于接收和发送服务器端口 |Microsoft 文档"
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection strings
- servers, sending
- ports, servers
- servers, receiving
- BizTalk Server, service accounts
- SSO, service accounts
ms.assetid: 19cafe74-6676-4779-8ced-de0841dba19f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04ddda71d04cf784f07cf8e0783775d7ae91e6d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-receive-and-send-servers"></a>用于接收服务器和发送服务器的端口
有关保护你的 BizTalk Server 部署的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了为使接收服务器和发送服务器能够访问所需服务而必须配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|目标服务器|目标服务|端口|协议|原因|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|BizTalk 服务帐户|文件共享<br /><br /> EDI 文档主页共享|接收/发送服务器|445|TCP|检索文件并将其存放于文件适配器的文件位置|  
|BizTalk 服务帐户|FTP 服务器|FTP 服务|20|TCP|用于 FTP 适配器检索文件并将其存放到 FTP 服务器|  
|BizTalk 服务帐户|FTP 服务器|FTP 服务|21|TCP|用于 FTP 适配器检索文件并将其存放到 FTP 服务器|  
|BizTalk 服务帐户|POP3 服务器|POP3 服务|110|TCP|用于 POP3 适配器从 POP3 服务器中检索电子邮件|  
|BizTalk 服务帐户|处理服务器|Windows 消息队列|1801|TCP|用于 BizTalk 消息队列适配器接收消息并将其发送到 BizTalk 运行时|  
|连接字符串|SQL 适配器目标|SQL Server|1433|TCP|检索并发送 SQL 适配器使用的数据库中的消息|  
|连接字符串|SQL 适配器目标|DTC|135|TCP|与 SQL Server 建立事务性连接，用于 SQL 适配器|  
|连接字符串|SQL 适配器目标|DTC|50000-50200|TCP|有关 SQL 适配器的辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|BizTalk 服务帐户|SMTP/Exchange|SMTP|25|TCP|用于 SMPT 适配器连接到 SMTP 服务器|  
|登录用户|BizTalk 管理数据库|SQL Server|1433|TCP|创建和配置 BizTalk 管理数据库|  
|登录用户|BizTalk 管理数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以创建、配置和更新数据库|  
|登录用户|BizTalk 管理数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|登录用户|MessageBox 数据库|SQL Server|1433|TCP|创建和配置 MessageBox 数据库|  
|登录用户|MessageBox 数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以创建主机|  
|登录用户|MessageBox 数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|SSO 服务帐户|SSO 数据库|SQL Server|1433|TCP|用于企业单一登录服务连接到 SSO 数据库|  
|登录用户|SSO 数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以连接到 SSO 数据库|  
|登录用户|SSO 数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|登录用户|跟踪数据库|SQL Server|1433|TCP|创建和配置跟踪数据库|  
|登录用户|跟踪数据库|DTC|135|TCP|与 SQL Server 建立事务性连接|  
|登录用户|跟踪数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|登录用户|业务规则引擎数据库|SQL Server|1433|TCP|创建和配置业务规则引擎数据库|  
|登录用户|业务规则引擎数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以创建、配置和更新数据库|  
|登录用户|业务规则引擎数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|登录用户|BAM 分析数据库|OLAP|2383 (SQL Server 2005 Analysis Services)|TCP|更新和检索 BAM 分析数据库中的信息|  
|登录用户|BAM 分析数据库|OLAP 服务器文件系统|445|TCP|若要创建远程计算机上的 OLAP 数据文件 (.mdb)|  
|登录用户|BAM 分析数据库|OLAP|2725|TCP|用于检索数据以进行分析（PivotTable® 报表）|  
|登录用户|BizTalk 分析数据库|OLAP|2383 (SQL Server 2005 Analysis Services)|TCP|若要创建和配置 BizTalk 分析数据库**注意：**处理服务器需要连接到此数据库，只在运行 BizTalk 配置管理器时。|  
|登录用户|BizTalk 分析数据库|OLAP 服务器文件系统|445|TCP|要在远程计算机上创建 OLAP 数据文件 (.mdb)**注意：**处理服务器需要连接到此数据库，只在运行 BizTalk 配置管理器时。|  
|登录用户|BizTalk 分析数据库|OLAP|2725|TCP|创建和配置数据库，并检索数据以进行分析（数据透视表）|  
|单一登录服务帐户|主密钥服务器|RPC|135|TCP|与 SQL Server 建立事务性连接，以便 SSO 服务连接到主密钥服务器|  
|单一登录服务帐户|主密钥服务器|辅助 RPC|50000-50200|TCP|辅助 RPC 端口，用于 SSO 服务连接到主密钥服务器。 **注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|BizTalk 主机实例的服务帐户|MessageBox 数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例的服务帐户|BizTalk 管理数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例的服务帐户|SSO 数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例的服务帐户|跟踪数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
  
## <a name="see-also"></a>另请参阅  
 [服务器的命名约定](../core/server-naming-conventions.md)   
 [HTTP 适配器安全建议](../core/http-adapter-security-recommendations.md)   
 [SOAP 适配器安全建议](../core/soap-adapter-security-recommendations.md)   
 [FTP 适配器安全建议](http://msdn.microsoft.com/library/ea7c0577-9d72-4d63-94e7-8f649c6e713f)   
 [SMTP 适配器安全建议](../core/smtp-adapter-security-recommendations.md)   
 [文件适配器安全建议](http://msdn.microsoft.com/library/fe4d51c0-b697-457b-bf27-f1cf6965d954)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 所需的端口](../core/required-ports-for-biztalk-server.md)