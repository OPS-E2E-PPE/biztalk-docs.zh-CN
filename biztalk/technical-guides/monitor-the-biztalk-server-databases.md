---
title: 监视 BizTalk Server 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f137fc5-0e95-4952-8465-008771a1a377
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0ad2f450a859bc7c56a4829ba5315745fbf80a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298917"
---
# <a name="monitor-the-biztalk-server-databases"></a><span data-ttu-id="da0aa-102">监视 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="da0aa-102">Monitor the BizTalk Server Databases</span></span>
<span data-ttu-id="da0aa-103">你可以运行的监视器 BizTalk Server SQL 代理作业来标识管理、 消息框中或 DTA 数据库中的所有已知的问题。</span><span class="sxs-lookup"><span data-stu-id="da0aa-103">You can run the Monitor BizTalk Server SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="da0aa-104">在 BizTalk Server 管理控制台中配置 BizTalk 组或从以前的版本升级 BizTalk 时创建该作业。</span><span class="sxs-lookup"><span data-stu-id="da0aa-104">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
## <a name="the-monitor-biztalk-server-job"></a><span data-ttu-id="da0aa-105">监视器 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="da0aa-105">The Monitor BizTalk Server Job</span></span>  
 <span data-ttu-id="da0aa-106">监视 BizTalk 服务器作业扫描管理、 消息框中，和 DTA 数据库中的以下问题：</span><span class="sxs-lookup"><span data-stu-id="da0aa-106">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da0aa-107">监视 BizTalk 服务器作业仅扫描的问题。</span><span class="sxs-lookup"><span data-stu-id="da0aa-107">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="da0aa-108">它不能解决找到的问题。</span><span class="sxs-lookup"><span data-stu-id="da0aa-108">It does not fix the issues found.</span></span>  
  
-   <span data-ttu-id="da0aa-109">没有任何引用的消息</span><span class="sxs-lookup"><span data-stu-id="da0aa-109">Messages without any references</span></span>  
  
-   <span data-ttu-id="da0aa-110">而无需引用计数的消息</span><span class="sxs-lookup"><span data-stu-id="da0aa-110">Messages without reference counts</span></span>  
  
-   <span data-ttu-id="da0aa-111">引用计数小于 0 的消息</span><span class="sxs-lookup"><span data-stu-id="da0aa-111">Messages with reference count less than 0</span></span>  
  
-   <span data-ttu-id="da0aa-112">无后台行的消息引用</span><span class="sxs-lookup"><span data-stu-id="da0aa-112">Message references without spool rows</span></span>  
  
-   <span data-ttu-id="da0aa-113">无实例的消息引用</span><span class="sxs-lookup"><span data-stu-id="da0aa-113">Message references without instances</span></span>  
  
-   <span data-ttu-id="da0aa-114">不包含实例的实例状态</span><span class="sxs-lookup"><span data-stu-id="da0aa-114">Instance state without instances</span></span>  
  
-   <span data-ttu-id="da0aa-115">实例不包含相应的实例的订阅</span><span class="sxs-lookup"><span data-stu-id="da0aa-115">Instance subscriptions without corresponding instances</span></span>  
  
-   <span data-ttu-id="da0aa-116">孤立的 DTA 服务实例</span><span class="sxs-lookup"><span data-stu-id="da0aa-116">Orphaned DTA service instances</span></span>  
  
-   <span data-ttu-id="da0aa-117">孤立的 DTA 服务实例异常</span><span class="sxs-lookup"><span data-stu-id="da0aa-117">Orphaned DTA service instance exceptions</span></span>  
  
-   <span data-ttu-id="da0aa-118">启用全局跟踪选项不在任何主机实例上运行 TDDS</span><span class="sxs-lookup"><span data-stu-id="da0aa-118">TDDS is not running on any host instance when global tracking option is enabled</span></span>  
  
 <span data-ttu-id="da0aa-119">“监视 BizTalk Server”作业已配置为每周自动运行一次。</span><span class="sxs-lookup"><span data-stu-id="da0aa-119">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="da0aa-120">由于该作业是计算密集型，我们建议你计划的停机时间或低流量期间运行。</span><span class="sxs-lookup"><span data-stu-id="da0aa-120">Since the job is computationally intensive, we recommended that you schedule it to run during periods of downtime or low traffic.</span></span>  
<span data-ttu-id="da0aa-121">作业失败时，如果遇到任何问题;返回的错误字符串包含发现的问题数。</span><span class="sxs-lookup"><span data-stu-id="da0aa-121">The job fails if it encounters any issues; the error string returned contains the number of issues found.</span></span> <span data-ttu-id="da0aa-122">否则，它将成功运行。</span><span class="sxs-lookup"><span data-stu-id="da0aa-122">Else, it runs successfully.</span></span> <span data-ttu-id="da0aa-123">您可以在作业历史中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="da0aa-123">You can see the details in the job history.</span></span> <span data-ttu-id="da0aa-124">如果您使用管理员特权运行该作业，将作业历史记录和 SQL Server 应用程序日志记录的错误字符串。</span><span class="sxs-lookup"><span data-stu-id="da0aa-124">If you run the job with Administrator privileges, the error string will be logged to both the job history and the SQL Server Application log.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="da0aa-125">此作业的失败不一定构成的严重问题，但而是应调查和解决 BizTalk Server 数据库的定期维护的一部分的问题。</span><span class="sxs-lookup"><span data-stu-id="da0aa-125">Failure of this job does not necessarily constitute a critical issue, but rather an issue that should be investigated and addressed as part of regular maintenance of the BizTalk Server databases.</span></span> <span data-ttu-id="da0aa-126">此作业失败设计使然，它发现上面列出的问题之一的事件中。</span><span class="sxs-lookup"><span data-stu-id="da0aa-126">This job fails by design in the event it discovers one of the issues listed above.</span></span> <span data-ttu-id="da0aa-127">上面列出的问题的详细信息，并访问通常用于 Microsoft 产品支持服务解决这些问题的实用程序，请参阅[使用 BizTalk 终止符，若要解决标识 BizTalk 的问题MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367)。</span><span class="sxs-lookup"><span data-stu-id="da0aa-127">For more information about the issues listed above and to access utilities that are commonly used by Microsoft Product Support Services to troubleshoot these issues please see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367).</span></span>