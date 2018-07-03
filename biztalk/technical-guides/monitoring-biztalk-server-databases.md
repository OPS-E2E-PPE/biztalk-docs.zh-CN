---
title: 监视 BizTalk Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fee5015-e818-459b-aeeb-a084ef355600
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3cb759bf377cfe77f1e346a94fca739b8532a44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002126"
---
# <a name="monitoring-biztalk-server-databases"></a><span data-ttu-id="5cc12-102">监视 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="5cc12-102">Monitoring BizTalk Server Databases</span></span>
<span data-ttu-id="5cc12-103">可以运行监视 BizTalk Server SQL 代理作业，以标识管理、 消息框中或 DTA 数据库中的任何已知的问题。</span><span class="sxs-lookup"><span data-stu-id="5cc12-103">You can run the Monitor BizTalk Server SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="5cc12-104">在 BizTalk Server 管理控制台中配置 BizTalk 组或从早期版本升级 BizTalk 时创建作业。</span><span class="sxs-lookup"><span data-stu-id="5cc12-104">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
## <a name="the-monitor-biztalk-server-job"></a><span data-ttu-id="5cc12-105">监视 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="5cc12-105">The Monitor BizTalk Server Job</span></span>  
 <span data-ttu-id="5cc12-106">监视 BizTalk Server 作业扫描管理、 消息框和 DTA 数据库中的以下问题：</span><span class="sxs-lookup"><span data-stu-id="5cc12-106">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cc12-107">监视 BizTalk Server 作业仅扫描问题。</span><span class="sxs-lookup"><span data-stu-id="5cc12-107">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="5cc12-108">它不能解决发现的问题。</span><span class="sxs-lookup"><span data-stu-id="5cc12-108">It does not fix the issues found.</span></span>  
  
- <span data-ttu-id="5cc12-109">没有任何引用的消息</span><span class="sxs-lookup"><span data-stu-id="5cc12-109">Messages without any references</span></span>  
  
- <span data-ttu-id="5cc12-110">没有引用计数的消息</span><span class="sxs-lookup"><span data-stu-id="5cc12-110">Messages without reference counts</span></span>  
  
- <span data-ttu-id="5cc12-111">引用计数小于 0 的消息</span><span class="sxs-lookup"><span data-stu-id="5cc12-111">Messages with reference count less than 0</span></span>  
  
- <span data-ttu-id="5cc12-112">无后台行的消息引用</span><span class="sxs-lookup"><span data-stu-id="5cc12-112">Message references without spool rows</span></span>  
  
- <span data-ttu-id="5cc12-113">无实例的消息引用</span><span class="sxs-lookup"><span data-stu-id="5cc12-113">Message references without instances</span></span>  
  
- <span data-ttu-id="5cc12-114">没有实例的实例状态</span><span class="sxs-lookup"><span data-stu-id="5cc12-114">Instance state without instances</span></span>  
  
- <span data-ttu-id="5cc12-115">没有相应的实例的实例订阅</span><span class="sxs-lookup"><span data-stu-id="5cc12-115">Instance subscriptions without corresponding instances</span></span>  
  
- <span data-ttu-id="5cc12-116">孤立的 DTA 服务实例</span><span class="sxs-lookup"><span data-stu-id="5cc12-116">Orphaned DTA service instances</span></span>  
  
- <span data-ttu-id="5cc12-117">孤立的 DTA 服务实例异常</span><span class="sxs-lookup"><span data-stu-id="5cc12-117">Orphaned DTA service instance exceptions</span></span>  
  
- <span data-ttu-id="5cc12-118">TDDS 未运行任何主机实例上启用全局跟踪选项</span><span class="sxs-lookup"><span data-stu-id="5cc12-118">TDDS is not running on any host instance when global tracking option is enabled</span></span>  
  
  <span data-ttu-id="5cc12-119">“监视 BizTalk Server”作业已配置为每周自动运行一次。</span><span class="sxs-lookup"><span data-stu-id="5cc12-119">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="5cc12-120">由于是计算密集型作业，我们建议您计划的停机时间或低流量期间运行。</span><span class="sxs-lookup"><span data-stu-id="5cc12-120">Since the job is computationally intensive, we recommended that you schedule it to run during periods of downtime or low traffic.</span></span>  
  <span data-ttu-id="5cc12-121">作业失败时如果遇到任何问题;返回的错误字符串包含找到的问题数。</span><span class="sxs-lookup"><span data-stu-id="5cc12-121">The job fails if it encounters any issues; the error string returned contains the number of issues found.</span></span> <span data-ttu-id="5cc12-122">否则，它将成功运行。</span><span class="sxs-lookup"><span data-stu-id="5cc12-122">Else, it runs successfully.</span></span> <span data-ttu-id="5cc12-123">您可以在作业历史中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cc12-123">You can see the details in the job history.</span></span> <span data-ttu-id="5cc12-124">如果使用管理员特权运行该作业，将向作业历史记录和 SQL Server 应用程序日志记录的错误字符串。</span><span class="sxs-lookup"><span data-stu-id="5cc12-124">If you run the job with Administrator privileges, the error string will be logged to both the job history and the SQL Server Application log.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5cc12-125">此作业的失败不一定是构成是关键问题，但而不是问题，应调查并解决的定期维护 BizTalk Server 数据库的一部分。</span><span class="sxs-lookup"><span data-stu-id="5cc12-125">Failure of this job does not necessarily constitute a critical issue, but rather an issue that should be investigated and addressed as part of regular maintenance of the BizTalk Server databases.</span></span> <span data-ttu-id="5cc12-126">此作业失败按照设计，它会发现其中一个上面列出的问题的事件中。</span><span class="sxs-lookup"><span data-stu-id="5cc12-126">This job fails by design in the event it discovers one of the issues listed above.</span></span>