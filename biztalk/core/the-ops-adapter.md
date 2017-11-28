---
title: "Ops 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67463adf4e1e960ab6608e67595a679804aa223e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-ops-adapter"></a><span data-ttu-id="549de-102">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="549de-102">The Ops Adapter</span></span>
<span data-ttu-id="549de-103">该解决方案设计为将存在问题的消息和错误传递（如果可能的话）给操作系统，由操作系统决定是修复错误还是终止订单。</span><span class="sxs-lookup"><span data-stu-id="549de-103">The design of the solution is to pass, where possible, problematic messages and errors to operations systems that make a decision about fixing the error or terminating the order.</span></span> <span data-ttu-id="549de-104">Ops 适配器与新的错误报告功能配合使用可以处理许多这样的情况。</span><span class="sxs-lookup"><span data-stu-id="549de-104">The Ops adapter, combined with the new error reporting feature, handles many of these cases.</span></span>  
  
 <span data-ttu-id="549de-105">该解决方案将该适配器用在配置为使用新的错误报告功能的端口上。</span><span class="sxs-lookup"><span data-stu-id="549de-105">The solution uses the adapter on a port configured to use the new error reporting feature.</span></span> <span data-ttu-id="549de-106">当它收到错误时，适配器将调用两种方法，**初始化**和**执行**，在指定程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="549de-106">When it receives an error, the adapter calls two methods, **Initialize** and **Execute**, on a class in a specified assembly.</span></span> <span data-ttu-id="549de-107">在该解决方案中，这些方法会将错误发送给正确的操作组。</span><span class="sxs-lookup"><span data-stu-id="549de-107">In the solution, these methods send the error to the correct operations group.</span></span>  
  
 <span data-ttu-id="549de-108">该解决方案包含一个示例处理程序，当然，您也可以很容易地编写自己的处理程序，并在其他解决方案中使用该适配器。</span><span class="sxs-lookup"><span data-stu-id="549de-108">The solution includes a sample handler, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="549de-109">有关新的错误报告功能的常规信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="549de-109">For general information about the new error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="549de-110">Ops 适配器是使用适配器框架构建的。</span><span class="sxs-lookup"><span data-stu-id="549de-110">The Ops adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="549de-111">有关生成的框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="549de-111">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
 <span data-ttu-id="549de-112">本部分介绍了该适配器的工作原理以及如何配置该适配器，并提供有关错误处理程序程序集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="549de-112">This section describes how the adapter works and how to configure it, and provides details about the error handler assemblies.</span></span> <span data-ttu-id="549de-113">本部分最后介绍了实现详细信息，这些信息对于那些希望修改该适配器或者在其他应用程序中使用该适配器的用户将会非常有用。</span><span class="sxs-lookup"><span data-stu-id="549de-113">The section concludes with implementation details that would be helpful to users who wish to modify the adapter or use it in other applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="549de-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="549de-114">In This Section</span></span>  
  
-   [<span data-ttu-id="549de-115">使用 Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="549de-115">Using the Ops Adapter</span></span>](../core/using-the-ops-adapter.md)  
  
-   [<span data-ttu-id="549de-116">示例操作错误处理程序</span><span class="sxs-lookup"><span data-stu-id="549de-116">The Sample Operations Error Handler</span></span>](../core/the-sample-operations-error-handler.md)  
  
-   [<span data-ttu-id="549de-117">Ops 适配器实现详细信息</span><span class="sxs-lookup"><span data-stu-id="549de-117">Ops Adapter Implementation Details</span></span>](../core/ops-adapter-implementation-details.md)