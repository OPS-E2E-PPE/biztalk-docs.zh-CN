---
title: 消息架构的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar Operations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f8cb98-8da8-40c1-bf87-4aad5a24bba2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ede2d471ce935d11286c49cc7cfb53c0e7ea9d92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001422"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息架构
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 出站操作在根级别，以在 SQL Server 中执行任何任意 SQL 语句。  
  
 有关详细信息：  
  
- 这些操作，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
- 执行这些操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息结构  
 这些操作中的消息遵循请求-响应消息交换模式，并下表显示了这些请求和响应消息的结构。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|ExecuteNonQuery 请求|`<ExecuteNonQuery xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">    <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query>  </ExecuteNonQuery>`|在`<Query>`标记，可以指定多个以分号分隔的 PL/SQL 语句。|  
|ExecuteNonQuery 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult> </ExecuteNonQueryResponse>`|对于 UPDATE、 INSERT 和 DELETE 语句，`[value]`表示的 PL/SQL 语句中受影响的行数*ExecuteNonQuery 请求*消息。 对于所有其他类型的语句，`[value]`为-1。|  
|ExecuteReader 请求|`<ExecuteReader xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteReader>`|在`<Query>`标记，可以指定多个以分号分隔的 PL/SQL 语句。|  
|ExecuteReader 响应|`<?xml version="1.0" encoding="utf-8" ?>  <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteReaderResult>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </ExecuteReaderResult> </ExecuteReaderResponse>`|结果集是中的 PL/SQL 语句的响应消息*ExecuteReader 请求*消息，并作为数据集的一个数组返回。 有关数据集的信息，请参阅"数据集类"处[ http://go.microsoft.com/fwlink/?LinkID=196853 ](http://go.microsoft.com/fwlink/?LinkID=196853)。|  
|ExecuteScalar 请求|`<ExecuteScalar xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <Query>[PL/SQL STATEMENT1];[PL/SQL STATEMENT2];…</Query> </ExecuteScalar>`|在`<Query>`标记，可以指定多个以分号分隔的 PL/SQL 语句。|  
|ExecuteScalar 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/GenericTableOp/">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|`[value]`表示中的 PL/SQL 语句中返回的结果集的第一行的第一列中的值*ExecuteScalar 请求*消息。|  
  
 [PL/SQL 语句] = 将执行的整个 PL/SQL 语句。  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息操作  
 下表显示了使用的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息操作。  
  
|运算|操作|  
|---------------|------------|  
|ExecuteNonQuery 请求|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery 响应|GenericOp/ExecuteNonQuery/响应|  
|ExecuteReader 请求|GenericOp/ExecuteReader|  
|ExecuteReader 响应|GenericOp/ExecuteReader/响应|  
|ExecuteScalar 请求|GenericOp/ExecuteScalar|  
|ExecuteScalar 响应|GenericOp/ExecuteScalar/响应|  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)