---
title: "适用于企业的端口单一登录服务器 |Microsoft 文档"
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, SSO
- SSO
ms.assetid: 30eb99f9-02cb-43c9-b038-d7bd898e3a7a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c0335a6a09cb8d323261c2d8357cc3d5b929b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-enterprise-single-sign-on-servers"></a>用于企业单一登录服务器的端口
有关保护你的 BizTalk Server 部署的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了处理域中的企业单一登录服务器访问主密钥服务器和 SSO 数据库所需的端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|目标服务器|目标服务|端口|协议|原因|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|SSO 数据库|SQL Server|1433|TCP|创建并连接到 SSO 数据库。|  
|单一登录服务帐户|主密钥服务器|单一登录服务|135|TCP|与 SQL Server 建立事务性连接，以便单一登录服务从主密钥服务器检索主密钥|  
|单一登录服务帐户|主密钥服务器|单一登录服务|50000-50200|TCP|辅助 RPC 端口，用于从主密钥服务器检索密钥。 **注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
  
 下表列出了为使企业单一登录 (SSO) 主密钥服务器能够访问所需服务而必须配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|目标服务器|目标服务|端口|协议|原因|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|SSO 数据库|SQL Server|1433|TCP|创建并连接到 SSO 数据库。|  
|单一登录服务帐户|处理服务器|单一登录服务|135|TCP|与 SQL Server 建立事务性连接，以便单一登录服务从主密钥服务器检索主密钥|  
|单一登录服务帐户|处理服务器|单一登录服务|50000-50200|TCP|辅助 RPC 端口，用于从主密钥服务器检索密钥。 **注意：**可能需要打开多个辅助的 RPC 端口，具体取决于你的服务器负载。|  
  
## <a name="see-also"></a>另请参阅  
 [服务器的命名约定](../core/server-naming-conventions.md)   
 [SSO 安全建议](../core/sso-security-recommendations.md)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 所需的端口](../core/required-ports-for-biztalk-server.md)