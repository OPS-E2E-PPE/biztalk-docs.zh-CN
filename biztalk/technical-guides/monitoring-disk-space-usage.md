---
title: "监视磁盘空间使用情况 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ae87de0b00e70ae03a30dd8ef20ede4a972388d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-disk-space-usage"></a><span data-ttu-id="25502-102">监视磁盘空间使用情况</span><span class="sxs-lookup"><span data-stu-id="25502-102">Monitoring Disk Space Usage</span></span>
<span data-ttu-id="25502-103">作为操作的准备情况的监视过程的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，监视的磁盘空间使用情况，如下所示：</span><span class="sxs-lookup"><span data-stu-id="25502-103">As part of the monitoring process for operational readiness of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], monitor the disk space usage as follows:</span></span>  
  
-   <span data-ttu-id="25502-104">**确定磁盘所需空间。**</span><span class="sxs-lookup"><span data-stu-id="25502-104">**Determine the disk space required.**</span></span>  
  
     <span data-ttu-id="25502-105">当使用文件或 MSMQ 发送 / 接收位置时，请确保没有足够的磁盘空间可容纳的停机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或接收的系统。</span><span class="sxs-lookup"><span data-stu-id="25502-105">When using File or MSMQ send / receive locations, ensure that there is ample disk space available to accommodate outages of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or of the receiving systems.</span></span> <span data-ttu-id="25502-106">例如，如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是 SAN 上的共享文件写入并且接收系统已关闭，为两天，确定是否有足够的磁盘空间以允许文件后，若要进行排队。</span><span class="sxs-lookup"><span data-stu-id="25502-106">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is writing files to a share on a SAN and the receiving system is down for two days, determine whether there is enough disk space to allow the files to queue up.</span></span>  
  
-   <span data-ttu-id="25502-107">**定期清理 BizTalk Server 备份文件目录。**</span><span class="sxs-lookup"><span data-stu-id="25502-107">**Clean up the BizTalk Server backup files directory periodically.**</span></span>  
  
     <span data-ttu-id="25502-108">你可以执行使用脚本从 SQL Server 代理作业调用此清理。</span><span class="sxs-lookup"><span data-stu-id="25502-108">You can perform this cleanup using a script called from a SQL Server Agent job.</span></span>  
  
-   <span data-ttu-id="25502-109">**定期清理 BizTalk 跟踪数据库存档文件目录。**</span><span class="sxs-lookup"><span data-stu-id="25502-109">**Clean up the BizTalk Tracking database archive files directory periodically.**</span></span>  
  
-   <span data-ttu-id="25502-110">**确保有足够的磁盘空间可用于在峰值数据流中的时间期间容纳更大的 BizTalk Server 数据库 (.mdf) 和事务日志 (.ldf) 文件。**</span><span class="sxs-lookup"><span data-stu-id="25502-110">**Ensure that there is sufficient disk space available to accommodate larger BizTalk Server database (.mdf) and transaction log (.ldf) files during times of peak data flow.**</span></span>