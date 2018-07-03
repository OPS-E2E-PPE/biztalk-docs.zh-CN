---
title: 执行负载和吞吐量测试 |Microsoft Docs
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
ms.openlocfilehash: 2d4313c073abff7022de99ac1d38375599b6ee43
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966910"
---
# <a name="performing-load-and-throughput-testing"></a><span data-ttu-id="616dd-102">执行负载和吞吐量测试</span><span class="sxs-lookup"><span data-stu-id="616dd-102">Performing Load and Throughput Testing</span></span>
<span data-ttu-id="616dd-103">您应提供匹配的性能和压力测试在生产环境的环境。</span><span class="sxs-lookup"><span data-stu-id="616dd-103">You should make available an environment that matches your production environment for performance and stress testing.</span></span> <span data-ttu-id="616dd-104">此环境应已安装并运行，如监视代理和防病毒软件的所有标准服务。</span><span class="sxs-lookup"><span data-stu-id="616dd-104">This environment should have all standard services installed and running, such as monitoring agents and antivirus software.</span></span>  
  
## <a name="how-adding-applications-affects-load"></a><span data-ttu-id="616dd-105">添加应用程序是如何影响负载</span><span class="sxs-lookup"><span data-stu-id="616dd-105">How Adding Applications Affects Load</span></span>  
 <span data-ttu-id="616dd-106">您还应测试新的 BizTalk 应用程序和要在生产环境中的相同硬件上运行的其他 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="616dd-106">You should also test new BizTalk applications alongside the other BizTalk applications that are going to run on the same hardware in production.</span></span> <span data-ttu-id="616dd-107">这是因为新的 BizTalk 应用程序将额外的负载的计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="616dd-107">This is because the new BizTalk applications put additional load on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span> <span data-ttu-id="616dd-108">这一点尤其重要根据主机阻止算法中使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="616dd-108">This is especially important in light of the host throttling algorithms that are used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="616dd-109">阻止算法监视总的可用资源，因此所产生的新的 BizTalk 应用程序的额外负载可能导致限制条件，这会影响所有正在运行的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="616dd-109">The throttling algorithm monitors total available resources and hence the additional load incurred by a new BizTalk application may induce a throttling condition which affects all running BizTalk applications.</span></span> <span data-ttu-id="616dd-110">有关详细信息，请参阅[如何 BizTalk Server 实现主机阻止](http://go.microsoft.com/fwlink/?LinkId=154389)(<http://go.microsoft.com/fwlink/?LinkId=154389>)。</span><span class="sxs-lookup"><span data-stu-id="616dd-110">For more information, see [How BizTalk Server Implements Host Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (<http://go.microsoft.com/fwlink/?LinkId=154389>).</span></span>  
  
## <a name="testing-load-and-determining-recovery-time"></a><span data-ttu-id="616dd-111">测试负载和确定恢复时间</span><span class="sxs-lookup"><span data-stu-id="616dd-111">Testing Load and Determining Recovery Time</span></span>  
 <span data-ttu-id="616dd-112">应测试性能和压力之前将其放到生产环境的所有 BizTalk 应用的程序。</span><span class="sxs-lookup"><span data-stu-id="616dd-112">You should test all BizTalk applications for performance and stress before you put them into production.</span></span> <span data-ttu-id="616dd-113">您应该执行测试针对预期负载和峰值负载。</span><span class="sxs-lookup"><span data-stu-id="616dd-113">You should perform your testing against expected loads and against peak loads.</span></span> <span data-ttu-id="616dd-114">您应确定为 BizTalk 应用程序的最大可承受吞吐量 (MST)。</span><span class="sxs-lookup"><span data-stu-id="616dd-114">You should determine the maximum sustainable throughput (MST) for the BizTalk application.</span></span> <span data-ttu-id="616dd-115">此外，应确定需要多长时间的峰值负载从恢复的系统。</span><span class="sxs-lookup"><span data-stu-id="616dd-115">In addition, you should determine how long it takes the system to recover from peak loads.</span></span> <span data-ttu-id="616dd-116">如果系统没有完全从此峰值负载下一步的峰值负载之前，则系统将以渐进方式更远全力支持，并且不能充分进行恢复。</span><span class="sxs-lookup"><span data-stu-id="616dd-116">If the system does not fully recover from a peak load before the next peak load occurs, then the system will get progressively farther behind and will not be able to fully recover.</span></span> <span data-ttu-id="616dd-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="616dd-117">For more information, see:</span></span>  
  
-   <span data-ttu-id="616dd-118">[测量最大可承受引擎吞吐量](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)</span><span class="sxs-lookup"><span data-stu-id="616dd-118">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkId=154388) (http://go.microsoft.com/fwlink/?LinkId=154388)</span></span>  
  
-   <span data-ttu-id="616dd-119">[测量最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)</span><span class="sxs-lookup"><span data-stu-id="616dd-119">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="616dd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="616dd-120">See Also</span></span>  
 [<span data-ttu-id="616dd-121">清单：测试操作准备情况</span><span class="sxs-lookup"><span data-stu-id="616dd-121">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)