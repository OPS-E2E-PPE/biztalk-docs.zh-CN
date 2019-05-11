---
title: 业务流程管理解决方案中的异常处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d06209f49a4702397ea13407593d9286e1f31be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388312"
---
# <a name="exception-handling-in-the-business-process-management-solution"></a><span data-ttu-id="f3d9b-102">业务流程管理解决方案中的异常处理</span><span class="sxs-lookup"><span data-stu-id="f3d9b-102">Exception Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="f3d9b-103">业务流程管理解决方案使用一个特殊的异常处理业务流程，以及标准 BizTalk Server 异常处理功能，以及适配器、 管道、 映射和路由故障，新的错误报告功能。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-103">The business process management solution uses a special exception handling orchestration, as well as the standard BizTalk Server exception handling, and for adapter, pipeline, mapping, and routing failures, the new error reporting feature.</span></span> <span data-ttu-id="f3d9b-104">此自定义的系统围绕**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-104">This customized system is built around the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="f3d9b-105">该解决方案使用**ExceptionHandler**重试操作或重试暂时性问题后可能会成功的调用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-105">The solution uses the **ExceptionHandler** orchestration to retry an operation or to retry a call that might succeed after a transient problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3d9b-106">您可以重用代码从业务流程，如**激活**，使用**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-106">You can re-use code from orchestrations, such as **Activate**, that use the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="f3d9b-107">所有这些业务流程都包括一个标题为的作用域**CallingCode**具有一个附加**异常**块。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-107">All of these orchestrations include a scope titled **CallingCode** with an attached **Exception** block.</span></span> <span data-ttu-id="f3d9b-108">中的代码替换**CallingCode**与您的代码的作用域。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-108">Replace the code in the **CallingCode** scope with your code.</span></span> <span data-ttu-id="f3d9b-109">**异常**块定义的变量需要调用所有**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-109">The **Exception** block defines all of the variables need to call the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="f3d9b-110">编辑分配给变量的值。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-110">Edit the values assigned to the variables.</span></span>  
  
 <span data-ttu-id="f3d9b-111">该解决方案使用自定义异常以及几个预定义的 BizTalk 异常，对于如格式不正确的订单消息不可恢复错误的情况。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-111">The solution uses custom exceptions, and a couple pre-defined BizTalk exceptions, for cases where the error is unrecoverable such as a malformed order message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3d9b-112">该解决方案使用自定义适配器来处理某些端口故障。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-112">The solution uses a custom adapter for handling failures on some ports.</span></span> <span data-ttu-id="f3d9b-113">有关适配器的详细信息，请参阅[Ops 适配器](../core/the-ops-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-113">For more information about the adapter, see [The Ops Adapter](../core/the-ops-adapter.md).</span></span>  
  
 <span data-ttu-id="f3d9b-114">本部分介绍**ExceptionHandler**业务流程和自定义异常。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-114">This section describes the **ExceptionHandler** orchestration and the custom exceptions.</span></span> <span data-ttu-id="f3d9b-115">它还讨论了，简单地说，对解决方案如何利用错误报告产品功能。</span><span class="sxs-lookup"><span data-stu-id="f3d9b-115">It also discusses, briefly, how the solution employs the error reporting product feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3d9b-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="f3d9b-116">In This Section</span></span>  
  
-   [<span data-ttu-id="f3d9b-117">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="f3d9b-117">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)  
  
-   [<span data-ttu-id="f3d9b-118">自定义异常</span><span class="sxs-lookup"><span data-stu-id="f3d9b-118">Custom Exceptions</span></span>](../core/custom-exceptions.md)