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
ms.openlocfilehash: 3564be0d8e49d64b3726f7aca360bfa4042343db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394968"
---
# <a name="planning-your-platform-for-fault-tolerance"></a><span data-ttu-id="a4dbe-102">规划你的平台容错功能</span><span class="sxs-lookup"><span data-stu-id="a4dbe-102">Planning Your Platform for Fault Tolerance</span></span>
<span data-ttu-id="a4dbe-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于 Microsoft Windows 和 Microsoft SQL Server 平台。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on the Microsoft Windows and Microsoft SQL Server platforms.</span></span> <span data-ttu-id="a4dbe-104">BizTalk Server 幸免或从灾难中恢复的能力取决于底层平台幸免或恢复的能力。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-104">The ability of BizTalk Server to survive or recover from a disaster depends on the ability of the underlying platform to survive or recover.</span></span>  
  
 <span data-ttu-id="a4dbe-105">有关业务活动监视 (BAM) 数据库和 MessageBox 数据库，我们建议你以下操作：</span><span class="sxs-lookup"><span data-stu-id="a4dbe-105">For your Business Activity Monitoring (BAM) databases and your MessageBox database, we recommend you do the following:</span></span>  
  
- <span data-ttu-id="a4dbe-106">设置故障转移群集，这是 SQL Server Enterprise Edition 中可用。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-106">Set up fail-over clustering, which is available in SQL Server Enterprise Edition.</span></span> <span data-ttu-id="a4dbe-107">故障转移群集，SQL Server 可自动切换到工作服务器从发生故障的服务器的 SQL Server 实例的处理。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-107">Fail-over clustering enables SQL Server to automatically switch the processing for an instance of SQL Server from a failed server to a working server.</span></span>  
  
   <span data-ttu-id="a4dbe-108">BAM 主导入数据库收集事件数据。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-108">The BAM Primary Import database collects event data.</span></span> <span data-ttu-id="a4dbe-109">发生灾难时，自上次备份后写入 BAM 主导入数据库的数据将会丢失。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-109">In the event of a disaster, data that was written to the BAM Primary Import database since the last backup will be lost.</span></span> <span data-ttu-id="a4dbe-110">因为没有方法来重新生成丢失的事件，是你启用故障转移群集在 BAM 主导入数据库上尤其重要。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-110">Because there is no way to regenerate lost events, it is especially important that you enable fail over clustering on your BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="a4dbe-111">使用 SQL Server RAID （独立磁盘冗余阵列），特别是对于 MessageBox 数据库和 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-111">Use SQL Server RAID (redundant array of independent disks), especially for the MessageBox database and the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="a4dbe-112">使用以下资源来设计您的 Windows 和 SQL Server 部署以实现容错。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-112">Use the following resources to design your Windows and SQL Server deployments for fault tolerance.</span></span> <span data-ttu-id="a4dbe-113">需要时间来了解硬件和服务器冗余技术，如聚类分析和磁盘镜像，以防止服务中断和数据丢失。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-113">Take time to learn about hardware and server redundancy technologies, such as clustering and disk mirroring, to prevent service outages and data loss.</span></span>  
  
