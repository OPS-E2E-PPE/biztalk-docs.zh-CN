---
title: 服务开发人员计算机设置面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- service solution tutorial, deployment prerequisites
- service solution tutorial, developer servers
ms.assetid: a088696f-c1ee-4578-ac02-af29b6de086b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb3407dbccbc4dccc902892cf04fa71991b8d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239453"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a><span data-ttu-id="0476b-102">面向服务的解决方案的开发人员计算机安装</span><span class="sxs-lookup"><span data-stu-id="0476b-102">Developer Machine Setup for the Service Oriented Solution</span></span>
<span data-ttu-id="0476b-103">面向服务的结构 (SOA) 是一种用于构建分布式系统的方法。</span><span class="sxs-lookup"><span data-stu-id="0476b-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="0476b-104">面向服务的解决方案演示了如何将使用不同协议的几种后端系统聚合为客户端可以使用的单个服务。</span><span class="sxs-lookup"><span data-stu-id="0476b-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="0476b-105">此解决方案将服务与可确保需要满足的服务级别协议的送达和性能特征的方法相集成。</span><span class="sxs-lookup"><span data-stu-id="0476b-105">This solution integrates services with an approach that guarantees delivery and performance characteristics for the service level agreement that you need to satisfy.</span></span>  
  
 <span data-ttu-id="0476b-106">面向服务的解决方案以服务级别协议方案为蓝图构建而成，在服务级别协议方案中，BizTalk Server 以及与其连接的业务 (LOB) 应用程序服务器可以有三秒钟的时间响应服务请求。</span><span class="sxs-lookup"><span data-stu-id="0476b-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="0476b-107">这三秒中的一秒可由 BizTalk Server 占用。</span><span class="sxs-lookup"><span data-stu-id="0476b-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="0476b-108">有三种版本的面向服务解决方案： 适配器、 嵌入式和存根 （stub）。</span><span class="sxs-lookup"><span data-stu-id="0476b-108">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="0476b-109">有关面向服务的解决方案的三个版本之间的差异的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="0476b-109">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span> <span data-ttu-id="0476b-110">作为开发人员，您要通过使用方案的存根版本来获取运行的方案。</span><span class="sxs-lookup"><span data-stu-id="0476b-110">As a developer, you get the scenario running by using the stub version of the scenario.</span></span> <span data-ttu-id="0476b-111">此版本不需要任何 LOB 后端服务器即可运行。</span><span class="sxs-lookup"><span data-stu-id="0476b-111">This version does not require any LOB back-end servers in order to run.</span></span> <span data-ttu-id="0476b-112">此后，您可以使用该方案的适配器版本来了解可以如何对各种适配器和后端服务器进行集成和配置以便将 BizTalk Server 用为单个服务进行响应。</span><span class="sxs-lookup"><span data-stu-id="0476b-112">After this you can use the adapter version of the scenario to learn how various adapters and back-end servers can be integrated and configured to respond using the BizTalk servers as a single service.</span></span> <span data-ttu-id="0476b-113">然后可以度量 BizTalk Server 及其适配器引起的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="0476b-113">You can then measure the latency induced by BizTalk Server and its adapters.</span></span>  
  
 <span data-ttu-id="0476b-114">如果 BizTalk Server 的延迟时间超过其服务需求，则您可以通过安装并运行 SOA 内联版本来绕过 LOB 适配器持久化点。</span><span class="sxs-lookup"><span data-stu-id="0476b-114">If the latency for the BizTalk server is in excess of its service requirement, you can bypass the LOB adapter persistence points by installing and running the SOA in-line version.</span></span> <span data-ttu-id="0476b-115">此版本可绕过适配器，并且随后可绕过这些适配器由于 MessageBox 持久化点而引起的延迟。</span><span class="sxs-lookup"><span data-stu-id="0476b-115">This version bypasses the adapters and subsequently their latency contributions due to the MessageBox persistence point.</span></span> <span data-ttu-id="0476b-116">实际上，内联版本通过 DCOM 等远程过程调用 (RPC) 机制来与后端服务器直接进行通信。</span><span class="sxs-lookup"><span data-stu-id="0476b-116">Instead, the inline version talks straight to the back-end servers through Remote Procedure Calls (RPC) mechanisms such as DCOM.</span></span>  
  
 <span data-ttu-id="0476b-117">MessageBox 暂留点有关的详细信息，请参阅[持久性和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="0476b-117">For more information about the MessageBox persistence point, see [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span>  
  
 <span data-ttu-id="0476b-118">本部署指南介绍了如何在单台计算机上安装和测试面向服务的解决方案的三种版本。</span><span class="sxs-lookup"><span data-stu-id="0476b-118">This deployment guide describes how to install and test the three versions of the service-oriented solution on a single computer.</span></span>  
  
 <span data-ttu-id="0476b-119">有关面向服务的解决方案的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="0476b-119">For more information about the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0476b-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="0476b-120">In This Section</span></span>  
  
-   [<span data-ttu-id="0476b-121">在安装之前面向服务解决方案</span><span class="sxs-lookup"><span data-stu-id="0476b-121">Before Installing the Service Oriented Solution</span></span>](../core/before-installing-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0476b-122">如何安装服务的存根 （stub） 版本面向解决方案</span><span class="sxs-lookup"><span data-stu-id="0476b-122">How to Install the Stub Version of the Service Oriented Solution</span></span>](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0476b-123">如何安装内联和服务的适配器版本面向解决方案</span><span class="sxs-lookup"><span data-stu-id="0476b-123">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0476b-124">如何运行服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="0476b-124">How to Run the Service Oriented Solution</span></span>](../core/how-to-run-the-service-oriented-solution.md)