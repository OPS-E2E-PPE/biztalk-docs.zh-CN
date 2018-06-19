---
title: 部署服务面向解决方案 |Microsoft 文档
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
ms.openlocfilehash: 7246635c4e0d55fd424fd0052eee91e118c8cb17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239189"
---
# <a name="deploying-the-service-oriented-solution"></a><span data-ttu-id="38d1e-102">部署服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="38d1e-102">Deploying the Service Oriented Solution</span></span>
<span data-ttu-id="38d1e-103">面向服务的结构 (SOA) 是一种用于构建分布式系统的方法。</span><span class="sxs-lookup"><span data-stu-id="38d1e-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="38d1e-104">面向服务的解决方案演示了如何将使用不同协议的几种后端系统聚合为客户端可以使用的单个服务。</span><span class="sxs-lookup"><span data-stu-id="38d1e-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="38d1e-105">此解决方案将服务与可确保送达和性能特征的方法相集成。</span><span class="sxs-lookup"><span data-stu-id="38d1e-105">This solution integrates services with an approach that guarantees delivery and performance characteristics.</span></span>  
  
 <span data-ttu-id="38d1e-106">面向服务的解决方案以服务级别协议方案为蓝图构建而成，在服务级别协议方案中，BizTalk Server 以及与其连接的业务 (LOB) 应用程序服务器可以有三秒钟的时间响应服务请求。</span><span class="sxs-lookup"><span data-stu-id="38d1e-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="38d1e-107">这三秒中的一秒可由 BizTalk Server 占用。</span><span class="sxs-lookup"><span data-stu-id="38d1e-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="38d1e-108">本部分中的主题介绍了如何在单台计算机上以及多台生产服务器上安装和测试面向服务的解决方案。</span><span class="sxs-lookup"><span data-stu-id="38d1e-108">The topics in this section describe how to install and test the service oriented solution on a single computer and multiple production servers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38d1e-109">有三种版本的面向服务解决方案： 适配器、 嵌入式和存根 （stub）。</span><span class="sxs-lookup"><span data-stu-id="38d1e-109">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="38d1e-110">有关面向服务的解决方案的三个版本之间的差异的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1e-110">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="38d1e-111">**读取器指南**</span><span class="sxs-lookup"><span data-stu-id="38d1e-111">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="38d1e-112">本文档假定您熟悉 BizTalk Server、Windows Server 和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="38d1e-112">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="38d1e-113">它还假定你已了解有关企业应用程序集成和 Web 服务的基本概念。</span><span class="sxs-lookup"><span data-stu-id="38d1e-113">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="38d1e-114">此外，我们建议你熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和你熟悉创建项目、 设置引用，以及使用调试模式下调试和测试你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="38d1e-114">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="38d1e-115">有关先决条件的技能和知识 IT 专业人员和开发人员的详细信息，请参阅[先决条件技能和知识](../core/prerequisite-skills-and-knowledge5.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1e-115">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38d1e-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="38d1e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="38d1e-117">服务开发人员计算机设置面向解决方案</span><span class="sxs-lookup"><span data-stu-id="38d1e-117">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)