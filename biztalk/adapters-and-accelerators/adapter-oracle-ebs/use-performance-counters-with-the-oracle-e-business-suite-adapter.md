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
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="bd19c-102">用于 Oracle E-business Suite 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="bd19c-102">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="bd19c-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="bd19c-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="bd19c-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建的性能计数器类别**适用于 Oracle E-business Suite 的 BizTalk.NET 适配器**以及安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd19c-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle E-Business Suite** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="bd19c-105">LOB Time （累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="bd19c-105">LOB Time (Cumulative) performance counter</span></span>  
 <span data-ttu-id="bd19c-106">**适用于 Oracle E-business Suite 的 BizTalk.NET 适配器**类别都有一个名为性能计数器"LOB 时间 （累积）。"</span><span class="sxs-lookup"><span data-stu-id="bd19c-106">The **BizTalk .NET Adapter for Oracle E-Business Suite** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="bd19c-107">此性能计数器表示的时间，以毫秒为单位，LOB 客户端库所需完成某项操作，适配器启动的。</span><span class="sxs-lookup"><span data-stu-id="bd19c-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="bd19c-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以下模式中的任意创建性能计数器的实例：</span><span class="sxs-lookup"><span data-stu-id="bd19c-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="bd19c-109">其中可能是"string":</span><span class="sxs-lookup"><span data-stu-id="bd19c-109">Where "string" could be:</span></span>  
  
- <span data-ttu-id="bd19c-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="bd19c-110">Connection.Open</span></span>  
  
- <span data-ttu-id="bd19c-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="bd19c-111">Connection.Close</span></span>  
  
- <span data-ttu-id="bd19c-112">元数据</span><span class="sxs-lookup"><span data-stu-id="bd19c-112">Metadata</span></span>  
  
- <span data-ttu-id="bd19c-113">消息操作。</span><span class="sxs-lookup"><span data-stu-id="bd19c-113">Message action.</span></span> <span data-ttu-id="bd19c-114">例如，如果操作为`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`字符串将为 InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE。</span><span class="sxs-lookup"><span data-stu-id="bd19c-114">For example, if the action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` then the string will be InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.</span></span>  
  
  <span data-ttu-id="bd19c-115">Oracle 数据源是与指定连接 URI 中相同。</span><span class="sxs-lookup"><span data-stu-id="bd19c-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
  <span data-ttu-id="bd19c-116">仅在该适配器进行首次调用到 Oracle 数据库后初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bd19c-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="bd19c-117">此外，性能计数器的 InstanceLifetime 属性设置为进程，这意味着，性能计数器将不再存在就立即创建计数器程序终止。</span><span class="sxs-lookup"><span data-stu-id="bd19c-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="bd19c-118">LOB Time （累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="bd19c-118">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="bd19c-119">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="bd19c-119">Enabling Performance Counters</span></span>  
 <span data-ttu-id="bd19c-120">可以启用或禁用通过设置绑定属性的性能计数器**EnablePerformanceCounters**。</span><span class="sxs-lookup"><span data-stu-id="bd19c-120">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="bd19c-121">若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="bd19c-121">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="bd19c-122">若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。</span><span class="sxs-lookup"><span data-stu-id="bd19c-122">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="bd19c-123">默认情况下**EnablePerformanceCounters**设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="bd19c-123">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="bd19c-124">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="bd19c-124">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="bd19c-125">更改的值**EnablePerformanceCounters**也绑定属性更改为相应的性能计数器的值[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd19c-125">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="bd19c-126">此外，有关的绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="bd19c-126">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="bd19c-127">因此，如果有两个实例[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]AppDomain 中的绑定和**EnablePerformanceCounters**绑定属性设置为**True**一个中和**False**中，一个中启用和禁用中的其他特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bd19c-127">Therefore, if there are two instances of the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="bd19c-128">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上一次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="bd19c-128">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd19c-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd19c-129">See Also</span></span>  
[<span data-ttu-id="bd19c-130">适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="bd19c-130">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)