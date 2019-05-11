---
title: 事务性业务流程 |Microsoft Docs
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
ms.openlocfilehash: 2607c6619391481870baa19b5cda07d7419f9dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313294"
---
# <a name="transacted-orchestrations"></a><span data-ttu-id="59a6a-102">事务处理业务流程</span><span class="sxs-lookup"><span data-stu-id="59a6a-102">Transacted Orchestrations</span></span>
<span data-ttu-id="59a6a-103">业务流程可以是事务性的作用域类似。</span><span class="sxs-lookup"><span data-stu-id="59a6a-103">Orchestrations can be transactional, just like scopes.</span></span> <span data-ttu-id="59a6a-104">实际上，业务流程本身可以视为作用域。</span><span class="sxs-lookup"><span data-stu-id="59a6a-104">In fact, an orchestration can itself be considered a scope.</span></span> <span data-ttu-id="59a6a-105">一般情况下，同一规则对进行事务处理业务流程与事务处理的作用域。</span><span class="sxs-lookup"><span data-stu-id="59a6a-105">In general, the same rules apply for transacted orchestrations as for transacted scopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59a6a-106">业务流程和其他作用域之间的一个区别是，业务流程没有异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="59a6a-106">One difference between orchestrations and other scopes is that orchestrations do not have exception handlers.</span></span>  
  
## <a name="orchestration-compensation"></a><span data-ttu-id="59a6a-107">业务流程补偿</span><span class="sxs-lookup"><span data-stu-id="59a6a-107">Orchestration compensation</span></span>  
 <span data-ttu-id="59a6a-108">如果**事务类型**业务流程的属性设置为长时间运行或原子的您还可以选择的值**补偿**属性，它可以是默认或自定义。</span><span class="sxs-lookup"><span data-stu-id="59a6a-108">If the **Transaction Type** property for your orchestration is set to long-running or atomic, you can also select a value for the **Compensation** property, which can be Default or Custom.</span></span>  
  
 <span data-ttu-id="59a6a-109">如果选择**自定义**补偿**补偿**选项卡将显示与业务流程设计图面。</span><span class="sxs-lookup"><span data-stu-id="59a6a-109">If you select **Custom** for the compensation, a **Compensation** tab will appear alongside the Orchestration Design Surface.</span></span> <span data-ttu-id="59a6a-110">它看起来相同作为业务流程设计图面上，并且可以添加形状和端口到该相同的方式。</span><span class="sxs-lookup"><span data-stu-id="59a6a-110">It will look the same as the Orchestration Design Surface, and you can add shapes and ports to it in the same way.</span></span>  
  
 <span data-ttu-id="59a6a-111">补偿只会在由其他业务流程调用的业务流程上发生。</span><span class="sxs-lookup"><span data-stu-id="59a6a-111">Compensations only take place on orchestrations that are called by other orchestrations.</span></span> <span data-ttu-id="59a6a-112">可以通过使用补偿特定业务流程实例**标识符**上的属性**调用业务流程**形状。</span><span class="sxs-lookup"><span data-stu-id="59a6a-112">You can compensate a specific orchestration instance by using the **Identifier** property on the **Call Orchestration** shape.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59a6a-113">如果补偿存在于顶级业务流程，运行时引擎将忽略它。</span><span class="sxs-lookup"><span data-stu-id="59a6a-113">If a compensation exists on a top-level orchestration, it will be ignored by the runtime engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a6a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="59a6a-114">See Also</span></span>  
 <span data-ttu-id="59a6a-115">[使业务流程成为事务性](../core/making-orchestrations-transactional.md) </span><span class="sxs-lookup"><span data-stu-id="59a6a-115">[Making Orchestrations Transactional](../core/making-orchestrations-transactional.md) </span></span>  
 [<span data-ttu-id="59a6a-116">使用事务和处理异常</span><span class="sxs-lookup"><span data-stu-id="59a6a-116">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)