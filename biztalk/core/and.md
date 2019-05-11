---
title: And | Microsoft Docs
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
ms.openlocfilehash: 2da29c40091664112ee8b481f3feeba9d7463b5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359704"
---
# <a name="and"></a><span data-ttu-id="367cf-102">And</span><span class="sxs-lookup"><span data-stu-id="367cf-102">And</span></span>
<span data-ttu-id="367cf-103">删除前两个项从堆栈中，执行一个布尔值**AND**的两个项，并将然后将推送到堆栈上的结果。</span><span class="sxs-lookup"><span data-stu-id="367cf-103">Removes the top two items from the stack, performs a Boolean **AND** of the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="367cf-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="367cf-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="367cf-105">Parameters</span></span>  
 <span data-ttu-id="367cf-106">在堆栈上前两个项。</span><span class="sxs-lookup"><span data-stu-id="367cf-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="367cf-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="367cf-107">Pushed Value</span></span>  
 <span data-ttu-id="367cf-108">一个布尔值的字符串结果**AND**操作。</span><span class="sxs-lookup"><span data-stu-id="367cf-108">String result of the Boolean **AND** operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="367cf-109">备注</span><span class="sxs-lookup"><span data-stu-id="367cf-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="367cf-110">示例</span><span class="sxs-lookup"><span data-stu-id="367cf-110">Example</span></span>  
 <span data-ttu-id="367cf-111">**和**操作时，你需要评估多个语句。</span><span class="sxs-lookup"><span data-stu-id="367cf-111">The **And** operation is useful when you need to evaluate multiple statements.</span></span> <span data-ttu-id="367cf-112">下面的示例筛选器表达式检查是否活动名称为"CheckPO"，并通过使用关闭的活动事件**和**操作。</span><span class="sxs-lookup"><span data-stu-id="367cf-112">The following example filter expression checks whether the activity name is "CheckPO" and the activity event is closed by using the **And** operation.</span></span>  
  
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
  
 <span data-ttu-id="367cf-113">在此示例中**和**是在表达式中的最后一个操作，因为它依赖于比较的结果 （并从要进行比较的堆栈中弹出它们）。</span><span class="sxs-lookup"><span data-stu-id="367cf-113">In this example **And** is the final operation in the expression because it relies on the results of the comparisons (and pops them from the stack to perform the comparison).</span></span> <span data-ttu-id="367cf-114">您可以扩展执行这一思路**和**对两个以上的项的操作。</span><span class="sxs-lookup"><span data-stu-id="367cf-114">You can extend this idea to perform **And** operations on more than two items.</span></span> <span data-ttu-id="367cf-115">例如，若要评估条件 A、 条件 B 和条件 C 是否，则返回 true，将使用的表达式如下所示：</span><span class="sxs-lookup"><span data-stu-id="367cf-115">For example, to evaluate whether Condition A and Condition B and Condition C are true, you would use an expression like the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="367cf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="367cf-116">See Also</span></span>  
 [<span data-ttu-id="367cf-117">侦听器运算</span><span class="sxs-lookup"><span data-stu-id="367cf-117">Interceptor Operations</span></span>](../core/interceptor-operations.md)