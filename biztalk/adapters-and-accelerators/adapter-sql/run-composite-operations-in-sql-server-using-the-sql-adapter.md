---
title: "在使用 SQL 适配器的 SQL Server 中运行复合操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36a1ff6e4b2c7d4d56855ce1531f99cd490a2a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a>在使用 SQL 适配器的 SQL Server 中运行复合操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]允许适配器客户端执行 SQL Server 数据库上的复合操作。 复合操作可以包含任意数量的以下操作，并按任何顺序：  
  
-   对表和视图插入、 更新和删除操作。  
  
-   作为适配器中的操作中加以表示的存储的过程。  
  
 中的复合操作的操作*必须*目标表和视图仅在单个数据库中的。  
  
 有关的信息：  
  
-   如何执行中的复合操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[运行 SQL Server 使用 BizTalk Server 上的复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)。  
  
-   消息复合操作的架构，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。  
  
> [!IMPORTANT]
>  如果有"n"中的操作数目的复合运算返回结果集然后"n + 1"连接的数目是要执行的复合操作所必需。 因此，你必须确保为指定的值**MaxConnectionPoolSize**绑定属性为 n + 1 或更高版本。 有关详细信息**MaxConnectionPoolSize**绑定属性，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)