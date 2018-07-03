---
title: 使用 SAP 适配器的性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7818f5f5cf24bd1d4e58da2c24691813fc2b761f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991454"
---
# <a name="use-performance-counters-with-the-sap-adapter"></a>使用 SAP 适配器的性能计数器
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"沿安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB Time （累积） 性能计数器  
 **适用于 SAP 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）"。 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下模式中创建的性能计数器实例：  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 终结点 ID 可能是：  
  
- 从适配器到 SAP 系统 （出站） 的调用  
  
  -   A，\<应用程序服务器主机\>，\<系统编号\>  
  
  -   B\<消息服务器主机\>，\<R3NAME\>  
  
  -   D，\<目标\>  
  
- 有关调用适配器从 SAP 系统 （入站）  
  
  -   我\<网关主机\>，\<网关服务器\>  
  
  -   ID、\<目标\>  
  
  操作 ID 可能是：  
  
- \<RFC 名称\>（为 RFC 调用）  
  
- T，\<RFC 名称\>（适用于 tRFC 调用）  
  
  仅在该适配器进行到 SAP 系统的第一个调用后初始化性能计数器。 此外， [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)的性能计数器的属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。
  
> [!NOTE]
>  LOB Time （累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 可以启用或禁用通过设置绑定属性的性能计数器*EnablePerformanceCounters*。 若要启用性能计数器，设置*EnablePerformanceCounters*属性绑定到**True**。 若要禁用性能计数器，设置*EnablePerformanceCounters*到**False**。 默认情况下*EnablePerformanceCounters*设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值*EnablePerformanceCounters*也绑定属性更改为相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]AppDomain 中的绑定和*EnablePerformanceCounters*绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上一次指定哪些值。  
  
## <a name="see-also"></a>请参阅  

[SAP 适配器疑难解答](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)