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
ms.openlocfilehash: 068bea9427ad82621307b0db41714aa2f9db49d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308689"
---
# <a name="scaling-your-solutions"></a>缩放你的解决方案
BizTalk Server 体系结构提供可扩展性很好的支持。 你选择的缩放模式取决于你的方案、 硬件和吞吐量/延迟要求的复杂性。 您应启动较小的拓扑最初并尝试纵向扩展或向下本部分中的准则。  
  
## <a name="scaling-out-and-scaling-up"></a>向外扩展和向上扩展  
 有两种方法来扩展 BizTalk Server 系统：  
  
- 向外扩展是添加其他计算机的过程。 例如，如果 BizTalk Server 通过 CPU 资源出现瓶颈，添加另一台服务器提供双倍的 CPU 资源，从而可以提供双倍的吞吐量。  
  
- 向上扩展是升级现有计算机的过程。 例如，可以在 BizTalk Server 计算机从 4 处理器计算机升级到 8 处理器。  
  
  BizTalk Server 系统有两个层： BizTalk Server 层和 SQL Server 层，其中包含您的 MessageBox 数据库。 在任何方案中，可以向外扩展或纵向扩展每个层。 也就是说，可以横向扩展 BizTalk Server 和 MessageBox 数据库中，也可以纵向扩展这两个值。  
  
  在大多数情况下，BizTalk 层则成为瓶颈第一次，并开始通过进行扩展来提高性能。但是，在某些时候，具体取决于您的系统以及所使用的硬件的复杂程度，您不能向外扩展 BizTalk 层不再而且 SQL Server 层则成为瓶颈。 然后，纵向扩展 SQL Server 层，并对其进行横向扩展通过添加多个 MessageBox 数据库。  
  
> [!NOTE]
>  新的 MessageBox 数据库并不一定意味着此处另一台服务器。 单个 SQL server 可以有多个 MessageBox 数据库。 此外，多个 MessageBox 数据库会导致 DTC 开销和网络跃点如果数据库位于不同的计算机上。  
  
 从理论上讲，SQL Server 层可以无限向外扩展，只要主 MessageBox 数据库未达饱和。  
  
 在本部分中的主题介绍这些扩展模式更多详细信息。 此外介绍了如何扩展每个模式以及如何确定何时不再可以使用该模式来扩展系统。  
  
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