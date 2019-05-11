---
title: 事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376d27c4d0371a207cae974c8a9f74da0cd36e9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399207"
---
# <a name="transactions"></a><span data-ttu-id="77343-102">事务</span><span class="sxs-lookup"><span data-stu-id="77343-102">Transactions</span></span>
<span data-ttu-id="77343-103">BizTalk Server 业务流程引擎管理的状态、 应用业务逻辑，并调用复杂流程和/或事务集的支持应用程序。</span><span class="sxs-lookup"><span data-stu-id="77343-103">The BizTalk Server Orchestration Engine manages the state, applies business logic, and invokes the supporting applications of complex processes and/or transaction sets.</span></span>  
  
 <span data-ttu-id="77343-104">业务流程可以组合为不同部分的工作使用自动回滚所有更改发生错误时的原子事务或长时间运行的它可以包含嵌套的事务，使用自定义异常处理从错误中恢复方案。</span><span class="sxs-lookup"><span data-stu-id="77343-104">Business processes can be composed as discrete pieces of work using atomic transactions that automatically roll back all changes in case of errors or long running, which can contain nested transactions and use custom exception handling to recover from error scenarios.</span></span> <span data-ttu-id="77343-105">这些事务性语义通常管理通过业务流程设计器中的作用域构造。</span><span class="sxs-lookup"><span data-stu-id="77343-105">These transactional semantics are typically managed through the Scope construct in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="77343-106">长时间运行的进程可以跨天、 周和更长时间持续时间。</span><span class="sxs-lookup"><span data-stu-id="77343-106">The long running processes can span days, weeks, and longer time durations.</span></span> <span data-ttu-id="77343-107">长时间运行进程通常利用相关将收到可能发送的消息的消息相关联。</span><span class="sxs-lookup"><span data-stu-id="77343-107">The long running processes typically utilize correlation to correlate messages that are received to the messages that may be sent.</span></span> <span data-ttu-id="77343-108">通常，业务流程引擎冻结这些实例以节省系统资源，并接收相关消息后解除冻结。</span><span class="sxs-lookup"><span data-stu-id="77343-108">The orchestration engine typically dehydrates these instances to conserve system resources and re-hydrates the process upon receipt of these correlated messages.</span></span> <span data-ttu-id="77343-109">业务流程引擎将保留到 MessageBox 数据库在已知检查点从任何应用程序或系统异常中恢复的业务流程状态。</span><span class="sxs-lookup"><span data-stu-id="77343-109">The orchestration engine persists the orchestration state to the MessageBox database at known checkpoints to recover from any application or system exceptions.</span></span>  
  
 <span data-ttu-id="77343-110">为 BizTalk 业务流程引擎支持异常处理和恢复失败的事务从提供的事务性编程模型，会发生自动回滚其操作错误时的原子事务，或可以包含其他事务，以及自定义异常处理的长时间运行事务。</span><span class="sxs-lookup"><span data-stu-id="77343-110">The transactional programming model provided for the BizTalk Orchestration engine includes support for exception handling and recovery from failed transactions, atomic transactions that automatically roll back their actions if an error occurs, or long-running transactions that can contain other transactions as well as custom exception handling.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77343-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="77343-111">In This Section</span></span>  
  
-   [<span data-ttu-id="77343-112">原子事务</span><span class="sxs-lookup"><span data-stu-id="77343-112">Atomic Transactions</span></span>](../core/atomic-transactions.md)  
  
-   [<span data-ttu-id="77343-113">使用原子事务的方案</span><span class="sxs-lookup"><span data-stu-id="77343-113">Scenarios Using Atomic Transactions</span></span>](../core/scenarios-using-atomic-transactions.md)  
  
-   [<span data-ttu-id="77343-114">长时间运行的事务</span><span class="sxs-lookup"><span data-stu-id="77343-114">Long-Running Transactions</span></span>](../core/long-running-transactions.md)  
  
-   [<span data-ttu-id="77343-115">使用长期事务的方案</span><span class="sxs-lookup"><span data-stu-id="77343-115">Scenarios Using Long-Running Transactions</span></span>](../core/scenarios-using-long-running-transactions.md)  
  
-   [<span data-ttu-id="77343-116">业务流程的持久性</span><span class="sxs-lookup"><span data-stu-id="77343-116">Persistence in Orchestrations</span></span>](../core/persistence-in-orchestrations.md)