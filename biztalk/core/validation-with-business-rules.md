---
title: 使用业务规则验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, process management solutions
- process management solution tutorial, validating
- business rules, validating
- process management solution tutorial, business rules
ms.assetid: a67f3781-629a-4157-9a27-3b73d7a5a3a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8926cf8bd95c2b90c7d16151b47f8893120b812e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287773"
---
# <a name="validation-with-business-rules"></a><span data-ttu-id="e20d0-102">使用业务规则验证</span><span class="sxs-lookup"><span data-stu-id="e20d0-102">Validation with Business Rules</span></span>
<span data-ttu-id="e20d0-103">执行验证的常用方法是构造一组使用业务规则框架的业务规则。</span><span class="sxs-lookup"><span data-stu-id="e20d0-103">A common way to do validation is to construct a set of business rules using the Business Rules Framework.</span></span> <span data-ttu-id="e20d0-104">然后你使用调用规则形状中业务流程你想要执行验证。</span><span class="sxs-lookup"><span data-stu-id="e20d0-104">Then you use the Call Rules shape in the orchestration where you want to perform validation.</span></span>  
  
 <span data-ttu-id="e20d0-105">在业务流程的管理应用程序，**验证**业务流程使用业务规则以测试顺序的有效性。</span><span class="sxs-lookup"><span data-stu-id="e20d0-105">In the business process management application, the **Validation** orchestration uses business rules to test the validity of the order.</span></span>  
  
 <span data-ttu-id="e20d0-106">使用业务规则框架使你能够更改规则而无需重新编译和重新部署**验证**业务流程。</span><span class="sxs-lookup"><span data-stu-id="e20d0-106">Using the Business Rules Framework enables you to change the rules without recompiling and redeploying the **Validation** orchestration.</span></span> <span data-ttu-id="e20d0-107">折中方案是，对于简单的一组规则，你可能能够进行编码业务流程中的逻辑来节省处理时间。</span><span class="sxs-lookup"><span data-stu-id="e20d0-107">The trade-off is that for simple sets of rules, you may be able to save processing time by coding the logic in the orchestration.</span></span>  
  
 <span data-ttu-id="e20d0-108">有关使用业务规则框架的详细信息，请参阅[创建和使用业务规则](../core/creating-and-using-business-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="e20d0-108">For more information about using the Business Rules Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="e20d0-109">有关调用规则形状的详细信息，请参阅[如何使用调用规则形状](../core/how-to-use-the-call-rules-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="e20d0-109">For more information about the Call Rules shape, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e20d0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e20d0-110">See Also</span></span>  
 <span data-ttu-id="e20d0-111">[实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="e20d0-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="e20d0-112">过程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="e20d0-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)