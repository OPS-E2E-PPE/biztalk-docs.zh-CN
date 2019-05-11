---
title: SQL Server 和适配器之间的安全 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3414cb5ed82cc9003e6207c4a58150dd914d2a19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367948"
---
# <a name="security-between-the-sql-server-and-the-adapter"></a>SQL Server 和适配器之间的安全性
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是符合标准的方法，例如，使用 SSO 和 IPSEC 来保护与数据库服务器的数据交换。 不安全的数据交换可以公开到未经授权的执行组件的数据。 有关使用 SQL Server 的安全问题的信息，请参阅[有关 SQL Server 的安全注意事项](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL 文档中。  
  
 可以通过使用 Internet 协议安全性 (IPsec) 来提高数据交换的安全性。 IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。 任何数据之间使用 IPSec，交换[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL server 通过网络进行加密，使其针对未经授权的执行组件使用的数据变得困难。 有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章[IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上它与数据库建立的连接进行身份验证支持 SSO 和集成安全性。 通过 SSO，凭据进行加密和存储在注册表中。 系统使用这些凭据来确定而不是要求用户输入其位置可能会看到这些功能由未经授权的参与者访问权限。 集成的安全性使用登录用户的凭据来访问 SQL server。 这还消除了需要用户输入凭据。 数据库管理员必须配置 SQL 以接受集成安全性才能正常工作的用户凭据。  
  
## <a name="see-also"></a>请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)