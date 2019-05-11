---
title: 用于管理服务器的端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, administration server
- administration server
ms.assetid: dc0094b2-5ba2-4b8f-84aa-b6232be358ee
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6e6a548604f74f6da6a7d17cb8a5a4be13e7457
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394881"
---
# <a name="ports-for-the-administration-server"></a>用于管理服务器的端口
有关确保 BizTalk Server 部署的安全性的完整信息，请参阅 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了必须为管理服务器能够访问所需的服务而配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 
  
|“目标服务器”|目标服务|Port|Protocol|Reason|  
|---|---|---|---|---|  
|BizTalk 管理数据库|SQL Server|1433|TCP|若要创建、 配置和访问 BizTalk 管理数据库中的信息|  
|BizTalk 管理数据库|DTC|135|TCP|与以更新数据库的 SQL Server 建立事务性的连接|  
|BizTalk 管理数据库|DTC|50000-50200|TCP|辅助 RPC 端口，**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|BAM 主导入数据库|SQL Server|1433|TCP|若要验证 BAM 主导入数据库存在通过使用 BizTalk 管理控制台 （或 WMI）|  
|BizTalk 管理数据库|SQL Server|1433|TCP|若要查看配置数据并通过使用 BizTalk 管理控制台 （或 WMI） 安装主机实例|  
|BizTalk 管理数据库|DTC|135|TCP|与创建和使用 BizTalk 管理控制台 （或 WMI） 更新主机的 SQL Server 建立事务性的连接|  
|BizTalk 管理数据库|DTC|50000-50200|TCP|辅助 RPC 端口，以使用 BizTalk 管理控制台 （或 WMI） 创建主机**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|MessageBox 数据库|SQL Server|1433|TCP|若要使用 BizTalk 管理控制台 （或 WMI） 创建主机|  
|MessageBox 数据库|DTC|135|TCP|与创建和使用 BizTalk 管理控制台 （或 WMI） 更新主机的 SQL Server 建立事务性的连接|  
|MessageBox 数据库|DTC|50000-50200|TCP|辅助 RPC 端口，以使用 BizTalk 管理控制台 （或 WMI） 创建主机**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|处理服务器|WMI/RPC|135|TCP|与使用 BizTalk 管理控制台 （或 WMI） 将新的服务器添加到组的 SQL Server 建立事务性的连接|  
|处理服务器|WMI/RPC|50000-50200|TCP|辅助 RPC 端口，以使用 BizTalk 管理控制台 （或 WMI） 将新服务器添加到组**注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|处理服务器|服务器消息块 (SMB)|445|TCP|用于访问文件共享。 此外可能需要安装使用 BizTalk 管理控制台 （或 WMI） 的主机实例。|  
|业务规则引擎数据库|SQL Server|1433|TCP|若要使用业务规则引擎部署向导部署业务规则|  
|业务规则引擎数据库|DTC|135|TCP|若要使用业务规则引擎部署向导部署业务规则的 SQL server 建立事务性的连接|  
|业务规则引擎数据库|DTC|50000-50200|TCP|辅助 RPC 端口，以使用业务规则引擎部署向导部署业务规则。 **注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
|BizTalk 管理数据库|SQL Server|1433|TCP|若要部署的程序集|  
|跟踪数据库|SQL Server|1433|TCP|若要部署的程序集|  
|IIS 服务器|IIS|1164|TCP|若要启用要打包 HTTP 或 Web 服务端口的 BizTalk 应用程序部署托管在 IIS 服务器上，到 MSI。|  
  
## <a name="see-also"></a>请参阅  
 [服务器命名约定](../core/server-naming-conventions.md)   
 [应用程序部署的安全建议](../core/application-deployment-security-recommendations.md)   
 [有关消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [具有信息工作者服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 必需的端口](../core/required-ports-for-biztalk-server.md)