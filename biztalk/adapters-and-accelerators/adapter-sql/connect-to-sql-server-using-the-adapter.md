---
title: 连接到 SQL Server 使用适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 727d73e6-fb84-48ce-ae72-5de70dcae8b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b837aa4e0bc0a815434307b10d249dccf54d70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222133"
---
# <a name="connect-to-sql-server-using-the-adapter"></a>连接到 SQL Server 使用适配器
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI)，以连接到 SQL Server 数据库的连接。 在内部，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将 URI 映射到一个数据库连接字符串以连接到 SQL Server 数据库。 通过连接 URI 适配器客户端可以指定要连接到外部系统的连接参数。 有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
 在连接 URI，主 SQL Server 数据库不可用时要连接到的备用计算机上，还可以指定故障转移 SQL Server 数据库的名称。 故障转移 SQL Server 数据库必须是主 SQL Server 数据库的镜像。 使用可选参数，FailoverPartner，连接 URI 中的指定故障转移 SQL Server 数据库。 提供故障转移 SQL Server 数据库可确保高可用性和数据冗余。 有关与 SQL Server 的高可用性的详细信息，请参阅[SQL Server 中的数据库镜像](https://msdn.microsoft.com/library/5h52hef8.aspx)。
  
 请确保您遵守安全指导原则建立与 SQL Server 数据库的连接时。 有关安全指导原则的详细信息，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。  
  
## <a name="see-also"></a>另请参阅  
 [用于 SQL Server 的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [创建与 SQL Server 的连接](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)