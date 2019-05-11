---
title: 开发业务流程管理解决方案 |Microsoft Docs
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
ms.openlocfilehash: e040d7a62628871e1daa45bb3aaf7bdec873bfd4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351582"
---
# <a name="developing-a-business-process-management-solution"></a><span data-ttu-id="374fb-102">开发业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="374fb-102">Developing a Business Process Management Solution</span></span>
<span data-ttu-id="374fb-103">本部分介绍解决方案的设计中相关的基本模式以及如何将这些模式转换为 BizTalk 组件和结构。</span><span class="sxs-lookup"><span data-stu-id="374fb-103">This section describes the basic patterns involved in the design of the solution and how those patterns translate into BizTalk components and structures.</span></span> <span data-ttu-id="374fb-104">遵循订单消息处理解决方案中，通过提供其他实现详细信息，告诉您如何版本控制和扩展该解决方案，并提供消息和文件引用。</span><span class="sxs-lookup"><span data-stu-id="374fb-104">It also follows an order message through processing in the solution, provides additional implementation details, tells you how to version and scale the solution, and provides message and file references.</span></span> <span data-ttu-id="374fb-105">有关解决方案和及其设计背后蕴含的业务要求的详细信息，请参阅"业务需求"中[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="374fb-105">For more information about the solution and the business requirements behind its design, see "Business Requirements" in [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="374fb-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="374fb-106">In This Section</span></span>  
  
-   [<span data-ttu-id="374fb-107">业务流程管理解决方案中的模式</span><span class="sxs-lookup"><span data-stu-id="374fb-107">Patterns in the Business Process Management Solution</span></span>](../core/patterns-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="374fb-108">业务流程管理解决方案的组件</span><span class="sxs-lookup"><span data-stu-id="374fb-108">Components of the Business Process Management Solution</span></span>](../core/components-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="374fb-109">在业务流程管理解决方案中处理</span><span class="sxs-lookup"><span data-stu-id="374fb-109">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="374fb-110">业务流程管理解决方案的实施重点</span><span class="sxs-lookup"><span data-stu-id="374fb-110">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="374fb-111">使用 BAM 监视业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="374fb-111">Monitoring the Business Process Management Solution with BAM</span></span>](../core/monitoring-the-business-process-management-solution-with-bam.md)  
  
-   [<span data-ttu-id="374fb-112">对业务流程管理解决方案进行版本控制</span><span class="sxs-lookup"><span data-stu-id="374fb-112">Versioning the Business Process Management Solution</span></span>](../core/versioning-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="374fb-113">业务流程管理解决方案参考</span><span class="sxs-lookup"><span data-stu-id="374fb-113">Business Process Management Solution Reference</span></span>](../core/business-process-management-solution-reference.md)