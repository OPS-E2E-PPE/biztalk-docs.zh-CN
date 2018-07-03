---
title: 规划你的平台容错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- MessageBox database, fault tolerance
- clustering, fault tolerance
- SQL Server RAID
- databases [BAM], fault tolerance
- BizTalk Server, planning
- fault tolerance
- clustering, fail-overs
- planning, fault tolerance
- Primary Import database [BAM]
- BizTalk Server, backing up
- fault tolerance, planning
- planning, BizTalk Server
- Primary Import database [BAM], fault tolerance
- fail-over clustering
ms.assetid: 512ed6b8-db1e-434a-8009-63e952cf5500
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ddc4565449171c71685bcddd2c68b699f5113b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007486"
---
# <a name="planning-your-platform-for-fault-tolerance"></a><span data-ttu-id="a83e7-102">规划你的平台容错功能</span><span class="sxs-lookup"><span data-stu-id="a83e7-102">Planning Your Platform for Fault Tolerance</span></span>
<span data-ttu-id="a83e7-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是基于 Microsoft Windows 和 Microsoft SQL Server 平台建立的。</span><span class="sxs-lookup"><span data-stu-id="a83e7-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on the Microsoft Windows and Microsoft SQL Server platforms.</span></span> <span data-ttu-id="a83e7-104">BizTalk Server 幸免于灾难或从灾难中恢复的能力取决于其底层平台幸免或恢复的能力。</span><span class="sxs-lookup"><span data-stu-id="a83e7-104">The ability of BizTalk Server to survive or recover from a disaster depends on the ability of the underlying platform to survive or recover.</span></span>  
  
 <span data-ttu-id="a83e7-105">有关业务活动监视 (BAM) 数据库和 MessageBox 数据库，我们建议你以下操作：</span><span class="sxs-lookup"><span data-stu-id="a83e7-105">For your Business Activity Monitoring (BAM) databases and your MessageBox database, we recommend you do the following:</span></span>  
  
- <span data-ttu-id="a83e7-106">建立故障转移群集，此功能在 SQL Server Enterprise Edition 中可用。</span><span class="sxs-lookup"><span data-stu-id="a83e7-106">Set up fail-over clustering, which is available in SQL Server Enterprise Edition.</span></span> <span data-ttu-id="a83e7-107">使用故障转移群集，SQL Server 可自动将 SQL Server 实例的处理从故障服务器切换到正常工作的服务器。</span><span class="sxs-lookup"><span data-stu-id="a83e7-107">Fail-over clustering enables SQL Server to automatically switch the processing for an instance of SQL Server from a failed server to a working server.</span></span>  
  
   <span data-ttu-id="a83e7-108">BAM 主导入数据库收集事件数据。</span><span class="sxs-lookup"><span data-stu-id="a83e7-108">The BAM Primary Import database collects event data.</span></span> <span data-ttu-id="a83e7-109">在系统发生灾难时，自上次备份后写入 BAM 主导入数据库的数据将会丢失。</span><span class="sxs-lookup"><span data-stu-id="a83e7-109">In the event of a disaster, data that was written to the BAM Primary Import database since the last backup will be lost.</span></span> <span data-ttu-id="a83e7-110">由于无法重新生成这些丢失的事件，因此，在 BAM 主导入数据库上启用故障转移群集是十分重要的。</span><span class="sxs-lookup"><span data-stu-id="a83e7-110">Because there is no way to regenerate lost events, it is especially important that you enable fail over clustering on your BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="a83e7-111">尤其对于 MessageBox 数据库和 BAM 主导入数据库，请使用 SQL Server RAID（独立磁盘冗余阵列）。</span><span class="sxs-lookup"><span data-stu-id="a83e7-111">Use SQL Server RAID (redundant array of independent disks), especially for the MessageBox database and the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="a83e7-112">使用以下资源来设计 Windows 和 SQL Server 部署以实现容错。</span><span class="sxs-lookup"><span data-stu-id="a83e7-112">Use the following resources to design your Windows and SQL Server deployments for fault tolerance.</span></span> <span data-ttu-id="a83e7-113">您需要了解硬件和服务器冗余技术（例如群集和磁盘镜像），以防止服务故障和数据丢失。</span><span class="sxs-lookup"><span data-stu-id="a83e7-113">Take time to learn about hardware and server redundancy technologies, such as clustering and disk mirroring, to prevent service outages and data loss.</span></span>  
  
