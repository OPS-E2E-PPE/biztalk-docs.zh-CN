---
title: "使用事务和处理异常 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab32729aa6b4f12aada623587f52728c6bd23240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-transactions-and-handling-exceptions"></a><span data-ttu-id="62707-102">使用事务和处理异常</span><span class="sxs-lookup"><span data-stu-id="62707-102">Using Transactions and Handling Exceptions</span></span>
<span data-ttu-id="62707-103">在您设计某一业务流程时，应该仔细考虑可能发生问题的地方以及如何最好地处理这些问题。</span><span class="sxs-lookup"><span data-stu-id="62707-103">When you design an orchestration, you should consider carefully where problems might occur and how best to deal with them.</span></span> <span data-ttu-id="62707-104">许多业务流程都存在若干潜在的故障点。</span><span class="sxs-lookup"><span data-stu-id="62707-104">Many orchestrations have several potential points of failure.</span></span> <span data-ttu-id="62707-105">问题可能出自许多方面；例如，服务器可能停机，或者消息的格式可能不正确。</span><span class="sxs-lookup"><span data-stu-id="62707-105">Problems can arise for any number of other reasons; for example, a server might go down or a message might be badly formatted.</span></span>  
  
 <span data-ttu-id="62707-106">对于长期或复杂业务流程尤其重要的是，应该跟踪其状态并且在错误发生时报告错误，以便您可以轻松、准确地解决问题。</span><span class="sxs-lookup"><span data-stu-id="62707-106">It is especially important for a long-running or complex orchestration to keep track of its state and to report errors as they occur, so that you can resolve problems accurately and with a minimum of effort.</span></span> <span data-ttu-id="62707-107">对于业务流程同样重要的是，需要维护一组密切相关的操作的完整性，以便如果事务的某一部分执行，而另一部分未执行，整个事务都可以回滚到从未发生任何事务时的状态。</span><span class="sxs-lookup"><span data-stu-id="62707-107">It is equally important for an orchestration to maintain the integrity of a set of closely related actions, so that if part of a transaction takes place but another does not, the entire transaction can be rolled back as though it never occurred.</span></span>  
  
 <span data-ttu-id="62707-108">通过 BizTalk 业务流程，您可以确保工作的原子性；也就是说，甚至在外部系统参与事务时，也能够确保相关操作的完整性。</span><span class="sxs-lookup"><span data-stu-id="62707-108">BizTalk Orchestration enables you to guarantee the atomicity of work, that is, the integrity of related actions, even when external systems are participating in transactions.</span></span> <span data-ttu-id="62707-109">它为您提供各种工具来处理错误，维护业务流程的状态，以及通过事务、补偿和异常处理在发生问题时解决问题。</span><span class="sxs-lookup"><span data-stu-id="62707-109">It gives you tools to handle errors, to maintain the state of an orchestration, and to fix problems as they occur through transactions, compensation, and exception handling.</span></span>  
  
 <span data-ttu-id="62707-110">业务流程设计器提供一个框架，用于事务和异常处理，作为**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="62707-110">As a framework for transactions and exception handling, Orchestration Designer provides the **Scope** shape.</span></span> <span data-ttu-id="62707-111">作用域可以具有事务类型、补偿和任意数目的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="62707-111">A scope can have a transaction type, a compensation, and any number of exception handlers.</span></span>  
  
 <span data-ttu-id="62707-112">设置事务和异常处理的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="62707-112">The steps for setting up a transaction and exception handling are:</span></span>  
  
-   <span data-ttu-id="62707-113">创建一个范围。</span><span class="sxs-lookup"><span data-stu-id="62707-113">Create a scope.</span></span>  
  
-   <span data-ttu-id="62707-114">标识所需事务的类型。</span><span class="sxs-lookup"><span data-stu-id="62707-114">Identify the kind of transaction you need.</span></span>  
  
-   <span data-ttu-id="62707-115">确定需要补偿的内容。</span><span class="sxs-lookup"><span data-stu-id="62707-115">Determine what will need to be compensated.</span></span>  
  
-   <span data-ttu-id="62707-116">标识潜在错误。</span><span class="sxs-lookup"><span data-stu-id="62707-116">Identify potential errors.</span></span>  
  
-   <span data-ttu-id="62707-117">添加适当的异常处理程序和补偿代码。</span><span class="sxs-lookup"><span data-stu-id="62707-117">Add appropriate exception handlers and compensation code.</span></span>  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a><span data-ttu-id="62707-118">使用事务、异常处理和补偿的示例</span><span class="sxs-lookup"><span data-stu-id="62707-118">Examples of Using Transactions, Exception Handlings, and Compensations</span></span>  
  
-   [<span data-ttu-id="62707-119">错误处理 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="62707-119">Error Handling (BizTalk Server Samples Folder)</span></span>](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="62707-120">补偿 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="62707-120">Compensation (BizTalk Server Sample)</span></span>](../core/compensation-biztalk-server-sample.md)  
  
-   <span data-ttu-id="62707-121">从下载 SDK 示例"原子事务与 COM + 服务组件中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="62707-121">Download the SDK sample "Atomic Transactions with COM+ Serviced Components in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="62707-122">从下载 SDK 示例"使用 SQL 适配器与原子事务中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="62707-122">Download the SDK sample "Using the SQL Adapter with Atomic Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="62707-123">从下载 SDK 示例"使用长时间运行事务中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="62707-123">Download the SDK sample "Using Long-Running Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="62707-124">从下载 SDK 示例"异常处理中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="62707-124">Download the SDK sample "Exception Handling in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62707-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="62707-125">In This Section</span></span>  
  
-   [<span data-ttu-id="62707-126">作用域</span><span class="sxs-lookup"><span data-stu-id="62707-126">Scopes</span></span>](../core/scopes.md)  
  
-   [<span data-ttu-id="62707-127">如何配置作用域形状</span><span class="sxs-lookup"><span data-stu-id="62707-127">How to Configure the Scope Shape</span></span>](../core/how-to-configure-the-scope-shape.md)  
  
-   [<span data-ttu-id="62707-128">使业务流程事务</span><span class="sxs-lookup"><span data-stu-id="62707-128">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)  
  
-   [<span data-ttu-id="62707-129">异常</span><span class="sxs-lookup"><span data-stu-id="62707-129">Exceptions</span></span>](../core/exceptions.md)  
  
-   [<span data-ttu-id="62707-130">补偿</span><span class="sxs-lookup"><span data-stu-id="62707-130">Compensation</span></span>](../core/compensation.md)  
  
## <a name="see-also"></a><span data-ttu-id="62707-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62707-131">See Also</span></span>  
 [<span data-ttu-id="62707-132">使用 BizTalk 消息传送引擎</span><span class="sxs-lookup"><span data-stu-id="62707-132">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)