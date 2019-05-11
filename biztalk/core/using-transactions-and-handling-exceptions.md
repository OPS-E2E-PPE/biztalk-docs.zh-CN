---
title: 使用事务和处理异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, orchestrations
- orchestrations, transactions
- orchestrations, errors
- transactions
- errors, orchestrations
- transactions, BizTalk Server Orchestration Engine
- errors, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], errors
- Scope shape [Orchestration Designer], transactions
ms.assetid: bb38f5eb-6641-4e7c-8e2a-c474fc739999
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac1ae71e9ff176156691fbb30a79c9d423b58da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396750"
---
# <a name="using-transactions-and-handling-exceptions"></a><span data-ttu-id="385f9-102">使用事务和处理异常</span><span class="sxs-lookup"><span data-stu-id="385f9-102">Using Transactions and Handling Exceptions</span></span>
<span data-ttu-id="385f9-103">在设计业务流程时，应仔细考虑可能会出现问题和如何最好地处理它们。</span><span class="sxs-lookup"><span data-stu-id="385f9-103">When you design an orchestration, you should consider carefully where problems might occur and how best to deal with them.</span></span> <span data-ttu-id="385f9-104">许多业务流程具有多个潜在的故障点。</span><span class="sxs-lookup"><span data-stu-id="385f9-104">Many orchestrations have several potential points of failure.</span></span> <span data-ttu-id="385f9-105">为任意数量的其他原因; 可能会出现问题例如，服务器可能停机或一条消息的格式可能是错误。</span><span class="sxs-lookup"><span data-stu-id="385f9-105">Problems can arise for any number of other reasons; for example, a server might go down or a message might be badly formatted.</span></span>  
  
 <span data-ttu-id="385f9-106">它是努力的对的运行时间较长或复杂的业务流程，了解跟踪其状态，并报告错误，因为它们发生，以便您可以准确地使用很少解决问题尤其重要。</span><span class="sxs-lookup"><span data-stu-id="385f9-106">It is especially important for a long-running or complex orchestration to keep track of its state and to report errors as they occur, so that you can resolve problems accurately and with a minimum of effort.</span></span> <span data-ttu-id="385f9-107">它是业务流程就可以保持一组密切相关的操作的完整性同等重要，以便像永远不会发生，如果事务的一部分执行，而另一个却没有，可以回滚整个事务。</span><span class="sxs-lookup"><span data-stu-id="385f9-107">It is equally important for an orchestration to maintain the integrity of a set of closely related actions, so that if part of a transaction takes place but another does not, the entire transaction can be rolled back as though it never occurred.</span></span>  
  
 <span data-ttu-id="385f9-108">BizTalk 业务流程使您能够保证工作的原子性，也就是说，相关操作的完整性，即使外部系统参与事务。</span><span class="sxs-lookup"><span data-stu-id="385f9-108">BizTalk Orchestration enables you to guarantee the atomicity of work, that is, the integrity of related actions, even when external systems are participating in transactions.</span></span> <span data-ttu-id="385f9-109">它提供用于处理错误，维护业务流程的状态并解决问题，在发生通过事务、 补偿和异常处理的工具。</span><span class="sxs-lookup"><span data-stu-id="385f9-109">It gives you tools to handle errors, to maintain the state of an orchestration, and to fix problems as they occur through transactions, compensation, and exception handling.</span></span>  
  
 <span data-ttu-id="385f9-110">作为用于事务和异常处理框架，业务流程设计器提供了**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="385f9-110">As a framework for transactions and exception handling, Orchestration Designer provides the **Scope** shape.</span></span> <span data-ttu-id="385f9-111">作用域可以具有事务类型、 补偿和任意数量的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="385f9-111">A scope can have a transaction type, a compensation, and any number of exception handlers.</span></span>  
  
 <span data-ttu-id="385f9-112">设置事务和异常处理的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="385f9-112">The steps for setting up a transaction and exception handling are:</span></span>  
  
-   <span data-ttu-id="385f9-113">创建一个作用域。</span><span class="sxs-lookup"><span data-stu-id="385f9-113">Create a scope.</span></span>  
  
-   <span data-ttu-id="385f9-114">标识所需的事务的类型。</span><span class="sxs-lookup"><span data-stu-id="385f9-114">Identify the kind of transaction you need.</span></span>  
  
-   <span data-ttu-id="385f9-115">确定将需要什么来进行补偿。</span><span class="sxs-lookup"><span data-stu-id="385f9-115">Determine what will need to be compensated.</span></span>  
  
-   <span data-ttu-id="385f9-116">识别潜在的错误。</span><span class="sxs-lookup"><span data-stu-id="385f9-116">Identify potential errors.</span></span>  
  
-   <span data-ttu-id="385f9-117">添加相应的异常处理程序和补偿代码。</span><span class="sxs-lookup"><span data-stu-id="385f9-117">Add appropriate exception handlers and compensation code.</span></span>  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a><span data-ttu-id="385f9-118">使用事务、 异常处理和补偿的示例</span><span class="sxs-lookup"><span data-stu-id="385f9-118">Examples of Using Transactions, Exception Handlings, and Compensations</span></span>  
  
-   [<span data-ttu-id="385f9-119">错误处理（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="385f9-119">Error Handling (BizTalk Server Samples Folder)</span></span>](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="385f9-120">补偿（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="385f9-120">Compensation (BizTalk Server Sample)</span></span>](../core/compensation-biztalk-server-sample.md)  
  
-   <span data-ttu-id="385f9-121">从下载 SDK 示例"原子事务与 COM + 服务组件中业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="385f9-121">Download the SDK sample "Atomic Transactions with COM+ Serviced Components in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="385f9-122">从下载 SDK 示例"使用 SQL 适配器与原子事务在业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="385f9-122">Download the SDK sample "Using the SQL Adapter with Atomic Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="385f9-123">从下载 SDK 示例"使用长时间运行的事务在业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="385f9-123">Download the SDK sample "Using Long-Running Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="385f9-124">从下载 SDK 示例"异常处理在业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="385f9-124">Download the SDK sample "Exception Handling in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="385f9-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="385f9-125">In This Section</span></span>  
  
-   [<span data-ttu-id="385f9-126">作用域</span><span class="sxs-lookup"><span data-stu-id="385f9-126">Scopes</span></span>](../core/scopes.md)  
  
-   [<span data-ttu-id="385f9-127">如何配置作用域形状</span><span class="sxs-lookup"><span data-stu-id="385f9-127">How to Configure the Scope Shape</span></span>](../core/how-to-configure-the-scope-shape.md)  
  
-   [<span data-ttu-id="385f9-128">使业务流程成为事务性业务流程</span><span class="sxs-lookup"><span data-stu-id="385f9-128">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)  
  
-   [<span data-ttu-id="385f9-129">异常</span><span class="sxs-lookup"><span data-stu-id="385f9-129">Exceptions</span></span>](../core/exceptions.md)  
  
-   [<span data-ttu-id="385f9-130">补偿</span><span class="sxs-lookup"><span data-stu-id="385f9-130">Compensation</span></span>](../core/compensation.md)  
  
## <a name="see-also"></a><span data-ttu-id="385f9-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="385f9-131">See Also</span></span>  
 [<span data-ttu-id="385f9-132">使用 BizTalk 消息引擎</span><span class="sxs-lookup"><span data-stu-id="385f9-132">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)