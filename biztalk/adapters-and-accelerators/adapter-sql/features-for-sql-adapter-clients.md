---
title: SQL 适配器客户端的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f638154b-0a09-4f89-9c52-2a62fafec7dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35dbd3c6236e1cd17bcfda0b083ef1309d7d9362
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369369"
---
# <a name="features-for-sql-adapter-clients"></a>SQL 适配器客户端的功能
除了讨论的主题的功能[概述的 BizTalk 适配器适用于 SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)，则[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]还提供了可用于适配器客户端的以下功能：  
  
- **配置使用绑定属性的适配器的支持**。 适配器客户端可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过指定特定绑定属性。 例如，客户端可以指定在连接池中允许特定连接字符串通过设置的连接的最大数**MaxConnectionPoolSize**属性绑定。 有关详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
- **操作参数的 null 值的支持**。 适配器客户端可以使用 XSD"nillable"属性的操作参数提供 null 值。  
  
- **支持在 BizTalk 中的动态端口**。 通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。 有关详细信息，请参阅[配置动态端口](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)。  
  
- **对性能计数器支持**。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以供适配器客户端支持的基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[使用与 SQL 适配器的性能计数器](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 SQL Server 的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)