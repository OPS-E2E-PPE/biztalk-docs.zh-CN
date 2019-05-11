---
title: 测试 BizTalk Server 虚拟化性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10a6b6e04a17cc79469932f7486d45c133fc166d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401186"
---
# <a name="testing-biztalk-server-virtualization-performance"></a>测试 BizTalk Server 虚拟化性能
在本指南中所述的性能测试方案的每个已部署在 Microsoft 测试实验室中，物理计算机上，然后在每个不同的系统体系结构上执行相同的负载测试。 每台物理计算机上的主机操作系统已完全安装的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]企业版、 64 位版本，安装了 HYPER-V 服务器角色。 用于测试 BizTalk Server 使用的虚拟机设置的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]企业版、 作为来宾操作系统的 64 位版本。 用于测试 SQL Server 的虚拟机使用已设置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]企业版、 作为来宾操作系统的 64 位版本。 测试方案、 测试方法、 性能测试结果和后续分析已用于明确表述一系列最佳实践和设计、 实现、 指南和优化虚拟化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- **测试方案 1:基线**– 确定基准性能的仅物理硬件上运行的 BizTalk Server 环境所需的第一个方案。 这种情况下为 BizTalk Server 和 SQL Server 已安装，并仅物理硬件上运行。  
  
- **测试方案 2:虚拟 BizTalk/物理服务器的 SQL Server** -第二个方案都可以确定在同一台物理服务器上的多个来宾虚拟机上托管 BizTalk Server 的性能影响。 测试结果来自配置已然后处理的物理机到比较具有相同数量的逻辑处理器的总数的多个虚拟机分布在所有虚拟机。  
  
- **测试方案 3:在单独的物理 HYPER-V 主机上虚拟 BizTalk 服务器/虚拟 SQL Server** -执行的第三个方案，以确定虚拟化环境中运行 BizTalk Server 和 SQL Server 的性能影响。 使用 BizTalk Server 与 BizTalk 数据库托管在 HYPER-V 虚拟机上运行的 SQL Server 实例上运行的 HYPER-V 虚拟机上执行测试。 对于此方案，BizTalk Server 虚拟机和 SQL Server 虚拟机已托管在单独的物理 HYPER-V 主机上。  
  
- **测试方案 4:服务器合并的合并完整 BizTalk 组包括 SQL 到一台物理服务器上的 HYPER-V** – 在方案中，运行测试应用程序所需的所有虚拟机 (Vm) 都位于一台物理服务器上。 此方案的目的是确定的托管 SQL Server 和统一的环境中的 BizTalk Server 虚拟机的性能成本。  
  
  本部分提供了测试应用程序和用于每个方案的服务器体系结构的概述，并还展示了在测试期间观察到的关键绩效指标 (Kpi)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [测试方案概述](../technical-guides/test-scenario-overview.md)  
  
-   [测试方案服务器体系结构](../technical-guides/test-scenario-server-architecture.md)  
  
-   [测试结果：BizTalk Server 关键性能指标](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [测试结果：SQL Server 关键性能指标](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [测试结果：网络关键性能指标](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [测试结果：内存关键性能指标](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [测试结果摘要](../technical-guides/summary-of-test-results.md)