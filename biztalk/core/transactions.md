---
title: "事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74827beade56e6e54414371c9796454d3b48609e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transactions"></a><span data-ttu-id="572d5-102">中的</span><span class="sxs-lookup"><span data-stu-id="572d5-102">Transactions</span></span>
<span data-ttu-id="572d5-103">BizTalk Server 业务流程引擎可管理复杂流程和/或事务集的状态，对其应用业务逻辑，并调用其支持应用程序。</span><span class="sxs-lookup"><span data-stu-id="572d5-103">The BizTalk Server Orchestration Engine manages the state, applies business logic, and invokes the supporting applications of complex processes and/or transaction sets.</span></span>  
  
 <span data-ttu-id="572d5-104">业务流程可由使用原子事务的若干分立工作组成，这些原子事务在发生错误或长时间运行时自动回滚所有更改，业务流程可包含嵌套事务，并可使用自定义异常处理从错误中恢复。</span><span class="sxs-lookup"><span data-stu-id="572d5-104">Business processes can be composed as discrete pieces of work using atomic transactions that automatically roll back all changes in case of errors or long running, which can contain nested transactions and use custom exception handling to recover from error scenarios.</span></span> <span data-ttu-id="572d5-105">这些事务性语义通常由业务流程设计器中的“作用域”构造管理。</span><span class="sxs-lookup"><span data-stu-id="572d5-105">These transactional semantics are typically managed through the Scope construct in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="572d5-106">长期流程可持续数天、数周，甚至更长的时间。</span><span class="sxs-lookup"><span data-stu-id="572d5-106">The long running processes can span days, weeks, and longer time durations.</span></span> <span data-ttu-id="572d5-107">长期流程通常利用相关将收到的消息和要发送的消息关联起来。</span><span class="sxs-lookup"><span data-stu-id="572d5-107">The long running processes typically utilize correlation to correlate messages that are received to the messages that may be sent.</span></span> <span data-ttu-id="572d5-108">业务流程引擎通常会冻结这些实例以节省系统资源，并在收到相关消息后解除冻结。</span><span class="sxs-lookup"><span data-stu-id="572d5-108">The orchestration engine typically dehydrates these instances to conserve system resources and re-hydrates the process upon receipt of these correlated messages.</span></span> <span data-ttu-id="572d5-109">业务流程引擎会在已知检查点处将业务流程状态持久化到 MessageBox 数据库，以便为从任何应用程序异常或系统异常中恢复做好准备。</span><span class="sxs-lookup"><span data-stu-id="572d5-109">The orchestration engine persists the orchestration state to the MessageBox database at known checkpoints to recover from any application or system exceptions.</span></span>  
  
 <span data-ttu-id="572d5-110">提供给 BizTalk 业务流程引擎的事务性编程模型不仅支持异常处理，还支持从失败的事务、在错误发生时自动回滚其操作的原子事务或包含其他事务的长期事务及自定义异常处理中恢复。</span><span class="sxs-lookup"><span data-stu-id="572d5-110">The transactional programming model provided for the BizTalk Orchestration engine includes support for exception handling and recovery from failed transactions, atomic transactions that automatically roll back their actions if an error occurs, or long-running transactions that can contain other transactions as well as custom exception handling.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="572d5-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="572d5-111">In This Section</span></span>  
  
-   [<span data-ttu-id="572d5-112">原子事务</span><span class="sxs-lookup"><span data-stu-id="572d5-112">Atomic Transactions</span></span>](../core/atomic-transactions.md)  
  
-   [<span data-ttu-id="572d5-113">使用原子事务的方案</span><span class="sxs-lookup"><span data-stu-id="572d5-113">Scenarios Using Atomic Transactions</span></span>](../core/scenarios-using-atomic-transactions.md)  
  
-   [<span data-ttu-id="572d5-114">长时间运行的事务</span><span class="sxs-lookup"><span data-stu-id="572d5-114">Long-Running Transactions</span></span>](../core/long-running-transactions.md)  
  
-   [<span data-ttu-id="572d5-115">使用长时间运行事务的方案</span><span class="sxs-lookup"><span data-stu-id="572d5-115">Scenarios Using Long-Running Transactions</span></span>](../core/scenarios-using-long-running-transactions.md)  
  
-   [<span data-ttu-id="572d5-116">在业务流程中的持久性</span><span class="sxs-lookup"><span data-stu-id="572d5-116">Persistence in Orchestrations</span></span>](../core/persistence-in-orchestrations.md)