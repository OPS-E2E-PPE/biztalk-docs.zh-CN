---
title: 监视的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8951b603fda6204ee8398d2dee9922a0f70a059
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399324"
---
# <a name="best-practices-for-monitoring"></a><span data-ttu-id="a5ce0-102">监视的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a5ce0-102">Best Practices for Monitoring</span></span>
<span data-ttu-id="a5ce0-103">本主题提供用于监视你的 Microsoft BizTalk Server 环境和应用程序的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-103">This topic provides best practices for monitoring your Microsoft BizTalk Server environment and applications.</span></span>  
  
 <span data-ttu-id="a5ce0-104">**创建，然后实现您的 BizTalk 应用程序和基础结构的监视计划**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-104">**Create and then implement a monitoring plan for your BizTalk applications and infrastructure**</span></span>  
  
- <span data-ttu-id="a5ce0-105">阅读本指南，以确保更完整的监视解决方案中的监视主题。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-105">Read the monitoring topics in this guide to ensure a more complete monitoring solution.</span></span> <span data-ttu-id="a5ce0-106">要考虑的因素包括：</span><span class="sxs-lookup"><span data-stu-id="a5ce0-106">Factors to consider include the following:</span></span>  
  
  -   <span data-ttu-id="a5ce0-107">谁将执行每日、 每周、 每月和作为所需的监视任务？</span><span class="sxs-lookup"><span data-stu-id="a5ce0-107">Who will perform the daily, weekly, monthly, and as needed monitoring tasks?</span></span>  
  
  -   <span data-ttu-id="a5ce0-108">有人通知的事件、 挂起的消息或其他系统或应用程序故障？</span><span class="sxs-lookup"><span data-stu-id="a5ce0-108">Is someone notified of events, suspended messages, or other system or application failures?</span></span>  
  
  -   <span data-ttu-id="a5ce0-109">已筛选或给定的较低优先级是否"预期"的异常？</span><span class="sxs-lookup"><span data-stu-id="a5ce0-109">Are "expected" exceptions filtered or given a lower priority?</span></span>  
  
  -   <span data-ttu-id="a5ce0-110">是否所有的主机实例监视，以确保它们继续运行？</span><span class="sxs-lookup"><span data-stu-id="a5ce0-110">Are all host instances monitored to ensure they continue running?</span></span>  
  
  -   <span data-ttu-id="a5ce0-111">所有自定义服务、 自定义的事件日志和监视的自定义数据库？</span><span class="sxs-lookup"><span data-stu-id="a5ce0-111">Are all custom services, custom event logs, and custom databases monitored?</span></span>  
  
  -   <span data-ttu-id="a5ce0-112">是 SQL Server 计算机和 BizTalk Server SQL 代理作业监视？</span><span class="sxs-lookup"><span data-stu-id="a5ce0-112">Are the SQL Server computers and the BizTalk Server SQL agent jobs monitored?</span></span>  
  
  <span data-ttu-id="a5ce0-113">**如果可能，请安装监视应用程序，如[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]才能自动执行 BizTalk Server 应用程序和基础结构监视**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-113">**If possible, install a monitoring application such as [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] in order to automate the monitoring of your BizTalk Server applications and infrastructure**</span></span>  
  
