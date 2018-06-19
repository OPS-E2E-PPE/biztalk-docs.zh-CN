---
title: 执行负载测试和吞吐量测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3da46b2dc3208208305e60e9efbfadd0c60d7d32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302109"
---
# <a name="performing-load-and-throughput-testing"></a><span data-ttu-id="672e2-102">执行负载测试和吞吐量测试</span><span class="sxs-lookup"><span data-stu-id="672e2-102">Performing Load and Throughput Testing</span></span>
<span data-ttu-id="672e2-103">你应提供与匹配性能和压力测试的生产环境的环境。</span><span class="sxs-lookup"><span data-stu-id="672e2-103">You should make available an environment that matches your production environment for performance and stress testing.</span></span> <span data-ttu-id="672e2-104">此环境应已安装并运行，如监视代理和防病毒软件的所有标准服务。</span><span class="sxs-lookup"><span data-stu-id="672e2-104">This environment should have all standard services installed and running, such as monitoring agents and antivirus software.</span></span>  
  
## <a name="how-adding-applications-affects-load"></a><span data-ttu-id="672e2-105">添加应用程序会负载的影响</span><span class="sxs-lookup"><span data-stu-id="672e2-105">How Adding Applications Affects Load</span></span>  
 <span data-ttu-id="672e2-106">你还应测试新的 BizTalk 应用程序以及要在生产环境中的相同硬件上运行的其他 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="672e2-106">You should also test new BizTalk applications alongside the other BizTalk applications that are going to run on the same hardware in production.</span></span> <span data-ttu-id="672e2-107">这是因为新的 BizTalk 应用程序将额外的负载的计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="672e2-107">This is because the new BizTalk applications put additional load on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span> <span data-ttu-id="672e2-108">这一点尤其重要限制中使用的算法的主机依照[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="672e2-108">This is especially important in light of the host throttling algorithms that are used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="672e2-109">限制算法监视总的可用资源，并因此额外的负载引起新的 BizTalk 应用程序可能导致限制条件，这会影响所有正在运行的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="672e2-109">The throttling algorithm monitors total available resources and hence the additional load incurred by a new BizTalk application may induce a throttling condition which affects all running BizTalk applications.</span></span> <span data-ttu-id="672e2-110">有关详细信息，请参阅[如何 BizTalk Server 实现主机限制](http://go.microsoft.com/fwlink/?LinkId=154389)(http://go.microsoft.com/fwlink/?LinkId=154389)。</span><span class="sxs-lookup"><span data-stu-id="672e2-110">For more information, see [How BizTalk Server Implements Host Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (http://go.microsoft.com/fwlink/?LinkId=154389).</span></span>  
  
## <a name="testing-load-and-determining-recovery-time"></a><span data-ttu-id="672e2-111">测试负载和确定恢复时间</span><span class="sxs-lookup"><span data-stu-id="672e2-111">Testing Load and Determining Recovery Time</span></span>  
 <span data-ttu-id="672e2-112">你应测试所有 BizTalk 应用程序的性能和压力之前将其放到生产环境。</span><span class="sxs-lookup"><span data-stu-id="672e2-112">You should test all BizTalk applications for performance and stress before you put them into production.</span></span> <span data-ttu-id="672e2-113">你应执行测试针对预期负载和峰值负载。</span><span class="sxs-lookup"><span data-stu-id="672e2-113">You should perform your testing against expected loads and against peak loads.</span></span> <span data-ttu-id="672e2-114">你应该确定 BizTalk 应用程序的最大可持续吞吐量 (MST)。</span><span class="sxs-lookup"><span data-stu-id="672e2-114">You should determine the maximum sustainable throughput (MST) for the BizTalk application.</span></span> <span data-ttu-id="672e2-115">此外，你应该确定时间系统来恢复从峰值负载。</span><span class="sxs-lookup"><span data-stu-id="672e2-115">In addition, you should determine how long it takes the system to recover from peak loads.</span></span> <span data-ttu-id="672e2-116">如果系统未完全恢复从峰值负载之前的下一步的峰值负载发生，则系统会逐渐变得更远，并将不能完全恢复。</span><span class="sxs-lookup"><span data-stu-id="672e2-116">If the system does not fully recover from a peak load before the next peak load occurs, then the system will get progressively farther behind and will not be able to fully recover.</span></span> <span data-ttu-id="672e2-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="672e2-117">For more information, see:</span></span>  
  
-   <span data-ttu-id="672e2-118">[衡量最大可持续引擎吞吐量](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)</span><span class="sxs-lookup"><span data-stu-id="672e2-118">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkId=154388) (http://go.microsoft.com/fwlink/?LinkId=154388)</span></span>  
  
-   <span data-ttu-id="672e2-119">[衡量最大可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)</span><span class="sxs-lookup"><span data-stu-id="672e2-119">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672e2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="672e2-120">See Also</span></span>  
 [<span data-ttu-id="672e2-121">清单： 测试操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="672e2-121">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)