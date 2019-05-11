---
title: 消息架构的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar Operations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0ae5bc30d8f65b87dfdad6b8c86ad7157197ac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375807"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开在根级别，以在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 出站操作。  
  
 有关详细信息：  
  
- 这些操作，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
- 执行这些操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息结构  
 这些操作中的消息遵循请求-响应消息交换模式，并下表显示了这些请求和响应消息的结构。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|操作|XML 消息|  
|---------------|-----------------|  
|ExecuteNonQuery 请求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|ExecuteNonQuery 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|ExecuteReader 请求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|ExecuteReader 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|ExecuteScalar 请求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|ExecuteScalar 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 实体说明：  
  
 [PL/SQL 块] = 整个 PL/SQL 块执行。  
  
 [stringvalue1] = 字符串数组中的值。  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息操作  
 下表显示了使用的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息操作。  
  
|操作|操作|  
|---------------|------------|  
|ExecuteNonQuery 请求|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery 响应|GenericOp/ExecuteNonQuery/response|  
|ExecuteReader 请求|GenericOp/ExecuteReader|  
|ExecuteReader 响应|GenericOp/ExecuteReader/response|  
|ExecuteScalar 请求|GenericOp/ExecuteScalar|  
|ExecuteScalar 响应|GenericOp/ExecuteScalar/response|