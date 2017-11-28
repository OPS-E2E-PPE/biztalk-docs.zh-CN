---
title: "缩放服务面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3026664d3a365630c93bf1c61d7cf635fdd9dc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-the-service-oriented-solution"></a><span data-ttu-id="97115-102">缩放服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="97115-102">Scaling the Service Oriented Solution</span></span>
<span data-ttu-id="97115-103">若要扩展解决方案以支持更高的吞吐量，同时保持较短的消息延迟时间，则需要使用该解决方案的内联版本。</span><span class="sxs-lookup"><span data-stu-id="97115-103">To scale the solution to support higher throughput while maintaining low message latency requires you to use the inline version of the solution.</span></span> <span data-ttu-id="97115-104">内联解决方案在与后端系统进行交互时将绕过 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="97115-104">The inline solution bypasses the MessageBox database when interacting with the back-end systems.</span></span>  
  
 <span data-ttu-id="97115-105">也可以添加 BizTalk Server 处理服务器来运行业务流程。</span><span class="sxs-lookup"><span data-stu-id="97115-105">You can also add BizTalk Server processing servers to run orchestrations.</span></span> <span data-ttu-id="97115-106">这样会降低每台服务器的使用率，从而可以迅速处理新的请求。</span><span class="sxs-lookup"><span data-stu-id="97115-106">This decreases the utilization of each server so that new requests can be processed quickly.</span></span> <span data-ttu-id="97115-107">还可以扩展 MessageBox 服务器，以便该服务器具有足够的能力处理消息吞吐量。</span><span class="sxs-lookup"><span data-stu-id="97115-107">You can also scale up the MessageBox server so that it has enough additional capacity to handle the message throughput.</span></span>  
  
 <span data-ttu-id="97115-108">但是，如果具有多个 MessageBox 数据库，则面向服务的体系结构解决方案不会从中受益。</span><span class="sxs-lookup"><span data-stu-id="97115-108">However, the service oriented architecture solution does not benefit from having multiple MessageBox databases.</span></span> <span data-ttu-id="97115-109">如有多个 MessageBox，则要求使用分布式事务处理协调器 (DTC) 事务。</span><span class="sxs-lookup"><span data-stu-id="97115-109">Multiple MessageBoxes require distributed transaction coordinator (DTC) transactions.</span></span> <span data-ttu-id="97115-110">这些事务会延长总的消息延迟时间。</span><span class="sxs-lookup"><span data-stu-id="97115-110">The transactions increase overall message latency.</span></span>  
  
 <span data-ttu-id="97115-111">通过取消用于添加 MQSeries 标头信息的管道组件，可以缩短响应时间。</span><span class="sxs-lookup"><span data-stu-id="97115-111">You can decrease response time by eliminating the pipeline component that adds MQSeries header information.</span></span> <span data-ttu-id="97115-112">有关详细信息，请参阅[实现突出显示的服务面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="97115-112">For more information, see [Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97115-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97115-113">See Also</span></span>  
 [<span data-ttu-id="97115-114">面向开发的服务解决方案</span><span class="sxs-lookup"><span data-stu-id="97115-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)