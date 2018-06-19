---
title: SQL Server 优化 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36317d99387fde1d7b5e1c56b45255129daedb25
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710800"
---
# <a name="sql-server-optimizations"></a>SQL Server 优化
BizTalk Server 是极数据库密集型应用程序可能需要最多 13 SQL Server 数据库的创建。 由于 BizTalk Server 的主要设计目标之一是确保任何消息会丢失，BizTalk 服务器仍然数据存储到磁盘存在很好的频率和此外，MSDTC 事务的上下文中执行此。 因此，数据库性能至关重要的 BizTalk Server 中的任何解决方案的总体性能。  
  
本部分介绍了最大程度地 SQL Server 的性能，以及特定于 BizTalk Server 环境最大程度地数据库性能的方法的常规方法。 下面的链接也是很好的资源： 

- [有关安装、 调整大小、 部署和维护解决方案的 BizTalk Server： 建议](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [BizTalk Server 性能优化指南](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a>后续步骤
  
-   [预配置数据库优化](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [配置后数据库优化](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [优化数据库文件组](../technical-guides/optimizing-filegroups-for-the-databases1.md)