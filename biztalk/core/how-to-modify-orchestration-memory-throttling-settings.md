---
title: 如何修改 Orchestration 内存限制设置 |Microsoft 文档
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
ms.openlocfilehash: c48f1ec5e74ae577a7c1d130e22f3b4a1b53874c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254669"
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a><span data-ttu-id="b29ae-102">如何修改内存阻止设置业务流程</span><span class="sxs-lookup"><span data-stu-id="b29ae-102">How to Modify Orchestration Memory Throttling Settings</span></span>
<span data-ttu-id="b29ae-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机实例内存阻止机制会连续监控阻止条件，计算阻止条件的严重性，并根据计算出的严重性以渐进方式应用主机实例内存阻止。</span><span class="sxs-lookup"><span data-stu-id="b29ae-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instance memory throttling mechanism continuously monitors for a throttling condition, calculates the severity of the throttling condition, and applies host instance memory throttling progressively depending on the calculated severity.</span></span> <span data-ttu-id="b29ae-104">本主题提供了使用设置仪表板修改这些设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="b29ae-104">This topic provides the step-by-step procedure to modify these settings using the Settings Dashboard.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b29ae-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="b29ae-105">Prerequisites</span></span>  
 <span data-ttu-id="b29ae-106">若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="b29ae-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a><span data-ttu-id="b29ae-107">修改主机实例的业务流程内存阻止设置</span><span class="sxs-lookup"><span data-stu-id="b29ae-107">To modify the orchestration memory throttling settings of a host instance</span></span>  
  
1.  <span data-ttu-id="b29ae-108">在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="b29ae-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="b29ae-109">在**BizTalk 设置仪表板**对话框中，在**主机实例**页上，单击**Orchestration 内存限制**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b29ae-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** page, click the **Orchestration Memory Throttling** tab.</span></span>  
  
