---
title: "使用 SAP 适配器使用性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5da387377f6201b518d3c5fdf37dabb872bcf600
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-sap-adapter"></a>使用 SAP 适配器使用性能计数器
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"沿安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB （累积） Time 性能计数器  
 **适用于 SAP 的 BizTalk.NET 适配器**类别都有一个性能计数器"LOB 次调用 （的累积）"。 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成操作时引发了适配器。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]创建性能计数器的实例中的以下模式：  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 终结点 ID 可能是：  
  
-   从适配器到 SAP 系统 （出站） 的调用  
  
    -   A、\<应用程序服务器主机 >，\<系统编号 >  
  
    -   B，\<消息服务器主机 >，\<R3NAME >  
  
    -   D、\<目标 >  
  
-   从 SAP 系统的适配器的调用 （入站）  
  
    -   I，\<网关主机 >，\<网关服务器 >  
  
    -   ID，\<目标 >  
  
 可能的操作 ID:  
  
-   \<RFC 名称 > （对于 RFC 调用）  
  
-   T，\<RFC 名称 > （对于 tRFC 调用）  
  
 仅在该适配器进行首次调用 SAP 系统后，将初始化性能计数器。 此外， [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)的性能计数器的属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。
  
> [!NOTE]
>  LOB Time （的累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 性能计数器可以启用或禁用通过设置绑定属性*EnablePerformanceCounters*。 若要启用性能计数器，设置*EnablePerformanceCounters*属性绑定到**True**。 若要禁用性能计数器，设置*EnablePerformanceCounters*到**False**。 默认情况下， *EnablePerformanceCounters*设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值*EnablePerformanceCounters*还绑定属性的相应性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]AppDomain 中中的绑定和*EnablePerformanceCounters*绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上次指定哪些值。  
  
## <a name="see-also"></a>另请参阅  

[故障排除 SAP 适配器](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)