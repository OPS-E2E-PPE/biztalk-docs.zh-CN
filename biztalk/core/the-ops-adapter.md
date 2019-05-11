---
title: Ops 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 052fff3518e3a302c6b632e9852a9d0c8f6b5ceb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277949"
---
# <a name="the-ops-adapter"></a><span data-ttu-id="a67e6-102">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="a67e6-102">The Ops Adapter</span></span>
<span data-ttu-id="a67e6-103">在解决方案的设计是传递，在可能的情况下，会出现问题的消息和错误给决定如何修复错误还是终止订单的操作系统。</span><span class="sxs-lookup"><span data-stu-id="a67e6-103">The design of the solution is to pass, where possible, problematic messages and errors to operations systems that make a decision about fixing the error or terminating the order.</span></span> <span data-ttu-id="a67e6-104">Ops 适配器，结合新的错误报告功能，可处理许多这样的情况。</span><span class="sxs-lookup"><span data-stu-id="a67e6-104">The Ops adapter, combined with the new error reporting feature, handles many of these cases.</span></span>  
  
 <span data-ttu-id="a67e6-105">该解决方案使用该适配器端口配置为使用新的错误报告功能。</span><span class="sxs-lookup"><span data-stu-id="a67e6-105">The solution uses the adapter on a port configured to use the new error reporting feature.</span></span> <span data-ttu-id="a67e6-106">当它收到错误时，适配器调用两种方法**初始化**并**Execute**，指定程序集中的类上。</span><span class="sxs-lookup"><span data-stu-id="a67e6-106">When it receives an error, the adapter calls two methods, **Initialize** and **Execute**, on a class in a specified assembly.</span></span> <span data-ttu-id="a67e6-107">在解决方案中，这些方法将错误发送到正确的操作组。</span><span class="sxs-lookup"><span data-stu-id="a67e6-107">In the solution, these methods send the error to the correct operations group.</span></span>  
  
 <span data-ttu-id="a67e6-108">该解决方案包含的示例处理程序，尽管您可以轻松地编写你自己和其他解决方案中使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="a67e6-108">The solution includes a sample handler, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="a67e6-109">有关新的错误报告功能的常规信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="a67e6-109">For general information about the new error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a67e6-110">Ops 适配器是使用适配器框架生成的。</span><span class="sxs-lookup"><span data-stu-id="a67e6-110">The Ops adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="a67e6-111">有关构建与框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="a67e6-111">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
 <span data-ttu-id="a67e6-112">本部分介绍了该适配器的工作原理以及如何配置它，并提供处理程序程序集的错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="a67e6-112">This section describes how the adapter works and how to configure it, and provides details about the error handler assemblies.</span></span> <span data-ttu-id="a67e6-113">本部分最后介绍会很有帮助的用户想要修改适配器或其他应用程序中使用它的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="a67e6-113">The section concludes with implementation details that would be helpful to users who wish to modify the adapter or use it in other applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a67e6-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="a67e6-114">In This Section</span></span>  
  
-   [<span data-ttu-id="a67e6-115">使用 Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="a67e6-115">Using the Ops Adapter</span></span>](../core/using-the-ops-adapter.md)  
  
-   [<span data-ttu-id="a67e6-116">操作错误处理程序示例</span><span class="sxs-lookup"><span data-stu-id="a67e6-116">The Sample Operations Error Handler</span></span>](../core/the-sample-operations-error-handler.md)  
  
-   [<span data-ttu-id="a67e6-117">Ops 适配器实施详细信息</span><span class="sxs-lookup"><span data-stu-id="a67e6-117">Ops Adapter Implementation Details</span></span>](../core/ops-adapter-implementation-details.md)