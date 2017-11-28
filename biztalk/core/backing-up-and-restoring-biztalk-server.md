---
title: "备份和还原 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1adac25b23c69b51e07ed5f30768d046a453887a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-biztalk-server"></a><span data-ttu-id="8e831-102">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8e831-102">Backing Up and Restoring BizTalk Server</span></span>
<span data-ttu-id="8e831-103">在发生硬件故障时，对 BizTalk Server 数据库和组件有完善的备份至关重要。</span><span class="sxs-lookup"><span data-stu-id="8e831-103">In the event of hardware failure, having a good backup of your BizTalk Server databases and components is essential.</span></span> <span data-ttu-id="8e831-104">完善的备份使您能够进行恢复，而数据损失很少甚至毫无损失。</span><span class="sxs-lookup"><span data-stu-id="8e831-104">A good backup will enable you to recover with little or no data loss.</span></span> <span data-ttu-id="8e831-105">如何还原 BizTalk Server，取决于发生硬件故障的系统上安装了什么组件。</span><span class="sxs-lookup"><span data-stu-id="8e831-105">How you restore BizTalk Server depends on which components were installed on the system where hardware failure occurred.</span></span> <span data-ttu-id="8e831-106">本指南涉及以下硬件故障情形：</span><span class="sxs-lookup"><span data-stu-id="8e831-106">This guide covers the following hardware failure scenarios:</span></span>  
  
 <span data-ttu-id="8e831-107">**在运行 BizTalk Server 的计算机的硬件故障**</span><span class="sxs-lookup"><span data-stu-id="8e831-107">**Hardware failure in the computer running BizTalk Server**</span></span>  
  
 <span data-ttu-id="8e831-108">如果 BizTalk 组不具备高可用性设计，那么运行 BizTalk Server 的计算机发生硬件故障可能会导致系统停机或性能下降。</span><span class="sxs-lookup"><span data-stu-id="8e831-108">A hardware failure in the computer running BizTalk Server may cause system downtime or degraded performance if the BizTalk group is not designed for high availability.</span></span> <span data-ttu-id="8e831-109">有关如何创建高度可用的 BizTalk 组的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="8e831-109">For more information about how to create a highly available BizTalk group, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
 <span data-ttu-id="8e831-110">要确保在硬件故障后可以更换运行 BizTalk Server 的计算机，必须备份计算机上的 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="8e831-110">To ensure that you can replace a computer running BizTalk Server after a hardware failure, you must back up the BizTalk Server components on that computer.</span></span> <span data-ttu-id="8e831-111">有关如何备份和还原运行 BizTalk Server 的计算机的详细信息，请参阅[Backing Up a 计算机运行 BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)和[恢复计算机运行的 BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8e831-111">For more information about how to back up and restore a computer running BizTalk Server, see [Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) and [Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="8e831-112">**在运行 SQL Server 的计算机的硬件故障**</span><span class="sxs-lookup"><span data-stu-id="8e831-112">**Hardware failure in the computer running SQL Server**</span></span>  
  
 <span data-ttu-id="8e831-113">通过使用 SQL Server 群集，可以尽可能减少运行 SQL Server 的计算机发生硬件故障的风险。</span><span class="sxs-lookup"><span data-stu-id="8e831-113">You can minimize the risk of a hardware failure in a computer running SQL Server by using SQL Server clustering.</span></span> <span data-ttu-id="8e831-114">不过，在使用 SQL Server 群集时，可能会出现包含 BizTalk Server 数据库的 SQL 服务器发生不可恢复的硬件故障的情况。</span><span class="sxs-lookup"><span data-stu-id="8e831-114">Even when using SQL Server clustering, however, there may be situations when the SQL server(s) containing the BizTalk Server databases experiences an unrecoverable hardware failure.</span></span> <span data-ttu-id="8e831-115">例如，整个数据层发生故障。</span><span class="sxs-lookup"><span data-stu-id="8e831-115">For example, the entire data tier suffered a failure.</span></span> <span data-ttu-id="8e831-116">在这种情况下，必须通过还原最新的一组备份的数据库来恢复 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="8e831-116">In these situations, you must revive the BizTalk group by restoring the most recent set of backed up databases.</span></span>  
  
 <span data-ttu-id="8e831-117">有关为 BizTalk Server 数据库提供容错功能的详细信息，请参阅[BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="8e831-117">For more information about providing fault tolerance for the BizTalk Server databases, see [Providing High Availability for BizTalk Server Databases](../core/providing-high-availability-for-biztalk-server-databases.md).</span></span> <span data-ttu-id="8e831-118">发生灾难性的 SQL Server 故障发生停机时间，应按照中的说明[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="8e831-118">In the case of a catastrophic SQL Server failure where downtime has occurred, you should follow the instructions in [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="8e831-119">如果既安装了 SQL Server 又安装了 BizTalk Server 的计算机发生硬件故障，应该还原 BizTalk Server 数据库，然后恢复 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="8e831-119">If you experience a hardware failure on a computer where both SQL Server and BizTalk Server are installed, you should restore the BizTalk Server databases, and then recover the BizTalk Server components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e831-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="8e831-120">In This Section</span></span>  
  
-   [<span data-ttu-id="8e831-121">清单： 备份和还原</span><span class="sxs-lookup"><span data-stu-id="8e831-121">Checklist: Backup and Restore</span></span>](../core/checklist-backup-and-restore.md)  
  
-   [<span data-ttu-id="8e831-122">备份和还原最佳实践</span><span class="sxs-lookup"><span data-stu-id="8e831-122">Best Practices for Backup and Restore</span></span>](../core/best-practices-for-backup-and-restore.md)  
  
-   [<span data-ttu-id="8e831-123">备份和还原的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="8e831-123">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="8e831-124">运行 BizTalk Server 的计算机的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="8e831-124">Disaster Recovery for Computers Running BizTalk Server</span></span>](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [<span data-ttu-id="8e831-125">备份运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="8e831-125">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [<span data-ttu-id="8e831-126">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="8e831-126">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)