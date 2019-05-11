---
title: 业务流程中调用业务规则 |Microsoft Docs
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
ms.openlocfilehash: 691fa4bf5e9633e32cfb5583ab8a181f0f69633a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380987"
---
# <a name="invoking-business-rules-in-orchestrations"></a><span data-ttu-id="cb4dc-102">业务流程中调用业务规则</span><span class="sxs-lookup"><span data-stu-id="cb4dc-102">Invoking Business Rules in Orchestrations</span></span>
<span data-ttu-id="cb4dc-103">可以调用策略 （或规则集） 从通过使用业务流程**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="cb4dc-103">You can invoke a policy (or rule set) from an orchestration by using the **Call Rules** shape.</span></span> <span data-ttu-id="cb4dc-104">策略将调用规则引擎，在策略中的规则执行操作。</span><span class="sxs-lookup"><span data-stu-id="cb4dc-104">The policy invokes the rule engine, which operates on the rules in the policy.</span></span>  
  
 <span data-ttu-id="cb4dc-105">除了使用调用规则，的规则引擎可以以编程方式调用从表达式中的代码，例如，**表达式**或**消息赋值**形状。</span><span class="sxs-lookup"><span data-stu-id="cb4dc-105">In addition to using Call Rules, the rules engine can be programmatically called from expression code, for example, in an **Expression** or **Message Assignment** shape.</span></span> <span data-ttu-id="cb4dc-106">有关以编程方式执行策略的信息，请参阅[如何执行策略](../core/how-to-execute-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4dc-106">For information about programmatically executing policies, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  
  
 <span data-ttu-id="cb4dc-107">本部分介绍配置信息和调用并执行业务策略从 BizTalk 业务流程所需的过程。</span><span class="sxs-lookup"><span data-stu-id="cb4dc-107">This section describes configuration information and the procedures required to call and execute a business policy from a BizTalk orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb4dc-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="cb4dc-108">In This Section</span></span>  
  
-   [<span data-ttu-id="cb4dc-109">配置信息</span><span class="sxs-lookup"><span data-stu-id="cb4dc-109">Configuration Information</span></span>](../core/configuration-information.md)  
  
-   [<span data-ttu-id="cb4dc-110">如何使用调用规则形状</span><span class="sxs-lookup"><span data-stu-id="cb4dc-110">How to Use the Call Rules Shape</span></span>](../core/how-to-use-the-call-rules-shape.md)