- [<span data-ttu-id="a4dbe-114">白皮书：高可用性-Alwayson 技术</span><span class="sxs-lookup"><span data-stu-id="a4dbe-114">White Paper: High Availability—Always On Technologies</span></span>](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   <span data-ttu-id="a4dbe-115">"高可用性 – Always On Technologies"白皮书描述 SQL Server 2008 提供的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-115">The “High Availability – Always On Technologies” whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- [<span data-ttu-id="a4dbe-116">高可用性解决方案概述</span><span class="sxs-lookup"><span data-stu-id="a4dbe-116">High Availability Solutions Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   <span data-ttu-id="a4dbe-117">为提高可用性的服务器或数据库的 SQL Server 2008 引入了多个高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-117">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- [<span data-ttu-id="a4dbe-118">第 15 章-高可用性选项，SQL Server 资源工具包</span><span class="sxs-lookup"><span data-stu-id="a4dbe-118">Chapter 15 - High Availability Options, SQL Server Resource Kit</span></span>](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   <span data-ttu-id="a4dbe-119">Microsoft SQL Server 资源工具包涉及范围广泛的管理和部署规划领域。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-119">The Microsoft SQL Server Resource Kit covers a wide range of administrative and deployment planning areas.</span></span> <span data-ttu-id="a4dbe-120">第 15 章介绍了规划容错和恢复。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-120">Chapter 15 covers planning for fault tolerance and recovery.</span></span>  
  
- [<span data-ttu-id="a4dbe-121">Windows 部署服务分步指南</span><span class="sxs-lookup"><span data-stu-id="a4dbe-121">Windows Deployment Services Step-by-Step Guide</span></span>](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   <span data-ttu-id="a4dbe-122">包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色循序渐进指南</span><span class="sxs-lookup"><span data-stu-id="a4dbe-122">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008</span></span>  
  
- <span data-ttu-id="a4dbe-123">[Windows Server 2003 部署工具包：规划服务器部署](http://go.microsoft.com/fwlink/?LinkId=24433)。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-123">[Windows Server 2003 Deployment Kit: Planning Server Deployments](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="a4dbe-124">本书提供了有关设计和部署文件服务器、 打印服务器和中型和大型组织中的终端服务器的规划服务器存储和信息有关的信息。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-124">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
   <span data-ttu-id="a4dbe-125">您还可用于指导原则在本书中的远程服务器管理的规划、 设计和部署服务器群集和设计和部署网络负载平衡群集中最大化可用性和可伸缩性的服务器。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-125">You can also use the guidelines in this book to maximize the availability and scalability of your servers by planning for remote server management, designing and deploying server clusters, and designing and deploying Network Load Balancing clusters.</span></span>  
  
## <a name="backing-up-your-platform"></a><span data-ttu-id="a4dbe-126">备份你的平台</span><span class="sxs-lookup"><span data-stu-id="a4dbe-126">Backing Up Your Platform</span></span>  
 <span data-ttu-id="a4dbe-127">配置您的系统后，准备你的服务器的完整备份，以便在发生数据丢失时可以快速还原相同的服务器。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-127">After you have configured your system, prepare full backups of your servers so you can quickly restore an identical server in the event of data loss.</span></span>  
  
 <span data-ttu-id="a4dbe-128">若要备份你的平台，请执行以下技术的每个有案可稽的备份过程：</span><span class="sxs-lookup"><span data-stu-id="a4dbe-128">To back up your platform, perform the documented backup procedures for each of the following technologies:</span></span>  
  
- <span data-ttu-id="a4dbe-129">Microsoft Windows Server Standard、 Enterprise 或 Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="a4dbe-129">Microsoft Windows Server Standard, Enterprise, or Datacenter Edition</span></span>  
  
- <span data-ttu-id="a4dbe-130">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="a4dbe-130">Internet Information Services (IIS)</span></span>  
  
- <span data-ttu-id="a4dbe-131">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4dbe-131">Microsoft SQL Server</span></span>  
  
- <span data-ttu-id="a4dbe-132">Windows SharePoint Services，它由 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-132">Windows SharePoint Services, which is used by the Windows SharePoint Services adapter.</span></span>  
  
  <span data-ttu-id="a4dbe-133">请遵循"备份 BizTalk Server"可在"BizTalk Server 操作指南"中的建议[核对清单：提供高可用性灾难恢复](http://go.microsoft.com/fwlink/?LinkId=130498)。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-133">Follow the recommendations in the “BizTalk Server Operations Guide” for “Backing up BizTalk Server” available at [Checklist: Increasing Availability with Disaster Recovery](http://go.microsoft.com/fwlink/?LinkId=130498).</span></span>  
  
  <span data-ttu-id="a4dbe-134">进行全面测试备份和还原过程，并将其放在一个安全的远程位置。</span><span class="sxs-lookup"><span data-stu-id="a4dbe-134">Thoroughly test your backup and restore procedures, and put them in a safe, remote location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4dbe-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4dbe-135">See Also</span></span>  
 [<span data-ttu-id="a4dbe-136">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a4dbe-136">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)