---
title: "监视和减少 DTC 日志文件的磁盘 I/O 争用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7206c4220153ee95f78e5744a2df2ff7eeb3541e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a><span data-ttu-id="8f149-102">监视和减少 DTC 日志文件的磁盘 I/O 争用</span><span class="sxs-lookup"><span data-stu-id="8f149-102">Monitoring and Reducing DTC Log File Disk I/O Contention</span></span>
<span data-ttu-id="8f149-103">分布式事务处理协调器 (DTC) 日志文件可以成为大型事务环境中的磁盘 I/O 瓶颈。</span><span class="sxs-lookup"><span data-stu-id="8f149-103">The Distributed Transaction Coordinator (DTC) log file can become a disk I/O bottleneck in transaction-intensive environments.</span></span> <span data-ttu-id="8f149-104">这在使用支持事务，如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时尤其如此。</span><span class="sxs-lookup"><span data-stu-id="8f149-104">This is especially true when using adapters that support transactions, such as SQL Server, MSMQ, or MQSeries, or in a multi-MessageBox environment.</span></span> <span data-ttu-id="8f149-105">事务的适配器使用 DTC 事务，以及多 MessageBox 环境广泛利用 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="8f149-105">Transactional adapters use DTC transactions, and multi-MessageBox environments make extensive use of DTC transactions.</span></span>  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a><span data-ttu-id="8f149-106">监视群集和非群集环境中的使用情况</span><span class="sxs-lookup"><span data-stu-id="8f149-106">Monitoring Usage in Clustered and Non-Clustered Environments</span></span>  
 <span data-ttu-id="8f149-107">若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘 DTC 日志文件驻留在 SQL Server 数据库服务器上的磁盘 I/O 使用情况。</span><span class="sxs-lookup"><span data-stu-id="8f149-107">To ensure that the DTC log file does not become a disk I/O bottleneck, you should monitor the disk I/O usage for the disk where the DTC log file resides on the SQL Server database server.</span></span>  
  
 <span data-ttu-id="8f149-108">在环境中在群集 SQL Server，这是不尽可能考虑因为日志文件已将共享的驱动器，可能会具有多个轴的快速 SAN 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="8f149-108">In an environment where SQL Server is clustered, this is not as much of a concern because the log file will already be on a shared drive, which will likely be a fast SAN drive with multiple spindles.</span></span> <span data-ttu-id="8f149-109">由于它可能成为瓶颈在非群集环境或 DTC 日志文件时与其他占用大量磁盘的文件的共享磁盘上，不过仍应监视磁盘 I/O 使用情况。</span><span class="sxs-lookup"><span data-stu-id="8f149-109">You should nevertheless still monitor the disk I/O usage since it can become a bottleneck in non-clustered environments or when the DTC log file is on a shared disk with other disk-intensive files.</span></span>  
  
## <a name="troubleshooting-dtc"></a><span data-ttu-id="8f149-110">故障排除 DTC</span><span class="sxs-lookup"><span data-stu-id="8f149-110">Troubleshooting DTC</span></span>  
 <span data-ttu-id="8f149-111">有关疑难解答 DTC 信息，请参阅"使用 MSDTC 疑难解答问题"中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237)。</span><span class="sxs-lookup"><span data-stu-id="8f149-111">For information about troubleshooting DTC, see "Troubleshooting Problems with MSDTC" in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f149-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f149-112">See Also</span></span>  
 [<span data-ttu-id="8f149-113">清单： 配置 Windows Server</span><span class="sxs-lookup"><span data-stu-id="8f149-113">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)