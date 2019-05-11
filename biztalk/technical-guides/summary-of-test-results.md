---
title: 测试结果的摘要 |Microsoft Docs
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
ms.openlocfilehash: e2cacbf9f4375e420fd1a201ca268767377c2d2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400666"
---
# <a name="summary-of-test-results"></a>测试结果的摘要
本主题概述了测试方案的结果。  
  
## <a name="summary-of-test-results"></a>测试结果的摘要  
 [测试 BizTalk Server 虚拟化性能](../technical-guides/testing-biztalk-server-virtualization-performance.md)本指南的本节描述使用的测试应用程序和各种配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对其运行测试应用程序的环境。 执行测试来比较的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  /  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境在物理硬件上运行的 HYPER-V 虚拟机上运行的环境的性能。 关键绩效指标 (Kpi) 度量在测试期间包括以下操作：  
  
1. 消息吞吐量测量上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
2. 请求-响应延迟测量提交同步请求到 Visual Studio 测试客户端上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
3. 处理器利用率和每秒批处理请求上观察到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
4. 在观察到的网络吞吐量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
5. 可用内存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
### <a name="throughput-comparison-sample-results"></a>吞吐量比较示例结果  
 与所有其他因素，吞吐量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案由度量"BizTalk： 消息传送/文档处理数/秒"性能监视器计数器时范围从 67%94.3%的吞吐量可以利用它来同时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境中的计算机已安装在物理硬件上。  
  
 当[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境中的计算机已安装的 HYPER-V 虚拟机上，观察到解决方案的吞吐量来显著降低，这种减少吞吐量可归因于 hyper-v 所需的 CPU 开销。  
  
### <a name="latency-comparison-sample-results"></a>延迟比较示例结果  
 所有其他因素，当在 BizTalk Server 环境中使用的 BizTalk Server 计算机上的 HYPER-V 虚拟机，延迟的测量得出的 BizTalk Server 解决方案运行时使用"BizTalk： 消息延迟/请求-响应延迟 （秒)"性能监视器计数器范围是从 66.9%94.3%的可以利用它来延迟时在物理硬件上安装 BizTalk Server 环境中使用的 BizTalk Server 计算机。  
  
 当[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境中的计算机已安装的 HYPER-V 虚拟机上，观察到解决方案的吞吐量来显著降低，这种减少吞吐量可归因于 hyper-v上所需的CPU开销[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]虚拟机。  
  
### <a name="sql-server-processor-utilization-and-batch-requests-per-second-sample-results"></a>SQL 服务器的处理器利用率和每个第二个示例结果的批处理请求  
 SQL Server 处理器使用率由 \SQL\Processor(_Total) 度量\\%Processor Time 计数器大约是在所有测试环境中，到 90.1%的高 88%较低的范围相同。 但是 \SQL Server:SQL Statistics\Batch 显著区别统一的环境 (4520) 的请求数/秒计量和 \SQL Server:SQL Statistics\Batch 物理环境 (6350) 的请求数/秒计量。 \SQL Server:SQL Statistics\Batch Requests/sec 性能监视器计数器提供了多少工作由 SQL Server 正在执行的良好指标。 在 Batch Requests/sec 在 HYPER-V 环境中运行 SQL Server 时减少可归因于 hyper-v 所需的 CPU 开销。  
  
### <a name="biztalk-server-and-sql-server-network-throughput-sample-results"></a>BizTalk Server 和 SQL Server 网络吞吐量示例结果  
 BizTalk Server 的 HYPER-V 虚拟机上运行的网络吞吐量已观察到范围从大约 70%到 96%的物理 BizTalk 服务器，具体取决于特定的测试环境上实现的网络吞吐量。 HYPER-V 虚拟机上运行的 SQL Server 的网络吞吐量已观察到范围从大约 68%到 81%的实现在物理 SQL 服务器上，再次根据特定的测试环境的网络吞吐量。 可以将观测到的网络吞吐量增量归为 HYPER-V 虚拟机监控程序的资源要求。  
  
### <a name="biztalk-server-and-sql-server-available-memory-sample-results"></a>BizTalk Server 和 SQL Server 的可用内存示例结果  
 可用于 SQL Server 和 BizTalk Server 根据 \Memory\Available Mbytes 性能监视器计数器进行度量总内存是相当一致的所有测试方案。