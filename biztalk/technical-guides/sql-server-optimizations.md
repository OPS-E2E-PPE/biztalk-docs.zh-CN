---
title: SQL Server 优化 |Microsoft Docs
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
ms.openlocfilehash: a84b6ec1a2c5febb4f0aafdde3f82f8c4afe1962
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313259"
---
# <a name="sql-server-optimizations"></a>SQL Server 优化
BizTalk Server 是极其数据库密集型应用程序可能需要创建的 SQL Server 中的最多 13 个数据库。 由于 BizTalk Server 的主要设计目标之一是不确保丢失任何消息，BizTalk Server 将数据保存到磁盘很好的频率和此外，MSDTC 事务的上下文中执行此操作。 因此，数据库性能至关重要的任何 BizTalk Server 解决方案的整体性能。  
  
本部分介绍了最大程度提高 SQL Server 的性能，以及特定于 BizTalk Server 环境的最大程度提高数据库性能的方法的常规方法。 下面的链接也是有用的资源： 

- [BizTalk Server:有关安装、 大小调整、 部署和维护解决方案的建议](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [BizTalk Server 性能优化指南](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a>后续步骤
  
-   [预配置数据库优化](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [配置后数据库优化](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [优化数据库文件组](../technical-guides/optimizing-filegroups-for-the-databases1.md)