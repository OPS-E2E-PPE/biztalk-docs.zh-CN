---
title: 事务处理业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c6fb466e0c3cc5cae4a076237d1dbc970b5794
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278733"
---
# <a name="transacted-orchestrations"></a><span data-ttu-id="a549a-102">事务处理的业务流程</span><span class="sxs-lookup"><span data-stu-id="a549a-102">Transacted Orchestrations</span></span>
<span data-ttu-id="a549a-103">业务流程可以是事务性的，与作用域类似。</span><span class="sxs-lookup"><span data-stu-id="a549a-103">Orchestrations can be transactional, just like scopes.</span></span> <span data-ttu-id="a549a-104">实际上，业务流程本身可以视为作用域。</span><span class="sxs-lookup"><span data-stu-id="a549a-104">In fact, an orchestration can itself be considered a scope.</span></span> <span data-ttu-id="a549a-105">通常，同一规则对进行事务处理的业务流程的适用性与对进行事务处理的作用域的适用性是一样的。</span><span class="sxs-lookup"><span data-stu-id="a549a-105">In general, the same rules apply for transacted orchestrations as for transacted scopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a549a-106">业务流程和其他作用域之间的一个区别是，业务流程没有异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="a549a-106">One difference between orchestrations and other scopes is that orchestrations do not have exception handlers.</span></span>  
  
## <a name="orchestration-compensation"></a><span data-ttu-id="a549a-107">业务流程补偿</span><span class="sxs-lookup"><span data-stu-id="a549a-107">Orchestration compensation</span></span>  
 <span data-ttu-id="a549a-108">如果**事务类型**适用于你的业务流程的属性设置为长时间运行或原子性的你还可以选择的值**补偿**属性，它可以是默认或自定义。</span><span class="sxs-lookup"><span data-stu-id="a549a-108">If the **Transaction Type** property for your orchestration is set to long-running or atomic, you can also select a value for the **Compensation** property, which can be Default or Custom.</span></span>  
  
 <span data-ttu-id="a549a-109">如果你选择**自定义**的补偿，**补偿**选项卡将显示与业务流程设计图面。</span><span class="sxs-lookup"><span data-stu-id="a549a-109">If you select **Custom** for the compensation, a **Compensation** tab will appear alongside the Orchestration Design Surface.</span></span> <span data-ttu-id="a549a-110">其外观与业务流程设计图面一样，您可以用同样的方式向其中添加形状和端口。</span><span class="sxs-lookup"><span data-stu-id="a549a-110">It will look the same as the Orchestration Design Surface, and you can add shapes and ports to it in the same way.</span></span>  
  
 <span data-ttu-id="a549a-111">补偿只针对被其他业务流程调用的业务流程进行。</span><span class="sxs-lookup"><span data-stu-id="a549a-111">Compensations only take place on orchestrations that are called by other orchestrations.</span></span> <span data-ttu-id="a549a-112">你可以通过使用补偿的特定业务流程实例**标识符**属性**调用 Orchestration**形状。</span><span class="sxs-lookup"><span data-stu-id="a549a-112">You can compensate a specific orchestration instance by using the **Identifier** property on the **Call Orchestration** shape.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a549a-113">如果补偿存在于顶级业务流程，将被运行时引擎忽略。</span><span class="sxs-lookup"><span data-stu-id="a549a-113">If a compensation exists on a top-level orchestration, it will be ignored by the runtime engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a549a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a549a-114">See Also</span></span>  
 <span data-ttu-id="a549a-115">[使业务流程事务](../core/making-orchestrations-transactional.md) </span><span class="sxs-lookup"><span data-stu-id="a549a-115">[Making Orchestrations Transactional](../core/making-orchestrations-transactional.md) </span></span>  
 [<span data-ttu-id="a549a-116">使用事务和处理异常</span><span class="sxs-lookup"><span data-stu-id="a549a-116">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)