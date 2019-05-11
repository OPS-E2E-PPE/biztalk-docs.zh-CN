---
title: 如何修改业务流程内存阻止设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceOrchestration
ms.assetid: f6953c68-7809-4518-87ec-e75c98884af3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839ef9d8d97e06c85192c3d8fee049029942fb99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336053"
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a><span data-ttu-id="e35a3-102">如何修改业务流程内存阻止设置</span><span class="sxs-lookup"><span data-stu-id="e35a3-102">How to Modify Orchestration Memory Throttling Settings</span></span>
<span data-ttu-id="e35a3-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例内存阻止机制会连续监控阻止条件，计算阻止条件的严重性和应用主机实例内存阻止以渐进方式具体取决于计算严重级别。</span><span class="sxs-lookup"><span data-stu-id="e35a3-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instance memory throttling mechanism continuously monitors for a throttling condition, calculates the severity of the throttling condition, and applies host instance memory throttling progressively depending on the calculated severity.</span></span> <span data-ttu-id="e35a3-104">本主题提供了使用设置仪表板修改这些设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="e35a3-104">This topic provides the step-by-step procedure to modify these settings using the Settings Dashboard.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="e35a3-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="e35a3-105">Prerequisites</span></span>  
 <span data-ttu-id="e35a3-106">若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e35a3-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  

### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a><span data-ttu-id="e35a3-107">若要修改业务流程内存阻止设置的主机实例</span><span class="sxs-lookup"><span data-stu-id="e35a3-107">To modify the orchestration memory throttling settings of a host instance</span></span>  

1. <span data-ttu-id="e35a3-108">在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="e35a3-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  

2. <span data-ttu-id="e35a3-109">在中**BizTalk 设置仪表板**对话框中，在**主机实例**页上，单击**业务流程内存阻止**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e35a3-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** page, click the **Orchestration Memory Throttling** tab.</span></span>  

