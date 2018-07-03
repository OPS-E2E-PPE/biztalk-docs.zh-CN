---
title: 运行 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7374a0852c4f6689a0c092e5ddf0b11c038d6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990318"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a>运行 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作使用 SQL 适配器
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开根级别上的以下操作：  
  
- **ExecuteNonQuery**： 此操作用于在 SQL Server 中执行任何任意 SQL 语句，如果不希望任何结果集返回。 可以使用此操作创建数据库对象或更改数据库中的数据，通过执行 UPDATE、 INSERT 或 DELETE 语句。 此操作的返回值是 Int32 数据类型的和：  
  
  -   对于 UPDATE、 INSERT 和 DELETE 语句中，返回值是由 SQL 语句影响的行数。  
  
  -   对于所有其他类型的语句，返回值是**为-1**。  
  
- **ExecuteReader**： 此操作用于在 SQL Server 中执行任何任意 SQL 语句，如果你想将结果集返回，如果有，作为数据集的数组。 有关数据集的信息，请参阅"数据集类"处[ http://go.microsoft.com/fwlink/?LinkID=196853 ](http://go.microsoft.com/fwlink/?LinkID=196853)。  
  
- **ExecuteScalar**： 使用此操作以返回单个值的 SQL Server 中执行任何任意 SQL 语句。 此操作仅在 SQL 语句返回结果集中的第一行的第一列中返回的值。  
  
  > [!NOTE]
  >  ExecuteScalar 优于 ExecuteReader 是 ExecuteScalar 操作的响应消息有效负载进行 ExecuteReader 操作返回的一个小得多比较。 因此，如果您需要返回一个值，您应使用 ExecuteScalar 而不是 ExecuteReader。  
  
  ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作可用于执行多个 SQL 语句。  
  
  有关执行这些操作使用的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作，它可以使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)