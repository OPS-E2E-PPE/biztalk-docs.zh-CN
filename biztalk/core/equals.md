---
title: "等于 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b82ac5c779dc6b4d3624b48cebe9df1bc3d1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="equals"></a><span data-ttu-id="11187-102">等于</span><span class="sxs-lookup"><span data-stu-id="11187-102">Equals</span></span>
<span data-ttu-id="11187-103">删除堆栈最上方的两项，比较这两项，然后将结果推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="11187-103">Removes the top two items from the stack, compares the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11187-104">语法</span><span class="sxs-lookup"><span data-stu-id="11187-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11187-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="11187-105">Parameters</span></span>  
 <span data-ttu-id="11187-106">堆栈最上方的两项。</span><span class="sxs-lookup"><span data-stu-id="11187-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="11187-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="11187-107">Pushed Value</span></span>  
 <span data-ttu-id="11187-108">比较操作的字符串结果。</span><span class="sxs-lookup"><span data-stu-id="11187-108">String result of the comparison operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11187-109">注释</span><span class="sxs-lookup"><span data-stu-id="11187-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="11187-110">示例</span><span class="sxs-lookup"><span data-stu-id="11187-110">Example</span></span>  
 <span data-ttu-id="11187-111">下面的示例筛选器表达式使用**等于**操作进行比较到常量"CheckPO"的当前活动名称。</span><span class="sxs-lookup"><span data-stu-id="11187-111">The following example filter expression uses the **Equals** operation to compare the current activity name to the constant "CheckPO".</span></span> <span data-ttu-id="11187-112">如果两者相等，则表达式的计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="11187-112">If the two are equal, the expression evaluates to `true`.</span></span>  
  
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
  
 <span data-ttu-id="11187-113">执行比较时，如果您在 C# 中写入语句，则可以确切地指引您生成表达式。</span><span class="sxs-lookup"><span data-stu-id="11187-113">You may be tempted to build your expression exactly as you would write a statement in C# when performing comparisons.</span></span> <span data-ttu-id="11187-114">例如，您可能要比较三个值；可在 C# 中会写入类似如下的语句：</span><span class="sxs-lookup"><span data-stu-id="11187-114">For example, you might want to compare three values; in C# you would write something like:</span></span>  
  
```  
bool res = a == b == c;  
```  
  
 <span data-ttu-id="11187-115">但是，作为表达式筛选器的模型，此语句有些短。</span><span class="sxs-lookup"><span data-stu-id="11187-115">However, as a model for your expression filter this falls a little short.</span></span> <span data-ttu-id="11187-116">因此，可以考虑下面修改后（但等效）的语句：</span><span class="sxs-lookup"><span data-stu-id="11187-116">Instead, consider the modified (but equivalent) statement:</span></span>  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 <span data-ttu-id="11187-117">这与您用来执行比较的筛选器表达式更加匹配。</span><span class="sxs-lookup"><span data-stu-id="11187-117">This more closely matches the filter expression you would use to perform the comparison.</span></span> <span data-ttu-id="11187-118">有关更多详细信息及示例，请参阅[和](../core/and.md)。</span><span class="sxs-lookup"><span data-stu-id="11187-118">For more details and an example, see [And](../core/and.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11187-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11187-119">See Also</span></span>  
 [<span data-ttu-id="11187-120">拦截器操作</span><span class="sxs-lookup"><span data-stu-id="11187-120">Interceptor Operations</span></span>](../core/interceptor-operations.md)