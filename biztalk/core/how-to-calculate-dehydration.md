---
title: 如何计算冻结 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a327695099ec575f2a13ccb75b4152e4a7de1af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248309"
---
# <a name="how-to-calculate-dehydration"></a><span data-ttu-id="21c94-102">如何计算冻结</span><span class="sxs-lookup"><span data-stu-id="21c94-102">How to Calculate Dehydration</span></span>
<span data-ttu-id="21c94-103">若要计算冻结，则需要使用已配置的属性和某些运行时值。</span><span class="sxs-lookup"><span data-stu-id="21c94-103">To calculate dehydration, you use the configured properties and certain run-time values.</span></span> <span data-ttu-id="21c94-104">下面的示例演示如何计算假设的冻结方案。</span><span class="sxs-lookup"><span data-stu-id="21c94-104">The following example demonstrates how to calculate a hypothetical dehydration scenario.</span></span>  
  
### <a name="to-calculate-dehydration"></a><span data-ttu-id="21c94-105">计算冻结</span><span class="sxs-lookup"><span data-stu-id="21c94-105">To calculate dehydration</span></span>  
  
1.  <span data-ttu-id="21c94-106">让 alpha 表示一个介于 0 和 1 之间的因子，以测量内存使用状况。</span><span class="sxs-lookup"><span data-stu-id="21c94-106">Let alpha represent a factor between 0 and 1 that measures memory stress.</span></span>  <span data-ttu-id="21c94-107">在实际操作中，alpha 有 3 个不同的部分分别与 3 个内存阻止标准（冻结属性）对应；在本示例中，我们将它们分别表示为 alpha(virtual)、alpha(private) 和 alpha(physical)。</span><span class="sxs-lookup"><span data-stu-id="21c94-107">In practice, alpha has a component for each of the three memory throttling criteria (dehydration properties); in this example we denote them as alpha(virtual), alpha(private) and alpha(physical).</span></span> <span data-ttu-id="21c94-108">定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="21c94-108">Define the following:</span></span>  
  
    ```  
    IF ActualPrivateBytes < OptimalUsage  
       alpha(private) = 1  
    ELSE IF ActualPrivateBytes > MaximalUsage  
       alpha(private) = 0  
    ELSE  
       alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="21c94-109">OptimalUsage 和 MaximalUsage 具有每个冻结属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="21c94-109">OptimalUsage and MaximalUsage have default values for each dehydration property.</span></span> <span data-ttu-id="21c94-110">可以在 BTSNTSvc.exe.config 文件中更改这些值。</span><span class="sxs-lookup"><span data-stu-id="21c94-110">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="21c94-111">有关详细信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="21c94-111">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
2.  <span data-ttu-id="21c94-112">用同样的方法定义其他 alpha 成分。</span><span class="sxs-lookup"><span data-stu-id="21c94-112">Define the other alpha components analogously.</span></span> <span data-ttu-id="21c94-113">定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="21c94-113">Define the following:</span></span>  
  
    ```  
    alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
    where alpha(…) = 1 whenever IsActive=false for that given memory unit  
    ```  
  
3.  <span data-ttu-id="21c94-114">然后定义 TestThreshold（以秒为单位定义 TestThreshold、MinThreshold、MaxThreshold）：</span><span class="sxs-lookup"><span data-stu-id="21c94-114">Then define TestThreshold (TestThreshold, MinThreshold, and MaxThreshold are defined in seconds):</span></span>  
  
    ```  
    TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="21c94-115">MinThreshold 默认值 = 1。</span><span class="sxs-lookup"><span data-stu-id="21c94-115">MinThreshold default value = 1.</span></span> <span data-ttu-id="21c94-116">MaxThreshold 默认值 = 1800年。</span><span class="sxs-lookup"><span data-stu-id="21c94-116">MaxThreshold default value = 1800.</span></span> <span data-ttu-id="21c94-117">可以在 BTSNTSvc.exe.config 文件中更改这些值。</span><span class="sxs-lookup"><span data-stu-id="21c94-117">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="21c94-118">有关详细信息，请参阅[冻结默认属性](../core/dehydration-default-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="21c94-118">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
4.  <span data-ttu-id="21c94-119">然后定义 TimeBlocked 和 EstimatedTime：</span><span class="sxs-lookup"><span data-stu-id="21c94-119">Then define TimeBlocked and EstimatedTime:</span></span>  
  
    -   <span data-ttu-id="21c94-120">TimeBlocked = 我们等待满足此订阅的实际时间</span><span class="sxs-lookup"><span data-stu-id="21c94-120">TimeBlocked = actual time we have been waiting for this subscription to be satisfied</span></span>  
  
    -   <span data-ttu-id="21c94-121">EstimatedTime = 此业务流程保持空闲的估计时间（例如，侦听的剩余超时）</span><span class="sxs-lookup"><span data-stu-id="21c94-121">EstimatedTime = estimated time that this orchestration will remain idle (e.g. remaining timeout on the listen)</span></span>  
  
 <span data-ttu-id="21c94-122">是否冻结取决于下面布尔值条件的结果（true = 冻结）：</span><span class="sxs-lookup"><span data-stu-id="21c94-122">The decision whether to dehydrate is the result of the following Boolean condition (true = dehydrate):</span></span>  
  
-   <span data-ttu-id="21c94-123">冻结 = (EstimatedTime > TestThreshold OR TimeBlocked > (2\* TestThreshold))</span><span class="sxs-lookup"><span data-stu-id="21c94-123">Dehydrate = (EstimatedTime > TestThreshold OR TimeBlocked > (2\* TestThreshold))</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21c94-124">估计时间是至延迟结束的剩余时间（如果延迟 5 分钟，过去了 2 分钟，则 TimeBlocked=120 秒，EstimatedTime=180 秒）。</span><span class="sxs-lookup"><span data-stu-id="21c94-124">Estimated time is the time remaining until the delay is ended (if delayed for 5 minutes and 2 minutes has passed, TimeBlocked=120 seconds, EstimatedTime=180 seconds).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c94-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21c94-125">See Also</span></span>  
 <span data-ttu-id="21c94-126">[冻结默认属性](../core/dehydration-default-properties.md) </span><span class="sxs-lookup"><span data-stu-id="21c94-126">[Dehydration Default Properties](../core/dehydration-default-properties.md) </span></span>  
 [<span data-ttu-id="21c94-127">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="21c94-127">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)