---
title: 补偿 |Microsoft Docs
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
ms.openlocfilehash: eba08eecad12c08a3bebd6f4704d7df82b74d279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357890"
---
# <a name="compensation"></a><span data-ttu-id="dcf2f-102">补偿</span><span class="sxs-lookup"><span data-stu-id="dcf2f-102">Compensation</span></span>
<span data-ttu-id="dcf2f-103">如果发生错误，并且需要进行撤消或已成功提交事务的影响，就可以做到补偿代码添加到您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-103">If an error occurs and you need to undo or reverse the effects of a successfully committed transaction, you can do so by adding compensation code to your orchestration.</span></span>  
  
 <span data-ttu-id="dcf2f-104">事务已成功完成其操作后，可以调用补偿。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-104">The compensation can be invoked after the transaction has completed its actions successfully.</span></span> <span data-ttu-id="dcf2f-105">此时，业务流程的状态已知的并且状态信息可供补偿，这意味着您可以编写代码时采取相应措施具体取决于业务流程的状态的事务提交中的代码。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-105">At that point, the state of the orchestration is known, and state information is available to the code in the compensation, which means that you can write code to act appropriately depending on the state of the orchestration when the transaction commits.</span></span>  
  
 <span data-ttu-id="dcf2f-106">也可以在原子事务提供补偿。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-106">Compensations can also be provided on atomic transactions.</span></span> <span data-ttu-id="dcf2f-107">这些补偿只能在原子事务提交后调用。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-107">These compensations can only be called after the atomic transaction commits.</span></span> <span data-ttu-id="dcf2f-108">您需要编写代码可以撤消的补偿中的常规执行路径。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-108">You need to write code to undo or reverse the path of the normal execution in the compensation.</span></span>  
  
 <span data-ttu-id="dcf2f-109">补偿模块是灵活;它可以包含其他任何形状，包括另一个事务作用域。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-109">The compensation block is flexible; it can contain any other shape, including another transaction scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcf2f-110">你可以执行补偿只能一次在给定作用域。</span><span class="sxs-lookup"><span data-stu-id="dcf2f-110">You can do a compensation only once on a given scope.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dcf2f-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="dcf2f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="dcf2f-112">如何配置补偿形状</span><span class="sxs-lookup"><span data-stu-id="dcf2f-112">How to Configure the Compensate Shape</span></span>](../core/how-to-configure-the-compensate-shape.md)  
  
-   [<span data-ttu-id="dcf2f-113">如何向业务流程添加自定义补偿</span><span class="sxs-lookup"><span data-stu-id="dcf2f-113">How to Add Custom Compensation to an Orchestration</span></span>](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [<span data-ttu-id="dcf2f-114">如何添加补偿块</span><span class="sxs-lookup"><span data-stu-id="dcf2f-114">How to Add a Compensation Block</span></span>](../core/how-to-add-a-compensation-block.md)