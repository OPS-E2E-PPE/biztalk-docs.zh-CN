---
title: 使用 SQL 适配器的性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29e6bdb107a845682aae8d587ccaa619ac075a45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367410"
---
# <a name="use-performance-counters-with-the-sql-adapter"></a>使用 SQL 适配器的性能计数器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别"[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]"以及适配器包安装。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB Time （累积） 性能计数器  
 **用于 SQL 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）"。 此性能计数器表示的时间，以毫秒为单位，SQL Server 客户端库所需完成某项操作，适配器启动的。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]创建的每个操作，对于特定的 SQL Server 实例和数据库名称的性能计数器实例。 下面的模式来创建实例：  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 `<endpointId>`派生为`<sql_server_name>, <instance_name>, <database_name>`。  
  
 \<ActionId\>按以下方式派生：  
  
- 用于打开连接，操作 ID 为"打开"。  
  
- 对于入站操作，操作 ID 是"Inbound"。  
  
- 对于出站操作，操作 ID 是被调用的操作的操作与"/"替换为下划线"_"。 此外，操作 ID 与"ExecuteScalar"、"ExecuteReader"或"ExecuteNonQuery"前缀根据适配器在内部使用以对 SQL Server 数据库执行的操作的方法。 例如，适配器在内部使用**ExecuteReader**要在 SQL Server 中执行存储的过程的方法。 因此，将为存储过程，MyProcedure，操作 ID:  
  
  ```  
  ExecuteReader_Procedure_dbo_MyProcedure  
  ```  

  仅在该适配器进行首次调用的 SQL Server 数据库后初始化性能计数器。 此外， [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)的性能计数器的属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。
  
> [!NOTE]
>  LOB Time （累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 可以启用或禁用通过设置绑定属性的性能计数器**EnablePerformanceCounters**。 若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下，该属性设置为**False**。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**也绑定属性更改为相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是动态的。 因此，如果有两个实例[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定在应用程序域中，并**EnablePerformanceCounters**绑定属性设置为**True**中一个和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上一次指定哪些值。  
  
## <a name="see-also"></a>请参阅  
[SQL 适配器疑难解答](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)