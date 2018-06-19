---
title: 对表和视图包含使用 SQL 适配器的较大的数据类型的操作 |Microsoft 文档
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
ms.openlocfilehash: e1d6d2c52ce0772297bb2834c13f31a55d7b7a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223861"
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a>对表和视图包含使用 SQL 适配器的较大的数据类型的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]以以下 SQL Server 较大的数据类型提供支持：  
  
-   Varchar （max)  
  
-   Nvarchar (max)  
  
-   Varbinary （max)  
  
 若要从 SQL Server，读取大数据值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开选择操作。  
  
 以较大的数据值写入 SQL Server，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开设置 < column_name > 操作中，其中 < column_name > 是的类型 varchar （max）、 nvarchar (max) 或 varbinary （max） 列的名称。 设置 < column_name > 操作也允许适配器客户端写入 SQL Server 2008 中的 FILESTREAM 数据。  
  
> [!NOTE]
>  设置 < column_name > 操作是仅适用于这些表和列包含与前面所述的三种大型数据类型的任意视图。  
  
 有关包含较大的数据类型的 SQL Server 中执行对表和视图的操作的详细信息，请参阅[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [连接到 SAP 系统使用适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)