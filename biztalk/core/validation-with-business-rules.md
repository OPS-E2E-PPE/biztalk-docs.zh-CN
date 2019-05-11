---
title: 使用业务规则验证 |Microsoft Docs
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
ms.openlocfilehash: 2383f8cabf2e27aa62b7bdcfd6ac56ec30acc018
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292622"
---
# <a name="validation-with-business-rules"></a><span data-ttu-id="1d164-102">使用业务规则进行验证</span><span class="sxs-lookup"><span data-stu-id="1d164-102">Validation with Business Rules</span></span>
<span data-ttu-id="1d164-103">执行验证的常用方法是构造的使用业务规则框架的业务规则集。</span><span class="sxs-lookup"><span data-stu-id="1d164-103">A common way to do validation is to construct a set of business rules using the Business Rules Framework.</span></span> <span data-ttu-id="1d164-104">然后使用调用规则形状在业务流程中想要执行验证。</span><span class="sxs-lookup"><span data-stu-id="1d164-104">Then you use the Call Rules shape in the orchestration where you want to perform validation.</span></span>  
  
 <span data-ttu-id="1d164-105">在业务流程管理应用程序，**验证**业务流程使用业务规则来测试订单的有效性。</span><span class="sxs-lookup"><span data-stu-id="1d164-105">In the business process management application, the **Validation** orchestration uses business rules to test the validity of the order.</span></span>  
  
 <span data-ttu-id="1d164-106">使用业务规则框架，可更改的规则，而无需重新编译和重新部署**验证**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1d164-106">Using the Business Rules Framework enables you to change the rules without recompiling and redeploying the **Validation** orchestration.</span></span> <span data-ttu-id="1d164-107">弊端是，对于简单的规则集，您可能必须能够通过编码在业务流程中的逻辑来节省处理时间。</span><span class="sxs-lookup"><span data-stu-id="1d164-107">The trade-off is that for simple sets of rules, you may be able to save processing time by coding the logic in the orchestration.</span></span>  
  
 <span data-ttu-id="1d164-108">有关使用业务规则框架的详细信息，请参阅[创建和使用业务规则](../core/creating-and-using-business-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="1d164-108">For more information about using the Business Rules Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="1d164-109">有关调用规则形状的详细信息，请参阅[如何使用调用规则形状](../core/how-to-use-the-call-rules-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="1d164-109">For more information about the Call Rules shape, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d164-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d164-110">See Also</span></span>  
 <span data-ttu-id="1d164-111">[业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="1d164-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="1d164-112">进程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="1d164-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)