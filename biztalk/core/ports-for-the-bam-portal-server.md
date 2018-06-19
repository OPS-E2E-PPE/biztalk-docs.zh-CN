---
title: BAM 门户服务器的端口 |Microsoft 文档
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df67c31c-a7a3-4bff-9374-0d8a0cf0ad21
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adfa47415c1e367941203d20533c5e3ac3f431da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266461"
---
# <a name="ports-for-the-bam-portal-server"></a>BAM 门户服务器的端口
有关保护你的 BizTalk Server 部署的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了为使 BAM 门户网站能够访问所需服务而必须配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|目标服务器|目标服务|端口|协议|原因|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|BizTalk 管理数据库|SQL Server|1433|TCP|创建和配置数据库|  
|登录用户|BizTalk 管理数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，用于创建、配置和更新数据库|  
|登录用户|BizTalk 管理数据库|DTC|50000-50200|TCP|要创建并连接到此数据库的辅助 RPC 端口**注意：** 可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|应用程序池|入站客户端|HTTP(S)|80 或 443|TCP|用于网站的入站通信。|  
|登录用户|MessageBox 数据库|SQL Server|1433|TCP|创建和配置数据库|  
|登录用户|MessageBox 数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，用于创建、配置和更新数据库|  
|登录用户|MessageBox 数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：** 可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|SSO 服务帐户|SSO 数据库|SQL Server|1433|TCP|连接到 SSO 数据库|  
|登录用户|跟踪数据库|SQL Server|1433|TCP|创建和配置数据库|  
|登录用户|业务规则引擎数据库|SQL Server|1433|TCP|创建和配置数据库|  
|登录用户|业务规则引擎数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以创建、配置和更新数据库|  
|登录用户|业务规则引擎数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：** 可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|登录用户|BAM 分析数据库|OLAP|2393|TCP|创建和配置数据库|  
|登录用户|BAM 分析数据库|OLAP 服务器文件系统|445|TCP|在远程计算机上创建 OLAP 数据文件 (.mdb)|  
|登录用户|BAM 分析数据库|OLAP|2725|TCP|更新和检索数据库中的信息|  
|SSO 服务帐户|SSO 数据库|SQL Server|1433|TCP|用于 SSO 服务更新和检索数据库中的信息|  
|SSO 服务帐户|主密钥服务器|主密钥服务器|135|TCP|与 SQL Server 建立事务性连接，以便 SSO 服务连接到主密钥服务器|  
|SSO 服务|主密钥服务器|辅助 RPC|50000-50200|TCP|辅助 RPC 端口，用于 SSO 服务连接到主密钥服务器。 **注意：** 可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|BizTalk 主机实例|MessageBox 数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例|BizTalk 管理数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例|SSO 数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例|跟踪数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BAM 应用程序池用户|BAM Notification Services|SQL Server|1433|TCP|访问 BAM Notification Services 数据库|  
  
## <a name="see-also"></a>另请参阅  
 [服务器的命名约定](../core/server-naming-conventions.md)   
 [BAM 门户的安全注意事项](../core/security-considerations-for-the-bam-portal.md)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 所需的端口](../core/required-ports-for-biztalk-server.md)