- <span data-ttu-id="a5ce0-114">使用 Microsoft System Center Operations Manager 是自动监视，因为 BizTalk Server 管理包为 BizTalk Server 提供数百个内置的规则的首选的方法。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-114">Using Microsoft System Center Operations Manager is the preferred approach for automated monitoring because the BizTalk Server management packs provide hundreds of built-in rules for BizTalk Server.</span></span>  
  
   <span data-ttu-id="a5ce0-115">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="a5ce0-115">For more information, see the following resources:</span></span>  
  
  -   <span data-ttu-id="a5ce0-116">[System Center Operations manager 2007 的 Microsoft BizTalk Server 管理包](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-116">[Microsoft BizTalk Server Management Pack for System Center Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=190339) (http://go.microsoft.com/fwlink/?LinkID=190339).</span></span>  
  
  -   <span data-ttu-id="a5ce0-117">[如何导入管理包在 Operations Manager 2007 中的](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)</span><span class="sxs-lookup"><span data-stu-id="a5ce0-117">[How to Import a Management Pack in Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) (http://go.microsoft.com/fwlink/?LinkID=98348)</span></span>  
  
  -   [<span data-ttu-id="a5ce0-118">如何为自定义监视标记 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a5ce0-118">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
  <span data-ttu-id="a5ce0-119">**运行 BizTalk Server 最佳实践分析工具**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-119">**Run the BizTalk Server Best Practices Analyzer**</span></span>  
  
- <span data-ttu-id="a5ce0-120">BizTalk Server Best Practices Analyzer 会检查 BizTalk Server 部署，并生成与最佳做法标准相关的问题的列表。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-120">The BizTalk Server Best Practices Analyzer examines a BizTalk Server deployment and generates a list of issues pertaining to best practices standards.</span></span> <span data-ttu-id="a5ce0-121">该工具通过不同的信息源，如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项中的数据收集执行配置级别验证。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-121">The tool performs configuration-level verification by gathering data from different information sources, such as Windows Management Instrumentation (WMI) classes, SQL Server databases, and registry entries.</span></span> <span data-ttu-id="a5ce0-122">数据然后用于评估部署配置。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-122">The data is then used to evaluate the deployment configuration.</span></span> <span data-ttu-id="a5ce0-123">该工具读取和仅报告并不会修改任何系统设置，并不是一个自我调整工具。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-123">The tool reads and reports only and does not modify any system settings, and is not a self-tuning tool.</span></span>  
  
   <span data-ttu-id="a5ce0-124">您可以下载 BizTalk Server Best Practices Analyzer 处[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-124">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
  <span data-ttu-id="a5ce0-125">**运行日志的性能分析工具 (PAL)**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-125">**Run the Performance Analysis of Logs tool (PAL)**</span></span>  
  
- <span data-ttu-id="a5ce0-126">PAL 是可作为免费下载[ https://github.com/clinthuffman/PAL ](https://github.com/clinthuffman/PAL)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-126">PAL is available as a free download at [https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL).</span></span> <span data-ttu-id="a5ce0-127">重要的安装信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-127">For important installation information, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
  <span data-ttu-id="a5ce0-128">**运行日志分析程序**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-128">**Run Log Parser**</span></span>  
  
- <span data-ttu-id="a5ce0-129">Log Parser 是 Windows® 操作系统 （如事件日志、 注册表、 文件系统和活动提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及关键的数据源的通用查询访问的功能全面的强大工具Directory®。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-129">Log Parser is a powerful, versatile tool that provides universal query access to text-based data such as log files, XML files and CSV files, as well as key data sources on the Windows® operating system such as the Event Log, the Registry, the file system, and Active Directory®.</span></span> <span data-ttu-id="a5ce0-130">您可能想要使用此工具来查询大量的日志记录信息。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-130">You may want to use this tool to query a significant amount of logging information.</span></span> <span data-ttu-id="a5ce0-131">您可以下载在 Log Parser 工具 [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span><span class="sxs-lookup"><span data-stu-id="a5ce0-131">You can download the Log Parser tool at [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span></span>  
  
  <span data-ttu-id="a5ce0-132">**运行 BizTalk MsgBoxViewer 工具**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-132">**Run the BizTalk MsgBoxViewer Tool**</span></span>  
  
  <span data-ttu-id="a5ce0-133">运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)从可用[ http://go.microsoft.com/fwlink/?LinkId=151930 ](http://go.microsoft.com/fwlink/?LinkId=151930)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-133">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) available from [http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="a5ce0-134">此工具分析 BizTalk MessageBox 和其他数据库，并生成 HTML 报表包含警告，如果与数据库相关的任何，和其他信息。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-134">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span> <span data-ttu-id="a5ce0-135">此外可以保存以供将来使用的报表。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-135">You can also save the reports for later use.</span></span> <span data-ttu-id="a5ce0-136">BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-136">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
  <span data-ttu-id="a5ce0-137">如果 BizTalk MsgBoxViewer 工具确定任何问题，运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)网址[ http://go.microsoft.com/fwlink/?LinkId=151931 ](http://go.microsoft.com/fwlink/?LinkId=151931)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-137">If the BizTalk MsgBoxViewer tool identifies any issues, run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) available at [http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="a5ce0-138">此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="a5ce0-139">有关如何使用 BizTalk MsgBoxViewer 工具相集成的终结器工具的详细信息，请参阅[使用 BizTalk 终止符，以解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5ce0-140">使用这些工具不受 Microsoft，因此 Microsoft 不保证这些程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-140">Use of these tools is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of these programs.</span></span> <span data-ttu-id="a5ce0-141">使用这些程序是完全由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-141">Use of these programs is entirely at your own risk.</span></span>  
  
 <span data-ttu-id="a5ce0-142">**请监视优先级**</span><span class="sxs-lookup"><span data-stu-id="a5ce0-142">**Make monitoring a priority**</span></span>  
  
-   <span data-ttu-id="a5ce0-143">BizTalk Server 应用程序和基础结构的持续不断的监视是必要的维护正常运行的环境。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-143">Consistent monitoring of BizTalk Server applications and infrastructure is essential to maintaining a healthy environment.</span></span>  
  
-   <span data-ttu-id="a5ce0-144">定期评估并调整监视工具，随着时间的推移和作为 BizTalk Server 应用程序和基础结构更改。</span><span class="sxs-lookup"><span data-stu-id="a5ce0-144">Regularly evaluate and adjust your monitoring tools over time and as your BizTalk Server applications and infrastructure change.</span></span>