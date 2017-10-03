---
title: "保护 SQL 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d631bc3ad87e9a8ec8ac51850b7dbe1eb244c140
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-sql-applications"></a>保护 SQL 应用程序
## <a name="overview"></a>概述
SQL Server 数据库通常包含敏感业务信息，例如客户帐户详细信息。 应用程序使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。 数据保护和安全是通常认为按下列术语：  
  
-   *授权*控制对基于请求者的身份的资源的访问。  
  
-   *身份验证*提供验证身份的请求者的机制。  
  
-   *数据保密性*提供用于保护通过加密的数据的隐私的机制。  
  
-   *数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。  
  
 需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 适配器使用这些凭据打开与 SQL 系统的连接。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不允许在连接 URI 中提供的凭据。 这可以防止凭据获取无意中公开。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供两种替代方法，以更安全的方式提供这些凭据：  
  
 集成的安全性。 在这种情况下，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]凭据。 你必须配置 SQL server 以接受这些凭据才能使用此方法。  
  
 企业单一登录 (SSO)。 有关使用 SSO 的详细信息，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。  
  
 本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SQL Server 和适配器之间的安全性](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [使用 SQL 适配器和 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [使用 SQL 适配器安全编程](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [最佳做法](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)