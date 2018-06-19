---
title: 和 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676940dfa5cbc23d0c8127923d292e382a4e3cad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230013"
---
# <a name="and"></a><span data-ttu-id="0d3b8-102">And</span><span class="sxs-lookup"><span data-stu-id="0d3b8-102">And</span></span>
<span data-ttu-id="0d3b8-103">删除前两个项从堆栈中，执行一个布尔值**AND**的两个项，并将然后将推送到堆栈的结果。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-103">Removes the top two items from the stack, performs a Boolean **AND** of the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d3b8-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d3b8-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d3b8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0d3b8-105">Parameters</span></span>  
 <span data-ttu-id="0d3b8-106">堆栈最上方的两项。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="0d3b8-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="0d3b8-107">Pushed Value</span></span>  
 <span data-ttu-id="0d3b8-108">字符串的布尔值结果**AND**操作。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-108">String result of the Boolean **AND** operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d3b8-109">注释</span><span class="sxs-lookup"><span data-stu-id="0d3b8-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d3b8-110">示例</span><span class="sxs-lookup"><span data-stu-id="0d3b8-110">Example</span></span>  
 <span data-ttu-id="0d3b8-111">**和**当你需要评估多个语句时，操作非常有用。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-111">The **And** operation is useful when you need to evaluate multiple statements.</span></span> <span data-ttu-id="0d3b8-112">下面的示例筛选器表达式检查是否活动的名称为"CheckPO"并通过使用关闭活动事件**和**操作。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-112">The following example filter expression checks whether the activity name is "CheckPO" and the activity event is closed by using the **And** operation.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="0d3b8-113">在此示例中**和**是表达式中的最后一个操作，因为它依赖于的比较结果 （和从要执行比较的堆栈中弹出）。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-113">In this example **And** is the final operation in the expression because it relies on the results of the comparisons (and pops them from the stack to perform the comparison).</span></span> <span data-ttu-id="0d3b8-114">你可以扩展此办法执行**和**对两个以上的项的操作。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-114">You can extend this idea to perform **And** operations on more than two items.</span></span> <span data-ttu-id="0d3b8-115">例如，若要计算条件 A、条件 B 和条件 C 是否都为真，可以使用类似于如下内容的表达式：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-115">For example, to evaluate whether Condition A and Condition B and Condition C are true, you would use an expression like the following:</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityType"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyType</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>   
```  
  
## <a name="see-also"></a><span data-ttu-id="0d3b8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d3b8-116">See Also</span></span>  
 [<span data-ttu-id="0d3b8-117">拦截器操作</span><span class="sxs-lookup"><span data-stu-id="0d3b8-117">Interceptor Operations</span></span>](../core/interceptor-operations.md)