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
# <a name="sql-server-optimizations"></a><span data-ttu-id="c9e9b-102">SQL Server 优化</span><span class="sxs-lookup"><span data-stu-id="c9e9b-102">SQL Server Optimizations</span></span>
<span data-ttu-id="c9e9b-103">BizTalk Server 是极数据库密集型应用程序可能需要最多 13 SQL Server 数据库的创建。</span><span class="sxs-lookup"><span data-stu-id="c9e9b-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="c9e9b-104">由于 BizTalk Server 的主要设计目标之一是确保任何消息会丢失，BizTalk 服务器仍然数据存储到磁盘存在很好的频率和此外，MSDTC 事务的上下文中执行此。</span><span class="sxs-lookup"><span data-stu-id="c9e9b-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="c9e9b-105">因此，数据库性能至关重要的 BizTalk Server 中的任何解决方案的总体性能。</span><span class="sxs-lookup"><span data-stu-id="c9e9b-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
 <span data-ttu-id="c9e9b-106">本部分介绍了最大程度地 SQL Server 的性能，以及特定于 BizTalk Server 环境最大程度地数据库性能的方法的常规方法。</span><span class="sxs-lookup"><span data-stu-id="c9e9b-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="c9e9b-107">有关其他信息优化 BizTalk 数据库性能，请参阅 BizTalk 数据库优化 TechNet 文章， [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001)。</span><span class="sxs-lookup"><span data-stu-id="c9e9b-107">For additional information on optimizing BizTalk database performance, see the BizTalk Database Optimization TechNet article at [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9e9b-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="c9e9b-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c9e9b-109">预配置数据库 Optimizations1</span><span class="sxs-lookup"><span data-stu-id="c9e9b-109">Pre-Configuration Database Optimizations1</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="c9e9b-110">后配置数据库 Optimizations1</span><span class="sxs-lookup"><span data-stu-id="c9e9b-110">Post-Configuration Database Optimizations1</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="c9e9b-111">针对 Databases1 优化文件组</span><span class="sxs-lookup"><span data-stu-id="c9e9b-111">Optimizing Filegroups for the Databases1</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)