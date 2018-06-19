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
# <a name="sql-server-optimizations"></a><span data-ttu-id="11cf3-102">SQL Server 优化</span><span class="sxs-lookup"><span data-stu-id="11cf3-102">SQL Server Optimizations</span></span>
<span data-ttu-id="11cf3-103">BizTalk Server 是极数据库密集型应用程序可能需要最多 13 SQL Server 数据库的创建。</span><span class="sxs-lookup"><span data-stu-id="11cf3-103">BizTalk Server is an extremely database intensive application that may require the creation of up to 13 databases in SQL Server.</span></span> <span data-ttu-id="11cf3-104">由于 BizTalk Server 的主要设计目标之一是确保任何消息会丢失，BizTalk 服务器仍然数据存储到磁盘存在很好的频率和此外，MSDTC 事务的上下文中执行此。</span><span class="sxs-lookup"><span data-stu-id="11cf3-104">Because one of the primary design goals of BizTalk Server is to ensure that no messages are lost, BizTalk Server persists data to disk with great frequency and furthermore, does so within the context of an MSDTC transaction.</span></span> <span data-ttu-id="11cf3-105">因此，数据库性能至关重要的 BizTalk Server 中的任何解决方案的总体性能。</span><span class="sxs-lookup"><span data-stu-id="11cf3-105">Therefore, database performance is paramount to the overall performance of any BizTalk Server solution.</span></span>  
  
<span data-ttu-id="11cf3-106">本部分介绍了最大程度地 SQL Server 的性能，以及特定于 BizTalk Server 环境最大程度地数据库性能的方法的常规方法。</span><span class="sxs-lookup"><span data-stu-id="11cf3-106">This section describes general methods for maximizing SQL Server performance as well as methods for maximizing database performance that are specific to a BizTalk Server environment.</span></span> <span data-ttu-id="11cf3-107">下面的链接也是很好的资源：</span><span class="sxs-lookup"><span data-stu-id="11cf3-107">The following links are also good resources:</span></span> 

- [<span data-ttu-id="11cf3-108">有关安装、 调整大小、 部署和维护解决方案的 BizTalk Server： 建议</span><span class="sxs-lookup"><span data-stu-id="11cf3-108">BizTalk Server: Recommendations for Installing, Sizing, Deploying, and Maintaining a Solution</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [<span data-ttu-id="11cf3-109">BizTalk Server 性能优化指南</span><span class="sxs-lookup"><span data-stu-id="11cf3-109">BizTalk Server Performance Optimization Guide</span></span>](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a><span data-ttu-id="11cf3-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="11cf3-110">Next steps</span></span>
  
-   [<span data-ttu-id="11cf3-111">预配置数据库优化</span><span class="sxs-lookup"><span data-stu-id="11cf3-111">Pre-Configuration Database Optimizations</span></span>](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="11cf3-112">配置后数据库优化</span><span class="sxs-lookup"><span data-stu-id="11cf3-112">Post-Configuration Database Optimizations</span></span>](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [<span data-ttu-id="11cf3-113">优化数据库文件组</span><span class="sxs-lookup"><span data-stu-id="11cf3-113">Optimizing Filegroups for the Databases</span></span>](../technical-guides/optimizing-filegroups-for-the-databases1.md)