---
title: 如何配置 Compensate 形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059ac58d95d33234737033c00c4a6a2a36e256f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248277"
---
# <a name="how-to-configure-the-compensate-shape"></a><span data-ttu-id="a130b-102">如何配置 Compensate 形状</span><span class="sxs-lookup"><span data-stu-id="a130b-102">How to Configure the Compensate Shape</span></span>
<span data-ttu-id="a130b-103">如果你在业务流程中使用嵌套的事务，你可以添加**Compensate**补偿块或事务范围的异常块中的形状。</span><span class="sxs-lookup"><span data-stu-id="a130b-103">If you are using nested transactions in your orchestration, you can add a **Compensate** shape in the compensation block or an exception block of a transaction scope.</span></span> <span data-ttu-id="a130b-104">这样可以使您的业务流程能够明确地对嵌套事务执行补偿操作。</span><span class="sxs-lookup"><span data-stu-id="a130b-104">This enables your orchestration to explicitly perform compensation on a nested transaction.</span></span> <span data-ttu-id="a130b-105">指定你想要在补偿的事务**Compensate**形状，以及在嵌套事务中的任何补偿代码将运行，提供已成功提交的事务。</span><span class="sxs-lookup"><span data-stu-id="a130b-105">You specify which transaction you would like to be compensated in the **Compensate** shape, and any compensation code in the nested transaction will be run, provided the transaction committed successfully.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a130b-106">**补偿**属性指的事务作用域的唯一标识符; 它不是指作用域的名称。</span><span class="sxs-lookup"><span data-stu-id="a130b-106">The **Compensation** property refers to the unique identifier of the transaction scope; it does not refer to the name of the scope.</span></span>  
  
 <span data-ttu-id="a130b-107">如果你想要补偿多个嵌套的事务，则添加附加**Compensate**每个事务的形状。</span><span class="sxs-lookup"><span data-stu-id="a130b-107">If you want to compensate more than one nested transaction, you add an additional **Compensate** shape for each transaction.</span></span>  
  
 <span data-ttu-id="a130b-108">不**Compensate**形状是外部事务中没有其他补偿代码是否有必要; 任何嵌套的事务的补偿代码将自动运行。</span><span class="sxs-lookup"><span data-stu-id="a130b-108">No **Compensate** shape is necessary if there is no other compensation code in an outer transaction; the compensation code of any nested transactions will be run automatically.</span></span> <span data-ttu-id="a130b-109">**Compensate**调整的允许你通过允许你决定是否要进行补偿的嵌套的事务控制该过程。</span><span class="sxs-lookup"><span data-stu-id="a130b-109">The **Compensate** shape gives you control over the process by allowing you to decide whether or not you want a nested transaction to be compensated.</span></span>  
  
### <a name="to-configure-a-compensate-shape"></a><span data-ttu-id="a130b-110">配置补偿形状</span><span class="sxs-lookup"><span data-stu-id="a130b-110">To configure a Compensate shape</span></span>  
  
-   <span data-ttu-id="a130b-111">在属性窗口中，选择要从调用的补偿块**补偿**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a130b-111">In the Properties window, select the compensation block to call from the **Compensation** drop-down list.</span></span>  
  
     <span data-ttu-id="a130b-112">该下拉列表将显示可以对其执行补偿操作的所有事务，其中包括当前事务以及当前事务的任何直接子事务。</span><span class="sxs-lookup"><span data-stu-id="a130b-112">The drop-down list will display all of the transactions which can be compensated, which includes the current transaction and any immediate child transactions of the current transaction.</span></span> <span data-ttu-id="a130b-113">如果您没有看到预期的事务，这可能是事务关系的原因导致的。</span><span class="sxs-lookup"><span data-stu-id="a130b-113">If you cannot see a transaction that you expect, it might be due to the relationship of the transactions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a130b-114">不能在当前事务的事务主体内对其执行补偿操作。</span><span class="sxs-lookup"><span data-stu-id="a130b-114">You cannot compensate the current transaction from within the body of the transaction.</span></span>  <span data-ttu-id="a130b-115">您可以从该事务的补偿模块或事务的异常块对其执行补偿操作。</span><span class="sxs-lookup"><span data-stu-id="a130b-115">You can compensate it from the compensation block or an exception block of the transaction.</span></span>  
  
     <span data-ttu-id="a130b-116">如果您选择对当前事务执行补偿操作，这意味着将调用默认处理程序，而不是显式补偿模块（如果有）。</span><span class="sxs-lookup"><span data-stu-id="a130b-116">If you choose to compensate the current transaction, that means that the default handler will be invoked, and not an explicit compensation block (if there is one).</span></span> <span data-ttu-id="a130b-117">这是一种用于自动补偿已成功完成的直接嵌套的事务的机制。</span><span class="sxs-lookup"><span data-stu-id="a130b-117">This is a mechanism for automatically compensating directly nested transactions that have completed successfully.</span></span>