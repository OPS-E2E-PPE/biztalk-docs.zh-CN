---
title: 优化性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bafa119b-187e-4595-a673-358dc0a109b7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf9354e1b7b8d40452e492b3801d73f1669c37ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291347"
---
# <a name="optimizing-performance"></a><span data-ttu-id="751da-102">优化性能</span><span class="sxs-lookup"><span data-stu-id="751da-102">Optimizing Performance</span></span>
<span data-ttu-id="751da-103">Windows 操作系统的 SQL Server 的默认安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，和 IIS 可以显著优化，可提供最佳性能，对于生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="751da-103">A default installation of the Windows operating system, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and IIS can be significantly optimized to provide optimal performance for a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="751da-104">也可以从默认设置，以显著提高的性能进行调整 WCF 配置参数。</span><span class="sxs-lookup"><span data-stu-id="751da-104">WCF configuration parameters can also be tuned from the default settings to provide significantly improved performance.</span></span> <span data-ttu-id="751da-105">本部分提供了部署生产时应遵循的特定性能优化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="751da-105">This section provides specific performance optimizations that should be followed when deploying a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="751da-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="751da-106">In This Section</span></span>  
  
-   [<span data-ttu-id="751da-107">优化操作系统性能</span><span class="sxs-lookup"><span data-stu-id="751da-107">Optimizing Operating System Performance</span></span>](../technical-guides/optimizing-operating-system-performance.md)  
  
-   [<span data-ttu-id="751da-108">优化网络性能</span><span class="sxs-lookup"><span data-stu-id="751da-108">Optimizing Network Performance</span></span>](../technical-guides/optimizing-network-performance.md)  
  
-   [<span data-ttu-id="751da-109">优化 IIS 性能</span><span class="sxs-lookup"><span data-stu-id="751da-109">Optimizing IIS Performance</span></span>](../technical-guides/optimizing-iis-performance.md)  
  
-   [<span data-ttu-id="751da-110">优化数据库性能</span><span class="sxs-lookup"><span data-stu-id="751da-110">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)  
  
-   [<span data-ttu-id="751da-111">优化 BizTalk Server 性能</span><span class="sxs-lookup"><span data-stu-id="751da-111">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="751da-112">优化业务流程性能</span><span class="sxs-lookup"><span data-stu-id="751da-112">Optimizing Orchestration Performance</span></span>](../technical-guides/optimizing-orchestration-performance.md)  
  
-   [<span data-ttu-id="751da-113">优化 WCF Web 服务性能</span><span class="sxs-lookup"><span data-stu-id="751da-113">Optimizing WCF Web Service Performance</span></span>](../technical-guides/optimizing-wcf-web-service-performance.md)  
  
-   [<span data-ttu-id="751da-114">优化 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="751da-114">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)  
  
-   [<span data-ttu-id="751da-115">Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="751da-115">Windows PowerShell Scripts</span></span>](../technical-guides/windows-powershell-scripts.md)