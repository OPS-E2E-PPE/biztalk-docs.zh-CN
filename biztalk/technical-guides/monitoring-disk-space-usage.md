---
title: 监视磁盘空间使用情况 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12a0b8f020457679f2769e188e8c1936a1cb1869
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253343"
---
# <a name="monitoring-disk-space-usage"></a><span data-ttu-id="5fa61-102">监视磁盘空间使用情况</span><span class="sxs-lookup"><span data-stu-id="5fa61-102">Monitoring Disk Space Usage</span></span>
<span data-ttu-id="5fa61-103">操作就绪性的监视过程的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，监视磁盘空间使用情况，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5fa61-103">As part of the monitoring process for operational readiness of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], monitor the disk space usage as follows:</span></span>  

- <span data-ttu-id="5fa61-104">**确定该磁盘所需的空间。**</span><span class="sxs-lookup"><span data-stu-id="5fa61-104">**Determine the disk space required.**</span></span>  

   <span data-ttu-id="5fa61-105">当使用 File 或 MSMQ 发送 / 接收位置时，请确保是否有足够的磁盘空间可容纳的停机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或接收系统。</span><span class="sxs-lookup"><span data-stu-id="5fa61-105">When using File or MSMQ send / receive locations, ensure that there is ample disk space available to accommodate outages of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or of the receiving systems.</span></span> <span data-ttu-id="5fa61-106">例如，如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是在 SAN 上的写入文件到共享和接收系统故障时间为两天，确定是否有足够的磁盘空间允许文件进行排队。</span><span class="sxs-lookup"><span data-stu-id="5fa61-106">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is writing files to a share on a SAN and the receiving system is down for two days, determine whether there is enough disk space to allow the files to queue up.</span></span>  

- <span data-ttu-id="5fa61-107">**定期清理 BizTalk Server 的备份文件目录。**</span><span class="sxs-lookup"><span data-stu-id="5fa61-107">**Clean up the BizTalk Server backup files directory periodically.**</span></span>  

   <span data-ttu-id="5fa61-108">您可以执行此清理使用名为 SQL Server 代理作业的脚本。</span><span class="sxs-lookup"><span data-stu-id="5fa61-108">You can perform this cleanup using a script called from a SQL Server Agent job.</span></span>  

- <span data-ttu-id="5fa61-109">**定期清除 BizTalk 跟踪数据库存档文件目录。**</span><span class="sxs-lookup"><span data-stu-id="5fa61-109">**Clean up the BizTalk Tracking database archive files directory periodically.**</span></span>  

- <span data-ttu-id="5fa61-110">**确保有足够可用磁盘空间来容纳峰值数据流量的时段内的更大的 BizTalk Server 数据库 (.mdf) 和事务日志 (.ldf) 文件。**</span><span class="sxs-lookup"><span data-stu-id="5fa61-110">**Ensure that there is sufficient disk space available to accommodate larger BizTalk Server database (.mdf) and transaction log (.ldf) files during times of peak data flow.**</span></span>
