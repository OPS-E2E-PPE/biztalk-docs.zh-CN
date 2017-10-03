---
title: "查看和测试 SQL Server 群集的故障转移方案配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e7bed17960700aee84631801e3e26cb05b25c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a>查看和测试故障转移方案的 SQL Server 群集配置
Windows 群集和 SQL Server，可以在主动/主动模式下运行 SQL Server 的群集的每个节点都是"活动"和正在运行一个或多个 SQL Server 实例。 这将允许您，例如，具有上一个节点和所有其他的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]另一个节点上的数据库。 这可以最大化群集的硬件使用情况。  
  
 如果你使用此配置，但是，您必须验证每个节点在 SQL Server 群集节点故障转移期间可以同时处理的所有 SQL Server 实例的负载。  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a>为主动/被动群集评估故障转移  
 验证单个节点可以处理的发生 SQL Server 群集节点故障转移的所有 SQL Server 实例的负载时的注意事项包括：  
  
-   故障转移节点是否有足够的 CPU 资源？  
  
-   故障转移节点是否具有足够的内存？  
  
-   是否有足够的网络带宽？  
  
-   故障转移节点可以处理增加的磁盘 I/O 争用？  
  
 测试故障转移时，应评估以下方案：  
  
-   在活动服务器上的电源故障  
  
-   被动的服务器上的电源故障  
  
-   磁盘连接中断  
  
-   在活动节点上中断公用网络连接  
  
-   在活动节点上中断专用网络连接  
  
-   在被动节点上中断公用网络连接  
  
-   在被动节点上中断专用网络连接  
  
-   失败的 SQL Server 服务  
  
-   失败的 SQL Server 代理服务  
  
## <a name="using-an-activeactivepassive-cluster"></a>使用主动/主动/被动群集  
 如果你确定该一个节点不能处理在故障转移方案中的所有 SQL Server 实例，一种替代方法是使用主动/主动/被动聚类分析模型。 主动/主动/被动群集模型会大大提高，始终会有一个被动节点可用于故障转移方案的可能性。  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)