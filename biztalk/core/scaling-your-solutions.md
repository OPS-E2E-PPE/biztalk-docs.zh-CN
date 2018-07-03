---
title: 缩放你的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7587c25a752c8613701c9177c42fad001e0e267
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994038"
---
# <a name="scaling-your-solutions"></a>缩放你的解决方案
BizTalk Server 结构为可伸缩性提供了非常好的支持。 您选择的扩展模式取决于方案的复杂性、硬件和吞吐量/延迟要求。 最初应从较小的拓扑开始，然后尝试按照本部分中的指导进行向上或向下扩展。  
  
## <a name="scaling-out-and-scaling-up"></a>向外扩展和向上扩展  
 可以通过以下两种方式来扩展 BizTalk Server 系统：  
  
- 向外扩展是添加其他计算机的过程。 例如，如果 BizTalk Server 由于 CPU 资源出现瓶颈，则添加另一个服务器可以提供双倍的 CPU 资源，从而可以提供双倍的吞吐量。  
  
- 向上扩展是升级现有计算机的过程。 例如，可以将 BizTalk Server 计算机从 4 处理器计算机升级到 8 处理器。  
  
  BizTalk Server 系统有两层：BizTalk Server 层和 SQL Server 层，后者包含 MessageBox 数据库。 在任何方案中，都可以横向扩展或纵向扩展每一层。 也就是说，可以横向扩展 BizTalk Server 和 MessageBox 数据库，也可以对它们进行纵向扩展。  
  
  在大多数情况下，BizTalk 层会首先成为瓶颈，因此通过对其进行向外扩展来开始提高性能。但是，某些情况下（具体取决于系统复杂性和所使用的硬件），无法继续向外扩展 BizTalk 层，SQL Server 层则成为瓶颈。 那么，需要纵向扩展 SQL Server 层，然后通过添加更多 MessageBox 数据库对其进行横向扩展。  
  
> [!NOTE]
>  此处，新的 MessageBox 数据库并不一定意味着另一台服务器。 单个 SQL Server 可以具有多个 MessageBox 数据库。 另外，如果数据库位于不同的计算机上，则多个 MessageBox 数据库会导致 DTC 开销和网络跃点。  
  
 理论上，只要主 MessageBox 数据库未达饱和，SQL Server 层就可以无限向外扩展。  
  
 本部分中的主题更详细地介绍了这些扩展模式。 还介绍了如何扩展每个模式，以及如何确定可以不再使用该模式来扩展系统的时间。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [可伸缩性概述](../core/what-is-scalability.md)  
  
-   [向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)  
  
-   [纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a>请参阅  
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展发送主机](../core/scaled-out-sending-hosts.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展数据库](../core/scaled-out-databases.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)