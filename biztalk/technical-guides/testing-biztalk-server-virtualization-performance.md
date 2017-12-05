---
title: "测试 BizTalk Server 虚拟化性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d45567918cebd18bfea7bf30f31b299f6bed02d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="testing-biztalk-server-virtualization-performance"></a>测试 BizTalk Server 虚拟化性能
在本指南中所述的性能测试方案的每个已部署在 Microsoft 测试实验室中，物理计算机上以及然后在每个不同的系统体系结构上执行相同的负载测试了。 每台物理计算机上的主机操作系统已完全安装的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、 64 位版本，安装了 HYPER-V 服务器角色。 用于测试 BizTalk Server 中的虚拟机使用已设置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、 作为来宾操作系统的 64 位版本。 用于测试 SQL Server 的虚拟机使用已设置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、 作为来宾操作系统的 64 位版本。 测试方案、 测试方法、 性能测试结果和后续分析用于制定一系列的最佳实践和指南设计，实现时，以及优化虚拟化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   **测试方案 1： 基线**– 第一个方案旨在来确定在仅物理硬件上运行的 BizTalk Server 环境的基准性能。 对于此方案 BizTalk Server 和 SQL Server 已安装，在仅物理硬件上运行。  
  
-   **测试方案 2： 虚拟 BizTalk Server/物理 SQL Server**的第二个方案都可以确定在同一台物理服务器上的多个来宾虚拟机上托管 BizTalk Server 的性能影响。 从多个虚拟机配置了然后相比物理机处理具有相同数量的逻辑处理器的总的数字的形式执行的测试结果分散的所有虚拟机。  
  
-   **在单独的物理 HYPER-V 主机上的测试方案 3： 虚拟 BizTalk Server/虚拟 SQL Server** -执行的第三个方案，以确定虚拟化环境中运行 BizTalk Server 和 SQL Server 的性能影响。 使用 BizTalk Server HYPER-V 虚拟机上运行与 BizTalk 数据库托管在 HYPER-V 虚拟机上运行的 SQL Server 实例上执行测试。 对于此方案中，BizTalk Server 虚拟机和 SQL Server 虚拟机已托管在单独的物理 HYPER-V 主机。  
  
-   **测试方案 4： 服务器合并-将完整 BizTalk 组包括 SQL 到 HYPER-V 上的一台物理服务器合并**– 在此方案中，运行测试应用程序所需的所有虚拟机 (Vm) 将都托管在一台物理服务器。 这种情况下的用途是确定承载 SQL Server 和 BizTalk Server 中合并的环境的虚拟机的性能成本。  
  
 本部分提供测试应用程序和用于每个方案的服务器体系结构的概述，并还会显示在测试期间观察到的关键性能指标 (Kpi)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [测试方案概述](../technical-guides/test-scenario-overview.md)  
  
-   [测试方案服务器体系结构](../technical-guides/test-scenario-server-architecture.md)  
  
-   [测试结果：BizTalk Server 关键性能指标](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [测试结果：SQL Server 关键性能指标](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [测试结果：网络服务关键性能指标](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [测试结果：内存关键性能指标](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [测试结果摘要](../technical-guides/summary-of-test-results.md)