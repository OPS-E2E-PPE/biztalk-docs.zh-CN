---
title: "如何避免磁盘 Contention1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702665046dbaee77412675e4be0edc602dd9e7e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a><span data-ttu-id="2825c-102">如何避免磁盘争用</span><span class="sxs-lookup"><span data-stu-id="2825c-102">How to Avoid Disk Contention</span></span>
<span data-ttu-id="2825c-103">BizTalk Server 是一种持久性的系统，因而对于高吞吐量的情况，MessageBox 可能会出现严重的资源争用。</span><span class="sxs-lookup"><span data-stu-id="2825c-103">BizTalk Server is designed as a persistent system whereby, for high throughput scenarios, the MessageBox can experience severe contention.</span></span> <span data-ttu-id="2825c-104">缓慢的磁盘速度会进一步加重这种争用状况。</span><span class="sxs-lookup"><span data-stu-id="2825c-104">This contention can be aggravated by slow disks.</span></span> <span data-ttu-id="2825c-105">如果磁盘速度缓慢（低于 % 磁盘空闲时间），则会导致 SQL 保存锁定的时间较长（锁定等待时间长，锁定超时时间长），从而导致 MessageBox 表（Spool 和应用程序队列）变大，引起数据库膨胀，阻止功能被启用，最终导致较低的整体稳定吞吐量。</span><span class="sxs-lookup"><span data-stu-id="2825c-105">If the disks are slow (low % Disk Idle Time), this can cause SQL to hold onto locks longer (high Lock Wait Time and high Lock Timeouts) which can cause the MessageBox tables (Spool and Application Queues) to grow, causing database bloat and throttling ultimately resulting in lower overall sustainable throughput.</span></span>  
  
 <span data-ttu-id="2825c-106">为避免磁盘争用，建议您采取以下措施：</span><span class="sxs-lookup"><span data-stu-id="2825c-106">To avoid disk contention, it is recommended that you do the following:</span></span>  
  
-   <span data-ttu-id="2825c-107">使用高速（多轴）磁盘。</span><span class="sxs-lookup"><span data-stu-id="2825c-107">Use of high speed (multiple spindles) disks.</span></span>  
  
-   <span data-ttu-id="2825c-108">如果可能，在高速 SAN 上部署数据库。</span><span class="sxs-lookup"><span data-stu-id="2825c-108">If possible, deploy the databases on a high speed SAN.</span></span> <span data-ttu-id="2825c-109">如果多个数据库共享相同的磁盘，则建议在不同的专用磁盘上分别配置这些数据库。</span><span class="sxs-lookup"><span data-stu-id="2825c-109">If multiple databases are sharing the same disks it is recommended to configure them on separate dedicated disks.</span></span> <span data-ttu-id="2825c-110">此外，建议将 MessageBox 数据库的 MDF 文件和 LDF 文件分别放在不同的磁盘中。</span><span class="sxs-lookup"><span data-stu-id="2825c-110">In addition it is recommended to separate the MDF and LDF files for the MessageBox database onto separate disks.</span></span>  
  
-   <span data-ttu-id="2825c-111">如果 SQL 可用的 CPU 资源严重不足，请考虑将 MessageBox 数据库部署到跟踪数据库所在服务器之外的其他专用服务器上。</span><span class="sxs-lookup"><span data-stu-id="2825c-111">If SQL is starved for CPU, consider separating the MessageBox database onto a dedicated server that is separate from the Tracking databases.</span></span>  
  
-   <span data-ttu-id="2825c-112">在设置之后 MessageBox 数据库的专用服务器，请考虑向上扩展通过升级 CPU 的和/或添加更多的 CPU。</span><span class="sxs-lookup"><span data-stu-id="2825c-112">After setting up a dedicated server for the MessageBox database, consider scaling up by upgrading the CPU’s and/or adding more CPU’s.</span></span> <span data-ttu-id="2825c-113">MSDTC 日志保存在本地驱动器 (C:\WINDOWS\system32\Msdtc) 进行监视 SQL Server 上的本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="2825c-113">Monitor the local drive on the SQL-Server as the MSDTC logs are saved on the local drive (C:\WINDOWS\system32\Msdtc).</span></span>  
  
-   <span data-ttu-id="2825c-114">如果因 PageFile 或 MSDTC 日志而在本地驱动器上出现争用情况，请尝试将 PageFile 和/或 MSDTC 日志移到不同的驱动器上。</span><span class="sxs-lookup"><span data-stu-id="2825c-114">If there is contention on the local drive due to the PageFile or MSDTC log, try moving the PageFile and/or the MSDTC log to a separate drive.</span></span>