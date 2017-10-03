---
title: "测试结果： SQL Server 关键绩效指标 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2459ee6d-7a75-4338-ba5c-f42ab673ab87
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e1f1bdef55ad726c308902062dccff67eeb170
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="test-results-sql-server-key-performance-indicators"></a>测试结果： SQL Server 关键绩效指标
本主题总结了 SQL Server 关键绩效指标 (KPI) 测试方案期间观察到。 这些测试评估以下 SQL Server KPI:  
  
-   SQL 处理器使用率测量**\SQL\Processor(_Total)\\%Processor Time**性能监视器计数器。  
  
-   每秒为单位，由接收的 TRANSACT-SQL 命令批数**\SQL Server:SQL Statistics\Batch 每秒请求数**性能监视器计数器。  
  
## <a name="summary-of-sql-server-key-performance-indicators"></a>SQL Server 关键绩效指标的摘要  
 每个方案的物理机被限制，以便已等效的逻辑处理器和虚拟处理器数。 执行此操作使用 /maxmem 和 /numproc boot.ini 开关。 有关使用这些开关的详细信息，请参阅"启动 INI 选项参考"在[http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139)。  
  
 **SQL Server 关键绩效指标 – 比较**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]处理器使用率测量**\SQL\Processor(_Total)\\%Processor Time**计数器已大约上所有相同测试环境中，为高 90.1%介于 88%低。   但是还有之间存在显著差异**\SQL Server:SQL Statistics\Batch 每秒请求数**测量合并环境 (4520) 和**\SQL Server:SQL Statistics\Batch 每秒请求数**测量物理环境 (6350)。 **\SQL Server:SQL Statistics\Batch 每秒请求数**性能监视器计数器提供了多少工作由 SQL Server 正在执行的良好指标。 减少批处理每秒请求数在 HYPER-V 环境中运行 SQL Server 时可以被归因于 hyper-v 所需的 CPU 开销。  
  
 没有，但是，存在重大差异**\SQL Server:SQL Statistics\Batch 每秒请求数**测量合并环境 (4520) 和**\SQL Server:SQL Statistics\Batch 每秒请求数**测量物理环境 (6350)。 **\SQL Server:SQL Statistics\Batch 每秒请求数**性能监视器计数器提供了多少工作由 SQL Server 正在执行的良好指标。 减少批处理每秒请求数在 HYPER-V 环境中运行 SQL Server 时可以被归因于 hyper-v 所需的 CPU 开销。  
  
 请按照下列步骤以提高性能测量的 HYPER-V 虚拟机上运行的 SQL Server **\SQL Server:SQL Statistics\Batch 每秒请求数**性能监视器计数器：  
  
1.  **分配其他固定的 VHD 磁盘与专用虚拟控制器和通道 –**分配其他固定 VHD 磁盘使用的专用虚拟控制器，通道将增加而不是使用单个 VHD 磁盘的磁盘吞吐量。  
  
2.  **优化网络性能 –**按照的"优化网络性能"部分中所述步骤[清单： HYPER-V 上优化性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。 在同一台 HYPER-V 主机上运行多个 HYPER-V 虚拟机时是非常重要，遵循"在相同的 HYPER-V 运行的配置 HYPER-V 虚拟机宿主计算机以使用专用虚拟网络"部分中的建议[网络优化](../technical-guides/network-optimizations.md)。  
  
 无状态性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 其他[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]虚拟机可轻松添加到环境需要提供向外的扩展，并提高系统的整体性能。  
  
 下图阐释了在不同的测试平台上的 SQL Server 的性能：  
  
 ![SQL 关键绩效指标](../technical-guides/media/sqlkpi.gif "SQLKPI")  
SQL 关键绩效指标  
  
 下表说明了每个配置的收集 KPI 的相对性能。 每个结果集计算的基线配置 KPI 百分比  
  
|KPI|虚拟 BizTalk/物理 SQL|在单独的主机的虚拟 BizTalk/虚拟 SQL|合并环境上的虚拟 BizTalk/虚拟 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\SQL\Processor(_Total)\\处理器时间百分比|97.7%|98.4%|99.9%|  
|\SQL server: SQL Statistics\Batch 每秒请求数|97.1%|83.3%|71.2%|  
  
 有关如何评估磁盘 I/O 性能的详细信息，请参阅**测量磁盘输入/输出性能**主题的部分[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
 有关在 HYPER-V 环境中运行 SQL Server 2008 时的最佳做法的详细信息，请参阅白皮书"运行 SQL Server 2008 in a HYPER-V 环境 – 最佳做法和性能建议"下载[http: / / go.microsoft.com/fwlink/？LinkId = 144622](http://go.microsoft.com/fwlink/?LinkId=144622)。