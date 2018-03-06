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
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d37bcce2d60167496bc55a12c65a488db17fceb
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="define-auto-growth-settings-for-databases"></a><span data-ttu-id="ed9c6-102">定义数据库的自动增长设置</span><span class="sxs-lookup"><span data-stu-id="ed9c6-102">Define Auto-Growth Settings for Databases</span></span>
<span data-ttu-id="ed9c6-103">你应设置为固定数量的兆字节而不是一个百分比，尤其是对于 MessageBox 和 BizTalk 跟踪数据库的数据库自动增长。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-103">You should set database auto-growth to a fixed number of megabytes instead of to a percentage, especially for the MessageBox and BizTalk Tracking databases.</span></span> <span data-ttu-id="ed9c6-104">根据你的 BizTalk 应用程序和吞吐量，MessageBox 和跟踪数据库可能会非常大。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-104">Depending on your BizTalk application and throughput, the MessageBox and Tracking databases can get quite large.</span></span> <span data-ttu-id="ed9c6-105">如果将自动增长设置为百分比，然后自动增长可能是非常高。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-105">If you set auto-growth to a percentage, then the auto-growth can be substantial as well.</span></span>  
  
## <a name="how-instant-file-initialization-works"></a><span data-ttu-id="ed9c6-106">如何即时文件初始化的工作原理</span><span class="sxs-lookup"><span data-stu-id="ed9c6-106">How Instant File Initialization Works</span></span>  
 <span data-ttu-id="ed9c6-107">当 SQL Server 会增加文件的大小时，它必须首先初始化的新空间，然后才能使用。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-107">When SQL Server increases the size of a file, it must first initialize the new space before it can be used.</span></span> <span data-ttu-id="ed9c6-108">这是涉及使用空页填充新的空间的阻止操作。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-108">This is a blocking operation that involves filling the new space with empty pages.</span></span> <span data-ttu-id="ed9c6-109">在 Windows 上的 SQL Server 支持"即时文件初始化。"</span><span class="sxs-lookup"><span data-stu-id="ed9c6-109">SQL Server on Windows supports “instant file initialization.”</span></span> <span data-ttu-id="ed9c6-110">这可以极大地降低文件增长操作的性能影响。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-110">This can greatly reduce the performance impact of a file growth operation.</span></span> <span data-ttu-id="ed9c6-111">有关详细信息，请参阅 [数据库文件初始化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-111">For more information, see [Database File Initialization](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization).</span></span> <span data-ttu-id="ed9c6-112">本主题概述了必须谨慎以启用即时文件初始化的步骤。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-112">This topic outlines the steps that must be taken to enable instant file initialization.</span></span>  
  
## <a name="enable-instant-file-initialization"></a><span data-ttu-id="ed9c6-113">启用即时文件初始化</span><span class="sxs-lookup"><span data-stu-id="ed9c6-113">Enable Instant File Initialization</span></span>  
 <span data-ttu-id="ed9c6-114">有关步骤启用即时文件初始化，请参阅[数据库文件初始化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-114">For steps on enabling instant file initialization, see [Database File Initialization](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization).</span></span> <span data-ttu-id="ed9c6-115">创建文件组并将 BizTalk Server 数据库表、 索引和日志文件移到相应的文件组，请按照中的建议[BizTalk 性能优化指南](../technical-guides/biztalk-server-2013-performance-optimization-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-115">For creating file groups and moving the BizTalk Server database tables, indexes, and log files into the appropriate file groups, follow the recommendations in the [BizTalk performance optimization guide](../technical-guides/biztalk-server-2013-performance-optimization-guide.md).</span></span> <span data-ttu-id="ed9c6-116">理想情况下支持的文件组的文件的大小应预分配并且如果可能，请设置为静态大小。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-116">Ideally the size of files supporting the file groups should be pre-allocated and if possible, set to a static size.</span></span>  
  
 <span data-ttu-id="ed9c6-117">如果新系统并不明确设定静态大小，然后配置带有**启用自动增长**选项并指定文件增长等手段**中兆字节为单位**。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-117">If the system is new and the static sizes have not been definitively established, then configure files with the **Enable Autogrowth** option and specify file growth **In Megabytes**.</span></span> <span data-ttu-id="ed9c6-118">增长增量通常应是不大于 100 MB （适用于大型文件）、 10 MB （适用于中型文件） 或 （适用于小文件） 的 1 MB。</span><span class="sxs-lookup"><span data-stu-id="ed9c6-118">The growth increment should generally be no larger than 100 MB (for large files), 10 MB (for medium-sized files), or 1 MB (for small files).</span></span>
