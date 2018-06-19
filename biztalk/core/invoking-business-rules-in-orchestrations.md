---
title: 调用在业务流程中的业务规则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], business rules
- business rules, orchestrations
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
- orchestrations, business rules
ms.assetid: ac3a3277-e9ea-4f40-9326-c63076c6b90e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ecbb9738089dfa2d885f9aa45ac12e92ed27aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261821"
---
# <a name="invoking-business-rules-in-orchestrations"></a><span data-ttu-id="15317-102">调用在业务流程中的业务规则</span><span class="sxs-lookup"><span data-stu-id="15317-102">Invoking Business Rules in Orchestrations</span></span>
<span data-ttu-id="15317-103">你可以调用从使用业务流程的策略 （或规则集）**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="15317-103">You can invoke a policy (or rule set) from an orchestration by using the **Call Rules** shape.</span></span> <span data-ttu-id="15317-104">策略将调用对策略中的规则执行操作的规则引擎。</span><span class="sxs-lookup"><span data-stu-id="15317-104">The policy invokes the rule engine, which operates on the rules in the policy.</span></span>  
  
 <span data-ttu-id="15317-105">除了使用调用的规则，可以从表达式以编程方式调用引擎的规则中的代码，例如，**表达式**或**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="15317-105">In addition to using Call Rules, the rules engine can be programmatically called from expression code, for example, in an **Expression** or **Message Assignment** shape.</span></span> <span data-ttu-id="15317-106">有关以编程方式执行策略的信息，请参阅[如何执行策略](../core/how-to-execute-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="15317-106">For information about programmatically executing policies, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  
  
 <span data-ttu-id="15317-107">本部分介绍调用并执行 BizTalk 业务流程中的业务策略所需的配置信息和过程。</span><span class="sxs-lookup"><span data-stu-id="15317-107">This section describes configuration information and the procedures required to call and execute a business policy from a BizTalk orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15317-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="15317-108">In This Section</span></span>  
  
-   [<span data-ttu-id="15317-109">配置信息</span><span class="sxs-lookup"><span data-stu-id="15317-109">Configuration Information</span></span>](../core/configuration-information.md)  
  
-   [<span data-ttu-id="15317-110">如何使用调用规则形状</span><span class="sxs-lookup"><span data-stu-id="15317-110">How to Use the Call Rules Shape</span></span>](../core/how-to-use-the-call-rules-shape.md)