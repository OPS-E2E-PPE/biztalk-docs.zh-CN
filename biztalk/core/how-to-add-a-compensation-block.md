---
title: 如何添加补偿块 |Microsoft 文档
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
ms.openlocfilehash: a2dec4f4dd01c2bbf522dfff44ec8aaf0c2f5e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246533"
---
# <a name="how-to-add-a-compensation-block"></a><span data-ttu-id="0a1d7-102">如何添加补偿模块</span><span class="sxs-lookup"><span data-stu-id="0a1d7-102">How to Add a Compensation Block</span></span>
<span data-ttu-id="0a1d7-103">如果您没有添加您自己的补偿，则运行时引擎将执行默认补偿，该默认补偿调用当前事务内任何嵌套事务的补偿。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-103">If you do not add your own compensation, the runtime engine performs a default compensation that invokes the compensations of any nested transactions within the current transaction.</span></span> <span data-ttu-id="0a1d7-104">它首先调用最近完成的事务的补偿，并直到所有嵌套的事务都已得到补偿前一直有效。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-104">It first invokes the compensation of the most recently completed transaction, and works backward until all nested transactions have been compensated.</span></span>  
  
 <span data-ttu-id="0a1d7-105">甚至当你补偿内发生循环形状这保持为 true: 补偿将按相反的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-105">This holds true even when your compensation takes place inside a Loop shape: the compensations will be run in reverse order.</span></span> <span data-ttu-id="0a1d7-106">首先，将调用循环中最后一个迭代的补偿，然后调用前一个迭代的补偿，依此类推。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-106">First, the compensation for the last iteration of the loop will be invoked, then the compensation for the previous iteration, and so on.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0a1d7-107">由于为使补偿有效，数据将保存到物理内存中，因此，在循环内使用补偿可能会影响性能，在有大量迭代存在的情况下，可能导致问题。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-107">Because data is persisted to physical memory for compensation to work, using compensations inside a loop might affect performance, which might be an issue given a large number of iterations.</span></span>  
  
 <span data-ttu-id="0a1d7-108">如果默认顺序无法满足您的要求，您可以编写自己的补偿处理程序，以便按您指定的顺序显式调用嵌套作用域的补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-108">If the default ordering does not fit your requirements, you can write your own compensation handler to explicitly call the compensation handlers of the nested scopes in the order you specify.</span></span>  
  
### <a name="to-add-a-compensation-block"></a><span data-ttu-id="0a1d7-109">添加补偿模块</span><span class="sxs-lookup"><span data-stu-id="0a1d7-109">To add a Compensation Block</span></span>  
  
1.  <span data-ttu-id="0a1d7-110">右键单击**作用域**你想要添加的事务的形状**补偿块**，然后单击**新补偿块**。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-110">Right-click the **Scope** shape for the transaction to which you want to add a **Compensation Block**, and then click **New Compensation Block**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a1d7-111">若要添加**补偿块**到**作用域**形状，**事务类型**属性**作用域**形状必须设置为**原子**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-111">To add a **Compensation Block** to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **Atomic** or **Long Running**.</span></span>  
  
     <span data-ttu-id="0a1d7-112">A**补偿块**添加到紧跟在关联的业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-112">A **Compensation Block** is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="0a1d7-113">内部**补偿块**形状，添加形状创建撤消已提交的事务的过程。</span><span class="sxs-lookup"><span data-stu-id="0a1d7-113">Inside the **Compensation Block** shape, add shapes to create the process for undoing a committed transaction.</span></span>