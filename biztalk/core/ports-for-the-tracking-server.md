---
title: "跟踪 Server 的端口 |Microsoft 文档"
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking server
- ports, tracking server
ms.assetid: 4b4913a4-7d8d-4fd0-a116-ba868c4ad7da
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975f5e42c800a6d4ae4015108afa2650b2c7f626
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-tracking-server"></a>跟踪 Server 的端口
有关保护你的 BizTalk Server 部署的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了为使跟踪服务器能够访问所需服务而必须配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|目标服务器|目标服务|端口|协议|原因|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|BizTalk 管理数据库|SQL Server|1433|TCP|创建和配置 BizTalk 管理数据库|  
|登录用户|BizTalk 管理数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以更新和检索数据库中的信息|  
|登录用户|BizTalk 管理数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|登录用户|SSO 数据库|SQL Server|1433|TCP|用于 SSO 服务连接到 SSO 数据库|  
|登录用户|BAM 主导入数据库|SQL Server|1433|TCP|验证 BAM 主导入数据库。 跟踪主机在运行时连接到此数据库。|  
|登录用户|BAM 星型架构数据库|SQL Server|1433||更新和检索数据库中的信息。 **注意：**只在运行要从此服务器中创建新的 BizTalk 组的 BizTalk 配置管理器时，跟踪主机连接到此数据库。|  
|登录用户|BAM 分析数据库|OLAP|445|TCP|在远程计算机上创建 OLAP 数据文件 (.mdb)。 **注意：**只在运行要从此服务器中创建新的 BizTalk 组的 BizTalk 配置管理器时，跟踪主机连接到此数据库。|  
|登录用户|BAM 分析数据库|OLAP|2383 (SQL Server 2005 Analysis Services)||若要创建和配置 BAM 分析数据库**注意：**只在运行要从此服务器中创建新的 BizTalk 组的 BizTalk 配置管理器时，跟踪主机连接到此数据库。|  
|登录用户|BAM 分析数据库|OLAP|2725|TCP|进行分析 （数据透视表报告） 的数据检索**注意：**只在运行要从此服务器中创建新的 BizTalk 组的 BizTalk 配置管理器时，跟踪主机连接到此数据库。|  
|登录用户|跟踪数据库|SQL Server|1433|TCP|更新和检索数据库中的信息|  
|登录用户|MessageBox 数据库|SQL|1433|TCP|更新和检索数据库中的信息|  
|登录用户|MessageBox 数据库|DTC|135|TCO|与 SQL Server 建立事务性连接|  
|登录用户|MessageBox 数据库|DTC|50000-50200||辅助 RPC 端口|  
|登录用户|BAM 存档数据库|SQL Server|1433|TCP|更新并从数据库中检索信息**注意：**只在运行要从此服务器中创建新的 BizTalk 组的 BizTalk 配置管理器时，跟踪主机连接到此数据库。|  
|SSO 服务帐户|SSO 数据库|SQL Server|1433|TCP|更新和检索数据库中的信息|  
|SSO 服务帐户|主密钥服务器|主密钥服务|135|TCP|与 SQL Server 建立事务性连接，以便 SSO 服务连接到主密钥服务器|  
|SSO 服务帐户|主密钥服务器|辅助 RPC|50000-50200|TCP|辅助 RPC 端口，用于 SSO 服务连接到主密钥服务器|  
  
## <a name="see-also"></a>另请参阅  
 [服务器的命名约定](../core/server-naming-conventions.md)   
 [消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 所需的端口](../core/required-ports-for-biztalk-server.md)   
 [BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)