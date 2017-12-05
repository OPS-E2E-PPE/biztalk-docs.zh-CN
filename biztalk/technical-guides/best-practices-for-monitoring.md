---
title: "监视的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b3d4761c32123db53ea35daf91d0f13d9a2488
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="best-practices-for-monitoring"></a><span data-ttu-id="0a717-102">用于监视的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0a717-102">Best Practices for Monitoring</span></span>
<span data-ttu-id="0a717-103">本主题提供有关监视你的 Microsoft BizTalk Server 环境和应用程序的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="0a717-103">This topic provides best practices for monitoring your Microsoft BizTalk Server environment and applications.</span></span>  
  
 <span data-ttu-id="0a717-104">**创建和实现你的 BizTalk 应用程序和基础结构的监视计划**</span><span class="sxs-lookup"><span data-stu-id="0a717-104">**Create and then implement a monitoring plan for your BizTalk applications and infrastructure**</span></span>  
  
-   <span data-ttu-id="0a717-105">阅读本指南，以确保更完整的监视解决方案中监视的主题。</span><span class="sxs-lookup"><span data-stu-id="0a717-105">Read the monitoring topics in this guide to ensure a more complete monitoring solution.</span></span> <span data-ttu-id="0a717-106">要考虑的因素包括：</span><span class="sxs-lookup"><span data-stu-id="0a717-106">Factors to consider include the following:</span></span>  
  
    -   <span data-ttu-id="0a717-107">谁将执行每日、 每周、 每月，和为所需的监视任务？</span><span class="sxs-lookup"><span data-stu-id="0a717-107">Who will perform the daily, weekly, monthly, and as needed monitoring tasks?</span></span>  
  
    -   <span data-ttu-id="0a717-108">有人通知的事件、 挂起的消息或其他系统或应用程序故障？</span><span class="sxs-lookup"><span data-stu-id="0a717-108">Is someone notified of events, suspended messages, or other system or application failures?</span></span>  
  
    -   <span data-ttu-id="0a717-109">筛选或给定的较低优先级，则是"预期"异常？</span><span class="sxs-lookup"><span data-stu-id="0a717-109">Are "expected" exceptions filtered or given a lower priority?</span></span>  
  
    -   <span data-ttu-id="0a717-110">是否所有主机监视以确保它们继续运行的实例？</span><span class="sxs-lookup"><span data-stu-id="0a717-110">Are all host instances monitored to ensure they continue running?</span></span>  
  
    -   <span data-ttu-id="0a717-111">所有自定义服务、 自定义的事件日志和监视的自定义数据库？</span><span class="sxs-lookup"><span data-stu-id="0a717-111">Are all custom services, custom event logs, and custom databases monitored?</span></span>  
  
    -   <span data-ttu-id="0a717-112">是否在 SQL Server 计算机和 BizTalk Server SQL 代理作业监视？</span><span class="sxs-lookup"><span data-stu-id="0a717-112">Are the SQL Server computers and the BizTalk Server SQL agent jobs monitored?</span></span>  
  
 <span data-ttu-id="0a717-113">**如果可能，请安装监视应用程序，如[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]为了自动执行 BizTalk Server 应用程序和基础结构监视**</span><span class="sxs-lookup"><span data-stu-id="0a717-113">**If possible, install a monitoring application such as [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] in order to automate the monitoring of your BizTalk Server applications and infrastructure**</span></span>  
  
