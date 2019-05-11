---
title: 用于 Oracle E-business Suite 适配器性能计数器 |Microsoft Docs
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
ms.openlocfilehash: 2d9590ad6d173c57eeba4841b5d8eab237cad056
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374303"
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a>用于 Oracle E-business Suite 适配器性能计数器
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别**适用于 Oracle E-business Suite 的 BizTalk.NET 适配器**以及安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB Time （累积） 性能计数器  
 **适用于 Oracle E-business Suite 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）。" 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以下模式中的任意创建性能计数器的实例：  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 其中可能是"string":  
  
- Connection.Open  
  
- Connection.Close  
  
- 元数据  
  
- 消息操作。 例如，如果操作为`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`字符串将为 InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE。  
  
  Oracle 数据源是与指定连接 URI 中相同。  
  
  仅在该适配器进行首次调用到 Oracle 数据库后初始化性能计数器。 此外，性能计数器的 InstanceLifetime 属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。 
  
> [!NOTE]
>  LOB Time （累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 可以启用或禁用通过设置绑定属性的性能计数器**EnablePerformanceCounters**。 若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下**EnablePerformanceCounters**设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**也绑定属性更改为相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]AppDomain 中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上一次指定哪些值。  
  
## <a name="see-also"></a>请参阅  
[适配器疑难解答](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)