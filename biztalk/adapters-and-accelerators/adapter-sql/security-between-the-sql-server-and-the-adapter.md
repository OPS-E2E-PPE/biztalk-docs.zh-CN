---
title: "SQL Server 和适配器之间的安全性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8673aee316a8a2ef83011ab3dd85016a99df1162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-sql-server-and-the-adapter"></a>SQL Server 和适配器之间的安全性
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是符合标准的方法中，例如，使用 SSO 和 IPSEC 来保护与数据库服务器的数据交换。 不安全的数据交换可以公开到未经授权的 actor 的数据。 有关与 SQL Server 的安全问题的信息，请参阅[的 SQL Server 的安全注意事项](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL 文档中。  
  
 可以通过使用 Internet 协议安全性 (IPsec) 来提高数据交换的安全性。 IPsec 是一种开放标准的保护通过 Internet 协议 (IP) 网络的通信框架。 任何数据之间使用 IPSec，交换[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL server 通过网络进行加密，这使得困难未经授权的参与者，要使用的数据。 有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章[IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上与数据库建立的连接进行身份验证支持实现 SSO 和集成安全性。 使用 SSO，凭据进行加密和存储在注册表中。 系统使用这些凭据来确定而不是要求用户输入其中他们可能看到未经授权的参与者的访问权限。 集成的安全性使用登录用户的凭据来访问 SQL server。 这还消除了对用户输入凭据的需要。 数据库管理员必须配置 SQL 接受集成安全性才能正常工作的用户凭据。  
  
## <a name="see-also"></a>另请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)