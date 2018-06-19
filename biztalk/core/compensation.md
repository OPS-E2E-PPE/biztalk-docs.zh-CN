---
title: 补偿 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, errors
- compensations
- errors, compensations
- compensations, about compensations
- compensations, atomic transactions
- atomic transactions, compensations
- transactions, compensations
ms.assetid: 0a80dd16-fd35-4f45-95b7-52bb9df80cbb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c572638ea6212c3fb79e6b239aa8ffbe713c3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231597"
---
# <a name="compensation"></a><span data-ttu-id="06739-102">补偿</span><span class="sxs-lookup"><span data-stu-id="06739-102">Compensation</span></span>
<span data-ttu-id="06739-103">如果出现错误，并且你需要撤消或反向成功提交事务的效果，你可以这样做将补偿代码添加到您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="06739-103">If an error occurs and you need to undo or reverse the effects of a successfully committed transaction, you can do so by adding compensation code to your orchestration.</span></span>  
  
 <span data-ttu-id="06739-104">事务成功完成其操作后，可以调用补偿。</span><span class="sxs-lookup"><span data-stu-id="06739-104">The compensation can be invoked after the transaction has completed its actions successfully.</span></span> <span data-ttu-id="06739-105">此时，已知的业务流程的状态，并且状态信息可供中的补偿，这意味着你可以编写代码以采取相应措施具体取决于业务流程的状态在事务提交时的代码。</span><span class="sxs-lookup"><span data-stu-id="06739-105">At that point, the state of the orchestration is known, and state information is available to the code in the compensation, which means that you can write code to act appropriately depending on the state of the orchestration when the transaction commits.</span></span>  
  
 <span data-ttu-id="06739-106">也可以在原子事务提供补偿。</span><span class="sxs-lookup"><span data-stu-id="06739-106">Compensations can also be provided on atomic transactions.</span></span> <span data-ttu-id="06739-107">原子事务提交后，可以仅调用这些补偿。</span><span class="sxs-lookup"><span data-stu-id="06739-107">These compensations can only be called after the atomic transaction commits.</span></span> <span data-ttu-id="06739-108">你需要编写代码以撤消或反向补偿在正常执行路径中。</span><span class="sxs-lookup"><span data-stu-id="06739-108">You need to write code to undo or reverse the path of the normal execution in the compensation.</span></span>  
  
 <span data-ttu-id="06739-109">补偿块是灵活;它可以包含任何其他形状，包括另一个事务范围。</span><span class="sxs-lookup"><span data-stu-id="06739-109">The compensation block is flexible; it can contain any other shape, including another transaction scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06739-110">你可以执行一次在给定作用域上的补偿。</span><span class="sxs-lookup"><span data-stu-id="06739-110">You can do a compensation only once on a given scope.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06739-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="06739-111">In This Section</span></span>  
  
-   [<span data-ttu-id="06739-112">如何配置 Compensate 形状</span><span class="sxs-lookup"><span data-stu-id="06739-112">How to Configure the Compensate Shape</span></span>](../core/how-to-configure-the-compensate-shape.md)  
  
-   [<span data-ttu-id="06739-113">如何将自定义补偿添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="06739-113">How to Add Custom Compensation to an Orchestration</span></span>](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [<span data-ttu-id="06739-114">如何添加补偿块</span><span class="sxs-lookup"><span data-stu-id="06739-114">How to Add a Compensation Block</span></span>](../core/how-to-add-a-compensation-block.md)