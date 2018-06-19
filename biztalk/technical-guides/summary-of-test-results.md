---
title: 测试结果摘要 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d95fbaa6-0e07-4086-bea2-0577d39ae7cd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2eebcdef457716cab9ad61415bf3fe46db301b55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302989"
---
# <a name="summary-of-test-results"></a>测试结果的摘要
本主题汇总了将测试方案中的结果。  
  
## <a name="summary-of-test-results"></a>测试结果的摘要  
 [测试 BizTalk 服务器虚拟化性能](../technical-guides/testing-biztalk-server-virtualization-performance.md)节本指南将介绍使用的测试应用程序和各种配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对其运行测试应用程序的环境。 测试的目的是为了比较的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  /  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境在物理硬件上运行 HYPER-V 虚拟机上运行的环境的性能。 关键绩效指标 (Kpi) 度量在测试期间包括以下操作;  
  
1.  消息吞吐量测量上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
2.  请求-响应延迟测量提交同步请求到 Visual Studio 测试客户端上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
3.  处理器利用率和每秒的批处理请求在上观察到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
4.  在上观察到的网络吞吐量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
5.  可用内存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
### <a name="throughput-comparison-sample-results"></a>吞吐量比较示例结果  
 与所有其他因素视为相同，吞吐量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案测量"BizTalk： 消息传送/文档处理数/秒"性能监视器计数器时范围从 67%到 94.3%可达成的吞吐量的同时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境中的计算机已安装在物理硬件上。  
  
 当[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境中的计算机已安装在 HYPER-V 虚拟机上，以显著降低可以观察到的解决方案的吞吐量，吞吐量这种数量缩减可以被归因于 hyper-v 所需的 CPU 开销。  
  
### <a name="latency-comparison-sample-results"></a>延迟比较示例结果  
 使用正在相等，当在 HYPER-V 虚拟机，BizTalk Server 解决方案测量的延迟上运行 BizTalk Server 环境中使用的 BizTalk Server 计算机的所有其他因素"BizTalk： 消息延迟/请求-响应延迟 （秒)"性能监视器计数器范围是从 66.9%到 94.3%可达成延迟的 BizTalk Server 环境中使用的 BizTalk Server 计算机安装在物理硬件上时。  
  
 当[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境中的计算机已安装在 HYPER-V 虚拟机上，以显著降低可以观察到的解决方案的吞吐量，吞吐量这种数量缩减可以被归因于上hyper-v所需的CPU开销[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]虚拟机。  
  
### <a name="sql-server-processor-utilization-and-batch-requests-per-second-sample-results"></a>SQL Server 处理器使用率和每个第二个示例结果的批处理请求  
 SQL Server 处理器使用率测量 \SQL\Processor(_Total)\\%Processor Time 计数器大约已在所有测试环境中，为高 90.1%从 88%低范围相同。 没有但 \SQL Server:SQL Statistics\Batch 之间存在显著差异合并环境 (4520) 的每秒请求数测量和 \SQL Server:SQL Statistics\Batch 每秒请求数测量物理环境 (6350)。 \SQL Server:SQL Statistics\Batch 每秒请求数性能监视器计数器提供了多少工作由 SQL Server 正在执行的良好指标。 减少批处理每秒请求数在 HYPER-V 环境中运行 SQL Server 时可以被归因于 hyper-v 所需的 CPU 开销。  
  
### <a name="biztalk-server-and-sql-server-network-throughput-sample-results"></a>BizTalk Server 和 SQL Server 网络吞吐量示例结果  
 BizTalk Server HYPER-V 虚拟机上运行的网络吞吐量观察到到范围从大约 70%到 96%的实现在 BizTalk 物理服务器上，具体取决于特定的测试环境的网络吞吐量。 HYPER-V 虚拟机上运行的 SQL Server 的网络吞吐量观察到到范围从大约 68%到 81%的实现在物理 SQL 服务器上，再次根据特定的测试环境的网络吞吐量。 观测到的网络吞吐量的增量可以被归因于 HYPER-V 虚拟机监控程序的资源要求。  
  
### <a name="biztalk-server-and-sql-server-available-memory-sample-results"></a>BizTalk Server 和 SQL Server 的可用内存示例结果  
 SQL Server 和 BizTalk Server \Memory\Available Mbytes 性能监视器计数器测量的可用总内存是相当一致的所有测试方案。