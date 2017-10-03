---
title: "业务流程管理解决方案中的异常处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd3134b8ed4e2fc6fd4a50d9b64397692ea32b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling-in-the-business-process-management-solution"></a><span data-ttu-id="453d3-102">业务流程管理解决方案中的异常处理</span><span class="sxs-lookup"><span data-stu-id="453d3-102">Exception Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="453d3-103">业务流程管理解决方案使用一个特殊的异常处理业务流程以及标准的 BizTalk Server 异常处理方式，对于适配器、管道、映射和路由故障，则使用新的错误报告功能。</span><span class="sxs-lookup"><span data-stu-id="453d3-103">The business process management solution uses a special exception handling orchestration, as well as the standard BizTalk Server exception handling, and for adapter, pipeline, mapping, and routing failures, the new error reporting feature.</span></span> <span data-ttu-id="453d3-104">此自定义的系统围绕**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="453d3-104">This customized system is built around the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="453d3-105">此解决方案使用**ExceptionHandler** orchestration 重试操作或重试后出现临时问题可能会成功的调用。</span><span class="sxs-lookup"><span data-stu-id="453d3-105">The solution uses the **ExceptionHandler** orchestration to retry an operation or to retry a call that might succeed after a transient problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="453d3-106">你可以重新使用支持业务流程，如下代码**激活**，使用**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="453d3-106">You can re-use code from orchestrations, such as **Activate**, that use the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="453d3-107">所有这些业务流程包括标题为作用域**CallingCode**与一个附加**异常**块。</span><span class="sxs-lookup"><span data-stu-id="453d3-107">All of these orchestrations include a scope titled **CallingCode** with an attached **Exception** block.</span></span> <span data-ttu-id="453d3-108">中的代码替换**CallingCode**与你的代码的作用域。</span><span class="sxs-lookup"><span data-stu-id="453d3-108">Replace the code in the **CallingCode** scope with your code.</span></span> <span data-ttu-id="453d3-109">**异常**块定义所有变量需调用**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="453d3-109">The **Exception** block defines all of the variables need to call the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="453d3-110">请编辑为这些变量指定的值。</span><span class="sxs-lookup"><span data-stu-id="453d3-110">Edit the values assigned to the variables.</span></span>  
  
 <span data-ttu-id="453d3-111">对于错误不可恢复的情况，该解决方案将使用自定义异常以及若干预定义的 BizTalk 异常。</span><span class="sxs-lookup"><span data-stu-id="453d3-111">The solution uses custom exceptions, and a couple pre-defined BizTalk exceptions, for cases where the error is unrecoverable such as a malformed order message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="453d3-112">该解决方案使用自定义适配器来处理某些端口故障。</span><span class="sxs-lookup"><span data-stu-id="453d3-112">The solution uses a custom adapter for handling failures on some ports.</span></span> <span data-ttu-id="453d3-113">关于适配器的详细信息，请参阅[Ops 适配器](../core/the-ops-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="453d3-113">For more information about the adapter, see [The Ops Adapter](../core/the-ops-adapter.md).</span></span>  
  
 <span data-ttu-id="453d3-114">本部分介绍**ExceptionHandler**业务流程和自定义的异常。</span><span class="sxs-lookup"><span data-stu-id="453d3-114">This section describes the **ExceptionHandler** orchestration and the custom exceptions.</span></span> <span data-ttu-id="453d3-115">在本部分中，还对解决方案如何利用错误报告产品功能进行了简要介绍。</span><span class="sxs-lookup"><span data-stu-id="453d3-115">It also discusses, briefly, how the solution employs the error reporting product feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="453d3-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="453d3-116">In This Section</span></span>  
  
-   [<span data-ttu-id="453d3-117">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="453d3-117">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)  
  
-   [<span data-ttu-id="453d3-118">自定义异常</span><span class="sxs-lookup"><span data-stu-id="453d3-118">Custom Exceptions</span></span>](../core/custom-exceptions.md)