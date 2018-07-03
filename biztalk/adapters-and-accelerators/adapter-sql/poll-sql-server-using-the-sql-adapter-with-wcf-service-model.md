---
title: SQL 适配器使用 WCF 服务模型轮询 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef2e868-bd51-4393-b091-f67299b4759d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb3bbd42c732f3377c5823831b9507bbeb0c83bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022307"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a>SQL 适配器使用 WCF 服务模型轮询 SQL Server
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收基于轮询的数据更改消息。 可以指定适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。 根据接收轮询消息的类型，该适配器公开不同的轮询操作：  
  
- **轮询**。 此操作将返回一个数据集作为轮询消息的一部分。  
  
- **TypedPolling**。 此操作将返回强类型的轮询消息。  
  
- **XmlPolling**。 此操作将返回作为 XML 消息轮询消息。 如果你想要使用的 SELECT 语句或使用 FOR XML 子句以 XML 消息形式返回数据的存储的过程，则必须使用此操作。 [FOR XML 子句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)提供详细信息。 
  
  有关这些轮询操作的详细信息，请参阅[在使用 SQL 适配器的 SQL Server 中轮询](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]允许适配器客户端有多个轮询或 TypedPolling 操作的同一个数据库或表的单个应用程序。 若要支持这种方案，该适配器包括唯一 ID- **InboundID**— 连接 URI 中。 此 ID，当添加到连接 URI，使其唯一的从而支持在单个应用程序中的多个轮询操作。  
  
 在本部分中的主题提供有关如何在.NET 应用程序中使用轮询和 TypedPolling 操作的说明。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 WCF 服务模型从 SQL Server 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)