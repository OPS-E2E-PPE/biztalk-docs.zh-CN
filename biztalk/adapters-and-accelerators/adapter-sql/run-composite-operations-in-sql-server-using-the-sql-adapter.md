---
title: 在使用 SQL 适配器的 SQL Server 中运行复合操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acf0eca210bd163c0d74e7d8d873ec6009d40a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999278"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a>在使用 SQL 适配器的 SQL Server 中运行复合操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使适配器客户端能够执行复合操作上的 SQL Server 数据库。 复合操作可以包含任意数量的以下操作，并按任何顺序：  
  
- 对表和视图插入、 更新和删除操作。  
  
- 显示为该适配器中的操作的存储的过程。  
  
  复合操作中的操作*必须*目标表和视图只能在单个数据库中的。  
  
  有关信息：  
  
- 如何执行中的复合操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[SQL Server 使用 BizTalk Server 上运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)。  
  
- 消息复合操作的架构，请参见[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。  
  
> [!IMPORTANT]
>  如果有"n"的复合操作返回的操作数目的连接数具有结果集然后"n + 1"所需的复合操作来执行。 因此，您必须确保为指定的值**MaxConnectionPoolSize**绑定属性是 n + 1 或更高版本。 有关详细信息**MaxConnectionPoolSize**绑定属性，请参阅[了解适用于 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)