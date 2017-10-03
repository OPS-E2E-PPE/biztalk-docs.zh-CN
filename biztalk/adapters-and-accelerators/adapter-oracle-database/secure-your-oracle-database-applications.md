---
title: "保护 Oracle 数据库应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8601463c02e32221c369023f05ed2fd3731bb4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-oracle-database-applications"></a>保护 Oracle 数据库应用程序
## <a name="data-protection-and-security-overview"></a>数据保护和安全概述
数据库通常包含敏感商业信息，例如客户帐户详细信息。 应用程序使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。 数据保护和安全是通常认为按下列术语：  
  
-   *授权*控制对基于请求者的标识的资源的访问。  
  
-   *身份验证*提供用于请求者的身份进行验证的机制。  
  
-   *数据保密性*提供用于保护通过加密的数据的隐私的机制。  
  
-   *数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。  
  
 需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 适配器使用这些凭据打开与 Oracle 数据库的连接。 可以在连接 URI; 中提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。  
  
 本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [Oracle 数据库和适配器之间的安全性](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [使用 Oracle 数据库适配器和 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [Oracle 数据库适配器使用的安全编程](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [最佳做法](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)