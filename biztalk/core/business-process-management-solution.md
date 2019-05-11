---
title: 业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9002d3fbd74ad6ceff649c59fa642447178d9b02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358114"
---
# <a name="business-process-management-solution"></a><span data-ttu-id="1c5d7-102">业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="1c5d7-102">Business Process Management Solution</span></span>
<span data-ttu-id="1c5d7-103">业务流程管理解决方案演示了如何设计 BizTalk 应用程序来管理业务流程服务订单处理等。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-103">The Business Process Management solution shows how to design a BizTalk application to manage a business process such as service order processing.</span></span> <span data-ttu-id="1c5d7-104">该解决方案演示了如何构造流程管理器，并提供有关将流程划分成不同的阶段的指导。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-104">The solution demonstrates how to construct a process manager and provides guidance about dividing a process into distinct stages.</span></span> <span data-ttu-id="1c5d7-105">解决方案还介绍了如何构造可中断业务流程以及大量复杂异常处理。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-105">The solution also describes how to construct interruptible orchestrations as well as extensive, sophisticated exception handling.</span></span>  
  
 <span data-ttu-id="1c5d7-106">各节概述了解决方案的模式和设计选项和有关生成和运行解决方案的信息的详细说明。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-106">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c5d7-107">模式和这些部分中介绍的指南旨在阐释一种特定类型的业务解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-107">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="1c5d7-108">模式是简单的机制，旨在应用于特定的问题，通常与其他模式相结合。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-108">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="1c5d7-109">它们不应插入到应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-109">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="1c5d7-110">"按原样"提供的示例代码，不适合生产环境中使用。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-110">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="1c5d7-111">它仅用于阐释模式，并因此不包含额外的代码，如异常处理、 日志记录、 安全性和验证。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-111">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="1c5d7-112">Microsoft 不支持"按原样"的示例代码部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="1c5d7-112">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c5d7-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="1c5d7-113">In This Section</span></span>  
  
-   [<span data-ttu-id="1c5d7-114">了解业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="1c5d7-114">Understanding the Business Process Management Solution</span></span>](../core/understanding-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="1c5d7-115">开发业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="1c5d7-115">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
-   [<span data-ttu-id="1c5d7-116">部署业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="1c5d7-116">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)