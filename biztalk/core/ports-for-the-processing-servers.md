---
title: 用于处理服务器的端口 |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, processing
- ports, processing servers
ms.assetid: 0207b68f-8769-4674-aadc-b3a67b6f210b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b352828afa630f90baec332fe20a9db8b92a6cb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394841"
---
# <a name="ports-for-the-processing-servers"></a>用于处理服务器的端口
有关确保 BizTalk Server 部署的安全性的完整信息，请参阅 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了必须为处理服务器能够访问所需的服务而配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|“目标服务器”|目标服务|Port|Protocol|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|BizTalk 管理数据库|SQL Server|1433|TCP|若要创建和配置 BizTalk 管理数据库|  
|登录用户|BizTalk 管理数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以创建、配置和更新数据库|  
|登录用户|BizTalk 管理数据库|DTC|50000-50200|TCP|辅助 RPC 端口，**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|登录用户|MessageBox 数据库|SQL Server|1433|TCP|若要创建和配置 MessageBox 数据库|  
|登录用户|MessageBox 数据库|DTC|135|TCP|与用来创建宿主的 SQL Server 建立事务性的连接|  
|登录用户|MessageBox 数据库|DTC|50000-50200|TCP|辅助 RPC 端口，**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|SSO 服务帐户|SSO 数据库|SQL Server|1433|TCP|企业单一登录服务用于连接到 SSO 数据库|  
|登录用户|SSO 数据库|DTC|135|TCP|与要连接到 SSO 数据库的 SQL Server 建立事务性的连接|  
|登录用户|SSO 数据库|DTC|50000-50200|TCP|辅助 RPC 端口，**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|登录用户|跟踪数据库|SQL Server|1433|TCP|若要创建和配置跟踪数据库|  
|登录用户|跟踪数据库|DTC|135|TCP|与 SQL Server 建立事务性的连接|  
|登录用户|跟踪数据库|DTC|50000-50200|TCP|辅助 RPC 端口，**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|登录用户|业务规则引擎数据库|SQL Server|1433|TCP|若要创建和配置业务规则引擎数据库|  
|登录用户|业务规则引擎数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以创建、配置和更新数据库|  
|登录用户|业务规则引擎数据库|DTC|50000-50200|TCP|辅助 RPC 端口，**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|登录用户|BAM 分析数据库|OLAP|2393|TCP|若要更新和检索 BAM 分析数据库中的信息|  
|登录用户|BAM 分析数据库|OLAP 服务器文件系统|445|TCP|若要创建的远程计算机上的 OLAP 数据文件 (.mdb)|  
|登录用户|BAM 分析数据库|OLAP|2725|TCP|用于检索数据以进行分析 （数据透视表报表）|  
|登录用户|BizTalk 分析数据库|OLAP|2393|TCP|若要创建和配置 BizTalk 分析数据库**注意：** 处理服务器需要连接到此数据库，仅当你运行 BizTalk 配置管理器时。|  
|登录用户|BizTalk 分析数据库|OLAP 服务器文件系统|445|TCP|若要在远程计算机上创建 OLAP 数据文件 (.mdb)**注意：** 处理服务器需要连接到此数据库，仅当你运行 BizTalk 配置管理器时。|  
|登录用户|BizTalk 分析数据库|OLAP|2725|TCP|创建和配置数据库，以及如何检索数据以进行分析 （数据透视表报表）|  
|单一登录服务帐户|主密钥服务器|RPC|135|TCP|与 SQL Server 建立事务性连接，以便 SSO 服务连接到主密钥服务器|  
|单一登录服务帐户|主密钥服务器|辅助 RPC|50000-50200|TCP|辅助 RPC 端口，用于 SSO 服务连接到主密钥服务器。 **注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|BizTalk 主机实例服务帐户|MessageBox 数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例服务帐户|BizTalk 管理数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例服务帐户|SSO 数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
|BizTalk 主机实例服务帐户|跟踪数据库|SQL Server|1433|TCP|在运行时操作期间更新和检索数据库中的信息|  
  
## <a name="see-also"></a>请参阅  
 [服务器命名约定](../core/server-naming-conventions.md)   
 [BizTalk Server 运行时安全建议](../core/biztalk-server-runtime-security-recommendations.md)   
 [业务规则引擎安全性建议](../core/business-rule-engine-security-recommendations.md)   
 [具有信息工作者服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 必需的端口](../core/required-ports-for-biztalk-server.md)