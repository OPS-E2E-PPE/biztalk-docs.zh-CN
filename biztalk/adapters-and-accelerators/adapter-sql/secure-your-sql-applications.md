---
title: 保护 SQL 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ec6222c68e37ab85414a5b6eb8137b5cba13f3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367884"
---
# <a name="secure-your-sql-applications"></a>保护 SQL 应用程序
## <a name="overview"></a>概述
SQL Server 数据库通常包含敏感商业信息，例如客户帐户详细信息。 使用的应用程序[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。 数据保护和安全性是通常认为的按下列术语：  
  
- *授权*控制对基于请求者的标识的资源的访问。  
  
- *身份验证*提供了用于请求者的身份进行验证的机制。  
  
- *数据保密性*提供了用于保护通过加密的数据的隐私的机制。  
  
- *数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。  
  
  需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 适配器使用这些凭据以打开到 SQL 系统的连接。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不允许要在连接 URI 中提供的凭据。 这可以防止凭据获取无意中公开。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供两种替代方法，以更安全的方式提供这些凭据：  
  
  集成的安全性。 在这种情况下，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]凭据。 必须配置为接受这些凭据，以便此方法运行的 SQL server。  
  
  企业单一登录 (SSO)。 有关使用 SSO 的详细信息，请参阅[SQL 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。  
  
  在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SQL Server 与适配器之间的安全性](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [SQL 适配器与 BizTalk Server 之间的安全性](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [使用 SQL 适配器进行安全编程](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [最佳做法](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)