- [<span data-ttu-id="a83e7-114">白皮书： 高可用性-Alwayson 技术</span><span class="sxs-lookup"><span data-stu-id="a83e7-114">White Paper: High Availability—Always On Technologies</span></span>](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   <span data-ttu-id="a83e7-115">"高可用性 – Always On Technologies"白皮书描述 SQL Server 2008 提供的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="a83e7-115">The “High Availability – Always On Technologies” whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- [<span data-ttu-id="a83e7-116">高可用性解决方案概述</span><span class="sxs-lookup"><span data-stu-id="a83e7-116">High Availability Solutions Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   <span data-ttu-id="a83e7-117">介绍了 SQL Server 2008 中若干改善服务器或数据库可用性的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="a83e7-117">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- [<span data-ttu-id="a83e7-118">第 15 章-高可用性选项，SQL Server 资源工具包</span><span class="sxs-lookup"><span data-stu-id="a83e7-118">Chapter 15 - High Availability Options, SQL Server Resource Kit</span></span>](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   <span data-ttu-id="a83e7-119">Microsoft SQL Server 资源工具包涉及了广泛的管理及部署规划领域的内容。</span><span class="sxs-lookup"><span data-stu-id="a83e7-119">The Microsoft SQL Server Resource Kit covers a wide range of administrative and deployment planning areas.</span></span> <span data-ttu-id="a83e7-120">第 15 章介绍了如何针对容错和恢复进行规划。</span><span class="sxs-lookup"><span data-stu-id="a83e7-120">Chapter 15 covers planning for fault tolerance and recovery.</span></span>  
  
- [<span data-ttu-id="a83e7-121">Windows 部署服务分步指南</span><span class="sxs-lookup"><span data-stu-id="a83e7-121">Windows Deployment Services Step-by-Step Guide</span></span>](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   <span data-ttu-id="a83e7-122">包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色的循序渐进指南</span><span class="sxs-lookup"><span data-stu-id="a83e7-122">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008</span></span>  
  
- <span data-ttu-id="a83e7-123">[Windows Server 2003 部署工具包： 规划服务器部署](http://go.microsoft.com/fwlink/?LinkId=24433)。</span><span class="sxs-lookup"><span data-stu-id="a83e7-123">[Windows Server 2003 Deployment Kit: Planning Server Deployments](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="a83e7-124">本书介绍了有关规划服务器存储的信息，以及有关设计和部署大、中型组织中的文件服务器、打印服务器和终端服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="a83e7-124">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
   <span data-ttu-id="a83e7-125">还可使用本书中的指导来规划远程服务器管理、设计和部署服务器群集与网络负载平衡群集，从而最大限度地提高服务器的可用性和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="a83e7-125">You can also use the guidelines in this book to maximize the availability and scalability of your servers by planning for remote server management, designing and deploying server clusters, and designing and deploying Network Load Balancing clusters.</span></span>  
  
## <a name="backing-up-your-platform"></a><span data-ttu-id="a83e7-126">备份您的平台</span><span class="sxs-lookup"><span data-stu-id="a83e7-126">Backing Up Your Platform</span></span>  
 <span data-ttu-id="a83e7-127">对系统进行配置后，准备服务器的完整备份，以便在数据丢失的情况下可以快速还原相同的服务器。</span><span class="sxs-lookup"><span data-stu-id="a83e7-127">After you have configured your system, prepare full backups of your servers so you can quickly restore an identical server in the event of data loss.</span></span>  
  
 <span data-ttu-id="a83e7-128">若要备份平台，请对以下各种技术执行所记录的备份过程：</span><span class="sxs-lookup"><span data-stu-id="a83e7-128">To back up your platform, perform the documented backup procedures for each of the following technologies:</span></span>  
  
- <span data-ttu-id="a83e7-129">Microsoft Windows Server Standard、Enterprise 或 Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="a83e7-129">Microsoft Windows Server Standard, Enterprise, or Datacenter Edition</span></span>  
  
- <span data-ttu-id="a83e7-130">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="a83e7-130">Internet Information Services (IIS)</span></span>  
  
- <span data-ttu-id="a83e7-131">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a83e7-131">Microsoft SQL Server</span></span>  
  
- <span data-ttu-id="a83e7-132">Windows SharePoint Services，由 Windows SharePoint Services 适配器使用。</span><span class="sxs-lookup"><span data-stu-id="a83e7-132">Windows SharePoint Services, which is used by the Windows SharePoint Services adapter.</span></span>  
  
  <span data-ttu-id="a83e7-133">请遵循"备份 BizTalk Server"可在"BizTalk Server 操作指南"中的建议[清单： 灾难恢复与提高可用性](http://go.microsoft.com/fwlink/?LinkId=130498)。</span><span class="sxs-lookup"><span data-stu-id="a83e7-133">Follow the recommendations in the “BizTalk Server Operations Guide” for “Backing up BizTalk Server” available at [Checklist: Increasing Availability with Disaster Recovery](http://go.microsoft.com/fwlink/?LinkId=130498).</span></span>  
  
  <span data-ttu-id="a83e7-134">对备份和还原过程进行彻底测试，然后将其放置于安全的远程位置。</span><span class="sxs-lookup"><span data-stu-id="a83e7-134">Thoroughly test your backup and restore procedures, and put them in a safe, remote location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83e7-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="a83e7-135">See Also</span></span>  
 [<span data-ttu-id="a83e7-136">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a83e7-136">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)