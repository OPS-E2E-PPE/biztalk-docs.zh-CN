---
title: 可伸缩性是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, scalability
ms.assetid: ac6acefd-864a-4f22-a136-a1951fe71e96
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46d74ed168f5dcc5a0d6d314627b6381ae5c4233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395928"
---
# <a name="what-is-scalability"></a>可伸缩性是什么？
可伸缩性是系统的扩展，以满足你的业务需求的功能。 对系统进行扩展通过添加额外的硬件或升级现有硬件，而无需更改多的应用程序。 在 BizTalk Server 系统的上下文中，可伸缩性是指 BizTalk 能够缩放和根据吞吐量需求增加时，如果您需要缩短延迟时间。  
  
 优化和调整 BizTalk 的各个组件后，仍可能会遇到 BizTalk 计算机上或在 MessageBox 数据库上的瓶颈。 类型的 BizTalk 环境中，通常会发生的瓶颈是 CPU、 内存、 IO 和锁争用瓶颈。 当您开始遇到瓶颈时，可能需要升级硬件或新的硬件添加到现有的拓扑。 幸运的是，BizTalk Server 体系结构，可轻松地向上和向外缩放。例如，可以将多个 BizTalk Server 计算机添加到组，并还将添加额外的 MessageBox 数据库。  
  
## <a name="see-also"></a>请参阅  
 [向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md)   
 [纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展发送主机](../core/scaled-out-sending-hosts.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展数据库](../core/scaled-out-databases.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)