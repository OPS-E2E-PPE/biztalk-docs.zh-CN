---
title: 用于 Oracle E-business Suite 适配器的性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2a9f345745c18ca03086833fffe3553e96cece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216069"
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a>用于 Oracle E-business Suite 适配器的性能计数器
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别**用于 Oracle E-business Suite 的 BizTalk.NET Adapter**以及安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB Time （的累积） 性能计数器  
 **用于 Oracle E-business Suite 的 BizTalk.NET Adapter**类别都有一个性能计数器"LOB 次调用 （的累积）。" 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成操作时引发了适配器。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以下模式中的任意创建性能计数器的实例：  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 其中可能是"string":  
  
-   Connection.Open  
  
-   Connection.Close  
  
-   元数据  
  
-   消息操作。 例如，如果操作是`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`则字符串将 InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE。  
  
 Oracle 数据源是与指定连接 URI 中相同。  
  
 仅在该适配器进行首次调用到 Oracle 数据库后初始化性能计数器。 此外，性能计数器的 InstanceLifetime 属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。 
  
> [!NOTE]
>  LOB Time （的累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。 若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下， **EnablePerformanceCounters**设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**还绑定属性的相应性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]AppDomain 中中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上次指定哪些值。  
  
## <a name="see-also"></a>另请参阅  
[故障排除适配器](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)