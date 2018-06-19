---
title: 轮询 SQL Server 与 BizTalk Server 中使用 SQL 适配器 |Microsoft 文档
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
ms.openlocfilehash: 31e631a966ffee632e6c866a962c4fe47b2f1025
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223085"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a>与 BizTalk Server 中使用 SQL 适配器的轮询 SQL Server
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收基于轮询的数据更改消息。 你可以指定适配器执行轮询数据库轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回的结果集。 基于收到的轮询消息类型，该适配器将公开轮询的三种不同的方式：  
  
-   **轮询**。 此操作将返回数据集作为轮询消息的一部分。 在设计时，轮询的数据库对象的架构不可用。 相反，架构是可用在运行时的轮询消息的一部分。  
  
-   **TypedPolling**。 此操作将返回强类型的轮询消息。 在设计时，数据库对象的架构也会提供。 你必须使用此操作对于轮询如果你想要映射到另一个架构，可能是用于另一操作中的轮询消息的某些元素。  
  
-   **XmlPolling**。 此操作返回作为 XML 消息的轮询消息。 如果你想要使用的 SELECT 语句或使用 FOR XML 子句以 XML 消息形式返回数据的存储的过程，你必须使用此操作。 有关 FOR XML 子句的详细信息，请参阅[FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)。 
  
 有关这些轮询操作的详细信息，请参阅[进行轮询的支持](https://msdn.microsoft.com/library/dd788416.aspx)。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器的客户端需要具有相同的数据库或表的多个轮询或 TypedPolling 操作的单个 BizTalk 应用程序。 若要支持这种方案，该适配器包括一个唯一的 ID- **InboundID**-连接 URI 中。 此 ID，当添加到连接 URI，使其唯一的从而支持单个 BizTalk 应用程序中的多个轮询操作。  
  
 本部分中的主题提供有关如何在 BizTalk 应用程序中使用轮询、 TypedPolling 和 XmlPolling 的说明。 本部分还提供有关如何使用信息**InboundID**连接属性。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [使用 BizTalk Server 从 SQL Server 接收强类型基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [从 SQL 使用 BizTalk Server 接收轮询消息使用 SELECT 语句与 FOR XML 子句](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a>另请参阅  
[开发使用 SQL 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)