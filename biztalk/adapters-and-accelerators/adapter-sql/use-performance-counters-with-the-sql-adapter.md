---
title: "使用 SQL 适配器使用性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f81189e34346d377686dac79b44e5a9b34889dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-sql-adapter"></a>使用 SQL 适配器使用性能计数器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别"[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]"以及适配器包安装。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB Time （累积） 性能计数器  
 **BizTalk.NET Adapter for SQL**类别都有一个性能计数器名为"LOB 时间 （的累积）"。 此性能计数器表示的时间，以毫秒为单位，SQL Server 客户端库所需完成操作时引发了适配器。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]创建的每个操作，特定的 SQL Server 实例和数据库名称的性能计数器实例。 下面的模式来创建实例：  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 `<endpointId>`作为派生`<sql_server_name>, <instance_name>, <database_name>`。  
  
 \<ActionId\>按以下方式派生：  
  
-   用于打开连接，该操作 ID 是"打开"。  
  
-   对于入站运算，操作 ID 是"入站"。  
  
-   对于出站运算，操作 ID 是从中调用该操作的操作与"/"替换为下划线"_"。 此外，操作 ID 的前面带"ExecuteScalar"、"ExecuteReader"或"ExecuteNonQuery"根据适配器内部使用的 SQL Server 数据库上执行的操作的方法。 例如，适配器内部使用**ExecuteReader**方法以在 SQL Server 中执行存储的过程。 因此，将是存储过程，MyProcedure，操作 ID:  
  
    ```  
    ExecuteReader_Procedure_dbo_MyProcedure  
    ```  

 仅在该适配器进行首次调用的 SQL Server 数据库后初始化性能计数器。 此外， [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)的性能计数器的属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。
  
> [!NOTE]
>  LOB Time （的累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。 若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下，该属性设置为**False**。 有关此绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**还绑定属性的相应性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是动态的。 因此，如果有两个实例的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定在应用程序域中，与**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上次指定哪些值。  
  
## <a name="see-also"></a>另请参阅  
[解决 SQL 适配器](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)