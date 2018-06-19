---
title: 使用 SQL 适配器使用性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f81189e34346d377686dac79b44e5a9b34889dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965515"
---
# <a name="use-performance-counters-with-the-sql-adapter"></a><span data-ttu-id="fdd16-102">使用 SQL 适配器使用性能计数器</span><span class="sxs-lookup"><span data-stu-id="fdd16-102">Use Performance Counters with the SQL adapter</span></span>
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="fdd16-103">客户端可以使用性能计数器来测量的适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="fdd16-103"> clients can use the performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="fdd16-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序创建性能计数器类别"[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]"以及适配器包安装。</span><span class="sxs-lookup"><span data-stu-id="fdd16-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]" along with the Adapter Pack installation.</span></span>  
  
## <a name="the-lob-time-cumulative-performance-counter"></a><span data-ttu-id="fdd16-105">LOB Time （累积） 性能计数器</span><span class="sxs-lookup"><span data-stu-id="fdd16-105">The LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="fdd16-106">**BizTalk.NET Adapter for SQL**类别都有一个性能计数器名为"LOB 时间 （的累积）"。</span><span class="sxs-lookup"><span data-stu-id="fdd16-106">The **BizTalk .NET Adapter for SQL** category has one performance counter called "LOB Time (Cumulative)".</span></span> <span data-ttu-id="fdd16-107">此性能计数器表示的时间，以毫秒为单位，SQL Server 客户端库所需完成操作时引发了适配器。</span><span class="sxs-lookup"><span data-stu-id="fdd16-107">This performance counter denotes the time, in milliseconds, that the SQL Server client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="fdd16-108">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]创建的每个操作，特定的 SQL Server 实例和数据库名称的性能计数器实例。</span><span class="sxs-lookup"><span data-stu-id="fdd16-108">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] creates an instance of the performance counter for each action, for a specific SQL Server instance and database name.</span></span> <span data-ttu-id="fdd16-109">下面的模式来创建实例：</span><span class="sxs-lookup"><span data-stu-id="fdd16-109">The instances are created in the following pattern:</span></span>  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 <span data-ttu-id="fdd16-110">`<endpointId>`作为派生`<sql_server_name>, <instance_name>, <database_name>`。</span><span class="sxs-lookup"><span data-stu-id="fdd16-110">The `<endpointId>` is derived as `<sql_server_name>, <instance_name>, <database_name>`.</span></span>  
  
 <span data-ttu-id="fdd16-111">\<ActionId\>按以下方式派生：</span><span class="sxs-lookup"><span data-stu-id="fdd16-111">The \<actionId\> is derived in the following manner:</span></span>  
  
-   <span data-ttu-id="fdd16-112">用于打开连接，该操作 ID 是"打开"。</span><span class="sxs-lookup"><span data-stu-id="fdd16-112">For opening a connection, the action ID is “Open”.</span></span>  
  
-   <span data-ttu-id="fdd16-113">对于入站运算，操作 ID 是"入站"。</span><span class="sxs-lookup"><span data-stu-id="fdd16-113">For inbound operations, the action ID is “Inbound”.</span></span>  
  
-   <span data-ttu-id="fdd16-114">对于出站运算，操作 ID 是从中调用该操作的操作与"/"替换为下划线"_"。</span><span class="sxs-lookup"><span data-stu-id="fdd16-114">For outbound operations, the action ID is the action of the operation being invoked, with “/” replaced by an underscore “_”.</span></span> <span data-ttu-id="fdd16-115">此外，操作 ID 的前面带"ExecuteScalar"、"ExecuteReader"或"ExecuteNonQuery"根据适配器内部使用的 SQL Server 数据库上执行的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="fdd16-115">Also, the action ID is prefixed with the “ExecuteScalar”, “ExecuteReader”, or “ExecuteNonQuery” depending on the method that the adapter internally uses to perform the operation on the SQL Server database.</span></span> <span data-ttu-id="fdd16-116">例如，适配器内部使用**ExecuteReader**方法以在 SQL Server 中执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="fdd16-116">For example, the adapter internally uses the **ExecuteReader** method to execute a stored procedure in SQL Server.</span></span> <span data-ttu-id="fdd16-117">因此，将是存储过程，MyProcedure，操作 ID:</span><span class="sxs-lookup"><span data-stu-id="fdd16-117">So, the action ID for the stored procedure, MyProcedure, will be:</span></span>  
  
    ```  
    ExecuteReader_Procedure_dbo_MyProcedure  
    ```  

 <span data-ttu-id="fdd16-118">仅在该适配器进行首次调用的 SQL Server 数据库后初始化性能计数器。</span><span class="sxs-lookup"><span data-stu-id="fdd16-118">The performance counter is initialized only after the adapter makes the first call to the SQL Server database.</span></span> <span data-ttu-id="fdd16-119">此外， [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)的性能计数器的属性设置为进程，这意味着性能计数器停止存在就会立即创建计数器在程序终止。</span><span class="sxs-lookup"><span data-stu-id="fdd16-119">Also, the [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="fdd16-120">LOB Time （的累积） 性能计数器的精度为 16 毫秒。</span><span class="sxs-lookup"><span data-stu-id="fdd16-120">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="fdd16-121">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="fdd16-121">Enabling Performance Counters</span></span>  
 <span data-ttu-id="fdd16-122">性能计数器可以启用或禁用通过设置绑定属性**EnablePerformanceCounters**。</span><span class="sxs-lookup"><span data-stu-id="fdd16-122">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="fdd16-123">若要启用性能计数器，设置**EnablePerformanceCounters**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="fdd16-123">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="fdd16-124">若要禁用性能计数器，设置**EnablePerformanceCounters**到**False**。</span><span class="sxs-lookup"><span data-stu-id="fdd16-124">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="fdd16-125">默认情况下，该属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="fdd16-125">By default, the property is set to **False**.</span></span> <span data-ttu-id="fdd16-126">有关此绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd16-126">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="fdd16-127">性能计数器和 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="fdd16-127">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="fdd16-128">更改的值**EnablePerformanceCounters**还绑定属性的相应性能计数器的值更改[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fdd16-128">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="fdd16-129">此外，绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的而，对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是动态的。</span><span class="sxs-lookup"><span data-stu-id="fdd16-129">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is dynamic.</span></span> <span data-ttu-id="fdd16-130">因此，如果有两个实例的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定在应用程序域中，与**EnablePerformanceCounters**绑定属性设置为**True**之一中和**False**中另一个，其中一个中启用和禁用另一部分中特定于适配器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="fdd16-130">Hence, if there are two instances of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding in the application domain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="fdd16-131">但是，因为绑定属性[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是静态的它将设置为**True**或**False**具体取决于上次指定哪些值。</span><span class="sxs-lookup"><span data-stu-id="fdd16-131">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd16-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdd16-132">See Also</span></span>  
[<span data-ttu-id="fdd16-133">解决 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="fdd16-133">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)