---
title: Equals | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e376445e8349663ab6196e99f9f31df8e5c1e139
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530735"
---
# <a name="equals"></a><span data-ttu-id="2e0d8-102">等于</span><span class="sxs-lookup"><span data-stu-id="2e0d8-102">Equals</span></span>
<span data-ttu-id="2e0d8-103">从堆栈中移除的前两个项、 进行比较的两个项目，然后将推送到堆栈上的结果。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-103">Removes the top two items from the stack, compares the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e0d8-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e0d8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2e0d8-105">Parameters</span></span>  
 <span data-ttu-id="2e0d8-106">在堆栈上前两个项。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="2e0d8-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="2e0d8-107">Pushed Value</span></span>  
 <span data-ttu-id="2e0d8-108">字符串比较操作的结果。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-108">String result of the comparison operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e0d8-109">备注</span><span class="sxs-lookup"><span data-stu-id="2e0d8-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e0d8-110">示例</span><span class="sxs-lookup"><span data-stu-id="2e0d8-110">Example</span></span>  
 <span data-ttu-id="2e0d8-111">下面的示例筛选器表达式使用**等于**操作以比较当前的活动名称与常数"CheckPO"。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-111">The following example filter expression uses the **Equals** operation to compare the current activity name to the constant "CheckPO".</span></span> <span data-ttu-id="2e0d8-112">如果两者相等，该表达式计算结果为`true`。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-112">If the two are equal, the expression evaluates to `true`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="2e0d8-113">你可能想要完全按照您写入语句，则生成表达式C#执行比较时。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-113">You may be tempted to build your expression exactly as you would write a statement in C# when performing comparisons.</span></span> <span data-ttu-id="2e0d8-114">例如，你可能想要比较三个值;在C#需要编写类似：</span><span class="sxs-lookup"><span data-stu-id="2e0d8-114">For example, you might want to compare three values; in C# you would write something like:</span></span>  
  
```  
bool res = a == b == c;  
```  
  
 <span data-ttu-id="2e0d8-115">但是，表达式筛选器的模型作为此语句有些短。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-115">However, as a model for your expression filter this falls a little short.</span></span> <span data-ttu-id="2e0d8-116">相反，请考虑修改后 （但等效） 语句：</span><span class="sxs-lookup"><span data-stu-id="2e0d8-116">Instead, consider the modified (but equivalent) statement:</span></span>  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 <span data-ttu-id="2e0d8-117">这与将用于执行比较的筛选器表达式更加匹配。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-117">This more closely matches the filter expression you would use to perform the comparison.</span></span> <span data-ttu-id="2e0d8-118">有关更多详细信息和示例，请参阅[和](../core/and.md)。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-118">For more details and an example, see [And](../core/and.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0d8-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e0d8-119">See Also</span></span>  
 [<span data-ttu-id="2e0d8-120">侦听器运算</span><span class="sxs-lookup"><span data-stu-id="2e0d8-120">Interceptor Operations</span></span>](../core/interceptor-operations.md)