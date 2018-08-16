---
title: 测试结果： SQL Server 关键性能指标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2459ee6d-7a75-4338-ba5c-f42ab673ab87
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed7f1348a23e6c4b145748ccfc0832c97648bdff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007510"
---
# <a name="test-results-sql-server-key-performance-indicators"></a>测试结果： SQL Server 关键性能指标
本主题总结了 SQL Server 关键性能指标 (KPI) 的测试方案期间观察到。 这些测试评估以下 SQL Server KPI:  
  
-   SQL 处理器使用率由度量**\SQL\Processor(_Total)\\%Processor Time**性能监视器计数器。  
  
-   每秒由度量接收的 TRANSACT-SQL 命令批处理的数目**\SQL Server:SQL Statistics\Batch 请求数/秒**性能监视器计数器。  
  
## <a name="summary-of-sql-server-key-performance-indicators"></a>SQL Server 关键性能指标的摘要  
 对于每个方案的物理机是受限制，以便逻辑处理器和虚拟处理器的数目是等效。 执行此操作使用 /maxmem 和 /numproc boot.ini 开关。 有关使用这些开关的详细信息，请参阅"启动 INI 选项参考"网址[ http://go.microsoft.com/fwlink/?LinkId=122139 ](http://go.microsoft.com/fwlink/?LinkId=122139)。  
  
 **比较 SQL Server 关键性能指标 –** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]处理器使用率由度量**\SQL\Processor(_Total)\\%Processor Time**计数器是大约上所有测试环境中，到较高，90.1%范围内的 88%低。   但是没有显著区别**\SQL Server:SQL Statistics\Batch 请求数/秒**统一的环境 (4520) 上测量和**\SQL Server:SQL Statistics\Batch 请求数/秒**上的物理环境 (6350) 为单位。 **\SQL Server:SQL Statistics\Batch 请求数/秒**性能监视器计数器提供了多少工作由 SQL Server 正在执行的良好指标。 在 Batch Requests/sec 在 HYPER-V 环境中运行 SQL Server 时减少可归因于 hyper-v 所需的 CPU 开销。  
  
 没有，但是，显著区别**\SQL Server:SQL Statistics\Batch 请求数/秒**统一的环境 (4520) 上测量和**\SQL Server:SQL Statistics\Batch 请求数/秒**上的物理环境 (6350) 为单位。 **\SQL Server:SQL Statistics\Batch 请求数/秒**性能监视器计数器提供了多少工作由 SQL Server 正在执行的良好指标。 在 Batch Requests/sec 在 HYPER-V 环境中运行 SQL Server 时减少可归因于 hyper-v 所需的 CPU 开销。  
  
 请按照以下步骤来增加由度量的 HYPER-V 虚拟机上运行的 SQL Server 的性能**\SQL Server:SQL Statistics\Batch 请求数/秒**性能监视器计数器：  
  
1. **分配其他固定的 VHD 磁盘具有专用的虚拟控制器和通道 –** 分配使用的其他固定 VHD 磁盘的专用虚拟控制器，通道将会增加与使用单个 VHD 磁盘的磁盘吞吐量。  
  
2. **优化网络性能 –** 的"优化网络性能"部分中所述的步骤[核对清单： 优化 HYPER-V 上的性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。 多个 HYPER-V 虚拟机相同的 HYPER-V 主机上运行时是非常重要，遵循"相同的 HYPER-V 运行的配置的 HYPER-V 虚拟机宿主计算机以使用专用虚拟网络"部分中的建议[网络优化](../technical-guides/network-optimizations.md)。  
  
   由于无状态性质[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 其他[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]虚拟机可以轻松地添加到环境根据需要提供横向扩展并提高系统的整体性能。  
  
   下图说明了各种测试平台上的 SQL Server 性能：  
  
   ![SQL 关键绩效指标](../technical-guides/media/sqlkpi.gif "SQLKPI")  
   SQL 关键绩效指标  
  
   下表说明了收集 KPI 的每个配置的相对性能。 每个结果集计算的基线配置 KPI 百分比  
  
|KPI|虚拟 BizTalk/物理 SQL|在单独主机上的虚拟 BizTalk/虚拟 SQL|合并环境上的虚拟 BizTalk/虚拟 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\SQL\Processor(_Total)\\处理器时间百分比|97.7%|98.4%|99.9%|  
|\SQL server: SQL Statistics\Batch 请求数/秒|97.1%|83.3%|71.2%|  
  
 有关如何评估磁盘 I/O 性能的详细信息，请参阅**衡量磁盘 I/O 性能**主题的部分[核对清单： 度量 HYPER-V 上的性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
 有关在 HYPER-V 环境中运行 SQL Server 2008 时的最佳做法的详细信息，请参阅白皮书"运行 SQL Server 2008 in a HYPER-V 环境 – 最佳实践和性能建议"下载[ http://go.microsoft.com/fwlink/?LinkId=144622](http://go.microsoft.com/fwlink/?LinkId=144622).