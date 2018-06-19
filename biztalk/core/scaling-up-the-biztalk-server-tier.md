---
title: BizTalk Server 层向上缩放 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55176072cd33e20dd1024bf2d9d1c39bca4567a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270133"
---
# <a name="scaling-up-the-biztalk-server-tier"></a>BizTalk Server 层向上扩展
若要向上扩展 BizTalk 层，则需要升级 CPU、内存、输入/输出以及其他资源。 以下示例图显示了如何从双处理器计算机向上扩展 BizTalk 层到具有四个处理器的计算机：  
  
 ![缩放 &#45; 向上 BTS](../core/media/scaleupbts.gif "ScaleUpBTS")  
  
 向上扩展 BizTalk 层的方案与选择扩展时相似：  
  
-   BizTalk Server 成为瓶颈。 该瓶颈本身可能是由于以下问题之一而导致的：  
  
-   CPU： 如果本方案使用 CPU 密集型管道、 地图或业务流程，BizTalk 服务器将不具有任何额外的 CPU 预留空间。  
  
-   内存和输入/输出：如果现有计算机已达到其对内存和输入/输出的最大限制，则该计算机需要升级。  
  
-   扩展的成本十分高昂。  
  
-   如果扩展不能解决瓶颈问题。 例如，扩展不能解决以下瓶颈问题：  
  
    -   大型消息转换  
  
    -   每个交换中的大量消息  
  
    -   某些 BTS 组件（例如，管道或适配器）的高内存使用率  
  
    -   传输，例如 EDI  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a>在无法向上扩展 BizTalk 层时  
  
-   MessageBox 数据库是瓶颈。  
  
-   适配器成为瓶颈。 例如，如果你使用适配器之后增加 BizTalk 接收方的数量，可能在其中 BizTalk 适配器中提取的数据从后端应用程序上增加锁争用。 这限制适配器向上扩展的能力。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 层向外缩放](../core/scaling-out-the-biztalk-server-tier.md)   
 [SQL Server 层向上扩展](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展的处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展的发送主机](../core/scaled-out-sending-hosts.md)   
 [Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展的数据库](../core/scaled-out-databases.md)   
 [群集的 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)