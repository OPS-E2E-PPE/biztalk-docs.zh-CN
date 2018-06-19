---
title: ExecuteNonQuery、 ExecuteReader，和 ExecuteScalar Operations1 消息架构 |Microsoft 文档
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
ms.openlocfilehash: b42ed9075ad16708f835786fd1fd09b414d06ebb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216149"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader，和 ExecuteScalar 操作的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]在根级别，以在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块将 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 出站操作公开。  
  
 有关详细信息：  
  
-   这些操作，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
-   执行这些操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或在 SQL 中使用 BizTalk Server ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader，和 ExecuteScalar 操作的消息结构  
 这些操作中的消息遵循请求-响应消息交换模式时，和下表显示这些请求和响应消息的结构。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|XML 消息|  
|---------------|-----------------|  
|ExecuteNonQuery 请求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|ExecuteNonQuery 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|ExecuteReader 请求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|ExecuteReader 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|ExecuteScalar 请求|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|ExecuteScalar 响应|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 实体说明：  
  
 [PL/SQL 块] = 整个的 PL/SQL 块，要执行。  
  
 [stringvalue1] = 字符串的数组中的值。  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、 ExecuteReader，和 ExecuteScalar 操作的消息操作  
 下表显示由 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作使用的消息操作。  
  
|运算|操作|  
|---------------|------------|  
|ExecuteNonQuery 请求|GenericOp/ExecuteNonQuery|  
|ExecuteNonQuery 响应|GenericOp/ExecuteNonQuery/响应|  
|ExecuteReader 请求|GenericOp/ExecuteReader|  
|ExecuteReader 响应|GenericOp/ExecuteReader/响应|  
|ExecuteScalar 请求|GenericOp/ExecuteScalar|  
|ExecuteScalar 响应|GenericOp/ExecuteScalar/响应|