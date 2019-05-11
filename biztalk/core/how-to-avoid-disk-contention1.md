---
title: 如何避免磁盘 Contention1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9204fc727339a5fbab31cdf54bc8de488e588dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342672"
---
# <a name="how-to-avoid-disk-contention"></a><span data-ttu-id="931d5-102">如何避免磁盘争用</span><span class="sxs-lookup"><span data-stu-id="931d5-102">How to Avoid Disk Contention</span></span>
<span data-ttu-id="931d5-103">BizTalk Server 设计为永久性系统因而对于高吞吐量方案中，MessageBox 可能会出现严重的争用现象。</span><span class="sxs-lookup"><span data-stu-id="931d5-103">BizTalk Server is designed as a persistent system whereby, for high throughput scenarios, the MessageBox can experience severe contention.</span></span> <span data-ttu-id="931d5-104">这种争用可以将变得更加严重缓慢的磁盘。</span><span class="sxs-lookup"><span data-stu-id="931d5-104">This contention can be aggravated by slow disks.</span></span> <span data-ttu-id="931d5-105">如果磁盘是缓慢 （低于 %磁盘空闲时间），则会导致 SQL 保存锁定更长 （高锁定等待时间和高锁定超时） 这可能导致 MessageBox 表 （Spool 和应用程序队列） 不断增长，引起数据库膨胀，最终限制从而导致较低的整体稳定吞吐量。</span><span class="sxs-lookup"><span data-stu-id="931d5-105">If the disks are slow (low % Disk Idle Time), this can cause SQL to hold onto locks longer (high Lock Wait Time and high Lock Timeouts) which can cause the MessageBox tables (Spool and Application Queues) to grow, causing database bloat and throttling ultimately resulting in lower overall sustainable throughput.</span></span>  
  
 <span data-ttu-id="931d5-106">为了避免磁盘争用，建议您以下：</span><span class="sxs-lookup"><span data-stu-id="931d5-106">To avoid disk contention, it is recommended that you do the following:</span></span>  
  
-   <span data-ttu-id="931d5-107">使用高速 （多轴） 磁盘。</span><span class="sxs-lookup"><span data-stu-id="931d5-107">Use of high speed (multiple spindles) disks.</span></span>  
  
-   <span data-ttu-id="931d5-108">如果可能，部署高速 SAN 上的数据库。</span><span class="sxs-lookup"><span data-stu-id="931d5-108">If possible, deploy the databases on a high speed SAN.</span></span> <span data-ttu-id="931d5-109">如果多个数据库共享相同的磁盘，建议在单独的专用磁盘上配置这些。</span><span class="sxs-lookup"><span data-stu-id="931d5-109">If multiple databases are sharing the same disks it is recommended to configure them on separate dedicated disks.</span></span> <span data-ttu-id="931d5-110">此外建议来分隔到不同的磁盘上的 MessageBox 数据库的 MDF 和 LDF 文件。</span><span class="sxs-lookup"><span data-stu-id="931d5-110">In addition it is recommended to separate the MDF and LDF files for the MessageBox database onto separate disks.</span></span>  
  
-   <span data-ttu-id="931d5-111">如果 SQL 可用的 CPU，请考虑将 MessageBox 数据库是从跟踪数据库的单独的专用服务器上。</span><span class="sxs-lookup"><span data-stu-id="931d5-111">If SQL is starved for CPU, consider separating the MessageBox database onto a dedicated server that is separate from the Tracking databases.</span></span>  
  
-   <span data-ttu-id="931d5-112">设置后将 MessageBox 数据库专用服务器，请考虑通过升级 CPU 的和/或增加 CPU 的扩展。</span><span class="sxs-lookup"><span data-stu-id="931d5-112">After setting up a dedicated server for the MessageBox database, consider scaling up by upgrading the CPU’s and/or adding more CPU’s.</span></span> <span data-ttu-id="931d5-113">监视 SQL Server 上的本地驱动器，因为 MSDTC 日志保存在本地驱动器 (C:\WINDOWS\system32\Msdtc)。</span><span class="sxs-lookup"><span data-stu-id="931d5-113">Monitor the local drive on the SQL-Server as the MSDTC logs are saved on the local drive (C:\WINDOWS\system32\Msdtc).</span></span>  
  
-   <span data-ttu-id="931d5-114">如果由于页面文件或 MSDTC 日志的本地驱动器上的争用，请尝试将 PageFile 和/或 MSDTC 日志移到单独的驱动器。</span><span class="sxs-lookup"><span data-stu-id="931d5-114">If there is contention on the local drive due to the PageFile or MSDTC log, try moving the PageFile and/or the MSDTC log to a separate drive.</span></span>