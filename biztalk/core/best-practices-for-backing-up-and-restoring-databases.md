---
title: 备份和还原数据库的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ac2784a19a55d477f71c9b6542b7d46948d63f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529133"
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a><span data-ttu-id="b1eaa-102">备份和还原数据库的最佳实践</span><span class="sxs-lookup"><span data-stu-id="b1eaa-102">Best Practices for Backing Up and Restoring Databases</span></span>
<span data-ttu-id="b1eaa-103">请查看以下最佳实践以帮助确保你可以备份和还原 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-103">Review the following best practices to help ensure that you can backup and restore your BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="b1eaa-104">**开发备份和还原策略并对其进行测试。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-104">**Develop backup and restore strategies and test them.**</span></span>  
  
     <span data-ttu-id="b1eaa-105">使用合适的计划，您可以因硬件故障而丢失时迅速恢复数据。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-105">With a good plan, you can quickly recover your data if it is lost due to hardware failure.</span></span>  
  
-   <span data-ttu-id="b1eaa-106">**管理磁盘空间并归档以前的备份文件。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-106">**Manage disk space and archive previous backup files.**</span></span>  
  
     <span data-ttu-id="b1eaa-107">备份 BizTalk Server 作业不会删除过期的备份文件，因此需要管理这些备份文件，以节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-107">The Backup BizTalk Server job does not delete outdated backup files, so you need to manage those backup files to conserve disk space.</span></span> <span data-ttu-id="b1eaa-108">为数据库创建了新的完全备份后，应该将过期的备份文件移到存档存储设备，以回收主磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-108">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span>  
  
-   <span data-ttu-id="b1eaa-109">**不要在同一计算机或您要备份的磁盘上存储备份。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-109">**Do not store backups on the same computer or disk that you are backing up.**</span></span>  
  
     <span data-ttu-id="b1eaa-110">应为不同于原始数据的计算机备份指定的计算机或磁盘。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-110">You should specify a computer or disk for your backup that is different from the computer with the original data.</span></span> <span data-ttu-id="b1eaa-111">否则，如果将丢失所有数据的硬件出现故障。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-111">Otherwise, you will lose all of your data if the hardware fails.</span></span>  
  
-   <span data-ttu-id="b1eaa-112">**保留副本。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-112">**Retain copies.**</span></span>  
  
     <span data-ttu-id="b1eaa-113">将保留该媒体的至少三个副本。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-113">Keep at least three copies of the media.</span></span> <span data-ttu-id="b1eaa-114">在正确受控环境中保留非现场至少一个副本。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-114">Keep at least one copy off-site in a properly controlled environment.</span></span>  
  
-   <span data-ttu-id="b1eaa-115">**执行试验性还原。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-115">**Perform trial restorations.**</span></span>  
  
     <span data-ttu-id="b1eaa-116">执行试验性还原每月至少一次以验证你的文件已正确备份。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-116">Perform a trial restoration at least once a month to verify that your files were properly backed up.</span></span> <span data-ttu-id="b1eaa-117">试验性还原可以发现不会显示验证您的软件运行正常时的硬件问题。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-117">A trial restoration can uncover hardware problems that do not show up when you verify that your software is functioning properly.</span></span> <span data-ttu-id="b1eaa-118">不要等到硬盘之前，请参阅是否可以还原系统和数据库。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-118">Do not wait until your hard disk fails to see if you can restore your system and databases.</span></span>  
  
-   <span data-ttu-id="b1eaa-119">**保护设备和媒体。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-119">**Secure devices and media.**</span></span>  
  
     <span data-ttu-id="b1eaa-120">保护存储设备和备份介质。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-120">Secure both the storage device and the backup media.</span></span> <span data-ttu-id="b1eaa-121">它是有人可以通过将数据还原到另一台服务器，它们是管理员的窃取的媒体来访问数据。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-121">It is possible for someone to access the data from a stolen medium by restoring the data to another server for which they are an administrator.</span></span>  
  
-   <span data-ttu-id="b1eaa-122">**监视备份和还原过程。**</span><span class="sxs-lookup"><span data-stu-id="b1eaa-122">**Monitor the backup and restore process.**</span></span>  
  
     <span data-ttu-id="b1eaa-123">若要确保备份和还原过程已成功，则应该监视用于备份和还原 BizTalk Server 的 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="b1eaa-123">To ensure that the backup and restore process was successful, you should monitor the SQL Server Agent jobs used to backup and restore BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1eaa-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1eaa-124">See Also</span></span>  
 [<span data-ttu-id="b1eaa-125">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="b1eaa-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)