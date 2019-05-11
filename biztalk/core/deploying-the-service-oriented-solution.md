---
title: 部署服务面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, service solution tutorial
- deploying, tutorials
- service solution tutorial, deploying
- service solution tutorial, background information
- tutorials, deploying
ms.assetid: 88d4d28d-9031-4fb8-ab62-04ee27949673
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d86b3b1cd1e5cadc8505e88db119cdffdaf653dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389539"
---
# <a name="deploying-the-service-oriented-solution"></a><span data-ttu-id="bd783-102">部署服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="bd783-102">Deploying the Service Oriented Solution</span></span>
<span data-ttu-id="bd783-103">面向服务的体系结构 (SOA) 是用于构建分布式的系统的方法。</span><span class="sxs-lookup"><span data-stu-id="bd783-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="bd783-104">面向服务的解决方案演示了几种使用不同的协议的后端系统可以整合到单个服务的客户端可以使用。</span><span class="sxs-lookup"><span data-stu-id="bd783-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="bd783-105">此解决方案将服务集成与可确保送达和性能特征的方法。</span><span class="sxs-lookup"><span data-stu-id="bd783-105">This solution integrates services with an approach that guarantees delivery and performance characteristics.</span></span>  
  
 <span data-ttu-id="bd783-106">面向的解决方案只现代性的在 BizTalk Server 和业务线 (LOB) 应用程序服务器连接到它的服务级别协议方案的服务提供三秒使用的服务请求进行响应。</span><span class="sxs-lookup"><span data-stu-id="bd783-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="bd783-107">这三个秒之一可能由 BizTalk Server 会占用。</span><span class="sxs-lookup"><span data-stu-id="bd783-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="bd783-108">在本部分中的主题介绍如何安装和测试面向服务的解决方案在一台计算机和多台生产服务器上。</span><span class="sxs-lookup"><span data-stu-id="bd783-108">The topics in this section describe how to install and test the service oriented solution on a single computer and multiple production servers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd783-109">有三个版本的面向服务的解决方案： 适配器、 内联和存根 （stub）。</span><span class="sxs-lookup"><span data-stu-id="bd783-109">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="bd783-110">有关面向服务的解决方案的三个版本之间的差异的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="bd783-110">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="bd783-111">**读者指南**</span><span class="sxs-lookup"><span data-stu-id="bd783-111">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="bd783-112">本文档假定您熟悉 BizTalk Server、 Windows Server 和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd783-112">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="bd783-113">它还假定您了解有关企业应用程序集成和 Web 服务的基本概念。</span><span class="sxs-lookup"><span data-stu-id="bd783-113">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="bd783-114">此外，我们建议你熟悉如何构建应用程序使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和您熟悉创建项目、 设置引用，以及使用调试模式下进行调试和测试你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="bd783-114">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="bd783-115">面向 IT 专业人员和开发人员的必备技能和知识的更多信息，请参阅[必备技能和知识](../core/prerequisite-skills-and-knowledge5.md)。</span><span class="sxs-lookup"><span data-stu-id="bd783-115">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd783-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="bd783-116">In This Section</span></span>  
  
-   [<span data-ttu-id="bd783-117">面向服务的解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="bd783-117">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)