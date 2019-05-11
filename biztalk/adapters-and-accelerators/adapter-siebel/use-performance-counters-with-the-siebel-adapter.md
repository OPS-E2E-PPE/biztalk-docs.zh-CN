---
title: 使用 Siebel 适配器的性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79bb582ca3f79dc20f537551d9aeb98db5cd6cc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370353"
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a>使用 Siebel 适配器的性能计数器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 客户端可以使用性能计数器来测量的适配器的性能。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"以及适配器包安装。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB Time （累积） 性能计数器  
 **用于 Siebel 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）"。 此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]创建的每个操作，为特定的 Siebel 服务器名称的性能计数器实例。 下面的模式来创建实例：  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 情况下[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，终结点 id 是 Siebel 服务器的连接 URI 中指定的名称。 操作 id 可能是由执行任何操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]登录、 注销、 元数据，如\<业务组件名称\>。\<操作\>，\<业务服务名称\>。\<业务服务方法\>。 如果前面的命名约定将导致超过 127 个字符的名称仅显示操作 ID 会显示格式如下：  
  
```  
:::<action id>  
```  
  
 如果`:::<action id>`还超过 127 个字符，修整到 127 个字符。  
  
 仅在该适配器进行到 Siebel 系统的第一个调用后初始化性能计数器。 此外， **InstanceLifetime**的性能计数器的属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。 
  
> [!NOTE]
>  LOB Time （累积） 性能计数器的精度为 16 毫秒。  
  
## <a name="enabling-performance-counters"></a>启用性能计数器  
 可以启用或禁用通过设置绑定属性的性能计数器**EnablePerformanceCounters**。 设置**EnablePerformanceCounters**属性绑定到**True**启用性能计数器。 若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。 默认情况下**EnablePerformanceCounters**设置为**False**。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>性能计数器和 WCF LOB 适配器 SDK  
 更改的值**EnablePerformanceCounters**绑定属性的相应的性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。 因此，如果有两个实例[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]AppDomain 中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。 但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**，取决于上一次指定哪些值。  
  
## <a name="see-also"></a>请参阅  
[Siebel 适配器疑难解答](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)