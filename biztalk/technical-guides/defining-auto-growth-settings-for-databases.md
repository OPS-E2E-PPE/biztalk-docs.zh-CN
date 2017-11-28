---
title: "定义数据库的自动增长设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d702898cdaab8f9993fdc9b901e34f51ba6941c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-auto-growth-settings-for-databases"></a><span data-ttu-id="6344c-102">定义数据库的自动增长设置</span><span class="sxs-lookup"><span data-stu-id="6344c-102">Defining Auto-Growth Settings for Databases</span></span>
<span data-ttu-id="6344c-103">你应设置为固定数量的兆字节而不是一个百分比，尤其是对于 MessageBox 和 BizTalk 跟踪数据库的数据库自动增长。</span><span class="sxs-lookup"><span data-stu-id="6344c-103">You should set database auto-growth to a fixed number of megabytes instead of to a percentage, especially for the MessageBox and BizTalk Tracking databases.</span></span> <span data-ttu-id="6344c-104">根据你的 BizTalk 应用程序和吞吐量，MessageBox 和跟踪数据库可能会非常大。</span><span class="sxs-lookup"><span data-stu-id="6344c-104">Depending on your BizTalk application and throughput, the MessageBox and Tracking databases can get quite large.</span></span> <span data-ttu-id="6344c-105">如果将自动增长设置为百分比，然后自动增长可能是非常高。</span><span class="sxs-lookup"><span data-stu-id="6344c-105">If you set auto-growth to a percentage, then the auto-growth can be substantial as well.</span></span>  
  
## <a name="how-instant-file-initialization-works"></a><span data-ttu-id="6344c-106">如何即时文件初始化的工作原理</span><span class="sxs-lookup"><span data-stu-id="6344c-106">How Instant File Initialization Works</span></span>  
 <span data-ttu-id="6344c-107">当 SQL Server 会增加文件的大小时，它必须首先初始化的新空间，然后才能使用。</span><span class="sxs-lookup"><span data-stu-id="6344c-107">When SQL Server increases the size of a file, it must first initialize the new space before it can be used.</span></span> <span data-ttu-id="6344c-108">这是涉及使用空页填充新的空间的阻止操作。</span><span class="sxs-lookup"><span data-stu-id="6344c-108">This is a blocking operation that involves filling the new space with empty pages.</span></span> [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]<span data-ttu-id="6344c-109">或更高版本运行 Windows Server 2003 或更高版本支持"即时文件初始化。"</span><span class="sxs-lookup"><span data-stu-id="6344c-109"> or later running on Windows Server 2003 or later supports “instant file initialization.”</span></span> <span data-ttu-id="6344c-110">这可以极大地降低文件增长操作的性能影响。</span><span class="sxs-lookup"><span data-stu-id="6344c-110">This can greatly reduce the performance impact of a file growth operation.</span></span> <span data-ttu-id="6344c-111">有关详细信息，请参阅["数据库文件初始化"](http://go.microsoft.com/fwlink/?LinkId=101579) (http://go.microsoft.com/fwlink/?LinkId=101579) SQL Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="6344c-111">For more information, see ["Database File Initialization"](http://go.microsoft.com/fwlink/?LinkId=101579) (http://go.microsoft.com/fwlink/?LinkId=101579) in the SQL Server documentation.</span></span> <span data-ttu-id="6344c-112">本主题概述了必须谨慎以启用即时文件初始化的步骤。</span><span class="sxs-lookup"><span data-stu-id="6344c-112">This topic outlines the steps that must be taken to enable instant file initialization.</span></span>  
  
## <a name="enabling-instant-file-initialization"></a><span data-ttu-id="6344c-113">启用即时文件初始化</span><span class="sxs-lookup"><span data-stu-id="6344c-113">Enabling Instant File Initialization</span></span>  
 <span data-ttu-id="6344c-114">有关步骤启用即时文件初始化，请参阅["数据库文件初始化"](http://go.microsoft.com/fwlink/?LinkId=101579) (http://go.microsoft.com/fwlink/?LinkId=101579) SQL Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="6344c-114">For steps on enabling instant file initialization, see ["Database File Initialization"](http://go.microsoft.com/fwlink/?LinkId=101579) (http://go.microsoft.com/fwlink/?LinkId=101579) in the SQL Server documentation.</span></span> <span data-ttu-id="6344c-115">用于创建文件组和移动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库表、 索引和日志文件入相应的文件组中，按照"附录 B-建议 BizTalk Server 数据库配置"中的建议["BizTalk服务器数据库优化"白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。</span><span class="sxs-lookup"><span data-stu-id="6344c-115">For creating file groups and moving the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database tables, indexes, and log files into the appropriate file groups, follow the recommendations in "Appendix B - Recommended BizTalk Server Database Configuration" in the ["BizTalk Server Database Optimization" white paper](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).</span></span> <span data-ttu-id="6344c-116">理想情况下支持的文件组的文件的大小应预分配并且如果可能，请设置为静态大小。</span><span class="sxs-lookup"><span data-stu-id="6344c-116">Ideally the size of files supporting the file groups should be pre-allocated and if possible, set to a static size.</span></span>  
  
 <span data-ttu-id="6344c-117">如果新系统并不明确设定静态大小，然后配置带有**启用自动增长**选项并指定文件增长等手段**中兆字节为单位**。</span><span class="sxs-lookup"><span data-stu-id="6344c-117">If the system is new and the static sizes have not been definitively established, then configure files with the **Enable Autogrowth** option and specify file growth **In Megabytes**.</span></span> <span data-ttu-id="6344c-118">增长增量通常应是不大于 100 MB （适用于大型文件）、 10 MB （适用于中型文件） 或 （适用于小文件） 的 1 MB。</span><span class="sxs-lookup"><span data-stu-id="6344c-118">The growth increment should generally be no larger than 100 MB (for large files), 10 MB (for medium-sized files), or 1 MB (for small files).</span></span>