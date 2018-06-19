---
title: 监视任务的例程 |Microsoft 文档
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
ms.openlocfilehash: d91a49393e2b43c9cf39add35e06c5bd864782e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301901"
---
# <a name="routine-monitoring-tasks"></a><span data-ttu-id="629cf-102">例程的监视任务</span><span class="sxs-lookup"><span data-stu-id="629cf-102">Routine Monitoring Tasks</span></span>
<span data-ttu-id="629cf-103">按定期计划定期执行以下监视任务将帮助您保留您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构做好运行准备。</span><span class="sxs-lookup"><span data-stu-id="629cf-103">Performing the following monitoring tasks on a regularly scheduled basis will assist you in keeping your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure operationally ready.</span></span>  
  
## <a name="daily-monitoring-tasks"></a><span data-ttu-id="629cf-104">每日的监视任务</span><span class="sxs-lookup"><span data-stu-id="629cf-104">Daily Monitoring Tasks</span></span>  
  
-   <span data-ttu-id="629cf-105">检查所有打开的警报。</span><span class="sxs-lookup"><span data-stu-id="629cf-105">Review all open alerts.</span></span>  
  
-   <span data-ttu-id="629cf-106">使用**组中心数据库**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来调查业务流程、 端口和消息失败。</span><span class="sxs-lookup"><span data-stu-id="629cf-106">Use the **Group Hub** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="629cf-107">**组中心数据库**页提供了当前的实时状态的系统，访问 MessageBox 数据库中的数据访问。</span><span class="sxs-lookup"><span data-stu-id="629cf-107">The **Group Hub** page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="629cf-108">您可以查看所有服务实例（例如业务流程、端口和消息传送）及其关联的消息。</span><span class="sxs-lookup"><span data-stu-id="629cf-108">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="629cf-109">使用**组中心数据库**页你可以执行以下活动：</span><span class="sxs-lookup"><span data-stu-id="629cf-109">Using the **Group Hub** page you can perform the following activities:</span></span>  
  
    -   <span data-ttu-id="629cf-110">请参阅当前正在运行的服务实例，如业务流程和消息，以及其关联的消息。</span><span class="sxs-lookup"><span data-stu-id="629cf-110">See currently running service instances, such as orchestrations and messaging, and their associated messages.</span></span>  
  
    -   <span data-ttu-id="629cf-111">在 MessageBox 数据库中进行搜索，以显示系统的当前数据以及实时状态的视图。</span><span class="sxs-lookup"><span data-stu-id="629cf-111">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
    -   <span data-ttu-id="629cf-112">挂起、终止和恢复服务实例。</span><span class="sxs-lookup"><span data-stu-id="629cf-112">Suspend, terminate, and resume service instances.</span></span>  
  
     <span data-ttu-id="629cf-113">有关使用**组中心数据库**页上，请参阅[http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281)。</span><span class="sxs-lookup"><span data-stu-id="629cf-113">For more information about using the **Group Hub** page, see [http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281).</span></span>  
  
-   <span data-ttu-id="629cf-114">检查警告（可选）。</span><span class="sxs-lookup"><span data-stu-id="629cf-114">Review warnings (optional).</span></span>  
  
 <span data-ttu-id="629cf-115">有关详细信息，请参阅[清单： 执行每日一次维护检查](../technical-guides/checklist-performing-daily-maintenance-checks.md)。</span><span class="sxs-lookup"><span data-stu-id="629cf-115">For more information, see [Checklist: Performing Daily Maintenance Checks](../technical-guides/checklist-performing-daily-maintenance-checks.md).</span></span>  
  
## <a name="weekly-monitoring-tasks"></a><span data-ttu-id="629cf-116">每周的监视任务</span><span class="sxs-lookup"><span data-stu-id="629cf-116">Weekly Monitoring Tasks</span></span>  
  
-   <span data-ttu-id="629cf-117">查看至少一次每周的事件日志。</span><span class="sxs-lookup"><span data-stu-id="629cf-117">Review the event logs at least once per week.</span></span> <span data-ttu-id="629cf-118">此任务的原因是为防止出现问题，如 DBNetLib 转未检测到的错误。</span><span class="sxs-lookup"><span data-stu-id="629cf-118">The reason for this task is to prevent issues, such as DBNetLib errors going undetected.</span></span> <span data-ttu-id="629cf-119">除非你拥有的延迟时间非常低系统，服务中断可能会被忽略。</span><span class="sxs-lookup"><span data-stu-id="629cf-119">Service interruption might go unnoticed unless you have a very low latency system.</span></span> <span data-ttu-id="629cf-120">但是，某些这些错误可能表示出现更大问题 （例如，过多主机或的消息框，在 SQL 中，等的性能问题数的 BizTalk Server 服务器）。</span><span class="sxs-lookup"><span data-stu-id="629cf-120">However, some of these errors can indicate a bigger issue (for example, too many hosts or BizTalk Server servers for the number of message boxes, performance issues on the SQL box, etc).</span></span>  
  
 <span data-ttu-id="629cf-121">有关详细信息，请参阅[清单： 执行每周维护检查](../technical-guides/checklist-performing-weekly-maintenance-checks.md)。</span><span class="sxs-lookup"><span data-stu-id="629cf-121">For more information, see [Checklist: Performing Weekly Maintenance Checks](../technical-guides/checklist-performing-weekly-maintenance-checks.md).</span></span>  
  
