---
title: 纵向扩展 BizTalk Server 层 |Microsoft Docs
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
ms.openlocfilehash: 6debecada3269374e2fd6f91a06d9e120c2538e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308811"
---
# <a name="scaling-up-the-biztalk-server-tier"></a>纵向扩展 BizTalk Server 层
若要纵向扩展 BizTalk 层，你需要升级 CPU、 内存、 IO 和其他资源。 下图显示了如何您可能会纵向扩展 BizTalk 层从双处理器计算机为四个处理器的计算机的示例。  
  
 ![缩放&#45;向上 BTS](../core/media/scaleupbts.gif "ScaleUpBTS")  
  
 纵向扩展 BizTalk 层的情况是类似于当您选择向外扩展：  
  
-   BizTalk Server 成为瓶颈。 该瓶颈本身可能会造成以下问题之一导致:  
  
-   CPU:如果本方案使用 CPU 密集型管道、 映射或业务流程，BizTalk server 将没有任何额外的 CPU 余量。  
  
-   内存和 I/O:如果现有计算机已达到其对内存和 IO 和要升级的计算机需要的最大限制。  
  
-   向外扩展成本十分高昂。  
  
-   如果是横向扩展不能解决瓶颈。 例如，向外扩展不能解决以下瓶颈问题：  
  
    -   大消息转换  
  
    -   大量的每个交换的消息  
  
    -   某些 BTS 组件，例如，管道或适配器的高内存使用率  
  
    -   传输，例如 EDI  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a>当您无法纵向扩展 BizTalk 层  
  
-   MessageBox 数据库是瓶颈。  
  
-   适配器成为瓶颈。 例如，如果使用适配器后增加 BizTalk 接收器的数量，锁争用可能会增加在其中的 BizTalk 适配器从其请求数据的后端应用程序。 这将限制增加该适配器的能力。  
  
## <a name="see-also"></a>请参阅  
 [向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md)   
 [纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展发送主机](../core/scaled-out-sending-hosts.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展数据库](../core/scaled-out-databases.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)