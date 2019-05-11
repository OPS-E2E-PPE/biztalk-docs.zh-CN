---
title: 优化网络性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6c3985a-48b3-489b-8fe3-3b7bfd0515f9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d58dcac30f2f2395aa9407aaf18fd039c3458f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291380"
---
# <a name="optimizing-network-performance"></a><span data-ttu-id="537a5-102">优化网络性能</span><span class="sxs-lookup"><span data-stu-id="537a5-102">Optimizing Network Performance</span></span>
<span data-ttu-id="537a5-103">在 BizTalk Server 环境中 BizTalk Server 计算机的 SQL 服务器计算机独立开来的位置，由 BizTalk Server 处理的每个消息需要通过网络通信。</span><span class="sxs-lookup"><span data-stu-id="537a5-103">In a BizTalk Server environment where the BizTalk Server computer is separate from the SQL Server computer, each and every message processed by BizTalk Server requires communication over the network.</span></span> <span data-ttu-id="537a5-104">此通信包括 BizTalk Server 计算机和 BizTalk MessageBox 数据库、 BizTalk 管理数据库、 BAM 数据库和其他数据库之间的大量流量。</span><span class="sxs-lookup"><span data-stu-id="537a5-104">This communication includes considerable traffic between the BizTalk Server computer and the BizTalk MessageBox database, the BizTalk Management database, the BAM databases, and other databases.</span></span> <span data-ttu-id="537a5-105">在高负载情况下，此通信可能会导致大量网络流量，可能成为瓶颈，尤其是在没有优化网络设置、 安装没有足够的网络接口卡，或没有足够的网络带宽可用。</span><span class="sxs-lookup"><span data-stu-id="537a5-105">In high-load scenarios, this communication can result in considerable network traffic and can become a bottleneck, especially when network settings have not been optimized, not enough network interface cards are installed, or insufficient network bandwidth is available.</span></span>  
  
 <span data-ttu-id="537a5-106">本部分提供了提高网络性能的一些常规建议，并介绍了几个可以修改，以优化网络堆栈，以缓解瓶颈在网络上的匹配项的注册表项。</span><span class="sxs-lookup"><span data-stu-id="537a5-106">This section provides some general recommendations for improving network performance and describes several registry entries that can be modified to optimize the network stack to mitigate the occurrence of bottlenecks on the network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="537a5-107">在本部分中建议的一些要求修改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="537a5-107">Some of the recommendations in this section require modifications to the Windows registry.</span></span> <span data-ttu-id="537a5-108">对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="537a5-108">Incorrect use of Registry Editor may cause problems requiring you to reinstall your operating system.</span></span> <span data-ttu-id="537a5-109">请慎用注册表编辑器，风险自负。</span><span class="sxs-lookup"><span data-stu-id="537a5-109">Use Registry Editor at your own risk.</span></span> <span data-ttu-id="537a5-110">有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章[256896，"Windows 注册表信息对于高级用户"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729)。</span><span class="sxs-lookup"><span data-stu-id="537a5-110">For more information about how to back up, restore, and modify the registry, see the Microsoft Knowledge Base article [256896, "Windows registry information for advanced users"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="537a5-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="537a5-111">In This Section</span></span>  
  
-   [<span data-ttu-id="537a5-112">优化网络性能的通用指南</span><span class="sxs-lookup"><span data-stu-id="537a5-112">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [<span data-ttu-id="537a5-113">优化网络性能的可修改设置</span><span class="sxs-lookup"><span data-stu-id="537a5-113">Settings that can be Modified to Improve Network Performance</span></span>](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a><span data-ttu-id="537a5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="537a5-114">See Also</span></span>  
 [<span data-ttu-id="537a5-115">优化性能</span><span class="sxs-lookup"><span data-stu-id="537a5-115">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)