---
title: 对表和视图包含使用 SQL 适配器的较大的数据类型的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f3b863-da3c-45b0-98f2-469a62286ebf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4f693b676c1e3c0675051e9d0faf685e8b9d8df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021185"
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a>对表和视图包含使用 SQL 适配器的较大的数据类型的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]用于以下 SQL Server 较大的数据类型提供支持：  
  
- Varchar （max)  
  
- Nvarchar （max)  
  
- Varbinary （max)  
  
  若要从 SQL Server 读取大型数据值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开选择操作。  
  
  若要将大型数据值写入到 SQL Server，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开设置 < column_name > 操作，其中 < column_name > 是类型 varchar （max）、 nvarchar （max） 或 varbinary （max） 列的名称。 设置 < column_name > 操作还允许适配器客户端写入 SQL Server 2008 中的 FILESTREAM 数据。  
  
> [!NOTE]
>  设置 < column_name > 操作是仅适用于这些表和视图包含的任何前面提到的三个大型数据类型的列。  
  
 有关在包含大型数据类型的 SQL Server 中执行对表和视图的操作的详细信息，请参阅[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [连接到 SAP 系统使用的适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)