---
title: 优化数据库性能 |Microsoft Docs
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
ms.openlocfilehash: 2d8dda22976bfd6770fd09b5b98d02f630f7cb28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291434"
---
# <a name="optimizing-database-performance"></a><span data-ttu-id="84fc8-102">优化数据库性能</span><span class="sxs-lookup"><span data-stu-id="84fc8-102">Optimizing Database Performance</span></span>
<span data-ttu-id="84fc8-103">BizTalk Server 是非常占用大量数据库的应用程序，可能需要创建的 SQL Server 中的最多 13 个数据库。</span><span class="sxs-lookup"><span data-stu-id="84fc8-103">BizTalk Server is an extremely database-intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="84fc8-104">由于 BizTalk Server 的主要设计目标之一是不确保丢失任何消息，BizTalk Server 将数据保存到磁盘很好的频率和此外，MSDTC 事务的上下文中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="84fc8-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="84fc8-105">因此，数据库性能至关重要的任何 BizTalk Server 解决方案的整体性能。</span><span class="sxs-lookup"><span data-stu-id="84fc8-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="84fc8-106">本部分介绍了最大程度提高 SQL Server 的性能，以及特定于 BizTalk Server 环境的最大程度提高数据库性能的方法的常规方法。</span><span class="sxs-lookup"><span data-stu-id="84fc8-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="84fc8-107">有关优化 BizTalk 数据库性能的其他信息，请参阅[BizTalk 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=101578)(http://go.microsoft.com/fwlink/?LinkId=101578)。</span><span class="sxs-lookup"><span data-stu-id="84fc8-107">For additional information about optimizing BizTalk database performance, see the [BizTalk Database Optimization whitepaper](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84fc8-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="84fc8-108">In This Section</span></span>  
  
-   [<span data-ttu-id="84fc8-109">预配置数据库 Optimizations2</span><span class="sxs-lookup"><span data-stu-id="84fc8-109">Pre-Configuration Database Optimizations2</span></span>](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [<span data-ttu-id="84fc8-110">配置后数据库 Optimizations2</span><span class="sxs-lookup"><span data-stu-id="84fc8-110">Post-Configuration Database Optimizations2</span></span>](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [<span data-ttu-id="84fc8-111">优化文件组的数据库 2</span><span class="sxs-lookup"><span data-stu-id="84fc8-111">Optimizing Filegroups for the Databases2</span></span>](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [<span data-ttu-id="84fc8-112">BizTalk Server MessageBox 数据库文件组 SQL 脚本</span><span class="sxs-lookup"><span data-stu-id="84fc8-112">BizTalk Server MessageBox Database Filegroups SQL Script</span></span>](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [<span data-ttu-id="84fc8-113">监视 SQL Server 性能</span><span class="sxs-lookup"><span data-stu-id="84fc8-113">Monitoring SQL Server Performance</span></span>](../technical-guides/monitoring-sql-server-performance.md)