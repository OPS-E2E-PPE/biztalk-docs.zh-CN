---
title: "备份和还原数据库的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2543f09c5118e58bd18ea2add113811fb733d884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a><span data-ttu-id="875e8-102">备份和还原数据库的最佳实践</span><span class="sxs-lookup"><span data-stu-id="875e8-102">Best Practices for Backing Up and Restoring Databases</span></span>
<span data-ttu-id="875e8-103">请查看以下最佳实践，以确保您能够备份和还原 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="875e8-103">Review the following best practices to help ensure that you can backup and restore your BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="875e8-104">**开发备份和还原策略，并对其进行测试。**</span><span class="sxs-lookup"><span data-stu-id="875e8-104">**Develop backup and restore strategies and test them.**</span></span>  
  
     <span data-ttu-id="875e8-105">有了好的计划，您就可以在由于硬件故障致使数据丢失时迅速恢复数据。</span><span class="sxs-lookup"><span data-stu-id="875e8-105">With a good plan, you can quickly recover your data if it is lost due to hardware failure.</span></span>  
  
-   <span data-ttu-id="875e8-106">**管理磁盘空间并存档以前的备份文件。**</span><span class="sxs-lookup"><span data-stu-id="875e8-106">**Manage disk space and archive previous backup files.**</span></span>  
  
     <span data-ttu-id="875e8-107">由于备份 BizTalk Server 作业并不删除过期的备份文件，所以需要对这些备份文件进行管理，以节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="875e8-107">The Backup BizTalk Server job does not delete outdated backup files, so you need to manage those backup files to conserve disk space.</span></span> <span data-ttu-id="875e8-108">为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="875e8-108">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span>  
  
-   <span data-ttu-id="875e8-109">**不在相同的计算机或要备份的磁盘上存储备份。**</span><span class="sxs-lookup"><span data-stu-id="875e8-109">**Do not store backups on the same computer or disk that you are backing up.**</span></span>  
  
     <span data-ttu-id="875e8-110">而应该为其指定其他计算机或磁盘。</span><span class="sxs-lookup"><span data-stu-id="875e8-110">You should specify a computer or disk for your backup that is different from the computer with the original data.</span></span> <span data-ttu-id="875e8-111">否则，当出现硬件故障时，您将丢失所有数据。</span><span class="sxs-lookup"><span data-stu-id="875e8-111">Otherwise, you will lose all of your data if the hardware fails.</span></span>  
  
-   <span data-ttu-id="875e8-112">**保留副本。**</span><span class="sxs-lookup"><span data-stu-id="875e8-112">**Retain copies.**</span></span>  
  
     <span data-ttu-id="875e8-113">至少应保留该媒体的三个副本。</span><span class="sxs-lookup"><span data-stu-id="875e8-113">Keep at least three copies of the media.</span></span> <span data-ttu-id="875e8-114">至少保留一个非现场副本，放置在安全控制良好的环境中。</span><span class="sxs-lookup"><span data-stu-id="875e8-114">Keep at least one copy off-site in a properly controlled environment.</span></span>  
  
-   <span data-ttu-id="875e8-115">**执行试验性还原。**</span><span class="sxs-lookup"><span data-stu-id="875e8-115">**Perform trial restorations.**</span></span>  
  
     <span data-ttu-id="875e8-116">至少每月执行一次试验性还原，以验证文件备份是否正确。</span><span class="sxs-lookup"><span data-stu-id="875e8-116">Perform a trial restoration at least once a month to verify that your files were properly backed up.</span></span> <span data-ttu-id="875e8-117">试验性还原可发现在验证软件功能是否正常时未发现的硬件问题。</span><span class="sxs-lookup"><span data-stu-id="875e8-117">A trial restoration can uncover hardware problems that do not show up when you verify that your software is functioning properly.</span></span> <span data-ttu-id="875e8-118">不要等到硬盘出现了故障，才去检查是否能还原系统和数据库。</span><span class="sxs-lookup"><span data-stu-id="875e8-118">Do not wait until your hard disk fails to see if you can restore your system and databases.</span></span>  
  
-   <span data-ttu-id="875e8-119">**保护设备和媒体。**</span><span class="sxs-lookup"><span data-stu-id="875e8-119">**Secure devices and media.**</span></span>  
  
     <span data-ttu-id="875e8-120">保护存储设备和备份媒体。</span><span class="sxs-lookup"><span data-stu-id="875e8-120">Secure both the storage device and the backup media.</span></span> <span data-ttu-id="875e8-121">其他人可能偷窃备份媒体，并将数据还原到他们具有管理员身份的其他服务器上，以访问媒体上的数据。</span><span class="sxs-lookup"><span data-stu-id="875e8-121">It is possible for someone to access the data from a stolen medium by restoring the data to another server for which they are an administrator.</span></span>  
  
-   <span data-ttu-id="875e8-122">**监视备份和还原过程。**</span><span class="sxs-lookup"><span data-stu-id="875e8-122">**Monitor the backup and restore process.**</span></span>  
  
     <span data-ttu-id="875e8-123">为了确保备份和还原过程成功，您应对用来备份和还原 BizTalk Server 的 SQL Server 代理作业进行监视。</span><span class="sxs-lookup"><span data-stu-id="875e8-123">To ensure that the backup and restore process was successful, you should monitor the SQL Server Agent jobs used to backup and restore BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875e8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="875e8-124">See Also</span></span>  
 [<span data-ttu-id="875e8-125">备份和还原的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="875e8-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)