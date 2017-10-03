---
title: "管理服务器的端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, administration server
- administration server
ms.assetid: dc0094b2-5ba2-4b8f-84aa-b6232be358ee
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd44158d721f8b6d247b51073e9f9e77ea7f6deb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-administration-server"></a>管理服务器的端口
有关保护你的 BizTalk Server 部署的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了为使管理服务器能够访问所需服务而必须配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 
  
|“目标服务器”|目标服务|端口|协议|原因|  
|---|---|---|---|---|  
|BizTalk 管理数据库|SQL Server|1433|TCP|创建、配置和访问 BizTalk 管理数据库中的信息|  
|BizTalk 管理数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以更新数据库|  
|BizTalk 管理数据库|DTC|50000-50200|TCP|辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|BAM 主导入数据库|SQL Server|1433|TCP|使用 BizTalk 管理控制台（或 WMI）验证 BAM 主导入数据库是否存在|  
|BizTalk 管理数据库|SQL Server|1433|TCP|使用 BizTalk 管理控制台（或 WMI）查看配置数据和安装主机实例|  
|BizTalk 管理数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以使用 BizTalk 管理控制台（或 WMI）创建和更新主机|  
|BizTalk 管理数据库|DTC|50000-50200|TCP|要使用的 BizTalk 管理控制台 （或 WMI） 创建一个主机的辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|MessageBox 数据库|SQL Server|1433|TCP|使用 BizTalk 管理控制台（或 WMI）创建主机|  
|MessageBox 数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以使用 BizTalk 管理控制台（或 WMI）创建和更新主机|  
|MessageBox 数据库|DTC|50000-50200|TCP|要使用的 BizTalk 管理控制台 （或 WMI） 创建一个主机的辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|处理服务器|WMI/RPC|135|TCP|与 SQL Server 建立事务性连接，以使用 BizTalk 管理控制台（或 WMI）将新服务器添加到组中|  
|处理服务器|WMI/RPC|50000-50200|TCP|若要使用的 BizTalk 管理控制台 （或 WMI） 将新服务器添加到组的辅助 RPC 端口**注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|处理服务器|服务器消息块 (SMB)|445|TCP|用于访问文件共享。 也可能需要安装使用的 BizTalk 管理控制台 （或 WMI） 的主机实例。|  
|业务规则引擎数据库|SQL Server|1433|TCP|使用业务规则引擎部署向导部署业务规则|  
|业务规则引擎数据库|DTC|135|TCP|与 SQL Server 建立事务性连接，以使用业务规则引擎部署向导部署业务规则|  
|业务规则引擎数据库|DTC|50000-50200|TCP|辅助 RPC 端口，以使用业务规则引擎部署向导部署业务规则。 **注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
|BizTalk 管理数据库|SQL Server|1433|TCP|若要将程序集部署|  
|跟踪数据库|SQL Server|1433|TCP|若要将程序集部署|  
|IIS 服务器|IIS|1164|TCP|若要启用 BizTalk 应用程序部署包 HTTP 或 Web 服务端口承载在 IIS 服务器上，到 MSI。|  
  
## <a name="see-also"></a>另请参阅  
 [服务器的命名约定](../core/server-naming-conventions.md)   
 [应用程序部署安全建议](../core/application-deployment-security-recommendations.md)   
 [消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 所需的端口](../core/required-ports-for-biztalk-server.md)