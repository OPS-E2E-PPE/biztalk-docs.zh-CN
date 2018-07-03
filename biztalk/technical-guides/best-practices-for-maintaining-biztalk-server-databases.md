---
title: 维护 BizTalk Server 数据库的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93333f41-ee83-4b64-b381-66584a7d5551
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b1d8f03201b04a3be1f7908eaf7e763a4ade226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981246"
---
# <a name="best-practices-for-maintaining-biztalk-server-databases"></a><span data-ttu-id="59153-102">维护 BizTalk Server 数据库的最佳做法</span><span class="sxs-lookup"><span data-stu-id="59153-102">Best Practices for Maintaining BizTalk Server Databases</span></span>
<span data-ttu-id="59153-103">本主题列出了维护的一些最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="59153-103">This topic lists some best practices for maintaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
- <span data-ttu-id="59153-104">请确保 SQL Server 代理正在运行的 SQL Server 上。</span><span class="sxs-lookup"><span data-stu-id="59153-104">Make sure the SQL Server Agent is running on the SQL Server.</span></span> <span data-ttu-id="59153-105">在 SQL Server 代理停止后，不能运行负责数据库维护的内置 BizTalk SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="59153-105">When the SQL Server Agent is stopped, the built-in BizTalk SQL Server Agent jobs that are responsible for database maintenance cannot run.</span></span> <span data-ttu-id="59153-106">此行为会导致数据库增长，这种增长可能导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="59153-106">This behavior causes database growth, and this growth may cause performance issues.</span></span> <span data-ttu-id="59153-107">有关监视 SQL Server 代理作业的信息，请参阅[监视 SQL Server 代理作业](../technical-guides/monitoring-sql-server-agent-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="59153-107">For information about monitoring SQL Server Agent Jobs see [Monitoring SQL Server Agent Jobs](../technical-guides/monitoring-sql-server-agent-jobs.md).</span></span>  
  
- <span data-ttu-id="59153-108">请确保 SQL Server LDF 和 MDF 文件是不同的驱动器上。</span><span class="sxs-lookup"><span data-stu-id="59153-108">Make sure the SQL Server LDF and MDF files are on separate drives.</span></span> <span data-ttu-id="59153-109">具有的 LDF 和 MDF 文件 BizTalkMsgBoxDb 和 BizTalkDTADb 数据库所在的驱动器上可能会导致磁盘争用。</span><span class="sxs-lookup"><span data-stu-id="59153-109">Having the LDF and MDF files for the BizTalkMsgBoxDb and BizTalkDTADb databases on the same drive may result in disk contention.</span></span>  
  
- <span data-ttu-id="59153-110">不要启用消息正文跟踪，不需要的功能。</span><span class="sxs-lookup"><span data-stu-id="59153-110">Do not enable message body tracking, if not required.</span></span> <span data-ttu-id="59153-111">通常情况下，你可能想要启用消息正文跟踪开发和对解决方案进行故障排除时。</span><span class="sxs-lookup"><span data-stu-id="59153-111">Frequently, you may want to enable message body tracking while you develop and troubleshoot a solution.</span></span> <span data-ttu-id="59153-112">如果是这样，请确保禁用消息正文跟踪完成后。</span><span class="sxs-lookup"><span data-stu-id="59153-112">If so, make sure you disable message body tracking when you are done.</span></span> <span data-ttu-id="59153-113">如果保留消息正文跟踪的启用，BizTalk Server 数据库增长。</span><span class="sxs-lookup"><span data-stu-id="59153-113">If you keep message body tracking enabled, the BizTalk Server databases grow.</span></span> <span data-ttu-id="59153-114">如果你有业务需求要求您启用消息正文跟踪，确认**TrackedMessages_Copy_BizTalkMsgBoxDb**并**DTA 清除和存档**运行 SQL Server 代理作业已成功。</span><span class="sxs-lookup"><span data-stu-id="59153-114">If you have a business need that requires you to enable message body tracking, confirm that the **TrackedMessages_Copy_BizTalkMsgBoxDb** and **DTA Purge and Archive** SQL Server Agent jobs are running successfully.</span></span>  
  
- <span data-ttu-id="59153-115">通常情况下，较小的事务日志会导致更好的性能。</span><span class="sxs-lookup"><span data-stu-id="59153-115">Typically, smaller transaction logs cause better performance.</span></span> <span data-ttu-id="59153-116">若要减小事务日志，配置**备份 BizTalk Server**更频繁地运行 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="59153-116">To keep the transaction logs smaller, configure the **Backup BizTalk Server** SQL Server Agent job to run more frequently.</span></span> <span data-ttu-id="59153-117">有关详细信息，请参阅[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=153594)(http://go.microsoft.com/fwlink/?LinkId=153594)。</span><span class="sxs-lookup"><span data-stu-id="59153-117">For more information, see the [BizTalk Server Database Optimization white paper](http://go.microsoft.com/fwlink/?LinkId=153594) (http://go.microsoft.com/fwlink/?LinkId=153594).</span></span>  
  
- <span data-ttu-id="59153-118">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最佳做法分析器 (BPA) 来评估现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="59153-118">Use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Best Practices Analyzer (BPA) to evaluate an existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span> <span data-ttu-id="59153-119">BPA 执行许多与数据库相关的检查。</span><span class="sxs-lookup"><span data-stu-id="59153-119">The BPA performs numerous database-related checks.</span></span> <span data-ttu-id="59153-120">您可以下载中的 BizTalk Server Best Practices Analyzer 工具[BizTalk Server Best Practices Analyzer 工具](http://go.microsoft.com/fwlink/?LinkId=83317)(<http://go.microsoft.com/fwlink/?LinkId=83317>)。</span><span class="sxs-lookup"><span data-stu-id="59153-120">You can download the BizTalk Server Best Practices Analyzer tool from [BizTalk Server Best Practices Analyzer tool](http://go.microsoft.com/fwlink/?LinkId=83317) (<http://go.microsoft.com/fwlink/?LinkId=83317>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59153-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="59153-121">See Also</span></span>  
 <span data-ttu-id="59153-122">[清单： 维护和故障排除 BizTalk Server 数据库](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="59153-122">[Checklist: Maintaining and Troubleshooting BizTalk Server Databases](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="59153-123">大量增长的 BizTalk Server 数据库表</span><span class="sxs-lookup"><span data-stu-id="59153-123">Large-growing BizTalk Server Database Tables</span></span>](../technical-guides/large-growing-biztalk-server-database-tables.md)