3. <span data-ttu-id="e35a3-110">执行以下操作，然后依次**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="e35a3-110">Do the following, and then click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  


   |     <span data-ttu-id="e35a3-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e35a3-111">Use this</span></span>      |                                                                                <span data-ttu-id="e35a3-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e35a3-112">To do this</span></span>                                                                                | <span data-ttu-id="e35a3-113">边界值</span><span class="sxs-lookup"><span data-stu-id="e35a3-113">Boundary values</span></span> | <span data-ttu-id="e35a3-114">默认值</span><span class="sxs-lookup"><span data-stu-id="e35a3-114">Default value</span></span> |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|
   | <span data-ttu-id="e35a3-115">**主机实例**</span><span class="sxs-lookup"><span data-stu-id="e35a3-115">**Host Instance**</span></span> | <span data-ttu-id="e35a3-116">从下拉列表框中，选择正在运行的主机实例上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机。</span><span class="sxs-lookup"><span data-stu-id="e35a3-116">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span> |        -        |       -       |

    <span data-ttu-id="e35a3-117">**物理**</span><span class="sxs-lookup"><span data-stu-id="e35a3-117">**Physical**</span></span>  

   |<span data-ttu-id="e35a3-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e35a3-118">Use this</span></span>|<span data-ttu-id="e35a3-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e35a3-119">To do this</span></span>|<span data-ttu-id="e35a3-120">边界值</span><span class="sxs-lookup"><span data-stu-id="e35a3-120">Boundary values</span></span>|<span data-ttu-id="e35a3-121">默认值</span><span class="sxs-lookup"><span data-stu-id="e35a3-121">Default value</span></span>|  
   |--------------|----------------|---------------------|-------------------|  
   |<span data-ttu-id="e35a3-122">**最佳使用率**</span><span class="sxs-lookup"><span data-stu-id="e35a3-122">**Optimal usage**</span></span>|<span data-ttu-id="e35a3-123">指定的冻结阻止生效的物理内存使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="e35a3-123">Specify the percentage of physical memory usage at which dehydration throttling comes into effect.</span></span> <span data-ttu-id="e35a3-124">这是用于主机实例的物理内存的最佳百分比。</span><span class="sxs-lookup"><span data-stu-id="e35a3-124">This is the optimum percentage of physical memory to use for the host instances.</span></span>|<span data-ttu-id="e35a3-125">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="e35a3-125">[0 – 100]</span></span>|<span data-ttu-id="e35a3-126">70</span><span class="sxs-lookup"><span data-stu-id="e35a3-126">70</span></span>|  
   |<span data-ttu-id="e35a3-127">**最大使用率**</span><span class="sxs-lookup"><span data-stu-id="e35a3-127">**Maximal usage**</span></span>|<span data-ttu-id="e35a3-128">指定冻结阻止处于最大物理内存使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="e35a3-128">Specify the percentage of physical memory usage at which dehydration throttling is maximum.</span></span> <span data-ttu-id="e35a3-129">这是用于主机实例的物理内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="e35a3-129">This is the maximum percentage of physical memory to use for the host instances.</span></span><br /><br /> <span data-ttu-id="e35a3-130">最小值**最大使用率**应**最佳使用率**。</span><span class="sxs-lookup"><span data-stu-id="e35a3-130">The minimum value of **Maximal usage** should be **Optimal usage**.</span></span>|<span data-ttu-id="e35a3-131">（最佳使用量 – 100]</span><span class="sxs-lookup"><span data-stu-id="e35a3-131">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="e35a3-132">两者都是 0 或 100 时除外。</span><span class="sxs-lookup"><span data-stu-id="e35a3-132">Except when both are 0 or 100.</span></span>|<span data-ttu-id="e35a3-133">85</span><span class="sxs-lookup"><span data-stu-id="e35a3-133">85</span></span>|  

    <span data-ttu-id="e35a3-134">**Virtual**</span><span class="sxs-lookup"><span data-stu-id="e35a3-134">**Virtual**</span></span>  

   |<span data-ttu-id="e35a3-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e35a3-135">Use this</span></span>|<span data-ttu-id="e35a3-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e35a3-136">To do this</span></span>|<span data-ttu-id="e35a3-137">边界值</span><span class="sxs-lookup"><span data-stu-id="e35a3-137">Boundary values</span></span>|<span data-ttu-id="e35a3-138">默认值</span><span class="sxs-lookup"><span data-stu-id="e35a3-138">Default value</span></span>|  
   |--------------|----------------|---------------------|-------------------|  
   |<span data-ttu-id="e35a3-139">**最佳使用率**</span><span class="sxs-lookup"><span data-stu-id="e35a3-139">**Optimal usage**</span></span>|<span data-ttu-id="e35a3-140">指定冻结阻止生效的虚拟内存使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="e35a3-140">Specify the percentage of virtual memory usage at which dehydration throttling comes into effect.</span></span><br /><br /> <span data-ttu-id="e35a3-141">在此情况下， **TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="e35a3-141">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>|<span data-ttu-id="e35a3-142">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="e35a3-142">[0 – 100]</span></span>|<span data-ttu-id="e35a3-143">65</span><span class="sxs-lookup"><span data-stu-id="e35a3-143">65</span></span>|  
   |<span data-ttu-id="e35a3-144">**最大使用率**</span><span class="sxs-lookup"><span data-stu-id="e35a3-144">**Maximal usage**</span></span>|<span data-ttu-id="e35a3-145">指定冻结阻止处于最大虚拟内存使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="e35a3-145">Specify the percentage of virtual memory usage at which dehydration throttling is maximum.</span></span><br /><br /> <span data-ttu-id="e35a3-146">在此情况下， **TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。</span><span class="sxs-lookup"><span data-stu-id="e35a3-146">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>|<span data-ttu-id="e35a3-147">（最佳使用量 – 100]</span><span class="sxs-lookup"><span data-stu-id="e35a3-147">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="e35a3-148">两者都是 0 或 100 时除外。</span><span class="sxs-lookup"><span data-stu-id="e35a3-148">Except when both are 0 or 100.</span></span>|<span data-ttu-id="e35a3-149">85</span><span class="sxs-lookup"><span data-stu-id="e35a3-149">85</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="e35a3-150">若要还原默认设置，请单击**还原为默认值**。</span><span class="sxs-lookup"><span data-stu-id="e35a3-150">To restore the default settings, click **Restore Defaults**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e35a3-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="e35a3-151">See Also</span></span>  
 [<span data-ttu-id="e35a3-152">如何修改主机实例设置</span><span class="sxs-lookup"><span data-stu-id="e35a3-152">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)