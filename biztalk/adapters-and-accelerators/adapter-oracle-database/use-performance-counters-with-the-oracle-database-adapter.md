---
title: 使用 Oracle 数据库适配器的性能计数器 |Microsoft Docs
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
ms.openlocfilehash: 4bd80a3dea7f0e1b0e0e99e82c195540cd931c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375872"
---
# <a name="use-performance-counters-with-the-oracle-database-adapter"></a><span data-ttu-id="09ce7-102">使用性能计数器与 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="09ce7-102">Use performance counters with the Oracle Database adapter</span></span>
<span data-ttu-id="09ce7-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="09ce7-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="09ce7-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别**BizTalk Oracle DB 的.NET 适配器**以及安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="09ce7-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle DB** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="09ce7-105">LOB Time （累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="09ce7-105">LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="09ce7-106">**Oracle DB 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）。"</span><span class="sxs-lookup"><span data-stu-id="09ce7-106">The **BizTalk .NET Adapter for Oracle DB** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="09ce7-107">此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。</span><span class="sxs-lookup"><span data-stu-id="09ce7-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="09ce7-108">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以下模式中的任意创建性能计数器的实例：</span><span class="sxs-lookup"><span data-stu-id="09ce7-108">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="09ce7-109">其中可能是"string":</span><span class="sxs-lookup"><span data-stu-id="09ce7-109">Where "string" could be:</span></span>  
  
- <span data-ttu-id="09ce7-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="09ce7-110">Connection.Open</span></span>  
  
- <span data-ttu-id="09ce7-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="09ce7-111">Connection.Close</span></span>  
  
- <span data-ttu-id="09ce7-112">元数据</span><span class="sxs-lookup"><span data-stu-id="09ce7-112">Metadata</span></span>  
  
- <span data-ttu-id="09ce7-113">消息操作。</span><span class="sxs-lookup"><span data-stu-id="09ce7-113">Message action.</span></span> <span data-ttu-id="09ce7-114">例如，如果操作为`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert`字符串将为 SCOTT。Table.EMP.Insert。</span><span class="sxs-lookup"><span data-stu-id="09ce7-114">For example, if the action is `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert` then the string will be SCOTT.Table.EMP.Insert.</span></span>  
  
  <span data-ttu-id="09ce7-115">Oracle 数据源是与指定连接 URI 中相同。</span><span class="sxs-lookup"><span data-stu-id="09ce7-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
  <span data-ttu-id="09ce7-116">仅在该适配器进行首次调用到 Oracle 数据库后初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="09ce7-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="09ce7-117">此外，性能计数器的 InstanceLifetime 属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。</span><span class="sxs-lookup"><span data-stu-id="09ce7-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> <span data-ttu-id="09ce7-118">有关详细信息`InstanceLifetime property`，请参阅[ http://go.microsoft.com/fwlink/p/?LinkId=104181 ](http://go.microsoft.com/fwlink/p/?LinkId=104181)。</span><span class="sxs-lookup"><span data-stu-id="09ce7-118">For more information about the `InstanceLifetime property`, see [http://go.microsoft.com/fwlink/p/?LinkId=104181](http://go.microsoft.com/fwlink/p/?LinkId=104181).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09ce7-119">LOB Time （累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="09ce7-119">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="09ce7-120">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="09ce7-120">Enabling Performance Counters</span></span>  
 <span data-ttu-id="09ce7-121">可以启用或禁用通过设置绑定属性的性能计数器**EnablePerformanceCounters**。</span><span class="sxs-lookup"><span data-stu-id="09ce7-121">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="09ce7-122">若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="09ce7-122">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="09ce7-123">若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。</span><span class="sxs-lookup"><span data-stu-id="09ce7-123">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="09ce7-124">默认情况下**EnablePerformanceCounters**设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="09ce7-124">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="09ce7-125">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="09ce7-125">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="09ce7-126">更改的值**EnablePerformanceCounters**也绑定属性更改为相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="09ce7-126">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="09ce7-127">此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="09ce7-127">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="09ce7-128">因此，如果有两个实例[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]AppDomain 中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="09ce7-128">Therefore, if there are two instances of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="09ce7-129">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上一次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="09ce7-129">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ce7-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="09ce7-130">See Also</span></span>  
[<span data-ttu-id="09ce7-131">Oracle 数据库适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="09ce7-131">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)