---
title: 查看和测试 SQL Server 群集故障转移方案的配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981a879a5dad68bfb423a03b82e11fb646f912c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973254"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a>查看和测试故障转移方案的 SQL Server 群集配置
Windows 群集和 SQL Server 允许您在主动/主动模式下运行 SQL Server 的群集的每个节点都是"活动"并运行一个或多个 SQL Server 实例。 这将允许您，例如，要使上一个节点和所有其他 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]另一个节点上的数据库。 这可以最大程度提高群集的硬件的使用情况。  
  
 如果使用此配置，但是，必须验证每个节点在 SQL Server 群集节点故障转移期间可以同时处理的所有 SQL Server 实例的负载。  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a>评估故障转移的主动/被动群集  
 验证单个节点可以处理的 SQL Server 群集节点故障转移时的所有 SQL Server 实例的负载时的注意事项包括：  
  
- 在故障转移节点是否有足够的 CPU 资源？  
  
- 在故障转移节点是否有足够的内存？  
  
- 是否有足够的网络带宽？  
  
- 在故障转移节点可以处理增加的磁盘 I/O 争用？  
  
  测试故障转移时，应评估以下方案：  
  
- 在活动服务器上的电源故障  
  
- 被动服务器上的电源故障  
  
- 磁盘连接丢失  
  
- 公共网络连接中断的活动节点上  
  
- 专用网络连接中断的活动节点上  
  
- 在被动节点上断开公共网络连接  
  
- 在被动节点上断开专用网络连接  
  
- 失败的 SQL Server 服务  
  
- 失败的 SQL Server 代理服务  
  
## <a name="using-an-activeactivepassive-cluster"></a>使用主动/主动/被动群集  
 如果您确定一个节点不能处理故障转移方案中的所有 SQL Server 实例，一种替代方法是使用主动/主动/被动聚类分析模型。 主动/主动/被动群集模型会大大提高，始终会有一个被动节点可用于故障转移方案的可能性。  
  
## <a name="see-also"></a>请参阅  
 [清单：配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)