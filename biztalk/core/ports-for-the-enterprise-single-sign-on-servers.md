---
title: 端口适用于企业单一登录服务器 |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, SSO
- SSO
ms.assetid: 30eb99f9-02cb-43c9-b038-d7bd898e3a7a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e5070fffd9cb6de3e058cd9f2db4612e5bb147a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394855"
---
# <a name="ports-for-the-enterprise-single-sign-on-servers"></a>用于企业单一登录服务器的端口
有关确保 BizTalk Server 部署的安全性的完整信息，请参阅 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 下表列出了处理域中的企业单一登录服务器访问主密钥服务器和 SSO 数据库所需的端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|“目标服务器”|目标服务|Port|Protocol|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|SSO 数据库|SQL Server|1433|TCP|若要创建并连接到 SSO 数据库。|  
|单一登录服务帐户|主密钥服务器|单一登录服务|135|TCP|与从主密钥服务器检索主密钥上单一登录服务的 SQL Server 建立事务性的连接|  
|单一登录服务帐户|主密钥服务器|单一登录服务|50000-50200|TCP|辅助 RPC 端口，用于从主密钥服务器检索的机密密钥。 **注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
  
 下表列出了必须为企业单一登录 (SSO) 主密钥服务器以访问所需的服务配置的端口。 根据目标服务器在结构中所处位置的不同，你需要在不同的防火墙上打开这些端口。 对于入站通信和出站通信，均必须打开这些端口。  
  
|服务或应用程序上下文|“目标服务器”|目标服务|Port|Protocol|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|登录用户|SSO 数据库|SQL Server|1433|TCP|若要创建并连接到 SSO 数据库。|  
|单一登录服务帐户|处理服务器|单一登录服务|135|TCP|与从主密钥服务器检索主密钥上单一登录服务的 SQL Server 建立事务性的连接|  
|单一登录服务帐户|处理服务器|单一登录服务|50000-50200|TCP|辅助 RPC 端口，用于从主密钥服务器检索的机密密钥。 **注意：** 您可能需要打开多个辅助 RPC 端口，具体取决于服务器负载。|  
  
## <a name="see-also"></a>请参阅  
 [服务器命名约定](../core/server-naming-conventions.md)   
 [SSO 安全建议](../core/sso-security-recommendations.md)   
 [具有信息工作者服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server 必需的端口](../core/required-ports-for-biztalk-server.md)