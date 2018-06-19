---
title: 使用 Oracle 数据库适配器使用性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- performance counter, LOB Time Cumulative
- performance counters, enabling
- performance counters, and the WCF LOB Adapter SDK
ms.assetid: beb80896-7594-411e-a83c-169d5278e2ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce36fe948daeb89d8fc248dbe33191aa69cdd9ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215181"
---
# <a name="use-performance-counters-with-the-oracle-database-adapter"></a>使用与 Oracle 数据库适配器的性能计数器
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别**针对 Oracle 数据库的 BizTalk.NET 适配器**以及安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB （累积） Time 性能计数器  
 **针对 Oracle 数据库的 BizTalk.NET 适配器**类别都有一个性能计数器"LOB 次调用 （的累积）。" 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成操作时引发了适配器。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以下模式中的任意创建性能计数器的实例：  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 其中可能是"string":  
  
-   Connection.Open  
  
-   Connection.Close  
  
-   元数据  
  
-   消息操作。 例如，如果操作是`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert`则字符串将 SCOTT。Table.EMP.Insert。  
  
 Oracle 数据源是与指定连接 URI 中相同。  
  
 仅在该适配器进行首次调用到 Oracle 数据库后初始化性能计数器。 此外，性能计数器的 InstanceLifetime 属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。 有关详细信息`InstanceLifetime property`，请参阅[http://go.microsoft.com/fwlink/p/?LinkId=104181](http://go.microsoft.com/fwlink/p/?LinkId=104181)。  
  
> [!NOTE]
>  LOB Time （的累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。 若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下， **EnablePerformanceCounters**设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**还绑定属性的相应性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]AppDomain 中中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上次指定哪些值。  
  
## <a name="see-also"></a>另请参阅  
[对 Oracle 数据库适配器进行故障排除](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)