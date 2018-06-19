---
title: 优化数据库性能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a95caf60-f1f5-458f-8a81-0aead88f07be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe9148c5b14c5c915de9a8d16699856922e051a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298725"
---
# <a name="optimizing-database-performance"></a>优化数据库性能
BizTalk Server 是极占用大量数据库的应用程序可能需要最多 13 SQL Server 数据库的创建。 由于 BizTalk Server 的主要设计目标之一是确保任何消息会丢失，BizTalk 服务器仍然数据存储到磁盘存在很好的频率和此外，MSDTC 事务的上下文中执行此。 因此，数据库性能至关重要的 BizTalk Server 中的任何解决方案的总体性能。  
  
 本部分介绍了最大程度地 SQL Server 的性能，以及特定于 BizTalk Server 环境最大程度地数据库性能的方法的常规方法。 有关优化 BizTalk 数据库性能的其他信息，请参阅[BizTalk 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=101578)(http://go.microsoft.com/fwlink/?LinkId=101578)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [针对 Databases2 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [BizTalk Server MessageBox 数据库文件组的 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [监视 SQL Server 的性能](../technical-guides/monitoring-sql-server-performance.md)