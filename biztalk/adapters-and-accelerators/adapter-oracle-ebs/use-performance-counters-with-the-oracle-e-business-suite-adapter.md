---
title: "用于 Oracle E-business Suite 适配器的性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2a9f345745c18ca03086833fffe3553e96cece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="4ab13-102">用于 Oracle E-business Suite 适配器的性能计数器</span><span class="sxs-lookup"><span data-stu-id="4ab13-102">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="4ab13-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="4ab13-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="4ab13-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别**用于 Oracle E-business Suite 的 BizTalk.NET Adapter**以及安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ab13-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle E-Business Suite** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="4ab13-105">LOB Time （的累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="4ab13-105">LOB Time (Cumulative) performance counter</span></span>  
 <span data-ttu-id="4ab13-106">**用于 Oracle E-business Suite 的 BizTalk.NET Adapter**类别都有一个性能计数器"LOB 次调用 （的累积）。"</span><span class="sxs-lookup"><span data-stu-id="4ab13-106">The **BizTalk .NET Adapter for Oracle E-Business Suite** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="4ab13-107">此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成操作时引发了适配器。</span><span class="sxs-lookup"><span data-stu-id="4ab13-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="4ab13-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以下模式中的任意创建性能计数器的实例：</span><span class="sxs-lookup"><span data-stu-id="4ab13-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="4ab13-109">其中可能是"string":</span><span class="sxs-lookup"><span data-stu-id="4ab13-109">Where "string" could be:</span></span>  
  
-   <span data-ttu-id="4ab13-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="4ab13-110">Connection.Open</span></span>  
  
-   <span data-ttu-id="4ab13-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="4ab13-111">Connection.Close</span></span>  
  
-   <span data-ttu-id="4ab13-112">元数据</span><span class="sxs-lookup"><span data-stu-id="4ab13-112">Metadata</span></span>  
  
-   <span data-ttu-id="4ab13-113">消息操作。</span><span class="sxs-lookup"><span data-stu-id="4ab13-113">Message action.</span></span> <span data-ttu-id="4ab13-114">例如，如果操作是`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`则字符串将 InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE。</span><span class="sxs-lookup"><span data-stu-id="4ab13-114">For example, if the action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` then the string will be InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="4ab13-115">Oracle 数据源是与指定连接 URI 中相同。</span><span class="sxs-lookup"><span data-stu-id="4ab13-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
 <span data-ttu-id="4ab13-116">仅在该适配器进行首次调用到 Oracle 数据库后初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="4ab13-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="4ab13-117">此外，性能计数器的 InstanceLifetime 属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。</span><span class="sxs-lookup"><span data-stu-id="4ab13-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="4ab13-118">LOB Time （的累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="4ab13-118">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="4ab13-119">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="4ab13-119">Enabling Performance Counters</span></span>  
 <span data-ttu-id="4ab13-120">性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。</span><span class="sxs-lookup"><span data-stu-id="4ab13-120">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="4ab13-121">若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="4ab13-121">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="4ab13-122">若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。</span><span class="sxs-lookup"><span data-stu-id="4ab13-122">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="4ab13-123">默认情况下， **EnablePerformanceCounters**设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="4ab13-123">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="4ab13-124">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="4ab13-124">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="4ab13-125">更改的值**EnablePerformanceCounters**还绑定属性的相应性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ab13-125">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="4ab13-126">此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="4ab13-126">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="4ab13-127">因此，如果有两个实例的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]AppDomain 中中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="4ab13-127">Therefore, if there are two instances of the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="4ab13-128">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="4ab13-128">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab13-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab13-129">See Also</span></span>  
[<span data-ttu-id="4ab13-130">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="4ab13-130">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)