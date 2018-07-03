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
# <a name="use-performance-counters-with-the-sap-adapter"></a><span data-ttu-id="5a5bd-102">使用 SAP 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="5a5bd-102">Use Performance Counters with the SAP adapter</span></span>
<span data-ttu-id="5a5bd-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="5a5bd-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"沿安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]" along installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="5a5bd-105">LOB Time （累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="5a5bd-105">LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="5a5bd-106">**适用于 SAP 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）"。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-106">The **BizTalk .NET Adapter for SAP** category has one performance counter called the "LOB Time (Cumulative)".</span></span> <span data-ttu-id="5a5bd-107">此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="5a5bd-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下模式中创建的性能计数器实例：</span><span class="sxs-lookup"><span data-stu-id="5a5bd-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates an instance of the performance counter in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="5a5bd-109">终结点 ID 可能是：</span><span class="sxs-lookup"><span data-stu-id="5a5bd-109">The endpoint ID could be:</span></span>  
  
- <span data-ttu-id="5a5bd-110">从适配器到 SAP 系统 （出站） 的调用</span><span class="sxs-lookup"><span data-stu-id="5a5bd-110">For calls from the adapter to the SAP system (outbound)</span></span>  
  
  -   <span data-ttu-id="5a5bd-111">A，\<应用程序服务器主机\>，\<系统编号\></span><span class="sxs-lookup"><span data-stu-id="5a5bd-111">A,\<application server host\>,\<system number\></span></span>  
  
  -   <span data-ttu-id="5a5bd-112">B\<消息服务器主机\>，\<R3NAME\></span><span class="sxs-lookup"><span data-stu-id="5a5bd-112">B,\<message server host\>,\<R3NAME\></span></span>  
  
  -   <span data-ttu-id="5a5bd-113">D，\<目标\></span><span class="sxs-lookup"><span data-stu-id="5a5bd-113">D,\<destination\></span></span>  
  
- <span data-ttu-id="5a5bd-114">有关调用适配器从 SAP 系统 （入站）</span><span class="sxs-lookup"><span data-stu-id="5a5bd-114">For calls from the SAP system to the adapter (inbound)</span></span>  
  
  -   <span data-ttu-id="5a5bd-115">我\<网关主机\>，\<网关服务器\></span><span class="sxs-lookup"><span data-stu-id="5a5bd-115">I,\<gateway host\>,\<gateway server\></span></span>  
  
  -   <span data-ttu-id="5a5bd-116">ID、\<目标\></span><span class="sxs-lookup"><span data-stu-id="5a5bd-116">ID,\<destination\></span></span>  
  
  <span data-ttu-id="5a5bd-117">操作 ID 可能是：</span><span class="sxs-lookup"><span data-stu-id="5a5bd-117">The action ID could be:</span></span>  
  
- <span data-ttu-id="5a5bd-118">\<RFC 名称\>（为 RFC 调用）</span><span class="sxs-lookup"><span data-stu-id="5a5bd-118">\<RFC name\> (for an RFC call)</span></span>  
  
- <span data-ttu-id="5a5bd-119">T，\<RFC 名称\>（适用于 tRFC 调用）</span><span class="sxs-lookup"><span data-stu-id="5a5bd-119">T,\<RFC name\> (for a tRFC call)</span></span>  
  
  <span data-ttu-id="5a5bd-120">仅在该适配器进行到 SAP 系统的第一个调用后初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-120">The performance counter is initialized only after the adapter makes the first call to the SAP system.</span></span> <span data-ttu-id="5a5bd-121">此外， [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)的性能计数器的属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-121">Also, the [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5a5bd-122">LOB Time （累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-122">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="5a5bd-123">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="5a5bd-123">Enabling Performance Counters</span></span>  
 <span data-ttu-id="5a5bd-124">可以启用或禁用通过设置绑定属性的性能计数器*EnablePerformanceCounters*。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-124">The performance counters can be enabled or disabled by setting the binding property *EnablePerformanceCounters*.</span></span> <span data-ttu-id="5a5bd-125">若要启用性能计数器，设置*EnablePerformanceCounters*属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-125">To enable performance counters, set the *EnablePerformanceCounters* binding property to **True**.</span></span> <span data-ttu-id="5a5bd-126">若要禁用性能计数器，设置*EnablePerformanceCounters*到**False**。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-126">To disable performance counters, set *EnablePerformanceCounters* to **False**.</span></span> <span data-ttu-id="5a5bd-127">默认情况下*EnablePerformanceCounters*设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-127">By default, *EnablePerformanceCounters* is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="5a5bd-128">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="5a5bd-128">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="5a5bd-129">更改的值*EnablePerformanceCounters*也绑定属性更改为相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-129">Changing the value of the *EnablePerformanceCounters* binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="5a5bd-130">此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-130">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="5a5bd-131">因此，如果有两个实例[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]AppDomain 中的绑定和*EnablePerformanceCounters*绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-131">Hence, if there are two instances of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding in the AppDomain, and the *EnablePerformanceCounters* binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="5a5bd-132">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上一次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="5a5bd-132">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5bd-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a5bd-133">See Also</span></span>  

[<span data-ttu-id="5a5bd-134">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="5a5bd-134">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)