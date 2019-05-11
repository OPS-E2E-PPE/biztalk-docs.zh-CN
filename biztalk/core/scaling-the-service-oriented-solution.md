---
title: 扩展面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 895b0ad325e9dce4086c90bccf932f73226780e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308911"
---
# <a name="scaling-the-service-oriented-solution"></a><span data-ttu-id="804f4-102">扩展面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="804f4-102">Scaling the Service Oriented Solution</span></span>
<span data-ttu-id="804f4-103">若要扩展解决方案以支持更高的吞吐量，同时保持低消息延迟要求使用该解决方案的内联版本。</span><span class="sxs-lookup"><span data-stu-id="804f4-103">To scale the solution to support higher throughput while maintaining low message latency requires you to use the inline version of the solution.</span></span> <span data-ttu-id="804f4-104">内联解决方案与后端系统进行交互时，会绕过 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="804f4-104">The inline solution bypasses the MessageBox database when interacting with the back-end systems.</span></span>  
  
 <span data-ttu-id="804f4-105">此外可以添加 BizTalk Server 处理服务器来运行业务流程。</span><span class="sxs-lookup"><span data-stu-id="804f4-105">You can also add BizTalk Server processing servers to run orchestrations.</span></span> <span data-ttu-id="804f4-106">这将减少每个服务器的使用率，以便可以快速处理新请求。</span><span class="sxs-lookup"><span data-stu-id="804f4-106">This decreases the utilization of each server so that new requests can be processed quickly.</span></span> <span data-ttu-id="804f4-107">此外可以纵向 MessageBox 服务器，以便有足够的额外容量来处理消息吞吐量。</span><span class="sxs-lookup"><span data-stu-id="804f4-107">You can also scale up the MessageBox server so that it has enough additional capacity to handle the message throughput.</span></span>  
  
 <span data-ttu-id="804f4-108">但是，面向服务的体系结构解决方案不会不受益于具有多个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="804f4-108">However, the service oriented architecture solution does not benefit from having multiple MessageBox databases.</span></span> <span data-ttu-id="804f4-109">多个 Messagebox 需要分布式的事务处理协调器 (DTC) 事务。</span><span class="sxs-lookup"><span data-stu-id="804f4-109">Multiple MessageBoxes require distributed transaction coordinator (DTC) transactions.</span></span> <span data-ttu-id="804f4-110">这些事务会延长总的消息延迟时间。</span><span class="sxs-lookup"><span data-stu-id="804f4-110">The transactions increase overall message latency.</span></span>  
  
 <span data-ttu-id="804f4-111">可以添加 MQSeries 标头信息的管道组件，从而缩短响应时间。</span><span class="sxs-lookup"><span data-stu-id="804f4-111">You can decrease response time by eliminating the pipeline component that adds MQSeries header information.</span></span> <span data-ttu-id="804f4-112">有关详细信息，请参阅[实现面向服务的解决方案的重点](../core/implementation-highlights-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="804f4-112">For more information, see [Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="804f4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="804f4-113">See Also</span></span>  
 [<span data-ttu-id="804f4-114">开发面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="804f4-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)