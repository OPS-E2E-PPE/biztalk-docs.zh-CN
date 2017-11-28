---
title: "如何执行策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0aa834150f0d5c84ebb4c757769a2be38f3942
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-execute-policies"></a><span data-ttu-id="754c8-102">如何执行策略</span><span class="sxs-lookup"><span data-stu-id="754c8-102">How to Execute Policies</span></span>
<span data-ttu-id="754c8-103">下面的示例代码演示如何调用要通过使用以编程方式执行策略的规则引擎**策略**类**Microsoft.RuleEngine**程序集。</span><span class="sxs-lookup"><span data-stu-id="754c8-103">The following sample code shows how to invoke the rule engine to execute a policy programmatically by using the **Policy** class in the **Microsoft.RuleEngine** assembly.</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a><span data-ttu-id="754c8-104">策略类的重要方法</span><span class="sxs-lookup"><span data-stu-id="754c8-104">Important methods of the Policy class</span></span>  
 <span data-ttu-id="754c8-105">以下是 Policy 类的重要方法及其说明。</span><span class="sxs-lookup"><span data-stu-id="754c8-105">Here are the important methods of the Policy class and their descriptions.</span></span>  
  
|<span data-ttu-id="754c8-106">Policy 类中的方法</span><span class="sxs-lookup"><span data-stu-id="754c8-106">Method in the Policy class</span></span>|<span data-ttu-id="754c8-107">Description</span><span class="sxs-lookup"><span data-stu-id="754c8-107">Description</span></span>|  
|--------------------------------|-----------------|  
|<span data-ttu-id="754c8-108">Execute</span><span class="sxs-lookup"><span data-stu-id="754c8-108">Execute</span></span>|<span data-ttu-id="754c8-109">将指定的短期事实添加到规则引擎的工作内存中，并使用匹配-冲突解决-操作算法执行策略。</span><span class="sxs-lookup"><span data-stu-id="754c8-109">Adds the specified short-term facts into the rule engine's working memory and executes the policy using Match-Conflict Resolution-Action algorithm.</span></span> <span data-ttu-id="754c8-110">匹配冲突解决操作算法的详细信息，请参阅[条件计算和操作执行](../core/condition-evaluation-and-action-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="754c8-110">For more information on Match-Conflict Resolution-Action algorithm, see [Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) .</span></span>|  
|<span data-ttu-id="754c8-111">释放</span><span class="sxs-lookup"><span data-stu-id="754c8-111">Dispose</span></span>|<span data-ttu-id="754c8-112">释放由规则引擎用来执行策略的资源。</span><span class="sxs-lookup"><span data-stu-id="754c8-112">Releases the resources used by the rule engine for executing the policy.</span></span>|  
|<span data-ttu-id="754c8-113">Clear</span><span class="sxs-lookup"><span data-stu-id="754c8-113">Clear</span></span>|<span data-ttu-id="754c8-114">清除或重置为执行策略而创建的规则引擎实例的工作内存和议程。</span><span class="sxs-lookup"><span data-stu-id="754c8-114">Clears or resets the working memory and the agenda of the rule engine instance created for executing the policy.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="754c8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="754c8-115">See Also</span></span>  
 [<span data-ttu-id="754c8-116">Policy.Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="754c8-116">Policy.Dispose Method</span></span>](../core/policy-dispose-method.md)