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
# <a name="use-performance-counters-with-the-siebel-adapter"></a><span data-ttu-id="aa86b-102">用于 Siebel 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="aa86b-102">Use Performance Counters with the Siebel adapter</span></span>
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="aa86b-103">客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="aa86b-103"> clients can use the performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="aa86b-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"以及适配器包安装。</span><span class="sxs-lookup"><span data-stu-id="aa86b-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]" along with the Adapter Pack installation.</span></span>  
  
## <a name="the-lob-time-cumulative-performance-counter"></a><span data-ttu-id="aa86b-105">LOB Time （累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="aa86b-105">The LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="aa86b-106">**用于 Siebel 的 BizTalk.NET Adapter**类别都有一个性能计数器名为"LOB 时间 （的累积）"。</span><span class="sxs-lookup"><span data-stu-id="aa86b-106">The **BizTalk .NET Adapter for Siebel** category has one performance counter called "LOB Time (Cumulative)".</span></span> <span data-ttu-id="aa86b-107">此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成操作时引发了适配器。</span><span class="sxs-lookup"><span data-stu-id="aa86b-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="aa86b-108">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]创建的每个操作，为特定的 Siebel 服务器名称的性能计数器实例。</span><span class="sxs-lookup"><span data-stu-id="aa86b-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] creates an instance of the performance counter for each action, for a specific Siebel server name.</span></span> <span data-ttu-id="aa86b-109">下面的模式来创建实例：</span><span class="sxs-lookup"><span data-stu-id="aa86b-109">The instances are created in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="aa86b-110">情况下[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，终结点 id 是 Siebel 服务器，作为连接 URI 中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="aa86b-110">In case of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the endpoint id is the name of the Siebel server, as specified in the connection URI.</span></span> <span data-ttu-id="aa86b-111">操作 id 可能是由执行任何操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]登录、 注销、 元数据，如\<业务组件名称\>。\<操作\>，\<业务服务名称\>。\<业务服务方法\>。</span><span class="sxs-lookup"><span data-stu-id="aa86b-111">The action id could be any action performed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] such as Login, Logoff, Metadata, \<business component name\>.\<operation\>, \<business service name\>.\<business service method\>.</span></span> <span data-ttu-id="aa86b-112">如果前面的命名约定将导致超过 127 个字符的名称仅显示操作 ID 将显示在以下格式：</span><span class="sxs-lookup"><span data-stu-id="aa86b-112">If the preceding naming convention results in a name that exceeds 127 characters only the action ID is displayed in the following format:</span></span>  
  
```  
:::<action id>  
```  
  
 <span data-ttu-id="aa86b-113">如果`:::<action id>`还超过 127 个字符，修整到 127 个字符。</span><span class="sxs-lookup"><span data-stu-id="aa86b-113">If `:::<action id>` also exceeds 127 characters, it is trimmed down to 127 characters.</span></span>  
  
 <span data-ttu-id="aa86b-114">仅在该适配器进行 Siebel 系统首次调用后，会初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="aa86b-114">The performance counter is initialized only after the adapter makes the first call to the Siebel system.</span></span> <span data-ttu-id="aa86b-115">此外， **InstanceLifetime**的性能计数器的属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。</span><span class="sxs-lookup"><span data-stu-id="aa86b-115">Also, the **InstanceLifetime** property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="aa86b-116">LOB Time （的累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="aa86b-116">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="aa86b-117">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="aa86b-117">Enabling Performance Counters</span></span>  
 <span data-ttu-id="aa86b-118">性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。</span><span class="sxs-lookup"><span data-stu-id="aa86b-118">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="aa86b-119">设置**EnablePerformanceCounters**属性绑定到**True**启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="aa86b-119">Set **EnablePerformanceCounters** binding property to **True** to enable performance counters.</span></span> <span data-ttu-id="aa86b-120">若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。</span><span class="sxs-lookup"><span data-stu-id="aa86b-120">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="aa86b-121">默认情况下， **EnablePerformanceCounters**设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="aa86b-121">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="aa86b-122">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="aa86b-122">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="aa86b-123">更改的值**EnablePerformanceCounters**绑定属性发生更改的相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="aa86b-123">Changing the value of the **EnablePerformanceCounters** binding property changes the value of the corresponding performance counter for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="aa86b-124">此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="aa86b-124">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="aa86b-125">因此，如果有两个实例的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]AppDomain 中中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="aa86b-125">Hence, if there are two instances of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="aa86b-126">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**，取决于上次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="aa86b-126">However, because the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False**, depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa86b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa86b-127">See Also</span></span>  
[<span data-ttu-id="aa86b-128">解决在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="aa86b-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)