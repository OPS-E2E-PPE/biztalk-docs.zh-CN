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
# <a name="use-performance-counters-with-the-siebel-adapter"></a><span data-ttu-id="91850-102">使用 Siebel 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="91850-102">Use Performance Counters with the Siebel adapter</span></span>
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="91850-103">客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="91850-103">clients can use the performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="91850-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"以及适配器包安装。</span><span class="sxs-lookup"><span data-stu-id="91850-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]" along with the Adapter Pack installation.</span></span>  
  
## <a name="the-lob-time-cumulative-performance-counter"></a><span data-ttu-id="91850-105">LOB Time （累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="91850-105">The LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="91850-106">**用于 Siebel 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）"。</span><span class="sxs-lookup"><span data-stu-id="91850-106">The **BizTalk .NET Adapter for Siebel** category has one performance counter called "LOB Time (Cumulative)".</span></span> <span data-ttu-id="91850-107">此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。</span><span class="sxs-lookup"><span data-stu-id="91850-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="91850-108">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]创建的每个操作，为特定的 Siebel 服务器名称的性能计数器实例。</span><span class="sxs-lookup"><span data-stu-id="91850-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] creates an instance of the performance counter for each action, for a specific Siebel server name.</span></span> <span data-ttu-id="91850-109">下面的模式来创建实例：</span><span class="sxs-lookup"><span data-stu-id="91850-109">The instances are created in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="91850-110">情况下[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，终结点 id 是 Siebel 服务器的连接 URI 中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="91850-110">In case of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the endpoint id is the name of the Siebel server, as specified in the connection URI.</span></span> <span data-ttu-id="91850-111">操作 id 可能是由执行任何操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]登录、 注销、 元数据，如\<业务组件名称\>。\<操作\>，\<业务服务名称\>。\<业务服务方法\>。</span><span class="sxs-lookup"><span data-stu-id="91850-111">The action id could be any action performed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] such as Login, Logoff, Metadata, \<business component name\>.\<operation\>, \<business service name\>.\<business service method\>.</span></span> <span data-ttu-id="91850-112">如果前面的命名约定将导致超过 127 个字符的名称仅显示操作 ID 会显示格式如下：</span><span class="sxs-lookup"><span data-stu-id="91850-112">If the preceding naming convention results in a name that exceeds 127 characters only the action ID is displayed in the following format:</span></span>  
  
```  
:::<action id>  
```  
  
 <span data-ttu-id="91850-113">如果`:::<action id>`还超过 127 个字符，修整到 127 个字符。</span><span class="sxs-lookup"><span data-stu-id="91850-113">If `:::<action id>` also exceeds 127 characters, it is trimmed down to 127 characters.</span></span>  
  
 <span data-ttu-id="91850-114">仅在该适配器进行到 Siebel 系统的第一个调用后初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="91850-114">The performance counter is initialized only after the adapter makes the first call to the Siebel system.</span></span> <span data-ttu-id="91850-115">此外， **InstanceLifetime**的性能计数器的属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。</span><span class="sxs-lookup"><span data-stu-id="91850-115">Also, the **InstanceLifetime** property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="91850-116">LOB Time （累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="91850-116">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="91850-117">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="91850-117">Enabling Performance Counters</span></span>  
 <span data-ttu-id="91850-118">可以启用或禁用通过设置绑定属性的性能计数器**EnablePerformanceCounters**。</span><span class="sxs-lookup"><span data-stu-id="91850-118">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="91850-119">设置**EnablePerformanceCounters**属性绑定到**True**启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="91850-119">Set **EnablePerformanceCounters** binding property to **True** to enable performance counters.</span></span> <span data-ttu-id="91850-120">若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。</span><span class="sxs-lookup"><span data-stu-id="91850-120">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="91850-121">默认情况下**EnablePerformanceCounters**设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="91850-121">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="91850-122">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="91850-122">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="91850-123">更改的值**EnablePerformanceCounters**绑定属性的相应的性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="91850-123">Changing the value of the **EnablePerformanceCounters** binding property changes the value of the corresponding performance counter for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="91850-124">此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="91850-124">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="91850-125">因此，如果有两个实例[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]AppDomain 中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="91850-125">Hence, if there are two instances of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="91850-126">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**，取决于上一次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="91850-126">However, because the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False**, depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91850-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="91850-127">See Also</span></span>  
[<span data-ttu-id="91850-128">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="91850-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)