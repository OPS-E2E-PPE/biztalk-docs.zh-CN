---
title: "使用 ESB 异常管理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec20c447b184c2fdadf87f62f37f576f5100d08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-esb-exception-management"></a><span data-ttu-id="2ffc8-102">使用 ESB 异常管理</span><span class="sxs-lookup"><span data-stu-id="2ffc8-102">Using ESB Exception Management</span></span>
<span data-ttu-id="2ffc8-103">在一组的上下文，并在大量不同的处理阶段中 ESB 期间可能出现错误和异常。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-103">Errors and exceptions can occur in a range of contexts and during a number of different processing stages in an ESB.</span></span> <span data-ttu-id="2ffc8-104">本部分提供有关处理异常的信息，并描述如何在您可以发布通过 ESB 管理门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-104">This section provides information about handling exceptions and describes how you can publish details through the ESB Management Portal.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="2ffc8-105">概述</span><span class="sxs-lookup"><span data-stu-id="2ffc8-105">Overview</span></span>  
 <span data-ttu-id="2ffc8-106">有多种方法在中处理异常[!INCLUDE[prague](../includes/prague-md.md)]解决方案，包括如 Enterprise Library 上使用的框架。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-106">There are many ways to handle exceptions in a [!INCLUDE[prague](../includes/prague-md.md)] solution, including using frameworks such as the Enterprise Library.</span></span> <span data-ttu-id="2ffc8-107">但是，当使用 ESB 和 BizTalk Server 进行开发时, 你会使用基于消息的环境。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-107">However, when developing with ESB and BizTalk Server, you are working in a message-based environment.</span></span> <span data-ttu-id="2ffc8-108">在 BizTalk 解决方案中的所有内容都是面向消息的和 BizTalk 开发人员思考面向消息的方式。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-108">Everything in a BizTalk solution is message-oriented, and BizTalk developers think in a message-oriented way.</span></span> <span data-ttu-id="2ffc8-109">因此，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]实现异常处理的面向消息的方法。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-109">Therefore, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a message-oriented approach to exception handling.</span></span>  
  
 <span data-ttu-id="2ffc8-110">ESB 异常管理 Framework 遵循提供灵活的方法，来监视异常并使错误响应为来自外部解决方案的设计模式-可能是在业务部门级别。</span><span class="sxs-lookup"><span data-stu-id="2ffc8-110">The ESB Exception Management Framework follows a design pattern that provides a flexible approach to exception monitoring and enables error responses to originate from outside of the solution—perhaps at business-unit level.</span></span>  
  
 <span data-ttu-id="2ffc8-111">以下主题讨论 ESB 异常管理框架中更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ffc8-111">The following topics discuss the ESB Exception Management Framework in more detail:</span></span>  
  
-   [<span data-ttu-id="2ffc8-112">ESB 异常管理框架的设计</span><span class="sxs-lookup"><span data-stu-id="2ffc8-112">Design of the ESB Exception Management Framework</span></span>](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [<span data-ttu-id="2ffc8-113">异常管理 Framework 的组件</span><span class="sxs-lookup"><span data-stu-id="2ffc8-113">The Components of the Exception Management Framework</span></span>](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="2ffc8-114">使用异常管理框架</span><span class="sxs-lookup"><span data-stu-id="2ffc8-114">Using the Exception Management Framework</span></span>](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="2ffc8-115">创建自定义异常处理程序</span><span class="sxs-lookup"><span data-stu-id="2ffc8-115">Creating Custom Exception Handlers</span></span>](../esb-toolkit/creating-custom-exception-handlers.md)