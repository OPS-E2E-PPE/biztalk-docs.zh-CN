---
title: 备份和还原 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b04e6db4a125b2c90e3417c53d77b10e06f63ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358684"
---
# <a name="backing-up-and-restoring-biztalk-server"></a><span data-ttu-id="4991e-102">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4991e-102">Backing Up and Restoring BizTalk Server</span></span>
<span data-ttu-id="4991e-103">如果发生硬件故障，具有良好的备份 BizTalk Server 数据库和组件非常重要。</span><span class="sxs-lookup"><span data-stu-id="4991e-103">In the event of hardware failure, having a good backup of your BizTalk Server databases and components is essential.</span></span> <span data-ttu-id="4991e-104">一个好的备份以便可以使用很少或没有数据丢失中恢复。</span><span class="sxs-lookup"><span data-stu-id="4991e-104">A good backup will enable you to recover with little or no data loss.</span></span> <span data-ttu-id="4991e-105">如何还原 BizTalk Server 取决于发生硬件故障在系统上安装了什么组件。</span><span class="sxs-lookup"><span data-stu-id="4991e-105">How you restore BizTalk Server depends on which components were installed on the system where hardware failure occurred.</span></span> <span data-ttu-id="4991e-106">本指南涉及以下硬件故障情形：</span><span class="sxs-lookup"><span data-stu-id="4991e-106">This guide covers the following hardware failure scenarios:</span></span>  
  
 <span data-ttu-id="4991e-107">**运行 BizTalk Server 的计算机发生硬件故障**</span><span class="sxs-lookup"><span data-stu-id="4991e-107">**Hardware failure in the computer running BizTalk Server**</span></span>  
  
 <span data-ttu-id="4991e-108">运行 BizTalk Server 的计算机发生硬件故障可能会导致系统停机时间，或如果 BizTalk 组不具备高可用性设计性能下降。</span><span class="sxs-lookup"><span data-stu-id="4991e-108">A hardware failure in the computer running BizTalk Server may cause system downtime or degraded performance if the BizTalk group is not designed for high availability.</span></span> <span data-ttu-id="4991e-109">有关如何创建高度可用的 BizTalk 组的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="4991e-109">For more information about how to create a highly available BizTalk group, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
 <span data-ttu-id="4991e-110">若要确保您可以替换在硬件故障后运行 BizTalk Server 的计算机，必须在该计算机上备份 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="4991e-110">To ensure that you can replace a computer running BizTalk Server after a hardware failure, you must back up the BizTalk Server components on that computer.</span></span> <span data-ttu-id="4991e-111">有关如何备份和还原运行 BizTalk Server 的计算机的详细信息，请参阅[Backing Up a 计算机运行 BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)并[恢复计算机运行的 BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4991e-111">For more information about how to back up and restore a computer running BizTalk Server, see [Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) and [Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="4991e-112">**运行 SQL Server 的计算机发生硬件故障**</span><span class="sxs-lookup"><span data-stu-id="4991e-112">**Hardware failure in the computer running SQL Server**</span></span>  
  
 <span data-ttu-id="4991e-113">可以通过使用 SQL Server 群集中运行 SQL Server 的计算机发生硬件故障的风险降至最低。</span><span class="sxs-lookup"><span data-stu-id="4991e-113">You can minimize the risk of a hardware failure in a computer running SQL Server by using SQL Server clustering.</span></span> <span data-ttu-id="4991e-114">即使使用 SQL Server 群集，但是，有可能的情况下包含 BizTalk Server 数据库的 SQL 服务器遇到了不可恢复的硬件故障时。</span><span class="sxs-lookup"><span data-stu-id="4991e-114">Even when using SQL Server clustering, however, there may be situations when the SQL server(s) containing the BizTalk Server databases experiences an unrecoverable hardware failure.</span></span> <span data-ttu-id="4991e-115">例如，整个数据层发生故障。</span><span class="sxs-lookup"><span data-stu-id="4991e-115">For example, the entire data tier suffered a failure.</span></span> <span data-ttu-id="4991e-116">在这些情况下，必须通过还原备份的数据库的最新一套恢复 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="4991e-116">In these situations, you must revive the BizTalk group by restoring the most recent set of backed up databases.</span></span>  
  
 <span data-ttu-id="4991e-117">有关为 BizTalk Server 数据库提供容错功能的详细信息，请参阅[的 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="4991e-117">For more information about providing fault tolerance for the BizTalk Server databases, see [Providing High Availability for BizTalk Server Databases](../core/providing-high-availability-for-biztalk-server-databases.md).</span></span> <span data-ttu-id="4991e-118">在发生灾难性 SQL Server 故障发生导致停机，应按照中的说明[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="4991e-118">In the case of a catastrophic SQL Server failure where downtime has occurred, you should follow the instructions in [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="4991e-119">如果遇到硬件故障，安装 SQL Server 和 BizTalk Server 的计算机上，您应还原 BizTalk Server 数据库中，然后再恢复 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="4991e-119">If you experience a hardware failure on a computer where both SQL Server and BizTalk Server are installed, you should restore the BizTalk Server databases, and then recover the BizTalk Server components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4991e-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="4991e-120">In This Section</span></span>  
  
-   [<span data-ttu-id="4991e-121">清单：备份和还原</span><span class="sxs-lookup"><span data-stu-id="4991e-121">Checklist: Backup and Restore</span></span>](../core/checklist-backup-and-restore.md)  
  
-   [<span data-ttu-id="4991e-122">备份和还原的最佳做法</span><span class="sxs-lookup"><span data-stu-id="4991e-122">Best Practices for Backup and Restore</span></span>](../core/best-practices-for-backup-and-restore.md)  
  
-   [<span data-ttu-id="4991e-123">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="4991e-123">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="4991e-124">运行 BizTalk Server 的计算机的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="4991e-124">Disaster Recovery for Computers Running BizTalk Server</span></span>](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [<span data-ttu-id="4991e-125">对运行 BizTalk Server 的计算机进行备份</span><span class="sxs-lookup"><span data-stu-id="4991e-125">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [<span data-ttu-id="4991e-126">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="4991e-126">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)