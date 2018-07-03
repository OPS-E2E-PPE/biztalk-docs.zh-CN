---
title: 例程监视任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2f9f56a-c839-4108-933d-69b00a1e3817
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d500e79cdf20c6a1914708976101715c2f00ae69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001654"
---
# <a name="routine-monitoring-tasks"></a><span data-ttu-id="07b57-102">例程监视任务</span><span class="sxs-lookup"><span data-stu-id="07b57-102">Routine Monitoring Tasks</span></span>
<span data-ttu-id="07b57-103">执行以下监视任务按定期计划将帮助您保护您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构做好运行准备。</span><span class="sxs-lookup"><span data-stu-id="07b57-103">Performing the following monitoring tasks on a regularly scheduled basis will assist you in keeping your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure operationally ready.</span></span>  
  
## <a name="daily-monitoring-tasks"></a><span data-ttu-id="07b57-104">每日监视任务</span><span class="sxs-lookup"><span data-stu-id="07b57-104">Daily Monitoring Tasks</span></span>  
  
- <span data-ttu-id="07b57-105">检查所有打开的警报。</span><span class="sxs-lookup"><span data-stu-id="07b57-105">Review all open alerts.</span></span>  
  
- <span data-ttu-id="07b57-106">使用**组中心**页中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来调查业务流程、 端口和消息失败。</span><span class="sxs-lookup"><span data-stu-id="07b57-106">Use the **Group Hub** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="07b57-107">**组中心**提供了对系统中，访问 MessageBox 数据库中的数据的当前实时状态的访问。</span><span class="sxs-lookup"><span data-stu-id="07b57-107">The **Group Hub** page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="07b57-108">您可以查看所有服务实例（例如业务流程、端口和消息传送）及其关联的消息。</span><span class="sxs-lookup"><span data-stu-id="07b57-108">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="07b57-109">使用**组中心**页面可以执行以下活动：</span><span class="sxs-lookup"><span data-stu-id="07b57-109">Using the **Group Hub** page you can perform the following activities:</span></span>  
  
  - <span data-ttu-id="07b57-110">请参阅当前正在运行的服务实例，如业务流程和消息传送和及其关联的消息。</span><span class="sxs-lookup"><span data-stu-id="07b57-110">See currently running service instances, such as orchestrations and messaging, and their associated messages.</span></span>  
  
  - <span data-ttu-id="07b57-111">在 MessageBox 数据库中进行搜索，以显示系统的当前数据以及实时状态的视图。</span><span class="sxs-lookup"><span data-stu-id="07b57-111">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
  - <span data-ttu-id="07b57-112">挂起、终止和恢复服务实例。</span><span class="sxs-lookup"><span data-stu-id="07b57-112">Suspend, terminate, and resume service instances.</span></span>  
  
    <span data-ttu-id="07b57-113">有关使用详细信息**组中心**页上，请参阅[ http://go.microsoft.com/fwlink/?LinkId=155281 ](http://go.microsoft.com/fwlink/?LinkId=155281)。</span><span class="sxs-lookup"><span data-stu-id="07b57-113">For more information about using the **Group Hub** page, see [http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281).</span></span>  
  
- <span data-ttu-id="07b57-114">检查警告（可选）。</span><span class="sxs-lookup"><span data-stu-id="07b57-114">Review warnings (optional).</span></span>  
  
  <span data-ttu-id="07b57-115">有关详细信息，请参阅[清单： 执行每日维护检查](../technical-guides/checklist-performing-daily-maintenance-checks.md)。</span><span class="sxs-lookup"><span data-stu-id="07b57-115">For more information, see [Checklist: Performing Daily Maintenance Checks](../technical-guides/checklist-performing-daily-maintenance-checks.md).</span></span>  
  
## <a name="weekly-monitoring-tasks"></a><span data-ttu-id="07b57-116">监视的每周任务</span><span class="sxs-lookup"><span data-stu-id="07b57-116">Weekly Monitoring Tasks</span></span>  
  
- <span data-ttu-id="07b57-117">查看至少一次每周的事件日志。</span><span class="sxs-lookup"><span data-stu-id="07b57-117">Review the event logs at least once per week.</span></span> <span data-ttu-id="07b57-118">此任务的原因是为了防止问题，例如将未能检测到的 DBNetLib 错误。</span><span class="sxs-lookup"><span data-stu-id="07b57-118">The reason for this task is to prevent issues, such as DBNetLib errors going undetected.</span></span> <span data-ttu-id="07b57-119">服务中断可能会被忽略，除非你有一个很短的延迟系统。</span><span class="sxs-lookup"><span data-stu-id="07b57-119">Service interruption might go unnoticed unless you have a very low latency system.</span></span> <span data-ttu-id="07b57-120">但是，这些错误的一些可以指示一个更大的问题 （示例中，过多主机或 BizTalk Server 服务器的消息框、 上的 SQL 框等的性能问题数）。</span><span class="sxs-lookup"><span data-stu-id="07b57-120">However, some of these errors can indicate a bigger issue (for example, too many hosts or BizTalk Server servers for the number of message boxes, performance issues on the SQL box, etc).</span></span>  
  
  <span data-ttu-id="07b57-121">有关详细信息，请参阅[清单： 执行每周维护检查](../technical-guides/checklist-performing-weekly-maintenance-checks.md)。</span><span class="sxs-lookup"><span data-stu-id="07b57-121">For more information, see [Checklist: Performing Weekly Maintenance Checks](../technical-guides/checklist-performing-weekly-maintenance-checks.md).</span></span>  
  
## <a name="as-needed-tasks"></a><span data-ttu-id="07b57-122">根据任务</span><span class="sxs-lookup"><span data-stu-id="07b57-122">As-Needed Tasks</span></span>  
  
- <span data-ttu-id="07b57-123">修改规则以自定义的监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。</span><span class="sxs-lookup"><span data-stu-id="07b57-123">Modify the rules to customize the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
- <span data-ttu-id="07b57-124">运行日志的性能分析工具 (PAL)。</span><span class="sxs-lookup"><span data-stu-id="07b57-124">Run the Performance Analysis of Logs tool (PAL).</span></span> <span data-ttu-id="07b57-125">如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署是相当稳定 （例如，新的贸易合作伙伴不定期，添加新代码没有部署），您可能会运行性能监视器和 PAL 一季度一次或甚至每隔六个月。</span><span class="sxs-lookup"><span data-stu-id="07b57-125">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is fairly constant (for example, new trading partners aren't added routinely, new code is not deployed), you might run Perfmon and PAL once a quarter or even every six months.</span></span> <span data-ttu-id="07b57-126">如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改更频繁地，你可能想要运行 Perfmon 和 PAL 每隔几个月要与基准进行比较。</span><span class="sxs-lookup"><span data-stu-id="07b57-126">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes more frequently, you may want to run Perfmon and PAL every couple of months to compare against a baseline.</span></span> <span data-ttu-id="07b57-127">有关 PAL 的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="07b57-127">For more information on PAL, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
- <span data-ttu-id="07b57-128">中的运行性能监视器每隔几个月，具体取决于更改数量的一次每个季度或甚至每隔六个月至发生在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="07b57-128">Run Perfmon every few months, to once a quarter or even every six months depending on the number of changes occur in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
- <span data-ttu-id="07b57-129">运行 BizTalk Server Best Practices Analyzer 时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改 （例如，添加新的应用程序） 或创建新主机。</span><span class="sxs-lookup"><span data-stu-id="07b57-129">Run BizTalk Server Best Practices Analyzer when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes (for example, the addition of new applications or creation of new hosts).</span></span> <span data-ttu-id="07b57-130">您可以下载 BizTalk Server Best Practices Analyzer 处[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317)。</span><span class="sxs-lookup"><span data-stu-id="07b57-130">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
- <span data-ttu-id="07b57-131">运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。</span><span class="sxs-lookup"><span data-stu-id="07b57-131">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="07b57-132">此工具分析 BizTalk MessageBox 和其他数据库，并生成 HTML 报表包含警告，如果与数据库相关的任何，和其他信息。</span><span class="sxs-lookup"><span data-stu-id="07b57-132">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span>  
  
  > [!TIP]  
  >  <span data-ttu-id="07b57-133">此外可以保存以供将来使用的报表。</span><span class="sxs-lookup"><span data-stu-id="07b57-133">You can also save the reports for later use.</span></span> <span data-ttu-id="07b57-134">BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。</span><span class="sxs-lookup"><span data-stu-id="07b57-134">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="07b57-135">使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="07b57-135">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="07b57-136">使用此程序风险自负。</span><span class="sxs-lookup"><span data-stu-id="07b57-136">Use of this program is entirely at your own risk.</span></span>  
  
- <span data-ttu-id="07b57-137">运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。</span><span class="sxs-lookup"><span data-stu-id="07b57-137">Run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="07b57-138">此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。</span><span class="sxs-lookup"><span data-stu-id="07b57-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="07b57-139">有关如何使用 BizTalk MsgBoxViewer 工具相集成的终结器工具的详细信息，请参阅[使用 BizTalk 终止符，以解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。</span><span class="sxs-lookup"><span data-stu-id="07b57-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="07b57-140">使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="07b57-140">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="07b57-141">使用此程序风险自负。</span><span class="sxs-lookup"><span data-stu-id="07b57-141">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="annual-monitoring-tasks"></a><span data-ttu-id="07b57-142">每年的监视任务</span><span class="sxs-lookup"><span data-stu-id="07b57-142">Annual Monitoring Tasks</span></span>  
  
- <span data-ttu-id="07b57-143">查看有效性的监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。</span><span class="sxs-lookup"><span data-stu-id="07b57-143">Review the effectiveness of the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
- <span data-ttu-id="07b57-144">创建计划以在监视中进行任何所需的更改。</span><span class="sxs-lookup"><span data-stu-id="07b57-144">Create a plan to make any needed changes in monitoring.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b57-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="07b57-145">See Also</span></span>  
 [<span data-ttu-id="07b57-146">例程维护清单</span><span class="sxs-lookup"><span data-stu-id="07b57-146">Routine Maintenance Checklists</span></span>](../technical-guides/routine-maintenance-checklists.md)