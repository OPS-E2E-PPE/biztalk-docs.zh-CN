---
title: "SQL Server 优化 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783c09b1155202ac8fe5a964d16c24d33082c26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-optimizations"></a>SQL Server 优化
BizTalk Server 是极数据库密集型应用程序可能需要最多 13 SQL Server 数据库的创建。 由于 BizTalk Server 的主要设计目标之一是确保任何消息会丢失，BizTalk 服务器仍然数据存储到磁盘存在很好的频率和此外，MSDTC 事务的上下文中执行此。 因此，数据库性能至关重要的 BizTalk Server 中的任何解决方案的总体性能。  
  
 本部分介绍了最大程度地 SQL Server 的性能，以及特定于 BizTalk Server 环境最大程度地数据库性能的方法的常规方法。 有关其他信息优化 BizTalk 数据库性能，请参阅 BizTalk 数据库优化 TechNet 文章， [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [预配置数据库 Optimizations1](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [后配置数据库 Optimizations1](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [针对 Databases1 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases1.md)