## <a name="as-needed-tasks"></a><span data-ttu-id="629cf-122">根据需要任务</span><span class="sxs-lookup"><span data-stu-id="629cf-122">As-Needed Tasks</span></span>  
  
-   <span data-ttu-id="629cf-123">修改规则以自定义的监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。</span><span class="sxs-lookup"><span data-stu-id="629cf-123">Modify the rules to customize the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
-   <span data-ttu-id="629cf-124">运行日志的性能分析工具 (PAL)。</span><span class="sxs-lookup"><span data-stu-id="629cf-124">Run the Performance Analysis of Logs tool (PAL).</span></span> <span data-ttu-id="629cf-125">如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署是相当常量 （例如，新的贸易合作伙伴并未例行，添加新代码不部署），你可能会运行 Perfmon 和 PAL 一季度一次或甚至每六个月。</span><span class="sxs-lookup"><span data-stu-id="629cf-125">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is fairly constant (for example, new trading partners aren't added routinely, new code is not deployed), you might run Perfmon and PAL once a quarter or even every six months.</span></span> <span data-ttu-id="629cf-126">如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改更频繁地，你可能想要运行 Perfmon 和 PAL 每隔几个月内要针对基线进行比较。</span><span class="sxs-lookup"><span data-stu-id="629cf-126">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes more frequently, you may want to run Perfmon and PAL every couple of months to compare against a baseline.</span></span> <span data-ttu-id="629cf-127">PAL 的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="629cf-127">For more information on PAL, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
-   <span data-ttu-id="629cf-128">运行的 Perfmon 中发生的每个几个月，具体取决于更改数的一季度一次或甚至每六个月至你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="629cf-128">Run Perfmon every few months, to once a quarter or even every six months depending on the number of changes occur in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
-   <span data-ttu-id="629cf-129">运行 BizTalk Server 最佳做法分析器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改 （例如，添加新的应用程序） 或创建新的主机。</span><span class="sxs-lookup"><span data-stu-id="629cf-129">Run BizTalk Server Best Practices Analyzer when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes (for example, the addition of new applications or creation of new hosts).</span></span> <span data-ttu-id="629cf-130">你可以下载 BizTalk Server 最佳做法分析器在[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)。</span><span class="sxs-lookup"><span data-stu-id="629cf-130">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
-   <span data-ttu-id="629cf-131">运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。</span><span class="sxs-lookup"><span data-stu-id="629cf-131">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="629cf-132">此工具可分析 BizTalk MessageBox 和其他数据库并生成 HTML 报告包含警告，如果与数据库相关的任何，和其他信息。</span><span class="sxs-lookup"><span data-stu-id="629cf-132">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="629cf-133">你还可以保存以供将来使用的报表。</span><span class="sxs-lookup"><span data-stu-id="629cf-133">You can also save the reports for later use.</span></span> <span data-ttu-id="629cf-134">与 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。</span><span class="sxs-lookup"><span data-stu-id="629cf-134">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="629cf-135">使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。</span><span class="sxs-lookup"><span data-stu-id="629cf-135">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="629cf-136">使用此程序风险自负。</span><span class="sxs-lookup"><span data-stu-id="629cf-136">Use of this program is entirely at your own risk.</span></span>  
  
-   <span data-ttu-id="629cf-137">运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。</span><span class="sxs-lookup"><span data-stu-id="629cf-137">Run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="629cf-138">此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。</span><span class="sxs-lookup"><span data-stu-id="629cf-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="629cf-139">有关如何使用 BizTalk MsgBoxViewer 工具相集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，若要解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。</span><span class="sxs-lookup"><span data-stu-id="629cf-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="629cf-140">使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。</span><span class="sxs-lookup"><span data-stu-id="629cf-140">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="629cf-141">使用此程序风险自负。</span><span class="sxs-lookup"><span data-stu-id="629cf-141">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="annual-monitoring-tasks"></a><span data-ttu-id="629cf-142">每年的监视任务</span><span class="sxs-lookup"><span data-stu-id="629cf-142">Annual Monitoring Tasks</span></span>  
  
-   <span data-ttu-id="629cf-143">查看监视的有效性你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。</span><span class="sxs-lookup"><span data-stu-id="629cf-143">Review the effectiveness of the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
-   <span data-ttu-id="629cf-144">创建计划在监视中进行任何所需的更改。</span><span class="sxs-lookup"><span data-stu-id="629cf-144">Create a plan to make any needed changes in monitoring.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629cf-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="629cf-145">See Also</span></span>  
 [<span data-ttu-id="629cf-146">日常维护清单</span><span class="sxs-lookup"><span data-stu-id="629cf-146">Routine Maintenance Checklists</span></span>](../technical-guides/routine-maintenance-checklists.md)