---
title: 如何执行策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eaf60193a3435808c0901ca1c441527a67884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337821"
---
# <a name="how-to-execute-policies"></a><span data-ttu-id="4feab-102">如何执行策略</span><span class="sxs-lookup"><span data-stu-id="4feab-102">How to Execute Policies</span></span>
<span data-ttu-id="4feab-103">下面的示例代码演示如何调用规则引擎，通过以编程方式执行策略**策略**类**Microsoft.RuleEngine**程序集。</span><span class="sxs-lookup"><span data-stu-id="4feab-103">The following sample code shows how to invoke the rule engine to execute a policy programmatically by using the **Policy** class in the **Microsoft.RuleEngine** assembly.</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a><span data-ttu-id="4feab-104">Policy 类的重要方法</span><span class="sxs-lookup"><span data-stu-id="4feab-104">Important methods of the Policy class</span></span>  
 <span data-ttu-id="4feab-105">以下是 Policy 类和及其说明的重要方法。</span><span class="sxs-lookup"><span data-stu-id="4feab-105">Here are the important methods of the Policy class and their descriptions.</span></span>  
  
|<span data-ttu-id="4feab-106">Policy 类中的方法</span><span class="sxs-lookup"><span data-stu-id="4feab-106">Method in the Policy class</span></span>|<span data-ttu-id="4feab-107">Description</span><span class="sxs-lookup"><span data-stu-id="4feab-107">Description</span></span>|  
|--------------------------------|-----------------|  
|<span data-ttu-id="4feab-108">Execute</span><span class="sxs-lookup"><span data-stu-id="4feab-108">Execute</span></span>|<span data-ttu-id="4feab-109">将指定的短期事实添加到规则引擎工作内存和执行使用匹配-冲突解决-操作算法策略。</span><span class="sxs-lookup"><span data-stu-id="4feab-109">Adds the specified short-term facts into the rule engine's working memory and executes the policy using Match-Conflict Resolution-Action algorithm.</span></span> <span data-ttu-id="4feab-110">匹配-冲突解决-操作算法的详细信息，请参阅[条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="4feab-110">For more information on Match-Conflict Resolution-Action algorithm, see [Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) .</span></span>|  
|<span data-ttu-id="4feab-111">释放</span><span class="sxs-lookup"><span data-stu-id="4feab-111">Dispose</span></span>|<span data-ttu-id="4feab-112">释放由执行策略的规则引擎使用的资源。</span><span class="sxs-lookup"><span data-stu-id="4feab-112">Releases the resources used by the rule engine for executing the policy.</span></span>|  
|<span data-ttu-id="4feab-113">Clear</span><span class="sxs-lookup"><span data-stu-id="4feab-113">Clear</span></span>|<span data-ttu-id="4feab-114">清除或重置的工作内存和议程为执行策略创建的规则引擎实例。</span><span class="sxs-lookup"><span data-stu-id="4feab-114">Clears or resets the working memory and the agenda of the rule engine instance created for executing the policy.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4feab-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4feab-115">See Also</span></span>  
 [<span data-ttu-id="4feab-116">Policy.Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="4feab-116">Policy.Dispose Method</span></span>](../core/policy-dispose-method.md)