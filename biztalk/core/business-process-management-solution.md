---
title: "业务流程管理解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business solutions, tutorials
- tutorials, orchestrations
- errors, tutorials
- business solutions, process management solutions
- process management solutions
- process management solutions, applications
- process management solutions, business solutions
- tutorials, applications
- tutorials, errors
- tutorials, process management solutions
- applications, tutorials
- tutorials, business solutions
- process management solutions, tutorials
- orchestrations, interrupting
- orchestrations, tutorials
- applications, process management solutions
ms.assetid: 30ebd248-7e31-4608-ae50-4fc6703ae613
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f37fa7691a3e780c0f972e1070a8bf639c4addcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-process-management-solution"></a><span data-ttu-id="9ac9b-102">业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="9ac9b-102">Business Process Management Solution</span></span>
<span data-ttu-id="9ac9b-103">业务流程管理解决方案介绍了如何设计 BizTalk 应用程序来管理业务流程（例如服务订单处理）。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-103">The Business Process Management solution shows how to design a BizTalk application to manage a business process such as service order processing.</span></span> <span data-ttu-id="9ac9b-104">该解决方案演示了如何构造流程管理器，并提供有关将流程划分成不同的阶段的指导信息。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-104">The solution demonstrates how to construct a process manager and provides guidance about dividing a process into distinct stages.</span></span> <span data-ttu-id="9ac9b-105">该解决方案还对如何构造可中断业务流程以及大量复杂异常的处理进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-105">The solution also describes how to construct interruptible orchestrations as well as extensive, sophisticated exception handling.</span></span>  
  
 <span data-ttu-id="9ac9b-106">本部分对该解决方案进行了概括介绍，对模式和设计选项进行了详细说明，并提供了有关构建和运行该解决方案的信息。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-106">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ac9b-107">这些部分中介绍的模式和指南旨在阐释一种针对特殊类型业务解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-107">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="9ac9b-108">模式是一些可应用于特定问题的简单机制并且通常结合了其他模式。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-108">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="9ac9b-109">它们并非是要插入到某个应用程序之中。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-109">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="9ac9b-110">示例代码按“原样”提供并且不应将其用于生产目的。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-110">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="9ac9b-111">提供示例代码的目的仅在于描述模式，因此并未包含诸如异常处理、日志记录、安全性和有效性验证之类的额外代码。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-111">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="9ac9b-112">Microsoft 不支持将按“原样”提供的示例代码部署到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="9ac9b-112">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ac9b-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="9ac9b-113">In This Section</span></span>  
  
-   [<span data-ttu-id="9ac9b-114">了解业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="9ac9b-114">Understanding the Business Process Management Solution</span></span>](../core/understanding-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="9ac9b-115">开发一个业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="9ac9b-115">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
-   [<span data-ttu-id="9ac9b-116">部署业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="9ac9b-116">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)