-   <span data-ttu-id="0a717-114">使用 Microsoft System Center Operations Manager 是自动监视，因为 BizTalk Server 管理包提供数百个内置的规则的 BizTalk Server 的首选的方法。</span><span class="sxs-lookup"><span data-stu-id="0a717-114">Using Microsoft System Center Operations Manager is the preferred approach for automated monitoring because the BizTalk Server management packs provide hundreds of built-in rules for BizTalk Server.</span></span>  
  
     <span data-ttu-id="0a717-115">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="0a717-115">For more information, see the following resources:</span></span>  
  
    -   <span data-ttu-id="0a717-116">[Microsoft BizTalk Server 适用于 System Center Operations Manager 2007 管理包](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)。</span><span class="sxs-lookup"><span data-stu-id="0a717-116">[Microsoft BizTalk Server Management Pack for System Center Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=190339) (http://go.microsoft.com/fwlink/?LinkID=190339).</span></span>  
  
    -   <span data-ttu-id="0a717-117">[如何导入 Operations Manager 2007 中的管理包](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)</span><span class="sxs-lookup"><span data-stu-id="0a717-117">[How to Import a Management Pack in Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) (http://go.microsoft.com/fwlink/?LinkID=98348)</span></span>  
  
    -   [<span data-ttu-id="0a717-118">如何为自定义监视标记 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="0a717-118">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
 <span data-ttu-id="0a717-119">**运行 BizTalk Server 最佳做法分析器**</span><span class="sxs-lookup"><span data-stu-id="0a717-119">**Run the BizTalk Server Best Practices Analyzer**</span></span>  
  
-   <span data-ttu-id="0a717-120">BizTalk Server 最佳做法分析器检查 BizTalk Server 部署，并生成与最佳做法标准相关的问题的列表。</span><span class="sxs-lookup"><span data-stu-id="0a717-120">The BizTalk Server Best Practices Analyzer examines a BizTalk Server deployment and generates a list of issues pertaining to best practices standards.</span></span> <span data-ttu-id="0a717-121">该工具执行配置级别验证从不同的信息源，例如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项收集数据。</span><span class="sxs-lookup"><span data-stu-id="0a717-121">The tool performs configuration-level verification by gathering data from different information sources, such as Windows Management Instrumentation (WMI) classes, SQL Server databases, and registry entries.</span></span> <span data-ttu-id="0a717-122">数据然后用于评估部署配置。</span><span class="sxs-lookup"><span data-stu-id="0a717-122">The data is then used to evaluate the deployment configuration.</span></span> <span data-ttu-id="0a717-123">该工具读取和仅限报告并不会修改任何系统设置，并不是自我调整工具。</span><span class="sxs-lookup"><span data-stu-id="0a717-123">The tool reads and reports only and does not modify any system settings, and is not a self-tuning tool.</span></span>  
  
     <span data-ttu-id="0a717-124">你可以下载 BizTalk Server 最佳做法分析器在[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。</span><span class="sxs-lookup"><span data-stu-id="0a717-124">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
 <span data-ttu-id="0a717-125">**运行日志的性能分析工具 (PAL)**</span><span class="sxs-lookup"><span data-stu-id="0a717-125">**Run the Performance Analysis of Logs tool (PAL)**</span></span>  
  
-   <span data-ttu-id="0a717-126">PAL 是可用作在免费下载[https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL)。</span><span class="sxs-lookup"><span data-stu-id="0a717-126">PAL is available as a free download at [https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL).</span></span> <span data-ttu-id="0a717-127">重要的安装信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="0a717-127">For important installation information, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
 <span data-ttu-id="0a717-128">**运行日志分析器**</span><span class="sxs-lookup"><span data-stu-id="0a717-128">**Run Log Parser**</span></span>  
  
-   <span data-ttu-id="0a717-129">Log Parser 是一个功能强大、 通用的工具，如事件日志、 注册表、 文件系统和活动 Windows® 操作系统提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及密钥的数据源的通用查询访问权限Directory®。</span><span class="sxs-lookup"><span data-stu-id="0a717-129">Log Parser is a powerful, versatile tool that provides universal query access to text-based data such as log files, XML files and CSV files, as well as key data sources on the Windows® operating system such as the Event Log, the Registry, the file system, and Active Directory®.</span></span> <span data-ttu-id="0a717-130">你可能想要使用此工具来查询占用大量的日志记录信息。</span><span class="sxs-lookup"><span data-stu-id="0a717-130">You may want to use this tool to query a significant amount of logging information.</span></span> <span data-ttu-id="0a717-131">你可以下载的 Log Parser 工具在[http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span><span class="sxs-lookup"><span data-stu-id="0a717-131">You can download the Log Parser tool at [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span></span>  
  
 <span data-ttu-id="0a717-132">**运行 BizTalk MsgBoxViewer 工具**</span><span class="sxs-lookup"><span data-stu-id="0a717-132">**Run the BizTalk MsgBoxViewer Tool**</span></span>  
  
 <span data-ttu-id="0a717-133">运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)可从[http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930)。</span><span class="sxs-lookup"><span data-stu-id="0a717-133">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) available from [http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="0a717-134">此工具可分析 BizTalk MessageBox 和其他数据库并生成 HTML 报告包含警告，如果与数据库相关的任何，和其他信息。</span><span class="sxs-lookup"><span data-stu-id="0a717-134">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span> <span data-ttu-id="0a717-135">你还可以保存以供将来使用的报表。</span><span class="sxs-lookup"><span data-stu-id="0a717-135">You can also save the reports for later use.</span></span> <span data-ttu-id="0a717-136">与 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。</span><span class="sxs-lookup"><span data-stu-id="0a717-136">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
 <span data-ttu-id="0a717-137">如果 BizTalk MsgBoxViewer 工具标识的任何问题，运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)在[http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931)。</span><span class="sxs-lookup"><span data-stu-id="0a717-137">If the BizTalk MsgBoxViewer tool identifies any issues, run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) available at [http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="0a717-138">此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。</span><span class="sxs-lookup"><span data-stu-id="0a717-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="0a717-139">有关如何使用 BizTalk MsgBoxViewer 工具相集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，若要解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。</span><span class="sxs-lookup"><span data-stu-id="0a717-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a717-140">使用这些工具不支持由 Microsoft 和 Microsoft 则没有有关这些程序的适用性的保证。</span><span class="sxs-lookup"><span data-stu-id="0a717-140">Use of these tools is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of these programs.</span></span> <span data-ttu-id="0a717-141">使用这些程序完全需要您自担风险。</span><span class="sxs-lookup"><span data-stu-id="0a717-141">Use of these programs is entirely at your own risk.</span></span>  
  
 <span data-ttu-id="0a717-142">**请监视优先级**</span><span class="sxs-lookup"><span data-stu-id="0a717-142">**Make monitoring a priority**</span></span>  
  
-   <span data-ttu-id="0a717-143">BizTalk Server 应用程序和基础结构的一致监视是必要的维护一个正常的环境。</span><span class="sxs-lookup"><span data-stu-id="0a717-143">Consistent monitoring of BizTalk Server applications and infrastructure is essential to maintaining a healthy environment.</span></span>  
  
-   <span data-ttu-id="0a717-144">定期评估并调整监视工具，随着时间的推移和根据你的 BizTalk Server 应用程序和基础结构变化。</span><span class="sxs-lookup"><span data-stu-id="0a717-144">Regularly evaluate and adjust your monitoring tools over time and as your BizTalk Server applications and infrastructure change.</span></span>