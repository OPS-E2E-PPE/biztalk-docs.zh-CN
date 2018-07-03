---
title: 使用 SQL 适配器与 BizTalk Server 轮询 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971de39bff2149b1b6bdb5d20d6e8b721821a8ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996438"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a>使用 SQL 适配器与 BizTalk Server 轮询 SQL Server
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收基于轮询的数据更改消息。 可以指定适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。 根据接收轮询消息的类型，该适配器公开轮询的三种不同的方式：  
  
- **轮询**。 此操作将返回一个数据集作为轮询消息的一部分。 在设计时，轮询的数据库对象的架构不可用。 相反，架构是可作为在运行时轮询消息的一部分。  
  
- **TypedPolling**。 此操作将返回强类型的轮询消息。 在设计时的数据库对象的架构是也可用。 必须使用此操作用于轮询如果你想要将映射到另一个架构，可能是用于另一操作轮询消息中的某些元素。  
  
- **XmlPolling**。 此操作将返回作为 XML 消息轮询消息。 如果你想要使用的 SELECT 语句或使用 FOR XML 子句以 XML 消息形式返回数据的存储的过程，则必须使用此操作。 有关 FOR XML 子句的详细信息，请参阅[FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)。 
  
  有关这些轮询操作的详细信息，请参阅[支持的轮询](https://msdn.microsoft.com/library/dd788416.aspx)。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]允许适配器客户端有多个轮询或 TypedPolling 操作相同的数据库或表的单个 BizTalk 应用程序。 若要支持这种方案，该适配器包括唯一 ID- **InboundID**— 连接 URI 中。 此 ID，当添加到连接 URI，使其唯一的从而支持在单个 BizTalk 应用程序中的多个轮询操作。  
  
 在本部分中的主题提供有关如何在 BizTalk 应用程序中使用轮询和 TypedPolling，XmlPolling 说明。 本部分还提供了有关如何使用信息**InboundID**连接属性。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [从 SQL Server 使用 BizTalk Server 接收强类型基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [从 SQL 使用 BizTalk Server 接收轮询消息使用 SELECT 语句与 FOR XML 子句](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)