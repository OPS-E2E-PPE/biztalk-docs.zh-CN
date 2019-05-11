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
# <a name="sql-server-optimizations"></a><span data-ttu-id="6d986-102">SQL Server 优化</span><span class="sxs-lookup"><span data-stu-id="6d986-102">SQL Server Optimizations</span></span>
<span data-ttu-id="6d986-103">BizTalk Server 是极其数据库密集型应用程序可能需要创建的 SQL Server 中的最多 13 个数据库。</span><span class="sxs-lookup"><span data-stu-id="6d986-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="6d986-104">由于 BizTalk Server 的主要设计目标之一是不确保丢失任何消息，BizTalk Server 将数据保存到磁盘很好的频率和此外，MSDTC 事务的上下文中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6d986-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="6d986-105">因此，数据库性能至关重要的任何 BizTalk Server 解决方案的整体性能。</span><span class="sxs-lookup"><span data-stu-id="6d986-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
<span data-ttu-id="6d986-106">本部分介绍了最大程度提高 SQL Server 的性能，以及特定于 BizTalk Server 环境的最大程度提高数据库性能的方法的常规方法。</span><span class="sxs-lookup"><span data-stu-id="6d986-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="6d986-107">下面的链接也是有用的资源：</span><span class="sxs-lookup"><span data-stu-id="6d986-107">The following links are also good resources:</span></span> 

- [<span data-ttu-id="6d986-108">BizTalk Server:有关安装、 大小调整、 部署和维护解决方案的建议</span><span class="sxs-lookup"><span data-stu-id="6d986-108">BizTalk Server: Recommendations for Installing, Sizing, Deploying, and Maintaining a Solution</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [<span data-ttu-id="6d986-109">BizTalk Server 性能优化指南</span><span class="sxs-lookup"><span data-stu-id="6d986-109">BizTalk Server Performance Optimization Guide</span></span>](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a><span data-ttu-id="6d986-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6d986-110">Next steps</span></span>
  
-   [<span data-ttu-id="6d986-111">预配置数据库优化</span><span class="sxs-lookup"><span data-stu-id="6d986-111">Pre-Configuration Database Optimizations</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="6d986-112">配置后数据库优化</span><span class="sxs-lookup"><span data-stu-id="6d986-112">Post-Configuration Database Optimizations</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="6d986-113">优化数据库文件组</span><span class="sxs-lookup"><span data-stu-id="6d986-113">Optimizing Filegroups for the Databases</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)