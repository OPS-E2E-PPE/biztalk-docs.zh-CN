---
title: Halt | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc7006581b3ccbf856d48d365cf6b003d97ec93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344790"
---
# <a name="halt"></a><span data-ttu-id="210a4-102">暂停</span><span class="sxs-lookup"><span data-stu-id="210a4-102">Halt</span></span>
<span data-ttu-id="210a4-103">可以使用**暂停**函数停止当前规则引擎执行。</span><span class="sxs-lookup"><span data-stu-id="210a4-103">You can use the **Halt** function to halt the current rule engine execution.</span></span> <span data-ttu-id="210a4-104">**暂停**函数采用一个参数类型的`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="210a4-104">The **Halt** function takes one parameter of type `Boolean`.</span></span> <span data-ttu-id="210a4-105">如果指定为参数的值为`true`，规则引擎还会清除包含挂起的候选规则的议程。</span><span class="sxs-lookup"><span data-stu-id="210a4-105">If you specify the value for the parameter as `true`, the rule engine also clears the agenda that contains the pending candidate rules.</span></span>  
  
 <span data-ttu-id="210a4-106">**Policy.Execute**方法基本上是周围的包装**RuleEngine.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="210a4-106">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="210a4-107">它具有类似于下面的代码的代码：</span><span class="sxs-lookup"><span data-stu-id="210a4-107">It has code similar to the following code:</span></span>  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="210a4-108">如果您使用**Policy.Execute**方法以执行策略，规则引擎将控制权返回给**Policy.Execute**方法时**暂停**执行函数。</span><span class="sxs-lookup"><span data-stu-id="210a4-108">If you use the **Policy.Execute** method to execute a policy, the rule engine returns control to the **Policy.Execute** method when the **Halt** function is executed.</span></span> <span data-ttu-id="210a4-109">**Policy.Execute**方法取消事实并将控制权返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="210a4-109">The **Policy.Execute** method retracts the facts and returns control to the caller.</span></span> <span data-ttu-id="210a4-110">因此，不能在这种情况下恢复已停止的策略执行。</span><span class="sxs-lookup"><span data-stu-id="210a4-110">Therefore, the halted policy execution cannot be resumed in this case.</span></span> <span data-ttu-id="210a4-111">当你使用时，会发生相同的操作**调用规则**形状来调用该策略。</span><span class="sxs-lookup"><span data-stu-id="210a4-111">The same thing happens when you use the **Call Rules** shape to invoke the policy.</span></span>  
  
 <span data-ttu-id="210a4-112">但是，如果您使用**RuleEngine.Execute**方法以执行策略，可以继续下一个挂起的规则触发已停止的策略执行只需调用直接**RuleEngine.Execute**再次 （只要没有取消两个调用之间所需的任何对象）。</span><span class="sxs-lookup"><span data-stu-id="210a4-112">However, if you use the **RuleEngine.Execute** method directly to execute the policy, you can resume the halted policy execution with the next pending rule firing by simply calling **RuleEngine.Execute** again (provided you did not retract any objects needed between the two calls).</span></span> <span data-ttu-id="210a4-113">恢复已停止的策略执行的示例代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="210a4-113">The sample code for resuming the halted policy execution is as follows:</span></span>  
  
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
  
 <span data-ttu-id="210a4-114">请注意， **Policy.Execute**方法将缓存规则引擎实例，以更好的性能。</span><span class="sxs-lookup"><span data-stu-id="210a4-114">Note that the **Policy.Execute** method caches the rule engine instances for better performance.</span></span> <span data-ttu-id="210a4-115">当你使用**RuleEngine.Execute**直接方法时，规则引擎实例不会被缓存。</span><span class="sxs-lookup"><span data-stu-id="210a4-115">When you use the **RuleEngine.Execute** method directly, the rule engine instances are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210a4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="210a4-116">See Also</span></span>  
 [<span data-ttu-id="210a4-117">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="210a4-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)