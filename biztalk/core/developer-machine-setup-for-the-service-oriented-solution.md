---
title: 面向开发人员计算机设置为服务的解决方案 |Microsoft Docs
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
ms.openlocfilehash: c7a296118d9154d51ffc1dba22524a50cc7e76b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351593"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a><span data-ttu-id="23a6b-102">面向开发人员计算机设置为服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="23a6b-102">Developer Machine Setup for the Service Oriented Solution</span></span>
<span data-ttu-id="23a6b-103">面向服务的体系结构 (SOA) 是用于构建分布式的系统的方法。</span><span class="sxs-lookup"><span data-stu-id="23a6b-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="23a6b-104">面向服务的解决方案演示了几种使用不同的协议的后端系统可以整合到单个服务的客户端可以使用。</span><span class="sxs-lookup"><span data-stu-id="23a6b-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="23a6b-105">此解决方案将服务集成与可确保为需要满足的服务级别协议的送达和性能特征的方法。</span><span class="sxs-lookup"><span data-stu-id="23a6b-105">This solution integrates services with an approach that guarantees delivery and performance characteristics for the service level agreement that you need to satisfy.</span></span>  
  
 <span data-ttu-id="23a6b-106">面向的解决方案只现代性的在 BizTalk Server 和业务线 (LOB) 应用程序服务器连接到它的服务级别协议方案的服务提供三秒使用的服务请求进行响应。</span><span class="sxs-lookup"><span data-stu-id="23a6b-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="23a6b-107">这三个秒之一可能由 BizTalk Server 会占用。</span><span class="sxs-lookup"><span data-stu-id="23a6b-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="23a6b-108">有三个版本的面向服务的解决方案： 适配器、 内联和存根 （stub）。</span><span class="sxs-lookup"><span data-stu-id="23a6b-108">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="23a6b-109">有关面向服务的解决方案的三个版本之间的差异的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="23a6b-109">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span> <span data-ttu-id="23a6b-110">作为开发人员，你可以使用该方案的存根版本运行的方案。</span><span class="sxs-lookup"><span data-stu-id="23a6b-110">As a developer, you get the scenario running by using the stub version of the scenario.</span></span> <span data-ttu-id="23a6b-111">若要运行，此版本不需要任何 LOB 后端服务器。</span><span class="sxs-lookup"><span data-stu-id="23a6b-111">This version does not require any LOB back-end servers in order to run.</span></span> <span data-ttu-id="23a6b-112">完成此操作后可以使用方案的适配器版本，若要了解如何对各种适配器和后端服务器可以集成并配置为响应作为单个服务中使用的 BizTalk 服务器。</span><span class="sxs-lookup"><span data-stu-id="23a6b-112">After this you can use the adapter version of the scenario to learn how various adapters and back-end servers can be integrated and configured to respond using the BizTalk servers as a single service.</span></span> <span data-ttu-id="23a6b-113">然后可以度量 BizTalk Server 和及其适配器引起的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="23a6b-113">You can then measure the latency induced by BizTalk Server and its adapters.</span></span>  
  
 <span data-ttu-id="23a6b-114">如果 BizTalk server 的延迟超过其服务需求，您可以通过安装和运行 SOA 内联版本来绕过 LOB 适配器持久化点。</span><span class="sxs-lookup"><span data-stu-id="23a6b-114">If the latency for the BizTalk server is in excess of its service requirement, you can bypass the LOB adapter persistence points by installing and running the SOA in-line version.</span></span> <span data-ttu-id="23a6b-115">此版本将忽略适配器以及随后由于 MessageBox 持久化点延迟贡献。</span><span class="sxs-lookup"><span data-stu-id="23a6b-115">This version bypasses the adapters and subsequently their latency contributions due to the MessageBox persistence point.</span></span> <span data-ttu-id="23a6b-116">相反，内联版本通过 DCOM 等远程过程调用 (RPC) 机制了直接转到后端服务器。</span><span class="sxs-lookup"><span data-stu-id="23a6b-116">Instead, the inline version talks straight to the back-end servers through Remote Procedure Calls (RPC) mechanisms such as DCOM.</span></span>  
  
 <span data-ttu-id="23a6b-117">有关 MessageBox 持久化点的详细信息，请参阅[持久化和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="23a6b-117">For more information about the MessageBox persistence point, see [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span>  
  
 <span data-ttu-id="23a6b-118">本部署指南介绍如何安装和测试面向服务的解决方案在单台计算机上的三个版本。</span><span class="sxs-lookup"><span data-stu-id="23a6b-118">This deployment guide describes how to install and test the three versions of the service-oriented solution on a single computer.</span></span>  
  
 <span data-ttu-id="23a6b-119">有关面向服务的解决方案的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="23a6b-119">For more information about the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23a6b-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="23a6b-120">In This Section</span></span>  
  
-   [<span data-ttu-id="23a6b-121">在安装面向服务的解决方案之前</span><span class="sxs-lookup"><span data-stu-id="23a6b-121">Before Installing the Service Oriented Solution</span></span>](../core/before-installing-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="23a6b-122">如何安装该服务的存根版本面向解决方案</span><span class="sxs-lookup"><span data-stu-id="23a6b-122">How to Install the Stub Version of the Service Oriented Solution</span></span>](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="23a6b-123">如何安装的内联版本和适配器版本的服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="23a6b-123">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="23a6b-124">如何运行该服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="23a6b-124">How to Run the Service Oriented Solution</span></span>](../core/how-to-run-the-service-oriented-solution.md)