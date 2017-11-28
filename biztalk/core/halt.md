---
title: "暂停 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ca8091d4ff4405704314d72939758c7600a71a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="halt"></a><span data-ttu-id="6482a-102">异常终止</span><span class="sxs-lookup"><span data-stu-id="6482a-102">Halt</span></span>
<span data-ttu-id="6482a-103">你可以使用**暂停**暂停当前规则引擎执行的函数。</span><span class="sxs-lookup"><span data-stu-id="6482a-103">You can use the **Halt** function to halt the current rule engine execution.</span></span> <span data-ttu-id="6482a-104">**暂停**函数采用一个类型的参数`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="6482a-104">The **Halt** function takes one parameter of type `Boolean`.</span></span> <span data-ttu-id="6482a-105">如果指定为参数的值`true`，规则引擎还会清除包含的挂起的候选规则的安排。</span><span class="sxs-lookup"><span data-stu-id="6482a-105">If you specify the value for the parameter as `true`, the rule engine also clears the agenda that contains the pending candidate rules.</span></span>  
  
 <span data-ttu-id="6482a-106">**Policy.Execute**方法基本上是周围的包装器**RuleEngine.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="6482a-106">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="6482a-107">其代码如下：</span><span class="sxs-lookup"><span data-stu-id="6482a-107">It has code similar to the following code:</span></span>  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="6482a-108">如果你使用**Policy.Execute**方法以执行策略，规则引擎将控制权返回到**Policy.Execute**方法时**暂停**执行函数。</span><span class="sxs-lookup"><span data-stu-id="6482a-108">If you use the **Policy.Execute** method to execute a policy, the rule engine returns control to the **Policy.Execute** method when the **Halt** function is executed.</span></span> <span data-ttu-id="6482a-109">**Policy.Execute**方法将收回事实数据并将控制权返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="6482a-109">The **Policy.Execute** method retracts the facts and returns control to the caller.</span></span> <span data-ttu-id="6482a-110">因此，已停止的策略执行不能在此情况下恢复。</span><span class="sxs-lookup"><span data-stu-id="6482a-110">Therefore, the halted policy execution cannot be resumed in this case.</span></span> <span data-ttu-id="6482a-111">当你使用时，会发生情况同样**调用规则**形状以调用该策略。</span><span class="sxs-lookup"><span data-stu-id="6482a-111">The same thing happens when you use the **Call Rules** shape to invoke the policy.</span></span>  
  
 <span data-ttu-id="6482a-112">但是，如果你使用**RuleEngine.Execute**方法直接以执行策略，可以继续挂起的规则触发下一步暂停的策略执行通过只需调用**RuleEngine.Execute**再次 （前提是未收回之间的两个调用所需的任何对象）。</span><span class="sxs-lookup"><span data-stu-id="6482a-112">However, if you use the **RuleEngine.Execute** method directly to execute the policy, you can resume the halted policy execution with the next pending rule firing by simply calling **RuleEngine.Execute** again (provided you did not retract any objects needed between the two calls).</span></span> <span data-ttu-id="6482a-113">恢复已停止的策略执行的示例代码如下：</span><span class="sxs-lookup"><span data-stu-id="6482a-113">The sample code for resuming the halted policy execution is as follows:</span></span>  
  
```  
//assert facts into working memory of the rule engine instance  
RuleEngine.Assert(facts);   
//execute the policy  
RuleEngine.Execute();   
//policy invokes the Halt method when executing actions.   
//control is returned to here when the Halt method is invoked  
  
//when engine is halted do the following  
//Add your code here  
  
//To resume the halted rule engine execution  
RuleEngine.Execute();  
//retract or remove facts frm the working memory of the rule engine  
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="6482a-114">请注意， **Policy.Execute**方法缓存更好的性能规则引擎实例。</span><span class="sxs-lookup"><span data-stu-id="6482a-114">Note that the **Policy.Execute** method caches the rule engine instances for better performance.</span></span> <span data-ttu-id="6482a-115">当你使用**RuleEngine.Execute**直接方法，不会缓存实例的规则引擎。</span><span class="sxs-lookup"><span data-stu-id="6482a-115">When you use the **RuleEngine.Execute** method directly, the rule engine instances are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6482a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6482a-116">See Also</span></span>  
 [<span data-ttu-id="6482a-117">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="6482a-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)