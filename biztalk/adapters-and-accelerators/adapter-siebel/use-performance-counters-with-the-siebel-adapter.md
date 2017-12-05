---
title: "性能计数器用于 Siebel 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bebbd605df52e023c78112b78ad51db13d896cc7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a>用于 Siebel 适配器的性能计数器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"以及适配器包安装。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB Time （累积） 性能计数器  
 **用于 Siebel 的 BizTalk.NET Adapter**类别都有一个性能计数器名为"LOB 时间 （的累积）"。 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成操作时引发了适配器。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]创建的每个操作，为特定的 Siebel 服务器名称的性能计数器实例。 下面的模式来创建实例：  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 情况下[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，终结点 id 是 Siebel 服务器，作为连接 URI 中指定的名称。 操作 id 可能是由执行任何操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]登录、 注销、 元数据，如\<业务组件名称\>。\<操作\>，\<业务服务名称\>。\<业务服务方法\>。 如果前面的命名约定将导致超过 127 个字符的名称仅显示操作 ID 将显示在以下格式：  
  
```  
:::<action id>  
```  
  
 如果`:::<action id>`还超过 127 个字符，修整到 127 个字符。  
  
 仅在该适配器进行 Siebel 系统首次调用后，会初始化性能计数器。 此外， **InstanceLifetime**的性能计数器的属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。 
  
> [!NOTE]
>  LOB Time （的累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。 设置**EnablePerformanceCounters**属性绑定到**True**启用性能计数器。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下， **EnablePerformanceCounters**设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**绑定属性发生更改的相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]AppDomain 中中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**，取决于上次指定哪些值。  
  
## <a name="see-also"></a>另请参阅  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)