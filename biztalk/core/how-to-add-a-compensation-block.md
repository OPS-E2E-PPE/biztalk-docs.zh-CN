---
title: 如何添加补偿块 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef3cce71a85b41ccfc4291f82c5736d77f15162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343852"
---
# <a name="how-to-add-a-compensation-block"></a><span data-ttu-id="3d836-102">如何添加补偿块</span><span class="sxs-lookup"><span data-stu-id="3d836-102">How to Add a Compensation Block</span></span>
<span data-ttu-id="3d836-103">如果不添加您自己的补偿，则运行时引擎将执行默认补偿调用当前事务中任何嵌套事务的补偿。</span><span class="sxs-lookup"><span data-stu-id="3d836-103">If you do not add your own compensation, the runtime engine performs a default compensation that invokes the compensations of any nested transactions within the current transaction.</span></span> <span data-ttu-id="3d836-104">首先调用最近完成的事务，补偿，并向后工作，直到所有嵌套的事务有补偿。</span><span class="sxs-lookup"><span data-stu-id="3d836-104">It first invokes the compensation of the most recently completed transaction, and works backward until all nested transactions have been compensated.</span></span>  
  
 <span data-ttu-id="3d836-105">这为 true 甚至当您的补偿内发生循环形状： 补偿将以反向顺序运行。</span><span class="sxs-lookup"><span data-stu-id="3d836-105">This holds true even when your compensation takes place inside a Loop shape: the compensations will be run in reverse order.</span></span> <span data-ttu-id="3d836-106">首先，将调用循环的最后一个迭代的补偿，然后补偿的上一次迭代，依次类推。</span><span class="sxs-lookup"><span data-stu-id="3d836-106">First, the compensation for the last iteration of the loop will be invoked, then the compensation for the previous iteration, and so on.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3d836-107">由于数据将保存到补偿有效的物理内存，使用补偿在循环内，可能会影响性能，这可能会提供大量迭代出现问题。</span><span class="sxs-lookup"><span data-stu-id="3d836-107">Because data is persisted to physical memory for compensation to work, using compensations inside a loop might affect performance, which might be an issue given a large number of iterations.</span></span>  
  
 <span data-ttu-id="3d836-108">如果默认顺序无法满足您的要求，可以编写您自己的补偿处理程序，以显式调用中所指定的顺序的嵌套作用域的补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="3d836-108">If the default ordering does not fit your requirements, you can write your own compensation handler to explicitly call the compensation handlers of the nested scopes in the order you specify.</span></span>  
  
### <a name="to-add-a-compensation-block"></a><span data-ttu-id="3d836-109">若要添加补偿模块</span><span class="sxs-lookup"><span data-stu-id="3d836-109">To add a Compensation Block</span></span>  
  
1.  <span data-ttu-id="3d836-110">右键单击**作用域**交易记录你想要添加的形状**补偿模块**，然后单击**新建补偿模块**。</span><span class="sxs-lookup"><span data-stu-id="3d836-110">Right-click the **Scope** shape for the transaction to which you want to add a **Compensation Block**, and then click **New Compensation Block**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d836-111">若要添加**补偿模块**到**作用域**形状，**事务类型**属性的**范围**形状必须设置为**原子**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="3d836-111">To add a **Compensation Block** to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **Atomic** or **Long Running**.</span></span>  
  
     <span data-ttu-id="3d836-112">一个**补偿模块**添加到紧跟相关业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="3d836-112">A **Compensation Block** is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="3d836-113">内部**补偿模块**形状中，添加形状以创建用于撤消已提交的事务的进程。</span><span class="sxs-lookup"><span data-stu-id="3d836-113">Inside the **Compensation Block** shape, add shapes to create the process for undoing a committed transaction.</span></span>