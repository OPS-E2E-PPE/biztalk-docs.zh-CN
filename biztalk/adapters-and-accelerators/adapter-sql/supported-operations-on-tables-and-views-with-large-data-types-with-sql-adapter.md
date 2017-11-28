---
title: "对表和视图包含使用 SQL 适配器的较大的数据类型的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f3b863-da3c-45b0-98f2-469a62286ebf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1d6d2c52ce0772297bb2834c13f31a55d7b7a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a><span data-ttu-id="4a4af-102">对表和视图包含使用 SQL 适配器的较大的数据类型的操作</span><span class="sxs-lookup"><span data-stu-id="4a4af-102">Operations on tables and views that contain large data types using the SQL adapter</span></span>
<span data-ttu-id="4a4af-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]以以下 SQL Server 较大的数据类型提供支持：</span><span class="sxs-lookup"><span data-stu-id="4a4af-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides supports for the following SQL Server large data types:</span></span>  
  
-   <span data-ttu-id="4a4af-104">Varchar （max)</span><span class="sxs-lookup"><span data-stu-id="4a4af-104">Varchar(Max)</span></span>  
  
-   <span data-ttu-id="4a4af-105">Nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="4a4af-105">Nvarchar(Max)</span></span>  
  
-   <span data-ttu-id="4a4af-106">Varbinary （max)</span><span class="sxs-lookup"><span data-stu-id="4a4af-106">Varbinary(Max)</span></span>  
  
 <span data-ttu-id="4a4af-107">若要从 SQL Server，读取大数据值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开选择操作。</span><span class="sxs-lookup"><span data-stu-id="4a4af-107">To read large data values from SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Select operation.</span></span>  
  
 <span data-ttu-id="4a4af-108">以较大的数据值写入 SQL Server，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开设置 < column_name > 操作中，其中 < column_name > 是的类型 varchar （max）、 nvarchar (max) 或 varbinary （max） 列的名称。</span><span class="sxs-lookup"><span data-stu-id="4a4af-108">To write large data values to SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Set<column_name> operation, where <column_name> is the name of the column of type Varchar(Max), Nvarchar(Max) or Varbinary(Max).</span></span> <span data-ttu-id="4a4af-109">设置 < column_name > 操作也允许适配器客户端写入 SQL Server 2008 中的 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="4a4af-109">The Set<column_name> operation also allows adapter clients to write FILESTREAM data in SQL Server 2008.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a4af-110">设置 < column_name > 操作是仅适用于这些表和列包含与前面所述的三种大型数据类型的任意视图。</span><span class="sxs-lookup"><span data-stu-id="4a4af-110">The Set<column_name> operation is available only for those tables and views that contain columns with any of the three large data types mentioned earlier.</span></span>  
  
 <span data-ttu-id="4a4af-111">有关包含较大的数据类型的 SQL Server 中执行对表和视图的操作的详细信息，请参阅[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4a4af-111">For detailed information about performing operations on tables and views in SQL Server that contain large data types, see [Operations on tables and views that contain large data types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4af-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a4af-112">See Also</span></span>  
 [<span data-ttu-id="4a4af-113">连接到 SAP 系统使用适配器</span><span class="sxs-lookup"><span data-stu-id="4a4af-113">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)