3.  <span data-ttu-id="b29ae-110">执行以下操作，并依次**应用**应用修改再转到另一个选项卡。或单击**确定**应用进行修改并退出设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="b29ae-110">Do the following, and then click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  
  
    |<span data-ttu-id="b29ae-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b29ae-111">Use this</span></span>|<span data-ttu-id="b29ae-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b29ae-112">To do this</span></span>|<span data-ttu-id="b29ae-113">边界值</span><span class="sxs-lookup"><span data-stu-id="b29ae-113">Boundary values</span></span>|<span data-ttu-id="b29ae-114">默认值</span><span class="sxs-lookup"><span data-stu-id="b29ae-114">Default value</span></span>|  
    |--------------|----------------|---------------------|-------------------|  
    |<span data-ttu-id="b29ae-115">**主机实例**</span><span class="sxs-lookup"><span data-stu-id="b29ae-115">**Host Instance**</span></span>|<span data-ttu-id="b29ae-116">从下拉框中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时计算机上选择正在运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="b29ae-116">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span>|-|-|  
  
     <span data-ttu-id="b29ae-117">**物理**</span><span class="sxs-lookup"><span data-stu-id="b29ae-117">**Physical**</span></span>  
  
    |<span data-ttu-id="b29ae-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b29ae-118">Use this</span></span>|<span data-ttu-id="b29ae-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b29ae-119">To do this</span></span>|<span data-ttu-id="b29ae-120">边界值</span><span class="sxs-lookup"><span data-stu-id="b29ae-120">Boundary values</span></span>|<span data-ttu-id="b29ae-121">默认值</span><span class="sxs-lookup"><span data-stu-id="b29ae-121">Default value</span></span>|  
    |--------------|----------------|---------------------|-------------------|  
    |<span data-ttu-id="b29ae-122">**最佳使用**</span><span class="sxs-lookup"><span data-stu-id="b29ae-122">**Optimal usage**</span></span>|<span data-ttu-id="b29ae-123">指定冻结阻止生效的物理内存使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="b29ae-123">Specify the percentage of physical memory usage at which dehydration throttling comes into effect.</span></span> <span data-ttu-id="b29ae-124">这是用于主机实例的物理内存的最佳百分比。</span><span class="sxs-lookup"><span data-stu-id="b29ae-124">This is the optimum percentage of physical memory to use for the host instances.</span></span>|<span data-ttu-id="b29ae-125">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="b29ae-125">[0 – 100]</span></span>|<span data-ttu-id="b29ae-126">70</span><span class="sxs-lookup"><span data-stu-id="b29ae-126">70</span></span>|  
    |<span data-ttu-id="b29ae-127">**最大限度地使用情况**</span><span class="sxs-lookup"><span data-stu-id="b29ae-127">**Maximal usage**</span></span>|<span data-ttu-id="b29ae-128">指定冻结阻止最大的物理内存使用率百分比。</span><span class="sxs-lookup"><span data-stu-id="b29ae-128">Specify the percentage of physical memory usage at which dehydration throttling is maximum.</span></span> <span data-ttu-id="b29ae-129">这是用于主机实例的物理内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="b29ae-129">This is the maximum percentage of physical memory to use for the host instances.</span></span><br /><br /> <span data-ttu-id="b29ae-130">最小值**最大限度地使用**应**最佳使用**。</span><span class="sxs-lookup"><span data-stu-id="b29ae-130">The minimum value of **Maximal usage** should be **Optimal usage**.</span></span>|<span data-ttu-id="b29ae-131">（ 最佳使用量 – 100]</span><span class="sxs-lookup"><span data-stu-id="b29ae-131">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="b29ae-132">都为 0 或都为 100 时除外。</span><span class="sxs-lookup"><span data-stu-id="b29ae-132">Except when both are 0 or 100.</span></span>|<span data-ttu-id="b29ae-133">85</span><span class="sxs-lookup"><span data-stu-id="b29ae-133">85</span></span>|  
  
     <span data-ttu-id="b29ae-134">**虚拟**</span><span class="sxs-lookup"><span data-stu-id="b29ae-134">**Virtual**</span></span>  
  
    |<span data-ttu-id="b29ae-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b29ae-135">Use this</span></span>|<span data-ttu-id="b29ae-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b29ae-136">To do this</span></span>|<span data-ttu-id="b29ae-137">边界值</span><span class="sxs-lookup"><span data-stu-id="b29ae-137">Boundary values</span></span>|<span data-ttu-id="b29ae-138">默认值</span><span class="sxs-lookup"><span data-stu-id="b29ae-138">Default value</span></span>|  
    |--------------|----------------|---------------------|-------------------|  
    |<span data-ttu-id="b29ae-139">**最佳使用**</span><span class="sxs-lookup"><span data-stu-id="b29ae-139">**Optimal usage**</span></span>|<span data-ttu-id="b29ae-140">指定冻结阻止生效的虚拟内存使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="b29ae-140">Specify the percentage of virtual memory usage at which dehydration throttling comes into effect.</span></span><br /><br /> <span data-ttu-id="b29ae-141">此时， **TestThreshold**具有值**MaxThreshold**和任何内存使用率大于**OptimalUsage**导致**TestThreshold**要小于**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="b29ae-141">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>|<span data-ttu-id="b29ae-142">[0 – 100]</span><span class="sxs-lookup"><span data-stu-id="b29ae-142">[0 – 100]</span></span>|<span data-ttu-id="b29ae-143">65</span><span class="sxs-lookup"><span data-stu-id="b29ae-143">65</span></span>|  
    |<span data-ttu-id="b29ae-144">**最大限度地使用情况**</span><span class="sxs-lookup"><span data-stu-id="b29ae-144">**Maximal usage**</span></span>|<span data-ttu-id="b29ae-145">指定冻结阻止最大的虚拟内存使用率百分比。</span><span class="sxs-lookup"><span data-stu-id="b29ae-145">Specify the percentage of virtual memory usage at which dehydration throttling is maximum.</span></span><br /><br /> <span data-ttu-id="b29ae-146">此时， **TestThreshold**具有值**MinThreshold**和任何内存使用率小于**MaximalUsage**导致**TestThreshold**晚于**MinThreshold**。</span><span class="sxs-lookup"><span data-stu-id="b29ae-146">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>|<span data-ttu-id="b29ae-147">（ 最佳使用量 – 100]</span><span class="sxs-lookup"><span data-stu-id="b29ae-147">(Optimal usage – 100]</span></span><br /><br /> <span data-ttu-id="b29ae-148">都为 0 或都为 100 时除外。</span><span class="sxs-lookup"><span data-stu-id="b29ae-148">Except when both are 0 or 100.</span></span>|<span data-ttu-id="b29ae-149">85</span><span class="sxs-lookup"><span data-stu-id="b29ae-149">85</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="b29ae-150">若要还原默认设置，请单击**还原为默认值**。</span><span class="sxs-lookup"><span data-stu-id="b29ae-150">To restore the default settings, click **Restore Defaults**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29ae-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b29ae-151">See Also</span></span>  
 [<span data-ttu-id="b29ae-152">如何修改主机实例设置</span><span class="sxs-lookup"><span data-stu-id="b29ae-152">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)