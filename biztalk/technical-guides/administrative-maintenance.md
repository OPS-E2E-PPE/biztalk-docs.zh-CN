---
title: 管理维护 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67cdf9d7-5448-40c5-8c5f-eae0e281d22c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd107a9b596919c92e4cb8ac5a0538e8f4ded3ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007966"
---
# <a name="administrative-maintenance"></a><span data-ttu-id="042c7-102">管理维护</span><span class="sxs-lookup"><span data-stu-id="042c7-102">Administrative Maintenance</span></span>
<span data-ttu-id="042c7-103">本部分提供有关如何解决管理问题的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="042c7-103">This section provides information about how you can resolve administration issues with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="042c7-104">这些问题可能会发现通过在中执行的日常维护检查[例程维护清单](../technical-guides/routine-maintenance-checklists.md)部分。</span><span class="sxs-lookup"><span data-stu-id="042c7-104">These issues may be discovered by the routine maintenance checks that are performed in the [Routine Maintenance Checklists](../technical-guides/routine-maintenance-checklists.md) section.</span></span>  

 <span data-ttu-id="042c7-105">除了此部分中的主题，本文档中的其他主题解决管理问题。</span><span class="sxs-lookup"><span data-stu-id="042c7-105">In addition to the topics in this section, other topics in this document address administration issues.</span></span> <span data-ttu-id="042c7-106">以下相关各节列出了这些主题。</span><span class="sxs-lookup"><span data-stu-id="042c7-106">These topics are listed in Related Sections below.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="042c7-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="042c7-107">In This Section</span></span>  

-   [<span data-ttu-id="042c7-108">管理维护的最佳做法</span><span class="sxs-lookup"><span data-stu-id="042c7-108">Best Practices for Administrative Maintenance</span></span>](../technical-guides/best-practices-for-administrative-maintenance.md)  

-   [<span data-ttu-id="042c7-109">如何启动 SQL Server 代理</span><span class="sxs-lookup"><span data-stu-id="042c7-109">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)  

-   [<span data-ttu-id="042c7-110">如何安排备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="042c7-110">How to Schedule a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-schedule-a-backup-biztalk-server-job.md)  

-   [<span data-ttu-id="042c7-111">如何配置备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="042c7-111">How to Configure a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)  

## <a name="related-sections"></a><span data-ttu-id="042c7-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="042c7-112">Related Sections</span></span>  

- <span data-ttu-id="042c7-113">有关确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理服务上运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，并确保所有 BizTalk 都相关 SQL Server 作业在正常工作，请参阅[监视 SQL Server 代理作业](../technical-guides/monitoring-sql-server-agent-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="042c7-113">For information about ensuring that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent service is running on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and ensuring that all BizTalk related SQL Server jobs are working properly, see [Monitoring SQL Server Agent Jobs](../technical-guides/monitoring-sql-server-agent-jobs.md).</span></span>  

- <span data-ttu-id="042c7-114">删除 BizTalk 应用程序或使用 BTSTask 命令行工具的项目的信息，请参阅"RemoveApp 命令"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154687 ](http://go.microsoft.com/fwlink/?LinkID=154687)。</span><span class="sxs-lookup"><span data-stu-id="042c7-114">For information about removing a BizTalk application or artifact using the BTSTask command-line tool, see "RemoveApp Command" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687).</span></span>  

- <span data-ttu-id="042c7-115">从使用 BizTalk Server 管理控制台或 BTSTask 命令行工具的应用程序中删除项目的信息，请参阅"如何删除项目从应用程序"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span><span class="sxs-lookup"><span data-stu-id="042c7-115">For information about removing an artifact from an application using either the BizTalk Server Administration console or the BTSTask command-line tool, see "How to Remove an Artifact from an Application" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span></span>  

- <span data-ttu-id="042c7-116">有关验证 BizTalk 管理控制台中的配置信息，请参阅"使用 BizTalk Server 管理控制台"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154689 ](http://go.microsoft.com/fwlink/?LinkID=154689)。</span><span class="sxs-lookup"><span data-stu-id="042c7-116">For information about verifying the configuration in the BizTalk Administration Console, see "Using the BizTalk Server Administration Console" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689).</span></span>  

- <span data-ttu-id="042c7-117">有关验证的 BTSNTSvc.exe.config 文件的信息，请参见"BTSNTSvc.exe.config 文件"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154690 ](http://go.microsoft.com/fwlink/?LinkID=154690)。</span><span class="sxs-lookup"><span data-stu-id="042c7-117">For information about verifying the BTSNTSvc.exe.config file, see "BTSNTSvc.exe.config File" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690).</span></span>  

- <span data-ttu-id="042c7-118">有关验证 BizTalk 信息相关的注册表项，请参阅"Windows 中的注册表信息对于高级用户"在 Microsoft 帮助和支持网站[ http://go.microsoft.com/fwlink/?LinkId=155583 ](http://go.microsoft.com/fwlink/?LinkId=155583)。</span><span class="sxs-lookup"><span data-stu-id="042c7-118">For information about verifying the BizTalk related registry keys, see "Windows registry information for advanced users" in the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583).</span></span>  

- <span data-ttu-id="042c7-119">有关运行 BizTalk 最佳实践分析工具的信息，请参阅"BizTalk Server 最佳做法分析器"在 Microsoft 下载中心[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317)。</span><span class="sxs-lookup"><span data-stu-id="042c7-119">For information about running the BizTalk Best Practices Analyzer, see "BizTalk Server Best Practices Analyzer" in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  

- <span data-ttu-id="042c7-120">有关维护 BAM 数据库的信息，请参阅"管理 BAM 数据库"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=155584 ](http://go.microsoft.com/fwlink/?LinkId=155584)。</span><span class="sxs-lookup"><span data-stu-id="042c7-120">For information about maintaining BAM databases, see "Managing BAM Databases" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584).</span></span>  

- <span data-ttu-id="042c7-121">有关确保安装最新 service pack 和修补程序的信息，请参阅 Microsoft Update 网站上的[ http://go.microsoft.com/fwlink/?LinkID=47813 ](http://go.microsoft.com/fwlink/?LinkID=47813)。</span><span class="sxs-lookup"><span data-stu-id="042c7-121">For information about ensuring that the latest service packs and hotfixes are installed, see the Microsoft Update Web site at [http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813).</span></span>
