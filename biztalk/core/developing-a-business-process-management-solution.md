---
title: 开发一个业务流程管理解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, process management solution tutorial
- process management solution tutorial, developing
ms.assetid: 3b590533-2b18-4e78-b9e5-88f4a680532f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60632efe6cfc8d48d395d20949012354874c7e46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239637"
---
# <a name="developing-a-business-process-management-solution"></a><span data-ttu-id="895c6-102">开发一个业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="895c6-102">Developing a Business Process Management Solution</span></span>
<span data-ttu-id="895c6-103">本部分介绍在设计解决方案时涉及的基本模式以及如何将这些模式转换为 BizTalk 组件和结构。</span><span class="sxs-lookup"><span data-stu-id="895c6-103">This section describes the basic patterns involved in the design of the solution and how those patterns translate into BizTalk components and structures.</span></span> <span data-ttu-id="895c6-104">此外，本部分还按照消息在解决方案中的处理顺序，提供其他实现详细信息，介绍如何对该解决方案进行版本控制和扩展，并提供消息和文件引用。</span><span class="sxs-lookup"><span data-stu-id="895c6-104">It also follows an order message through processing in the solution, provides additional implementation details, tells you how to version and scale the solution, and provides message and file references.</span></span> <span data-ttu-id="895c6-105">有关解决方案和其设计背后的业务要求的详细信息，请参阅"业务要求"中[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="895c6-105">For more information about the solution and the business requirements behind its design, see "Business Requirements" in [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="895c6-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="895c6-106">In This Section</span></span>  
  
-   [<span data-ttu-id="895c6-107">业务流程管理解决方案中的模式</span><span class="sxs-lookup"><span data-stu-id="895c6-107">Patterns in the Business Process Management Solution</span></span>](../core/patterns-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="895c6-108">业务流程管理解决方案的组件</span><span class="sxs-lookup"><span data-stu-id="895c6-108">Components of the Business Process Management Solution</span></span>](../core/components-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="895c6-109">在业务流程管理解决方案中进行处理</span><span class="sxs-lookup"><span data-stu-id="895c6-109">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="895c6-110">实现突出显示的业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="895c6-110">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="895c6-111">监视与 BAM 业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="895c6-111">Monitoring the Business Process Management Solution with BAM</span></span>](../core/monitoring-the-business-process-management-solution-with-bam.md)  
  
-   [<span data-ttu-id="895c6-112">版本控制业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="895c6-112">Versioning the Business Process Management Solution</span></span>](../core/versioning-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="895c6-113">业务流程管理解决方案参考</span><span class="sxs-lookup"><span data-stu-id="895c6-113">Business Process Management Solution Reference</span></span>](../core/business-process-management-solution-reference.md)